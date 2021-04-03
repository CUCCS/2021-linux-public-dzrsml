# 第三次实验

## 操作视频

[![asciicast](https://asciinema.org/a/GwI7JNbjkL6DTIE9RxFD7lpBV.svg)](https://asciinema.org/a/GwI7JNbjkL6DTIE9RxFD7lpBV)

[![asciicast](https://asciinema.org/a/o6hFqnpzUPR7FzwLSMXaXJ8u2.svg)](https://asciinema.org/a/o6hFqnpzUPR7FzwLSMXaXJ8u2)

[![asciicast](https://asciinema.org/a/bEQV6yYHKyWOAWf8f7hHW7bAd.svg)](https://asciinema.org/a/bEQV6yYHKyWOAWf8f7hHW7bAd)

[![asciicast](https://asciinema.org/a/LlZVGwayczrDZmlsqg4FUrxos.svg)](https://asciinema.org/a/LlZVGwayczrDZmlsqg4FUrxos)

[![asciicast](https://asciinema.org/a/A3z3MkkXq23Tqaytakt1Jys4s.svg)](https://asciinema.org/a/A3z3MkkXq23Tqaytakt1Jys4s)

[![asciicast](https://asciinema.org/a/Tq7CKz3Mi3201ATyR2P2rsNBl.svg)](https://asciinema.org/a/Tq7CKz3Mi3201ATyR2P2rsNBl)

[![asciicast](https://asciinema.org/a/J1hVDF5Y9yDxvZu09Vq2PBhVN.svg)](https://asciinema.org/a/J1hVDF5Y9yDxvZu09Vq2PBhVN)

## 过程中出现的问题

1.一些unit报错 不存在 改用为ufw基本可以解决
2.更改时间 set-time YYYY-MM-DD 时失败 需要先关闭时间同步 并且输入具体时间 例：2021-04-03

## 自查清单

1. 
先用adduser命令创建用户，然后把新建的用户加入到sudo组里面,就可以看到新建用户在sudo组里面

2. 
usermod -a -G groupA user

3. 
df -hT 
fdisk -l 
gdisk -l 
parted -l 
lsblk -f 
4. 
在windows下创建一个共享文件夹并配置共享文件夹（不点击自动挂载）
在虚拟机中新建共享文件夹 /mnt/share
执行挂载命令 ```sudo mount -t vboxsf [Windows共享文件夹名称] /mnt/dirname```
修改 /etc/fstab 文件 在文末添加```[Windows共享文件夹名称] /mnt/dirname/ vboxsf defaults 0 0```即可完成开机自动挂载

5. 

```bash
分区扩容：
lvresize --size +{{120G}} --resizefs {{volume_group}}/{{logical_volume}}
lvresize --size {{100}}%FREE {{volume_group}}/{{logical_volume}}
lvextend -L size
分区缩减：
lvresize --size -{{120G}} --resizefs {{volume_group}}/{{logical_volume}}
lvreduce -L size
```

6. 
让一个脚本在网络连通时运行,然后设置开机启动
`vim /usr/lib/systemd/system/after_networking.service`
修改内容：

```bash
[Unit]
Description=after networking 
After=networking.service # 网络启动之后
[Service]
Type=oneshot # 执行一次
ExecStart=/bin/bash -e  {{目标脚本路径}}
KillSignal=SIGINT
[Install]
WantedBy=multi-user.target
```

7. 
修改配置文件[service]区块，将  restart  设置为  always

```bash
[Service]
Restart = always
```
重新加载配置文件`sudo systemctl daemon-reload`
重新启动服务`sudo systemctl restart ××××`