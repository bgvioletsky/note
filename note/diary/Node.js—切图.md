# Node.js——切图

**简介：** Node.js——切图

### 安装

```javascript
# 建一个文件
npm init 
# 安装两个依赖
npm i image-size sharp
```

### 代码

```js
const sizeOf = require('image-size');
const sharp = require('sharp');
const currentImageInfo = sizeOf('./wallhaven-3zwvk3.jpg') // 加载一张图
let clientHeight = currentImageInfo.height
console.log(currentImageInfo)
const heights = []
const SPLIT_HEIGHT = 200
while (clientHeight > 0) {
    // 切图高度充足时
    if (clientHeight >= SPLIT_HEIGHT) {
        heights.push(SPLIT_HEIGHT)
        clientHeight -= SPLIT_HEIGHT
    } else {
        // 切割高度不够时，直接切成一张
        heights.push(clientHeight)
        clientHeight = 0
    }
}
console.log(heights)
let top = 0
heights.forEach((h, index) => {
    sharp('./wallhaven-3zwvk3.jpg')
        .extract({ left: 0, top: top, width: currentImageInfo.width, height: h })
        .toFile(`./img/split_${index + 1}_block.jpg`, (err, info) => {
            if(!err){
                onsole.log(`split_${index + 1}_block.jpg切割成功`)
            }else{
                console.log(JSON.stringify(err), 'error')
            }
        })
    top += h
})
```

### 执行

```js
node index.js
```



![image.png](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/99204cb779224350aff32928dbf0ba4c.png)

### 扩展

#### sharp

> 一个利用高速node.js将普通大图片转换成更小的、对web更友好的JPEG、PNG、WebP等不同尺寸的图像的出色的模块。调整图像大小通常比使用最快的ImageMagick和GraphicsMagick设置还要快4到5倍

##### extract

提取图像的一个区域

- left 从左边缘开始的零索引偏移量
- top zero-indexed offset from top edge
- width 提取图像的宽度
- height 提取图像的高度

#### toFile

将输出图像数据写入文件。

如果没有选择输出格式，将从扩展中推断它，支持JPEG、PNG、WebP、TIFF、DZI和libvip的V格式。注意，原始像素数据只支持缓冲区输出。

未提供回调时，将返回Promise

- fileOut (String) 写入图像数据的路径
- callback (Function) 在完成时调用，带有两个参数(err, info)。info包含输出图像格式、大小(字节)、宽度、高度、通道和预乘(指示是否使用预乘)。在使用裁剪策略时还
- 包含cropOffsetLeft和cropOffsetTop

```js
示列
.toFile(`./img/split_${index + 1}_block.jpg`, (err, info) => {
    if (!err) {
        onsole.log(`split_${index + 1}_block.jpg切割成功`)
    } else {
        console.log(JSON.stringify(err), 'error')
    }
})
.toFile(`./img/split_${index + 1}_block.jpg`).then(info => {
    console.log(`split_${index + 1}_block.jpg切割成功`)
}).catch(err => {
    console.log(JSON.stringify(err), 'error')
})
sharp.js中文文档
image-size.js文档
```

### 

### 代码修改
```js
const sizeOf = require('image-size');
const sharp = require('sharp');

const currentImageInfo = sizeOf('./00002.webp');
let clientHeight = currentImageInfo.height;
const heights = [];
const SPLIT_HEIGHT = Math.floor(clientHeight / 10);

while (clientHeight > 0) {
    const h = Math.min(clientHeight, SPLIT_HEIGHT);
    heights.push(h);
    clientHeight -= h;
}

let top = 0;
let url = [];

heights.forEach((h, index) => {
    sharp('./00002.webp')
        .extract({ left: 0, top: top, width: currentImageInfo.width, height: h })
        .toFile(`./img/${index + 1}.webp`, (err, info) => {
            if (!err) {
                const imagePath = `img/${index + 1}.webp`;
                url.push({ path: imagePath, id: index });
                console.log(`${index + 1}.webp 切割成功`);

                if (url.length === heights.length) {
                    url.sort((a, b) => parseInt(b.id) - parseInt(a.id));
                    mergeImages(url);
                }
            } else {
                console.log(JSON.stringify(err), 'error');
            }
        });

    top += h;
});

function mergeImages(url) {
    const image = sharp({
        create: {
            width: currentImageInfo.width,
            height: currentImageInfo.height, // 计算总高度
            channels: 3,
            background: { r: 255, g: 255, b: 255 }
        }
    });

    let x = 0;

    const compositeOperations = url.map((imagePath, index) => {
        x += sizeOf(imagePath.path).height;
        return { input: imagePath.path, left: 0, top: x };
    });

    image.composite(compositeOperations)
        .toFile('sa.webp', (err, info) => {
            if (!err) {
                console.log('图片拼接成功，已保存为 sa.webp');
            } else {
                console.log('拼接失败:', err);
            }
        });
}
```