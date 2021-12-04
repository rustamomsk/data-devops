#### 0. Подключаемся по ssh ко второй машине
> ssh rustam2@10.0.2.4

#### 1) Используя команду ls, необходимо вывести на экран все файлы, которые расположены в секционных директориях /usr/share/man/manX и содержат слово "config" в имени.
> ls -la man?.*config*

####  Одним вызовом ls найти все файлы, содержащие слово "system" в каталогах /usr/share/man/man1 и /usr/share/man/man7
> ls -la man[1,7]/*system*

#### 2) Найти в директории /usr/share/man все файлы, которые содержат слово "help" в имени, найти там же все файлы, имя которых начинается на "conf".
> find -name "*help*" && find -name "config*"
или
> find . \( -name "*help*" -o -name "config*" \)

![image](https://user-images.githubusercontent.com/87946097/143626428-7b91afa5-aa05-4278-a515-a3d917a7dd0e.png)

Пример использования команды find:

> find /path_to_smth -type d | xargs chmod 0777  
эта команда будет задавать права доступа для найденных подкаталогов

#### 3) При помощи команд head и tail, выведите последние 2 строки файла /etc/fstab и первые 7 строк файла /etc/yum.conf  
> tail -n2 fstab  
![image](https://user-images.githubusercontent.com/87946097/143655003-0afab91a-09ad-47dd-ad34-3df4988352f4.png)

> head -n7 yum.conf  
![image](https://user-images.githubusercontent.com/87946097/143655622-e8c6ffb4-6c21-4653-be06-59f6d7f88b32.png)

При попытке вывода большего количества строк, чем есть, будет выведен полный текст файла.  
![image](https://user-images.githubusercontent.com/87946097/143658165-c058ab58-0135-4411-b1f5-dcc07508aef4.png)

#### 4) Создайте в домашней директории файлы file_name1.md, file_name2.md и file_name3.md. Используя {}, переименуйте:
> touch file_name{1..3}.md  
> mv file_name1.{md,textdoc}  
> mv file_name2{.md,}  
> mv file_name3{,.latest}  
> mv file_name1.{textdoc,txt}   


#### 5) Напишите как можно больше различных вариантов команды cd, с помощью которых вы можете вернуться обратно в домашнюю директорию вашего пользователя.  
>cd -  
>cd  
>cd ~rustam2  
>cd /home/rustam2  

#### 6) Создайте одной командой в домашней директории 3 папки new, in-process, processed...

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
> rm new/*  

![image](https://user-images.githubusercontent.com/87946097/143662159-672ec5f3-fc0c-4b90-a9dd-72ad24b62e23.png)
