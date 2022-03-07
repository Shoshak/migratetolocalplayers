
# Локальные музыкальные плееры или как избавиться от стриминга раз и навсегда

Так как спотифай премиум подписки отрубаются в России, эпл продвигает агрессивный анти-российский маркетинг, а слушать музыку на онли шаффле и ебаться с хост файлами, либо открывать отдельный таб в браузере и покупать подписку вК мУзЫкИ мало кто хочет...
Предлагаю перейти на ничем не уступающие стриминговым сервисам альтернативы! Сначала может быть неудобно, но чувствую с текущим мировым климатом именно так мы и будем жить.

## Что вы получаете с перехода?

**Плюсы:**
1. Полностью бесплатно;
2. Независимость от интернета;
3. Независимость от компаний;
4. Ноль рекламы;
5. Без регистраций (и смс);
6. Кастомизация плеера (уровень зависит от конкретного плеера);
7. Ненадобность запускать браузер, который жрет дохерища памяти;
8. Возможность слушать любую андерграунд музыку, которая вам нравится.

**Минусы:**
1. Сравнительно непростой процесс перехода;
2. В зависимости от способа переноса музыки, в некоторых случаях вы получите интересные "бонусы", по типу 2-5 секундного старта/стопа мелодии, интро/аутро к клипу и другую подобную херню. Вам придется разбираться с ней самим!;
3. Эксклюзивы спотифая, эпл музыки, etc. в некоторых случаях придется искать самим. Но это происходит от "крайне редко" до "редко", в зависимости от ваших музыкальных вкусов;
4. В большинстве случаев - отсутствие рич презенса в дискорде (что исправимо);
5. Сложности с совместным прослушиванием музыки ([Синхронное прослушивание](#синхронное-прослушивание)).

Если для вас перспектива локальных плееров выглядит привлекательно, то... *__Приступим!__*

## Prerequisites или "Какое оптимальное количество мозговых клеток нужно иметь?" (хотя бы две)
- Версия ОС Windows 10/11 или Linux. Если на этом сервере есть пользователи яблока, то дополняйте гайд;
- Хоть какой-то интернет, возможно использование dial-up;
- Умеренные знания английского языка для чтения документаций;
- Произвольное количество времени, зависящее от прямоты ваших рук.

## Перенос музыки
Есть несколько вариантов, как это можно сделать:

### 1. Spotify-DL
Самый быстрый (для знающих) способ перенести всю свою библиотеку со спотифая в mp3 файлы - это [**spotify-dl**](https://github.com/SathyaBhat/spotify-dl/blob/master/GETTING_STARTED.md). На странице есть гайд для новичков, но для более простого понимания дальше будет гайд на русском:


### Что нужно:
1. [Python](https://www.python.org/) 3.6+
2. [FFMpeg](https://github.com/BtbN/FFmpeg-Builds/releases/download/latest/ffmpeg-master-latest-win64-gpl.zip)
3. Аккаунт Spotify

### Порядок действий:
**Windows**
1. Откройте `Windows Powershell` через поиск;
2. Распакуйте скачачнный zip ffmpeg в папку `C:\` на вашем компьютере;
3. Переименуйте находящуюся внутри архива корневую папку в `ffmpeg`;
4. Пропишите в терминал Windows: `setx /m PATH "C:\ffmpeg\bin;%PATH%"`. К этому времени ваш путь к папкам `bin` и `doc` должен быть `C:\ffmpeg\`;
5. Пропишите в терминал Windows: `ffmpeg --version`. Если выводится `ffmpeg version` и название версии, а также список флагов (начинающихся на `--`), то у вас все работает! Если нет, то проверьте путь и почитайте гайды по установке ffmpeg на Windows.

**Linux**
1. Обратитесь к репозиториям вашего дистрбутива и скачайте оттуда пакет `ffmpeg`;
2. Проверьте версию ffmpeg командой `ffmpeg --version`.

**Всем**

1. Войдите в [консоль разработчика Spotify](https://developer.spotify.com/dashboard) и нажмите "Создать приложение". Заполните детали для имени и описания (можно вбить что угодно);
2. Запишите идентификатор клиента и секрет клиента;
3. Найдите папку в которую вы хотите загрузить вашу музыку. В этой папке будет создана другая папка, которая будет содержать музыку;
4. Откройте терминал в выбранной папке. На Windows это можно сделать через зажатие кнопки `shift` и последующим нажатием правой кнопку мыши. После этого в меню должна отобразиться кнопка "Открыть в терминале Windows";
5. После открытия терминала значения из пункта 2 необходимо установить в токены `SPOTIPY_CLIENT_ID`, `SPOTIPY_CLIENT_SECRET` (именно spoti**P**y, это не опечатка). Сделать это можно так:

**Linux:**
```
export SPOTIPY_CLIENT_ID=ваш-spotify-client-id
export SPOTIPY_CLIENT_SECRET=ваш-spotify-client-secret
```
**Windows:**
```
$env:SPOTIPY_CLIENT_ID=ваш-spotify-client-id
$env:SPOTIPY_CLIENT_SECRET=ваш-spotify-client-secret
```

6. В том же терминале пропишите команды в следующем порядке:
```
python3 -m pip install --upgrade pip
pip install spotify_dl
```
7. Скопируйте ссылку на любой плейлист Spotify. Это можно сделать так:
![делать вот так](https://raw.githubusercontent.com/SathyaBhat/spotify-dl/master/images/spotify-playlist.png)
8. Дальше пропишите `spotify_dl -l ссылка-на-плейлист ссылка-на-другой-плейлист`. Можно прописать любое количество плейлистов!;
9. Бинго! Музыка должна начать загружаться. Если выводятся ошибки `.cache` - перезагрузите скрипт.

### 2. Ручная загрузка с ютуба и конвертация в mp3
Может быть долго, не спорю. Но не такой уж и плохой вариант, учитывая то, сколько сервисов для этого существует.
Для начала можно пользоваться [**yt-dlp**](https://github.com/yt-dlp/yt-dlp), но это решение подходит не всем, так как... терминал. Однако, оно имеет свои плюсы! (по типу пропуска секции без музыки, см. пункт 2 минусов перехода)

У youtube-dl (на базе которого построен yt-dlp) есть графическая оболочка в виде [**youtube-dl-gui**](https://github.com/jely2002/youtube-dl-gui). Сам софт не проверен, но должен работать.

Для конвертации (если по какой-то причине в самом youtube-dl вы не указали режим "Audio only") видео в mp3 существует [удобный аудио конвертер](https://online-audio-converter.com/).

### 3. Скачивание из ВК Музыки
В этом может помочь удобное [расширение для гугла](https://chrome.google.com/webstore/detail/%D1%81%D0%BA%D0%B0%D1%87%D0%B0%D1%82%D1%8C-%D0%BC%D1%83%D0%B7%D1%8B%D0%BA%D1%83-%D1%81-%D0%B2%D0%BA/bgmpjmdignpongmfjpgaikghaajeidid). Находясь во вкладке "Музыка" наведитесь на любой трек, на нем появится маленькая синяя стрелочка. Думаю, дальше все просто. Треки качаются в выбранную по умолчанию папку для загрузок.
Также у этого расширения есть возможность скачать все треки из плейлиста одной кнопкой, что поможет в быстром переносе библиотеки.

### 4. Скачивание из сторонних источников
Думаю тут все и так ясно. "Залив пиратов" и рутрекер (тем более его сейчас по сути легализовали) в помощь, а также любые вариации зайцев.нет
Если у вас есть доступные, лежащие на компьютере или в плеерах mp3 файлы, то можете также добавить их к своей коллекции.

## Таблица плееров

### PC
| Windows | Linux | Cross |
| --- | --- | --- |
| [foobar](https://www.foobar2000.org/) | [sayonara](https://sayonara-player.com/) | [quod libet](https://github.com/quodlibet/quodlibet)
| [AIMP](https://www.aimp.ru) | [TauonMusicBox](https://github.com/Taiko2k/TauonMusicBox) | [VLC](https://www.videolan.org/vlc/)

### Мобильные устройства
| Бесплатные | Платные | 
| --- | --- |
| AIMP ([Google Play](https://play.google.com/store/apps/details?id=com.aimp.player)) | Neutron ([Google Play](https://play.google.com/store/apps/details?id=com.neutroncode.mp) / [App Store](https://apps.apple.com/us/app/neutron-music-player/id766858884)) |
| VLC ([Google Play](https://play.google.com/store/apps/details?id=org.videolan.vlc) / [App Store](https://apps.apple.com/ru/app/vlc-for-mobile/id650377962)) | Poweramp ([Google Play](https://play.google.com/store/apps/details?id=com.maxmpz.audioplayer)) |

Предлагайте другие плееры, с которыми у вас есть опыт. Консольные не предлагать, ради доступности для всех юзеров.
 
## Синхронное прослушивание
Что касается эпичного прослушивания музыки в компании, то единого простого решения не существует. Это происходит в связи с тем, что плееров разных много и каждый связывать друг с другом - сложно.
Для продвинутых пользователей можно порекомендовать [snapcast](https://github.com/badaix/snapcast), который является серверным решением этого вопроса. Пока простых способов не существует. Следите за новостями!


## Альтернативы
Существует альтернатива в виде [nuclear](https://nuclear.js.org/), позволяющая получить практически идентичный опыт от стриминга, при этом используя огромную площадку ютуба, как базу для контента. Казалось бы, что может пойти не так?
В моем опыте - все. Большинство треков загружаются крайне долго, загрузки треков работают крайне топорно, а система плейлистов является в моих глазах огромным стыдом. Возможно ваш опыт будет другим, но... Используйте на свой страх плохого софта.
Ну и конечно, существует альтернатива возвращения к нашей любимой ВК музыке. Что лучше для вас - решать вам.
