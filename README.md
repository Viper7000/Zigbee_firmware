# Zigbee_firmware
Alternative Zigbee firmware for some devices

Тут собраны прошивки, которые я пересобирал под другие модули либо вносил какие-либо изменения. Изначально прошивки будут собираться под модули E18-MS1PA2, которые имеют усилитель и доступны сейчас к покупке. По возможности буду писать какие прошивки проверены мной или другими пользователями. Прошивки в двух форматах: .hex для прошивки CC Debager-ом и .bin для прошивки [СС Loader](https://github.com/RedBearLab/CCLoader)-ом через ESP32.
Оригинальную инструкцию СС Loader для Arduino Uno/ESP8266 брал [тут](https://www.zigbee2mqtt.io/guide/adapters/flashing/alternative_flashing_methods.html#via-arduino-uno-esp8266-with-ccloader-3min)

## Доступные прошивки

Проект [DIYRuZ_Geiger](https://modkam.ru/2020/06/05/indikator-radioaktivnosti-zigbee/)
1.0.8 под модуль E18-MS1PA2, оригинальная - проверена мной.

Проект [DIYRuZ_FreePad](https://modkam.ru/2019/11/13/pult-zigbee-v2-prosto-otlomi-lishnee/)
2.0.7 под модуль E18-MS1PA2, оригинальная - ___не проверена___.

# CC Loader
Мой метод прошивки модулей СС2530. Дебагера у меня нет, малинку я не стал разбирать, а через [VLK DIY Multi Flasher](https://zigbee.wiki/books/прошивки/page/vlk-diy-multi-flasher) 
мне прошить не удалось (на 50-80% прогресса ошибка)

Качаем папку CCLoader. Открываем скетч CCLoader.ino и прошиваем ESP32. Подключаем ESP32 к модулю СС2530 по схеме (пины пожно изменить в скетче) и прошиваем модуль .bin файлом прошивки

СС2530 | ESP32 
:-----:|:--------:
VCC | 3V3 
P2.1 DD | IO19 
P2.2 DC | IO18 
RST | IO5
GND | GND

## Как конвертировать прошивку из .hex в .bin
С помощью утилиты objcopy.exe. Смотрите пример в файле hex2bin.bat. Можно просто подставить свои названия и запустить

## Как прошить модуль
Пример в файле flash.bat. Первый параметр (в моем случае 8) - COM порт куда подключена ESP32
