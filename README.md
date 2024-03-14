# Docker Docker-Compose ubuntu
## Install last version

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)



## Docker

Обновим apt 

```sh
sudo apt update
```

Затем установите несколько необходимых пакетов, которые позволяют apt использовать пакеты через HTTPS:

```sh
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

Добавьте ключ GPG для официального репозитория Docker в вашу систему:
```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Добавьте репозиторий Docker в источники APT:

```sh
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

Убедитесь, что установка будет выполняться из репозитория Docker, а не из репозитория Ubuntu по умолчанию:

```sh
apt-cache policy docker-ce
```
получим:
```sh
docker-ce:
  Installed: (none)
  Candidate: 5:19.03.9~3-0~ubuntu-focal
  Version table:
     5:19.03.9~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
```
Установим Докер
```sh
sudo apt install docker-ce
sudo systemctl status docker
```

## Docker-compose
Мы проверим [текущую версию] текущую версию и при необходимости обновим ее с помощью следующей команды:
```sh
sudo curl -L https://github.com/docker/compose/releases/download/v2.24.7/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```
[текущую версию]: <https://github.com/docker/compose/releases>

После этого мы настроим разрешения:
```sh
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```
