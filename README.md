<img width="820" height="330" alt="Скриншот 05 10 26_03 14 17" src="https://github.com/user-attachments/assets/9f587b99-d475-417e-99f7-aa385c608a7d" />


# TryHackMe — OhSINT

**Платформа:** TryHackMe  
**Категория:** OSINT / IMINT / SOCMINT  
**Сложность:** Easy

# 1. _Сама задача_

### Дан единственный файл изображения. Требуется, используя методы OSINT, извлечь из него максимум информации и ответить на семь вопросов:

#### 1. What is this user's avatar of?
#### 2. What city is this person in?
#### 3. What is the SSID of the WAP he connected to?
#### 4. What is his personal email address?
#### 5. What site did you find his email address on?
#### 6. Where has he gone on holiday?
#### 7. What is the person's password?

# 2. _Действия по ней_

### Шаг 1. Извлечение метаданных

#### Инструмент: `exiftool`  
#### Команда:  
##### ```bash
##### exiftool C:(ваш путь)\WindowsXP_1551719014755.jpg

### __Вывод:__

#### ExifTool Version Number         : 13.59
#### File Name                       : WindowsXP_1551719014755.jpg
#### Directory                       : C:/Users/╧╩/Downloads
#### File Size                       : 234 kB
#### File Modification Date/Time     : 2026:10:05 02:47:39+03:00
#### File Type                       : JPEG
#### MIME Type                       : image/jpeg
#### XMP Toolkit                     : Image::ExifTool 11.27
#### GPS Latitude                    : 54 deg 17' 41.27" N
#### GPS Longitude                   : 2 deg 15' 1.33" W
#### Copyright                       : OWoodflint
#### Image Width                     : 1920
#### Image Height                    : 1080
#### GPS Position                    : 54 deg 17' 41.27" N, 2 deg 15' 1.33" W

### _Шаг 2. Поиск по имени пользователя_

#### С помощью GOOGLE-дорков находим twitter/github аккаунт с таким никнеймом

#### Результат: обнаружены аккаунты на нескольких платформах:
#### Twitter/X: @OWoodflint
#### GitHub: OWoodfl1nt/people_finder
#### WordPress: oliverwoodflint.wordpress.com

<img width="540" height="115" alt="Скриншот 05 10 26_03 32 01" src="https://github.com/user-attachments/assets/439818b0-baad-4a81-be1a-73917799804a" />

### _Шаг 3. Анализ Twitter/X_

#### Найденные данные:
#### Пост с раскрытием BSSID: B4:5D:50:AA:86:41

### _Шаг 4. Геолокация Wi-Fi точки доступа_

#### Инструмент: wigle.net
#### Запрос: BSSID B4:5D:50:AA:86:41

### Результат:
#### Город: London.
#### SSID: UnileverWiFi.

### _Шаг 5. Анализ GitHub_

#### Репозиторий: OWoodfl1nt/people_finder
#### В README-файле найдено:
#### Email: OWoodflint@gmail.com.
#### Упоминание: «I am from London»

### _Шаг 6. Анализ WordPress (ФИНАЛЬНЫЙ ШАГ)_

### Инструмент: WordPress
### Блог: oliverwoodflint.wordpress.com

#### Найденные данные:
#### В одном из постов: «Im in New York right now».
#### В исходном коде страницы (или при выделении текста) обнаружен скрытый пароль: pennYDr0pper.!.

## Решение задачи:
<img width="690" height="325" alt="Скриншот 05 10 26_03 35 39" src="https://github.com/user-attachments/assets/f5570fc5-1b2f-4da0-8f76-3c568fc1f515" />
