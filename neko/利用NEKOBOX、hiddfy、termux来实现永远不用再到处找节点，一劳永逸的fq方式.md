# 利用NEKOBOX、hiddfy、termux来实现永远不用再到处找节点，一劳永逸的fq方式。 

支持IPV4和V6的wireguard协议。 




视频地址:https://m.youtube.com/watch?v=S3hJSro-R7M


# 方法1

文中用到的软件 

NEKOBOX 

https://github.com/MatsuriDayo/NekoBoxForAndroid

termux-app下载地址
 
https://github.com/termux/termux-app 

1.先用nekbox生成配置。打开neko左上角三横-工具-cloudflare warp-生成配置

2.替换网址和端口。打开termux,
(第一次打开请输入
``` 
pkg update && pkg install wget 
``` 
)

输入优选脚本，获得优选网址和端口，替换配置中的服务器和端口。



优选脚本
``` 
curl -sSL https://ghproxy.net/https://raw.githubusercontent.com/wokaotianshi123/cf-clean-ips/main/endip.sh -o endip.sh && chmod +x endip.sh && bash endip.sh
```
或者
``` 
wget -N https://gitjs.wokaotianshi123.cloudns.org/https://raw.githubusercontent.com/wokaotianshi123/warp-script/main/warp.sh && bash warp.sh 
```
下面这个优选只生成一个优选ip
``` 
wget -N https://gitjs.wokaotianshi123.cloudns.org/https://raw.githubusercontent.com/wokaotianshi123/warp/main/endip/install.sh && bash install.sh

``` 
安卓 Termux 如无 wget 请使用以下命令安装：
``` 
pkg update && pkg install wget
``` 

windows优选程序 https://gitjs.wokaotianshi123.cloudns.org/https://raw.githubusercontent.com/wokaotianshi123/wokaotianshi123.github.io/main/neko/warp-yxip-win.7z

生成配置

sn://wg?eNoVzjFOwzAUAFADYuEU3SPZ_38SN7HUhVLTFhUqUCFraqcQCHZkKCFsOVDFAuJIXAN4J3j7jDFjHfeu7pzPsoyb2m-te-Y-_HwcMPaNQ-IoOXASx3REEqSKhwAKEVRKmKjCGqkIgdRaxsoaEkjprjprvEijEMfzk_aUcmev_Kpw3SYKsLywMzPJQZeteNCPo936Kb8cRxr122ShM9tV5zRNBF6vXt6nMN_e-ATvqV1u7jo_6tkhY-Vs8bX3Vx__Z3VdhHJwW4RmUDWvn33_C3_OP7w


# 另外，还可以优选ip在hiddfy最新版使用，同样不需要建节点。

1.下载安装hiddify next

https://github.com/hiddify/hiddify-next/releases/


2.打开termux,(
第一次打开请输入
```
pkg update && pkg install wget 
```
)输入下面代码得到优选endip和端口
``` 
curl -sSL https://ghproxy.net/https://raw.githubusercontent.com/wokaotianshi123/cf-clean-ips/main/endip.sh -o endip.sh && chmod +x endip.sh && bash endip.sh
```
或者
``` 
wget -N https://gitjs.wokaotianshi123.cloudns.org/https://raw.githubusercontent.com/wokaotianshi123/warp-script/main/warp.sh && bash warp.sh 
```
下面这个优选只生成一个优选ip
``` 
wget -N https://gitjs.wokaotianshi123.cloudns.org/https://raw.githubusercontent.com/wokaotianshi123/warp/main/endip/install.sh && bash install.sh

``` 
3.选排序靠前的endip填入配置 warp://优选ip:端口号/?ifp=5-10 用第一步得到的网址和端口替换配置中的服务器和端口。

得出
```
warp://188.114.96.213:1002/?ifp=5-10
```

4.复制到hiddfy里，从剪贴板导入（不要手动输入，手动添加不成功）

(更新的时候需要先删除原来warp节点)



# 方法2 cmliu/Warp2Clash 来自大佬们的代码 目前仅仅适用于ipv6网络环境，手机端是ipv6应该也能使用

1.安装nekobox和termux，hiddfy 14.20版（若有请忽略跳到第二步）

NEKOBOX 
 
https://github.com/MatsuriDayo/NekoBoxForAndroid

termux下载地址：

https://github.com/termux/termux-app/releases

hiddify next下载地址：查找14.20版

https://github.com/hiddify/hiddify-next/releases/


2.先用nekbox生成配置。打开neko左上角三横-工具-cloudflare warp-生成配置，分别复制节点私钥 比如iGpo/8+r44JBwD2XndRoUanyf+r0PNdIcEX0Few/jFk= 和节点公钥 比如 bmXOC+F1FxEMF9dyiK2H5/1SUtzH0JuVo51h2wPfgyo= 到手机便签备用

