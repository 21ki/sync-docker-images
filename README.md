# sync-docker-images

# [skopeo-sync](https://github.com/containers/skopeo/blob/main/docs/skopeo-sync.1.md)
```shell
skopeo sync --src yaml --dest docker sync.yml my-registry.local.lan/repo/
```

## 1.修改设置自己的仓库
```shell
env:
  ACTOR: Myki
  #修改cheche成自己的仓库名称即可
  DEST-REGISTORY: docker.io/cheche
```

## 2.设置仓库账号密码(脱敏设置)
DOCKER_USERNAME和DOCKER_PASSWORD为仓库的登录密码，本来要写入配置文件容易暴露，所以脱敏一下
设置入口

Settings --> 左侧菜单栏 secrets --> New repository secret

## 3.修改需要备份的镜像(配置文件sync.yml)"[]"为备份所有镜像tag
```shell
docker.io:
    tls-verify: false
    images:
      #备份青龙
      whyour/qinglong: []
      #备份诺兰jdc
      cheche/nvjdc: []
```
## [如需备份其他镜像可以去提issues](https://github.com/21ki/sync-docker-images/issues/new)

