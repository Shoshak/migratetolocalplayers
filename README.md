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
- Рабочая версия ОС Windows или Linux. Если на этом сервере есть пользователи яблока, то дополняйте гайд;
- Хоть какой-то интернет, возможно использование dial-up;
- Умеренные знания английского языка, для чтения документаций;
- Произвольное количество времени, зависящее от прямоты ваших рук.

## Перенос музыки
Есть несколько вариантов, как это можно сделать:

### 1. Spotify-DL
Самый быстрый (для знающих) способ перенести всю свою библиотеку со спотифая в mp3 файлы - это [**spotify-dl**](https://github.com/SathyaBhat/spotify-dl).

Если для кого-то все, что написано в репозитории слишком сложно непонятно (включая установку питона), то обращайтесь ко мне, я попробую скачать за вас ваши любимые плейлисты. Плюс, можно построить графическую оболочку, не только для нас. Кто хочет заняться этим?

### 2. Ручная загрузка с ютуба и конвертация в mp3
Может быть долго, не спорю. Но не такой уж и плохой вариант, учитывая то, сколько сервисов для этого существует.
Для начала можно пользоваться [**yt-dlp**](https://github.com/yt-dlp/yt-dlp), но это решение подходит не всем, так как... терминал. Однако, оно имеет свои плюсы! (по типу пропуска секции без музыки, см. пункт 2 минусов перехода)

У youtube-dl (на базе которого построен yt-dlp) есть графическая оболочка в виде [**youtube-dl-gui**](https://github.com/jely2002/youtube-dl-gui). Сам софт не проверен, но должен работать.

Для конвертации (если по какой-то причине в самом youtube-dl вы не указали режим "Audio only") видео в mp3 существует [удобный аудио конвертер](https://online-audio-converter.com/).

### 3. Скачивание из сторонних источников
Думаю тут все и так ясно. "Залив пиратов" и рутрекер (тем более его сейчас по сути легализовали) в помощь, а также любые вариации зайцев.нет
Если у вас есть доступные, лежащие на компьютере или в плеерах mp3 файлы, то можете также примкнуть их к своей коллекции.

## Таблица плееров

| Windows | Linux | Cross |
| --- | --- | --- |
| [foobar](https://www.foobar2000.org/) | [sayonara](https://sayonara-player.com/) | [quod libet](https://github.com/quodlibet/quodlibet)

Предлагайте другие плееры, с которыми у вас есть опыт. Консольные не предлагать, ради доступности для всех юзеров.
 
## Синхронное прослушивание
Что касается эпичного прослушивания музыки в компании, то единого простого решения не существует. Это происходит в связи с тем, что плееров разных много и каждый связывать друг с другом - сложно.
Вполне возможно скоро будет развернут сервер [snapcast](https://github.com/badaix/snapcast), который может быть решением этого вопроса. Следите за новостями!

## Альтернативы
Существует альтернатива в виде [nuclear](https://nuclear.js.org/), позволяющая получить практически идентичный опыт от стриминга, при этом используя огромную площадку ютуба, как базу для контента. Казалось бы, что может пойти не так?
В моем опыте - все. Большинство треков загружаются крайне долго, загрузки треков работают крайне топорно, а система плейлистов является в моих глазах огромным стыдом. Возможно ваш опыт будет другим, но... Используйте на свой страх плохого софта.
Ну и конечно, существует альтернатива возвращения к нашей любимой ВК музыке. Что лучше для вас - решать вам.
