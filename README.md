# NPS

[新特性文档](https://yisier.github.io/)

# 说明
由于nps已经停更多年，存留了不少bug和未完善的功能。

此版本基于 nps 0.26.10的基础上二次开发而来。

***DockerHub***： [NPS](https://hub.docker.com/r/yisier1/nps) [NPC](https://hub.docker.com/r/yisier1/npc)

***宝塔面板***：[宝塔面板 Docker](https://yisier.github.io/nps/install/#%E5%AE%9D%E5%A1%94%E9%9D%A2%E6%9D%BF-%E4%B8%80%E9%94%AE%E9%83%A8%E7%BD%B2)


# 提示
首次启动时 nps 会在可执行文件同级目录自动生成 conf/nps.conf，并随机生成 web_password、auth_key、auth_crypt_key，web 管理界面的访问密码请在conf/nps.conf文件中或启动日志中查看。


## 更新日志(于2026-06-20 基于[yisier/nps](https://github.com/yisier/nps)的v0.26.34版本修改)
- 1.调用新增修改客户端、隧道、域名的API，返回当前新增或修改后的记录json。
- 2.修改默认日志级别为7。关闭默认http及https默认端口。修改默认端口为9000。默认打开允许本地代理。
- 3.增加展开客户端时，显示安装或注册系统服务的命令。
- 4.修改以服务方式安装nps和npc的服务名及显示名称（因特殊场景需要，改了服务名及名称，可Fork回去自行修改）。
- 5.管理域名和隧道时，客户端ID改成下拉列表选择。

![image](https://user-images.githubusercontent.com/43511466/204796815-c293e805-12f6-431e-a8f7-1d6b91dbbfc3.png)


---
## 🚀 快速开始

### 下载

从 [releases](https://github.com/yisier/nps/releases) 下载对应平台版本。服务端 `nps` 和客户端 `npc` 是独立的压缩包。

### 服务端

```shell
./nps -server    # 交互菜单：安装/卸载/启动/停止/更新
```

首次启动自动生成 `conf/nps.conf`，随机生成 `web_password`、`auth_key`、`auth_crypt_key`，请从启动日志或 `nps.conf` 获取。

![img](https://raw.githubusercontent.com/yisier/nps/master/docs/.vuepress/public/image/new/server.png)

### 客户端

```shell
./npc            # 直接双击运行，按提示输入即可
```

在 Web 后台复制【快捷启动命令】，客户端粘贴即可注册系统服务、启停或卸载。


![image](https://raw.githubusercontent.com/yisier/nps/master/docs/.vuepress/public/image/new/cmd.png)

#### 命令行直接启动

```shell
npc -server=ip:8024 -vkey=xxx                           # 标准
npc -server=ip:8025 -vkey=xxx -tls_enable=true           # TLS 桥接
npc -server=ip:8024 -vkey=vkey1,vkey2                    # 多隧道
```

---
