Для ограничение ресурсов со значениями CPU 1, RAM 1Gb, выполнить команду:
docker run -d -m=1g --cpus='1' -p 5000:80 --name net net:latest
