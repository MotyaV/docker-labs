<font face="times new roman" size="3">
<center> МИНИСТЕРСТВО ЦИФРОВОГО РАЗВИТИЯ, СВЯЗИ И МАССОВЫХ КОММУНИКАЦИЙ РОССИЙСКОЙ ФЕДЕРАЦИИ </center>
<center>Ордена Трудового Красного Знамени федеральное государственное бюджетное образовательное учреждение высшего образования </center>
<center> <strong> «Московский технический университет связи и информатики» </strong> </center>

  <hr>
<center> Кафедра «Телевидения и звукового вещания им. С.И. Катаева (ТиЗВ)» </center>
<br>
<center> <font face="times new roman" size="3" > Отчет по упражнениям 1.1-1.8 </center>
<center>по дисциплине </center>
<center><b>«Введение в информационные технологии»</b></center>
<center>на тему</center>
<center><b>«Docker»</b> </center>

</font>

  <br><br><br><br><br>
  <p  align="right"> <font face="times new roman" size="3" > Выполнил: студент группы </p>
  <p  align="right"> <font face="times new roman" size="3" >       БИК2502 </p>
  <p  align="right"> <font face="times new roman" size="3" > Вартке Матвей Данилович</p>
  <p  align="right"> <font face="times new roman" size="3" > Проверил:</p>
  <p  align="right"> <font face="times new roman" size="3" > Старший преподаватель кафедры ТиЗВ Егоров Дмитрий Аркадьевич  </p>
  <br>
  <br>

  <p  align="center"> <font face="times new roman" size="2" > Москва, 2026 г. </p>

  <hr>

## 1.1

```
dokart@DESKTOP-L0JFK38:~/devops-docker$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                      PORTS     NAMES
2ca7b09eb794   nginx     "/docker-entrypoint.…"   About a minute ago   Exited (0) 50 seconds ago             nginx3
4cd6254657be   nginx     "/docker-entrypoint.…"   About a minute ago   Exited (0) 50 seconds ago             nginx2
60f438246a7f   nginx     "/docker-entrypoint.…"   11 minutes ago       Up 11 minutes               80/tcp    inspiring_wilson
```

## 1.2

```
dokart@DESKTOP-L0JFK38:~/devops-docker$ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
dokart@DESKTOP-L0JFK38:~/devops-docker$
```
```
dokart@DESKTOP-L0JFK38:~/devops-docker$ docker image ls
                                                                                                                                     i Info →   U  In Use
IMAGE   ID             DISK USAGE   CONTENT SIZE   EXTRA
dokart@DESKTOP-L0JFK38:~/devops-docker$
```

## 1.3

```
docker run -d --name 13 devopsdockeruh/simple-web-service:ubuntu
docker exec -it 13 bash
tailf -f ./text.log

Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```

## 1.4

```
dokart@DESKTOP-L0JFK38:~/devops-docker$ docker run -it ubuntu sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'
Input website:
helsinki.fi
Searching..
sh: 1: curl: not found
```
```
второе окно терминала
dokart@DESKTOP-L0JFK38:~$ docker exec -it cdd bash -c  "apt update"
......
Fetched 36.1 MB in 5s (7369 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
8 packages can be upgraded. Run 'apt list --upgradable' to see them.
dokart@DESKTOP-L0JFK38:~$

dokart@DESKTOP-L0JFK38:~$ docker exec -it cdd bash -c  "apt install curl -y"
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
......
done.
dokart@DESKTOP-L0JFK38:~$
```
```
dokart@DESKTOP-L0JFK38:~/devops-docker$ docker run -it ubuntu sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'
Input website:
helsinki.fi
Searching..
sh: 1: curl: not found
Input website:
helsinki.fi
Searching..
<html>
<head><title>301 Moved Permanently</title></head>
<body>
<center><h1>301 Moved Permanently</h1></center>
<hr><center>nginx/1.24.0</center>
</body>
</html>
Input website:
^Cdokart@DESKTOP-L0JFK38:~/devops-docker$
```

## 1.5
```
dokart@DESKTOP-L0JFK38:~$ docker image ls devopsdockeruh/simple-web-service
                                                                                                                                        i Info →   U  In Use
IMAGE                                      ID             DISK USAGE   CONTENT SIZE   EXTRA
devopsdockeruh/simple-web-service:alpine   dd4d367476f8       24.3MB         7.93MB
devopsdockeruh/simple-web-service:ubuntu   d44e1dce3987        126MB         33.7MB    U
dokart@DESKTOP-L0JFK38:~$
```
```
dokart@DESKTOP-L0JFK38:~$ docker run -d --name alpine devopsdockeruh/simple-web-service:alpine
82c05b2ad835807049e4cf77c269f50239fbc1a82b6f14a894645199c08f11b9
dokart@DESKTOP-L0JFK38:~$ docker exec -it alpine sh
/usr/src/app # tail -f ./text.log
2026-02-17 20:23:07 +0000 UTC
2026-02-17 20:23:09 +0000 UTC
2026-02-17 20:23:11 +0000 UTC
2026-02-17 20:23:13 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2026-02-17 20:23:15 +0000 UTC
2026-02-17 20:23:17 +0000 UTC
2026-02-17 20:23:19 +0000 UTC
2026-02-17 20:23:21 +0000 UTC
2026-02-17 20:23:23 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2026-02-17 20:23:25 +0000 UTC
2026-02-17 20:23:27 +0000 UTC
2026-02-17 20:23:29 +0000 UTC
2026-02-17 20:23:31 +0000 UTC
2026-02-17 20:23:33 +0000 UTC
^C
/usr/src/app # ^C
/usr/src/app # exit
dokart@DESKTOP-L0JFK38:~$
```
```
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```

## 1.6
```
dokart@DESKTOP-L0JFK38:~$ docker run -it devopsdockeruh/pull_exercise
Unable to find image 'devopsdockeruh/pull_exercise:latest' locally
latest: Pulling from devopsdockeruh/pull_exercise
67c4f504c224: Pull complete
5e2195587d10: Pull complete
6f595b2fc66d: Pull complete
165f32bf4e94: Pull complete
8e402f1a9c57: Pull complete
Digest: sha256:7c0635934049afb9ca0481fb6a58b16100f990a0d62c8665b9cfb5c9ada8a99f
Status: Downloaded newer image for devopsdockeruh/pull_exercise:latest
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"

dokart@DESKTOP-L0JFK38:~$

пароль - basics

Secret message is:
"This is the secret message"
```