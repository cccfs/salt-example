### 启动命令
```
cd /srv
git clone git@github.com:cccfs/salt-example.git 
docker run -d --name salt --hostname salt -p 4505-4506:4505-4506 -p 8000:8000 -v /srv/salt-example/config:/etc/salt/master.d -v /srv/salt-example/salt:/srv/salt reg.deeproute.ai/deeproute-public/salt:3004.2-v0.3
```

### 配置步骤
- 进入docker容器，创建admin用户及密码
```
useradd admin
password admin
```

- ui登录
```
http://127.0.0.1:8000
用户名密码为上面所设置的
```

### 说明
示例为pam方式登录，可根据需要修改为ad登录，config目录为salt master配置，salt目录为salt编排配置

### 客户端配置
1、安装salt-minion
2、修改/etc/salt/minion文件
```
master: 127.0.0.1
```
