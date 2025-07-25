
## EasySystemctl

自动化脚本运维工具,保活关键服务

```
Using:
  python ./service_main.py update|restart service_name|stop service_name|state|log [service_name]
```

配置服务

```
KEEPALIVE_SERVICE = {
    'tg_bot': {  #  服务名称
        'description': 'TG Bot Service',   #   服务备注
        'exec_start': 'python3 ./tg_bot_server.py',  #  启动命令
        'exec_user': 'ubuntu',  #  服务运行用户
        'env_list': ['HTTP_PROXY=http://192.168.123.1:7890/'],  #  环境变量
        'work_directory': '/home/ubuntu/tg_bot_api',  #  服务运行路径
    },
}
```

更新配置

```
sudo python3 ./service_main.py update
```

查看服务运行状态

```
sudo python3 ./service_main.py state
```

重启服务

```
sudo python3 ./service_main.py restart tg_bot
```

