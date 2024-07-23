## 黑苹果dmg创建

#### 1、在苹果商店下载相关系统镜像

![image-20240723094909419](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230949443.png)

#### 2、通过磁盘管理工具创建空白映像

![image-20240723091801778](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230918230.png)

>名称可以随便填写
>大小为20GB后期可以修改
>格式修改为Mac OS 扩展（日志式）
>点击储存

![image-20240723091941887](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230919910.png)

>打开创建的映像如图

![image-20240723092105708](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230921726.png)

#### 3、通过访达进入应用程序找到系统左键选择显示包内容找到在Resources文件夹下的createinstallmedia文件

![image-20240723092255421](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230922440.png)![image-20240723092415344](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230924367.png)

#### 4、打开终端工具

> 输入sudo再将createinstallmedia拖入终端再输入 --volume 最后将刚刚创建的映像打开盘注意是打开盘没有dmg后缀拖入最终在终端显示如下

```shell
sudo /Applications/Install\macOS\Sonoma.app/Contents/Resources/createinstallmedia --volume  /Volumes/install#映像地址#Sonoma.app为系统安装包地址可以修改
```

![image-20240723092846063](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230928096.png)

> 在此需要输入本机密码

![image-20240723092858932](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230928968.png)

> 出现在这个地方需要输入y确认

![image-20240723092912517](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230929551.png)

![image-20240723093128145](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230931189.png)5、添加EFI文件挂载该磁盘打开EFI文件夹将准备好的EFI拖入其中，一份完美的黑苹果映像创建成功下载挂载工具[ESP Mounter Pro](https://us.softpedia-secure-download.com/dl/1ea05ed60713d81fc4559b735a7d062f/669f0e1c/400142042/mac/Utilities/ESP%20Mounter%20Pro.app_v1.9.1.zip) 
![image-20240723094023133](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230940183.png) 

![image-20240723094117379](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230941430.png)

![image-20240723094149254](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230941311.png)

![image-20240723094207170](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230942219.png)

![image-20240723094239860](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230942910.png)
#### 6、精简通过磁盘工具的映像选择转换功能将映像进行压缩

![image-20240723093419143](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230934706.png)

![image-20240723094347590](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230943639.png)



![image-20240723093517685](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230935269.png)

![image-20240723094729776](https://cdn.jsdelivr.net/gh/bgvioletsky/ImgBlog/Typora/202407230947801.png)

#### 7、创建多系统安装盘同理