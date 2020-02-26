## Настройки для Ubuntu (18.4) после установки

#### Настройка SSH-клиента
```
ssh-keygen -t rsa
```

#### Устанавливаем `nodejs` с помощью [nvm](https://github.com/nvm-sh/nvm#install--update-script)
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash
nvm install node
node --version
```

#### Увеличиваем лимит количества файловых наблюдателей
```
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

#### Устанавливаем программу для скриншотов
```
sudo add-apt-repository ppa:atareao/flameshot
sudo apt update
sudo apt install flameshot
```

#### Включение «Сворачивание в один клик» для док-панели Ubuntu
```
gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize'
```

#### Настройки тачпада на свайпы 3-4 пальцами
```
sudo gpasswd -a $USER input  
sudo apt-get install libinput-tools  
sudo apt-get install xdotool 
sudo apt install ruby  
sudo gem install fusuma  
cd ~/.config  
mkdir fusuma
cd fusuma
touch config.yml
gedit config.yml
```
Добавляем конфигурацию в конфиг, сохраняем:
```
swipe:
  3:
    left: 
      command: 'xdotool key ctrl+alt+Down'
    right: 
      command: 'xdotool key ctrl+alt+Up'
    up: 
      command: 'xdotool key super'
    down: 
      command: 'xdotool key super+d'
  4: 
    left: 
      command: 'xdotool key alt+Right'
    right: 
      command: 'xdotool key alt+Left'
    up: 
      command: 'xdotool key ctrl+t'
    down: 
      command: 'xdotool key ctrl+w'
pinch:
  2:
    in:
      command: 'xdotool key ctrl+plus'
      threshold: 0.1
    out:
      command: 'xdotool key ctrl+minus'
      threshold: 0.1

threshold:
  swipe: 0.4
  pinch: 0.4

interval:
  swipe: 0.8
  pinch: 0.1
```
Настраиваем автозапуск:
* Открываем стандартное приложение `Startup Application`
* Нажимаем `Add`
* Вводим поля:
```
Name :    fusuma touch gestures
Command : fusuma
Comment : Touch Pad
```
