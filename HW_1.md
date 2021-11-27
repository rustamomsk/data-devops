0. Подключаемся по ssh ко второй машине
![image](https://user-images.githubusercontent.com/87946097/143620682-9896e705-e5c0-4de3-8ce4-5d6708e422e1.png)

1) Ищем файлы по заданным шаблонам
> ls -la man* | grep "config"
![image](https://user-images.githubusercontent.com/87946097/143625399-8dcab144-7f4a-44c2-a147-b8e1854aa420.png)

> ls -ls man[1,7] | grep "system"
![image](https://user-images.githubusercontent.com/87946097/143625516-48779812-6776-4e85-befe-a11298b189b1.png)

2) find -name "*help*" && find -name "config*"
 или
 find . \( -name "*help*" -o -name "config*" \)

![image](https://user-images.githubusercontent.com/87946097/143626428-7b91afa5-aa05-4278-a515-a3d917a7dd0e.png)

Пример использования команды find:

> find /path_to_smth -type d | xargs chmod 0777
#эта команда будет задавать права доступа для найденных подкаталогов

3) tail -n2 fstab
![image](https://user-images.githubusercontent.com/87946097/143655003-0afab91a-09ad-47dd-ad34-3df4988352f4.png)

head -n7 yum.conf
![image](https://user-images.githubusercontent.com/87946097/143655622-e8c6ffb4-6c21-4653-be06-59f6d7f88b32.png)

При попытке вывода большего количества строк, чем есть, будет выведен полный текст файла.
![image](https://user-images.githubusercontent.com/87946097/143658165-c058ab58-0135-4411-b1f5-dcc07508aef4.png)

4) Переименование файлов
![image](https://user-images.githubusercontent.com/87946097/143659405-c276816d-a8d8-4395-b965-1d3e4a4f8c3e.png)

5)
>cd -
>cd 
>cd ~rustam2
>cd /home/rustam2

6) вв

> mkdir new in-process processed
> cd in-processed
> mkdir thr

Команды копирования:
> cp data{00..33} ../in-process/thread0
> cp data{34..66} ../in-process/thread1
> cp data{67..99} ../in-process/thread2

Команда вывода:
> cd in-process
> ll thread* | grep "data"

Перемещаем содержимое thread-ов в processed
> mv `find -name "data*"` ../processed/

Показываем содержимое
> ls in-process/thread*/ && ls processed

Смотрим количество файлов в директориях
> find new -type f | wc -l
> find processed -type f | wc -l

Удаляем содержимое new
rm new/*

![image](https://user-images.githubusercontent.com/87946097/143662159-672ec5f3-fc0c-4b90-a9dd-72ad24b62e23.png)










