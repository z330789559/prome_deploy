分为四个工程
切换到project 文件夹
admin-web: 后台管理系统web
docker命令：
```shell
打包: docker compose build   admin-web
发布: docker compose up -d admin-web
```
back-admin: 后台管理系统service java
```shell
打包:  docker compose build  back-admin
发布:  docker compose up -d back-admin

```
weilany-app:活动页面
```shell
打包:  docker compose build  web-app
发布:  docker compose up -d web-app
```

api 服务
```shell
打包:  docker compose build  backend
发布:  docker compose up -d backend
```

确保容器都已经正常运行配置nginx
web-app是3000端口 可以把aidrop.promte.network.com 指向
backend 是4001端口 可以把 aidrop.promte.network.com/api 指向并且rewrite调/api

admin-web 8060 可以把 norbert.promte.network.com  指向
back-admin 8080 可以把 norbert.promte.network.com/dev-api 指向 并且rewrite调/dev-api





