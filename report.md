## Part 1. Установка ОС

- ``Смотрим версию Ubuntu после установки ``<br>
![alt text](1q.png)<br>


---

## Part 2. Создание пользователя
- ``Создаём пользователя и назначаем ему группу adm``<br>
![alt text](2q.png)<br>


- ``Вывод списка пользователей (новый юзер в конце списка)``<br>
![alt text](2.1q.png)<br>


---

## Part 3. Настройка сети ОС

- ``Установили новое имя машины и вывели его в терминал``<br>
![alt text](3.1q.png)<br>

- ``Установили новую временную зону и вывели информацию в терминал``<br>
![alt text](3.2q.png)<br>

- ``Устанавливаем набор сетевых инструментов``<br>
![alt text](3.3q.png)<br>
``Выводим информацию о сетевых интерфейсах``<br>
![alt text](3.4q.png)<br>
**lo (loopback device)** – виртуальный интерфейс, присутствующий по умолчанию в любом Linux. Он используется для отладки сетевых программ и запуска серверных приложений на локальной машине. С этим интерфейсом всегда связан адрес 127.0.0.1. У него есть dns-имя – localhost.

- ``Удалили старый и получили новый ip от dhcp сервера``<br>
![alt text](3.5q.png)<br>
**DHCP - Dynamic Host Configuration Protocol**

- ``Узнали внешний IP-адрес``<br>
![alt text](3.6q.png)<br>

- ``Узнали внутренний IP-адрес шлюза, он же ip-адрес по умолчанию``<br>
![alt text](3.7q.png)<br>

