还在 DD 别人的 Centos 吗，分区不是自己想要的分区吗？使用本脚本即可可视化安装 centos ！

* 支持大部分Centos机器，理当支持ORALCE，做了EFI兼容支持
* 不支持 Centos 6
* Centos8 只需要提示输入repo 的输入centos8的源就行，不过内存得大于2G，
* 小于1G的就用默认的吧，链接VNC以后再进去切换安装源刀最新版的 Centos
* 测试机器本机 HYPER-V 开的机器。阿里云轻量，腾讯云轻量，AWS轻量

临时URL  https://raw.githubusercontent.com/zvg/dd/master/centos/vnc/vnc.sh

使用方法：

```sh
bash <(curl -s -S -L https://raw.githubusercontent.com/zvg/dd/master/centos/vnc/vnc.sh)
```