3.用手机安装termux，然后先安装python环境（首次运行需要，以后不需要）获取读写sd权限，预计有600M，手机空间要足够。

运行以下代码
``` 
pkg install python
```
获取读写sd卡权限，允许
``` 
termux-setup-storage
``` 
4.复制运行代码后添加私钥和公钥，（同一行，运行代码后紧接着先私钥后公钥，之间空一格）

运行代码

``` 
wget -N -P Warp2Clash https://gitjs.wokaotianshi123.cloudns.org/https://raw.githubusercontent.com/wokaotianshi123/Warp2Clash/main/W2C_start.sh && cd Warp2Clash && chmod +x W2C_start.sh && bash W2C_start.sh  
``` 
私钥公钥
``` 
iGpo/8+r44JBwD2XndRoUanyf+r0PNdIcEX0Few/jFk= bmXOC+F1FxEMF9dyiK2H5/1SUtzH0JuVo51h2wPfgyo=
``` 

最后实际合并后的代码为
``` 
wget -N -P Warp2Clash https://gitjs.wokaotianshi123.cloudns.org/https://raw.githubusercontent.com/wokaotianshi123/Warp2Clash/main/W2C_start.sh && cd Warp2Clash && chmod +x W2C_start.sh && bash W2C_start.sh iGpo/8+r44JBwD2XndRoUanyf+r0PNdIcEX0Few/jFk= bmXOC+F1FxEMF9dyiK2H5/1SUtzH0JuVo51h2wPfgyo=
``` 

5.在手机根目录查看 Warp2Clash.yaml是否存在,将Warp2Clash.yaml上传到个人空间得到外链链接。http...，复制下来。以后每次更新就直接更新Warp2Clash.yaml内容即可。

6.下载安装 14.20版本 hiddify next，打开,右上角，剪贴板导入外链链接。

好用的自建节点和订阅
节点：
```
trojan://cf2tj@cfip.wofuck.ddnsfree.com:443?security=tls&type=ws&host=cftj.wofuck.rr.nu&path=%2F%3Fed%3D2560#cfip.wofuck.ddnsfree.com%20%E6%89%93%E5%BC%80https%3A%2F%2Fscanner.github1.cloud%2F%E7%AD%9B%E9%80%89443%E7%AB%AF%E5%8F%A3ip
trojan://cf2tj@cfip.wofuck.gleeze.com:443?security=tls&type=ws&host=cftj.wofuck.rr.nu&path=%2F%3Fed%3D2560#cfip.wofuck.gleeze.com%20%E6%89%93%E5%BC%80https%3A%2F%2Fscanner.github1.cloud%2F%E7%AD%9B%E9%80%89443%E7%AB%AF%E5%8F%A3ip
trojan://cf2tj@cloudflare.net:443?security=tls&type=ws&host=cftj.wofuck.rr.nu&path=%2F%3Fed%3D2560#cloudflare.net
trojan://cf2tj@fbi.gov:443?security=tls&type=ws&host=cftj.wofuck.rr.nu&path=%2F%3Fed%3D2560#fbi.gov
trojan://cf2tj@www.visa.com.sg:443?security=tls&type=ws&host=cftj.wofuck.rr.nu&path=%2F%3Fed%3D2560#www.visa.com.sg
vless://543e12fe-f437-43fd-aff3-afe982741e8d@543e12fe-f437-43fd-aff3-afe982741e8d-00-e8zlkxsj2dzt.spock.replit.dev:443?encryption=none&security=tls&sni=543e12fe-f437-43fd-aff3-afe982741e8d-00-e8zlkxsj2dzt.spock.replit.dev&type=ws&host=543e12fe-f437-43fd-aff3-afe982741e8d-00-e8zlkxsj2dzt.spock.replit.dev&path=%2F543e12fe-f437-43fd-aff3-afe982741e8d-vl#%E9%98%B2%E5%A4%B1%E8%81%94%E3%80%82%E5%B9%B3%E6%97%B6%E4%B8%8D%E8%BF%90%E8%A1%8C%E3%80%82%E4%BD%BF%E7%94%A8%E6%97%B6%E6%89%93%E5%BC%80replit%EF%BC%8C%E7%99%BB%E5%BD%95529442986%40qq.com%208606....%E6%89%BE%E5%88%B0newyear20202%2C%E8%BF%90%E8%A1%8Crun%20replit-vless
trojan://cf2tj@www.dzy66666.com:443?security=tls&type=ws&host=cftj.wofuck.rr.nu&path=%2F%3Fed%3D2560#www.dzy66666.com
```
订阅：
```
https://cfdyhj.wofuck.rr.nu/ziyong
https://cfdy.wofuck.rr.nu/cf2w
http://short.wokaotianshi123.cloudns.org/bpbv2
https://cftj.wofuck.rr.nu/cf2tj
https://short.wokaotianshi123.cloudns.org/kxdy
```
