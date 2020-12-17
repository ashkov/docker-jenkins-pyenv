# docker-jenkins-pyenv

Поскольку официальной встроенной версии python недостаточно, а для проектов требуются различные версии, то в официальный образ jenkins/jenkins:latest, добавлена поддержка pyenv.

- Набор версий python устанавливаемых при помощи pyenv можно отредактировать в файле `python-versions.txt`
- 默认安装 nox（https://nox.thea.codes/en/stable/）

## 注意事项

因 pyenv 是使用 root 用户进行安装的，所以 jenkins 镜像默认的用户 jenkins 在使用时，需要修改 PATH

```shell
export PATH=/opt/pyenv/shims:/opt/pyenv/bin:$PATH
```

或者使用绝对路径进行使用 `pyenv`
