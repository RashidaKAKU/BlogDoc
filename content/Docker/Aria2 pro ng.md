---
title: "Aria2 下载器部署"
description: "Aria2 下载器 群晖Docker部署，带 UI 界面"
tags: [群晖,Docker,下载,教程]
categories: "Docler"
date: 2023-05-15T05:53:11+09:00
featured_image: "https://rashida.cab:6901/uploads/2023/05/15/6461c3f92bd88.jpeg"
---

# Aria2 Pro Dockor Cli 部署
需要修改用户路径，其余可不修改。

```
docker run -d \
    --name Aria2 \
    --restart unless-stopped \
    --log-opt max-size=1m \
    --network host \
    -e PUID=$UID \
    -e PGID=$GID \
    -e RPC_SECRET=<TOKEN> \
    -e RPC_PORT=6800 \
    -e LISTEN_PORT=6888 \
    -v $PWD/aria2-config:/config \
    -v $PWD/aria2-downloads:/downloads \
    p3terx/aria2-pro
```

# AriaNG Dockor Cli 部署
可以修改用户端口
可以在 Docker 面板中设置关联容器 Aria2

```
docker run -d \
    --name AriaNG \
    --restart unless-stopped \
    --log-opt max-size=1m \
    -p 6880:6880 \
    p3terx/ariang
```

# 群晖使用 Docker Cli 方法



<audio src="http://192.168.50.5:8091/api/raw/volume1/docker/jmalcloud/Rashida/Blog/%E9%9F%B3%E9%A2%91/Docker/%E7%BE%A4%E6%99%96cli%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B.wav?auth=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7ImlkIjoxLCJsb2NhbGUiOiJ6aC1jbiIsInZpZXdNb2RlIjoibW9zYWljIiwic2luZ2xlQ2xpY2siOmZhbHNlLCJwZXJtIjp7ImFkbWluIjp0cnVlLCJleGVjdXRlIjp0cnVlLCJjcmVhdGUiOnRydWUsInJlbmFtZSI6dHJ1ZSwibW9kaWZ5Ijp0cnVlLCJkZWxldGUiOnRydWUsInNoYXJlIjp0cnVlLCJkb3dubG9hZCI6dHJ1ZX0sImNvbW1hbmRzIjpbXSwibG9ja1Bhc3N3b3JkIjpmYWxzZSwiaGlkZURvdGZpbGVzIjpmYWxzZSwiZGF0ZUZvcm1hdCI6ZmFsc2V9LCJpc3MiOiJGaWxlIEJyb3dzZXIiLCJleHAiOjE2ODYyMzk3NzAsImlhdCI6MTY4NjIzMjU3MH0.vo23L3z9RZ0XrqF9HMhbSiJzjcSb_4dQFNq_HemNXrI&inline=true"></audio>

1. 打开群晖控制面板
2. 找到任务计划
3. 新增计划任务-用户脚本
4. 随意填写任务名称
5. 用户角色选 Root
6. 在脚本处粘贴 Docker Cli 并保存
7. 运行脚本后删除
8. 等待部署完成