- ``Изменили файл /etc/netplan/*.yaml, применили изменения в netplan, сделали ребут``<br>
![alt text](3.8q.png)<br>
![alt text](3.10q.png)<br>
- ``Проверяем, что адреса соотсветствуют заданным в предыдущем пункте``<br>
![alt text](3.11q.png)<br>
- ``Успешно пропинговали удаленные хосты 1.1.1.1 и ya.ru``<br>
![alt text](3.12q.png)<br>

---

## Part 4. Обновление ОС
- ``Успешно обновили системыне пакеты``<br>
![alt text](4q.png)<br>

---

## Part 5. Использование команды sudo
- **sudo** - позволяет временно поднимать привилегии и выполнять задачи администрирования системы с максимальными правами<br>
``Добавили пользователя в группу с привилегиями sudo, переключились на этого пользователя и поменяли hostname``<br>
![alt text](5q.png)<br>

---

## Part 6. Установка и настройка службы времени
- ``Вывод команды с корректным временем``<br>
![alt text](6q.png)<br>
![alt text](q6.jpg)<br>

---
юююююююююю
## Part 7. Установка и использование текстовых редакторов
- ``**VIM** Для сохранения и выхода нажал ESC и прописал :wq и имя документа``<br>
![alt text](7.1viim.png)<br>

- ``**NANO** Для сохранения нажал ^O, ввёл имя файла и подтвердил. Вышел через ^X``<br>
![alt text](7.1nano.png)<br>
- ``**JOE** Для сохранения и выхода нажал ^KX, ввёл имя файла и подтвердил.``<br>
![alt text](7.1joe.png)<br>

- ``**VIM** Для выхода без сохранения ESC -> :q! -> ENTER``<br>
![alt text](7.1.1vim.png)<br>
- ``**NANO** Для выхода без сохранения ^X -> N``<br>
![alt text](7.1.1nano.png)<br>
- ``**JOE** Для выхода без сохранения ^C -> y``<br>
![alt text](7.1.1joe.png)<br>
- ``**VIM** Для поиска: /что_ищем``<br>
![alt text](7.2vim.png)<br>
![alt text](7.2.1vim.png)<br>
- ``**VIM** Для замены: :s/что_заменить/чем``<br>
![alt text](7.2.2vim.png)<br>
![alt text](7.2.3vim.png)<br>
- ``**NANO** Для поиска: ^W -> что ищем``<br>
![alt text](7.2nano.png)<br>
![alt text](7.2.1nano.png)<br>
- ``**NANO** Для замены: ^\ -> что заменить -> чем -> Y``<br>
![alt text](7.2.2nano.png)<br>
![alt text](7.2.4nano.png)<br>
- ``**JOE** Для поиска: ^K F -> что ищем -> I``<br>
![alt text](7.2joe.png)<br>
![alt text](7.2.1joe.png)<br>
- ``**JOE** Для замены: ^K F -> что заменить -> R -> чем -> Y``<br>
![alt text](7.2.2joe.png)<br>
![alt text](7.2.3joe.png)<br>
![alt text](7.2.4joe.png)<br>

---

## Part 8. Установка и базовая настройка сервиса SSHD
- ``Установил openssh-server и настроил конфиг``<br>
- ``Выполнил sudo systemctl start sshd``<br>
- ``Выполнил sudo systemctl enable sshd``<br>
- ``Отобразил наличие процесса``<br>
**ps** - выводит сведения о процессах в статическом виде<br>
**-e** - позволяет выбрать все процессы<br>
**| grep sshd** - поиск по выводу через пайп<br>
![alt text](<8.1q — копия.png>)<br>
- ``reboot``<br>
- ``netstat -tan``<br>
![alt text](8.2q.png)<br>
**-tan**: <br>
-a -	Показывать состояние всех сокетов; обычно сокеты, используемые серверными процессами, не показываются.<br>
-n - Показывать сетевые адреса как числа. netstat обычно показывает адреса как символы.<br>
-t - Отображать TCP подключения<br>
**Proto** - Содержит тип протокола<br>
**Recv-Q** - Счётчик байтов не скопированных программой пользователя из этого сокета.<br>
**Send-Q** - Счётчик байтов, не подтверждённых удалённым узлом.<br>
**Local Address** - Адрес и номер порта локального конца сокета.<br>
**Foreign Address** - Адрес и номер порта удалённого конца сокета.<br>
**State** - Состояние сокета.<br> 
LISTEN Сокет ожидает входящих подключений.<br> 
SYN_SENT Сокет, находящийся в режиме активной попытки установки подключения.<br>
0.0.0.0 -  это немаршрутизируемый адрес IPv4, который используется в качестве адреса по умолчанию или адреса-заполнителя.

---

## Part 9. Установка и использование утилит top, htop
- Uptime: 7 min<br>
- 1 user<br>
- Load average: 0.03, 0.07, 0.06<br>
- Tasks: 95 total<br>
- %Cpu(s): 0.3 us, 0.3 sy, 0.0 ni, 99.3 id, 0.0 wa, 0.0 hi, 0.0 si, 0.0 st<br>
- MiB Mem: 965.1 total, 297.6 free, 148.4 used, 519.1 buff/cache<br>
- PID 1231<br>
![alt text](<9q top-1.png>)<br>

- ``htop сортировка по PID``<br>
![alt text](<9q htop PID.png>)<br>
- ``htop сортировка по PERCENT_CPU``<br>
![alt text](<9q htop RECENT_CPU.png>)<br>
- ``htop сортировка по PERCENT_MEM``<br>
![alt text](<9q htop RECENT_MEM.png>)<br>
- ``htop сортировка по TIME``<br>
![alt text](<9q htop TIME.png>)<br>
- ``htop фильтр по процессу sshd``<br>
![alt text](<9q sshd.png>)<br>
- ``htop поиск процесса syslog``<br>
![alt text](<9q syslog.png>)<br>
- ``htop с добавленным выводом hostname, clock и uptime``<br>
![alt text](<9q host clock uptime.png>)<br>

---

## Part 10. Использование утилиты fdisk
- Disk /dev/sda, size: 8 GiB, 8589934592 bytes, 16777216 sectors<br>
![alt text](10q.png)<br>

---

## Part 11. Использование утилиты df
![alt text](<11q df.png>)<br>
bytes
![alt text](<11q df -Th.png>)<br>
ext4

---

## Part 12. Использование утилиты du
- ``du command:``<br>
![alt text](<12q du.png>)<br>
- ``/home:``<br>
![alt text](<12q home.png>)<br>
- ``/var:``<br>
![alt text](<12q var.png>)<br>
- ``/var/log/*:``<br>
![alt text](<12q var log.png>)<br>

---

## Part 13. Установка и использование утилиты ncdu
- ``Установка``<br>
![alt text](<13q install.png>)<br>
- ``/home``<br>
![alt text](<q13 home.png>)<br>
- ``/var``<br>
![alt text](<13q var.png>)<br>
- ``/var/log``<br>
![alt text](<13q var log.png>)<br>

---

## Part 14. Работа с системными журналами
- ``Напиши в отчёте время последней успешной авторизации, имя пользователя и метод входа в систему.``<br>
- ``13:51:07 micahbev root ``<br>
- ``Перезапуск OpenSSH Server``<br>
![alt text](<q14 restart.png>)<br>

---

## Part 15. Использование планировщика заданий CRON
- ``Создание задачи в cron``<br>
![alt text](q15.png)<br>
- ``uptime каждые 2 минуты``<br>
![alt text](<15q uptime.png>)<br>
- ``Вывели список задач``<br>
![alt text](<15q tab cat.png>)<br>
- ``Удалили все задачи вывели список``<br>
![alt text](<15q delete.png>)<br>
