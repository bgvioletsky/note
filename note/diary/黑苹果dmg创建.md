黑苹果dmg创建

1、在苹果商店下载相关系统镜像

2、通过磁盘管理工具创建空白映像

3、通过访达进入应用程序找到系统左键选择显示包内容找到文件createinstallmedia

4、打开终端工具

输入sudo再将createinstallmedia拖入终端再输入 --volume 最后将刚刚创建的映像拖入最终在终端显示如下

```shell
sudo /Applications/Install\macOS\Sonoma.app/Contents/Resources/createinstallmedia --volume  /Volumes/install#映像地址#Sonoma.app为系统安装包地址可以修改
```

5、精简通过磁盘工具的映像选择转换功能将映像进行压缩

6、添加EFI文件挂载该磁盘打开EFI文件夹将准备好的EFI拖入其中，一份完美的黑苹果映像创建成功

7、创建多系统安装盘同理