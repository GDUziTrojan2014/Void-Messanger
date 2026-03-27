# Void-Messanger
Void Messenger — анонимный мессенджер на протоколе RMM/IP с маскировкой трафика, шифрованием сообщений и стилем Windows XP. Полная конфиденциальность в классическом интерфейсе. Написан на Python


Требования: 
Python(не ниже 3)
socket - сетевое взаимодействие
threading - многопоточность
tkinter - графический интерфейс
hashlib - шифрование
json - работа с конфигурацией
base64 - кодирование сообщений
datetime - временные метки
random - генерация VMID
time - тайминги
pickle - сохранение избранного
os - работа с файловой системой
platform - определение устройства
pyaudio - звонки

тутор:

1. скачиваем voidmessenger.py
2. если есть питон, скачиваем в требованиях библиотеки(если нет, переходите сюда: https://www.python.org/downloads/, и скачивайте 
(deb-сообщества: 
sudo apt update
sudo apt install python3
sudo apt install python3-tk
sudo apt install python3-pip
sudo apt install python3-venv;

Redhat-основанные

Fedora:
sudo dnf install python3
sudo dnf install python3-pip

CentOS/RHEL 7-8

sudo yum install epel-release
sudo yum install python3

CentOS/RHEL 8+

sudo yum install epel-release
sudo yum install python3

Arch Linux / Manjaro

sudo pacman -S python          
sudo pacman -S python-pip      
sudo pacman -S python-virtualenv

openSUSE (Leap)

sudo zypper install python3
sudo zypper install python3-pip
sudo zypper install python3-virtualenv

openSUSE (Tumbleweed)

sudo zypper install python3

MacOS:

brew install python(или через сайт питона))

2. настраиваем venv(для pip, иначе ошибка будет)

# Если у вас несколько версий Python
python3.12 -m venv venv
# или
/usr/local/bin/python3.11 -m venv venv
2. Linux (все дистрибутивы)
Установка venv (если отсутствует)
На некоторых дистрибутивах venv нужно установить отдельно:

Debian/Ubuntu/Mint:
bash
sudo apt update
sudo apt install python3-venv python3-pip
Fedora/RHEL/CentOS:
bash
sudo dnf install python3-virtualenv
# или для старых версий
sudo yum install python3-virtualenv
Arch Linux:
bash
sudo pacman -S python-virtualenv
# venv уже входит в состав python
Создание окружения
bash
# Перейти в папку проекта
cd ~/projects/myproject

# Создать виртуальное окружение
python3 -m venv venv
# или
python3 -m venv .venv
Активация
Для bash/zsh:

bash
source venv/bin/activate
Для fish:

bash
source venv/bin/activate.fish
Для csh/tcsh:

bash
source venv/bin/activate.csh
Деактивация
bash
deactivate
Особенности Linux
Права доступа: На Linux важно, чтобы папка проекта принадлежала вашему пользователю:

bash
# Если возникли проблемы с правами
sudo chown -R $USER:$USER ~/projects/myproject
Системный Python: Никогда не используйте sudo с pip внутри venv:

bash
# ПЛОХО - нарушит права
sudo pip install package

# ХОРОШО
pip install package
Shebang в скриптах: При создании исполняемых скриптов используйте:

python
#!/usr/bin/env python
Это обеспечит использование Python из активного venv

# 3. Windows
На Windows синтаксис отличается, особенно в командах активации и путях.

Установка Python и venv
Скачайте Python с python.org

ВАЖНО: При установке отметьте галочку "Add Python to PATH"

venv устанавливается автоматически

Проверка установки:
cmd
python --version
pip --version
Создание окружения
В командной строке (cmd) или PowerShell:

cmd
# Перейти в папку проекта
cd C:\Users\%USERNAME%\projects\myproject

# Создать виртуальное окружение
python -m venv venv
# или
py -m venv venv
Активация
В классической командной строке (cmd):
cmd
venv\Scripts\activate.bat
В PowerShell:
powershell
.\venv\Scripts\Activate.ps1
Если PowerShell запрещает выполнение скриптов:
powershell
# Временно разрешить выполнение скриптов
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# После этого активируйте
.\venv\Scripts\Activate.ps1
Деактивация
cmd
deactivate
Особенности Windows
Пути: Вместо / используются \

Активация: Нет source, используется прямой запуск .bat или .ps1

Кодировка: Могут быть проблемы с UTF-8 в консоли:

cmd
# Установить кодировку UTF-8
chcp 65001
Длинные пути: На Windows может быть ограничение в 260 символов. Чтобы снять его:

Редактор групповых политик → Административные шаблоны → Система → Файловая система → "Включить длинные пути Win32"
