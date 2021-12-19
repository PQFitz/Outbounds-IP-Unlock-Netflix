# Outbounds-IP-Unlock-Netflix


## 无意中发现通过设置出口IP，解锁所有原生支持奈飞的VPS

## 过程：在用过很多VPS后发现，许多原生IP本来是支持解锁奈飞非自制剧的。由于奈飞检测越来越严苛，在搭建柯学上网方式的时候，奈飞很容易检测到VPS可疑流量，就ban掉了IP。通过使用，意外发现，在用到“Cloudflare WARP 一键配置脚本”的时候，由于出口IP改变，由CF warp托管一段时间后，VPS原生IP再隔上一段时间后又会莫名其妙的支持解锁非自制剧。

## 目标：让原生IP无法被奈飞检测到可疑流量，进而被ban掉。故而通过WARP一键脚本修改VPS进出IP，再通过修改V2ray、Xray出口IP为原生IP达到目的。

## 总结：绕开使用VPS时的流量不被奈飞检测到，让VPS出口IP为WARP的IP，再让柯学工具的出口IP为原生IP。即可。

## 1.Cloudflare WARP 一键配置脚本 功能菜单
```bash
   bash <(curl -fsSL git.io/warp.sh) menu
```
## 2.修改V2ray、Xray 出口IP
```bash
   "outbounds": [
    {
      "sendThrough": "123.123.123.123",
      "protocol": "freedom",
      "settings": {}

    }
```

# 大功告成~！
