# X4 9 и Launchpad S

Проверка от 9 ноября 2026 года. Установлена X4 9.00, Steam build 23660954. Обнаружены 25 сторонних расширений и 7 официальных DLC.

Для кокпита нужен собственный Python-сервис. Для первых кнопок достаточно MIDI → клавиши X4; мод нужен для получения состояния игры. Для постоянной интеграции предпочтителен небольшой собственный MD/Lua-адаптер поверх уже установленного SirNukes Named Pipes API. x4-simpit полезен как прототип и источник примеров, но его работу на X4 9 ещё нужно проверить.

## Выполненная очистка

- Старый **[8.X] Ship Variation Expansion** убран из папки расширений в резервную папку. Он уже был отключён в профиле до проверки. Версия **Ship Variation Expansion for 9.0** оставлена включённой.
- **Sector Explorer 1.52** отключён. В упакованном скрипте обнаружена ссылка на несуществующее значение перечисления; подробности ниже.
- **Enhanced Kill Credit 9.0.0** временно отключён. Он дублирует Better Kill Credit; кроме того, для этой версии есть сообщения о поломке Extension Options, которые автор расследует. Это основание исключить его из теста, но не доказательство несовместимости во всех конфигурациях. **Better Kill Credit 1.33** оставлен включённым.
- **Print Extension List** восстановлен до **1.02** из репозитория автора. Вместо мода был только 107-байтный content.xml с error="6"; каталог не содержал кода. Восстановлены content.xml, ui.xml, ui/print_extension_list.lua, README.md и LICENSE. Это обязательная зависимость установленного Protect Sector.
- Все 7 DLC оставлены без изменений.

Итого в профиле включены 22 сторонних расширения. Игра в ходе проверки не запускалась: восстановление файлов и настройки проверены, загрузка модов в игре ещё не проверена.

### Подписки и возврат изменений

Подписки Steam не изменены: управление через интерфейс Steam не удалось. Поэтому старый SVE может снова скачаться, хотя в профиле он останется выключенным. Для окончательного удаления следует отписаться от [SVE 8.x](https://steamcommunity.com/sharedfiles/filedetails/?id=2229061492).

Пути:

- Игра: G:\SteamLibrary\steamapps\common\X4 Foundations
- Профиль расширений: C:\Users\besch\OneDrive\Документы\Egosoft\X4\76426932\content.xml
- Резервная папка старого SVE: G:\SteamLibrary\steamapps\common\X4 Foundations\_disabled_extensions\cockpit-2026-11-09\ws_2229061492
- Копии конфигурации и исходников восстановленного мода: C:\Проекты\cockpit\backups\x4-2026-11-09

Для возврата отдельных модов достаточно включить их в меню Extensions; старый SVE также потребует возврата папки. Полная исходная конфигурация находится в profile-content.before.xml. Восстанавливать её целиком следует только при закрытой игре и с учётом более поздних изменений настроек. Сохранения игры не изменялись.

Старое прохождение с кораблями SVE 8.x не следует перезаписывать после изменения набора модов: автор старой версии требует подготовить чистое сохранение перед переходом. Для теста панели использовать отдельную новую игру. [Указание автора SVE](https://steamcommunity.com/sharedfiles/filedetails/?id=2229061492).

## Полный список расширений

«Заявлена 9.0» означает заявление в названии или описании установленной версии. «Оставлен» не означает, что комбинация модов прошла игровой тест. Дата последнего обновления сама по себе не доказывает совместимость или несовместимость.

| Расширение | Установленная версия | Результат |
|---|---|---|
| [Antigone Destroyer pack](https://steamcommunity.com/sharedfiles/filedetails/?id=3616342050) | 1.00 | Заявлена 9.0; оставлен |
| [Paintjobs Galore!](https://steamcommunity.com/sharedfiles/filedetails/?id=2083714551) | 1.10 | Заявлена 9.0; оставлен, несмотря на старую дату пакета |
| [Vibrant Engine Plumes](https://steamcommunity.com/sharedfiles/filedetails/?id=3438911633) | 1.31 | Заявлена 9.0; оставлен |
| [Better Kill Credit](https://steamcommunity.com/sharedfiles/filedetails/?id=1700645587) | 1.33 | Оставлен; пакет от 26.10.2026, второй мод наград отключён |
| [Emporos class freighter](https://steamcommunity.com/sharedfiles/filedetails/?id=3558596297) | 1.00 | Заявлена 9.0; оставлен |
| [Enhanced Kill Credit](https://steamcommunity.com/sharedfiles/filedetails/?id=3691165036) | 9.0.0 | Временно отключён: дублирование наград и сообщения о проблемах меню |
| [Faster Crew Leveling](https://steamcommunity.com/sharedfiles/filedetails/?id=2050537227) | raw 19 | Оставлен; есть сообщения игроков о работе в 9.0, игровая проверка нужна |
| [Sector Explorer](https://steamcommunity.com/sharedfiles/filedetails/?id=2074838459) | 1.52 | Отключён: подтверждён дефект blacklisttype.travel |
| [Nova MK2 fighter](https://steamcommunity.com/sharedfiles/filedetails/?id=3404629275) | 1.00 | Заявлена 9.0; оставлен |
| [No Resource Probe Decay](https://steamcommunity.com/sharedfiles/filedetails/?id=3766239549) | 1.00 | Предназначен для 9.0; оставлен |
| [Options Helper](https://steamcommunity.com/sharedfiles/filedetails/?id=3715253556) | 1.32 | Оставлен; требует X4 ≥ 8.00 и SirNukes ≥ 1.95, оба установлены |
| [Protect Sector](https://steamcommunity.com/sharedfiles/filedetails/?id=3379427822) | 2.02 | Заявлена 8.00 и выше; оставлен, повреждённая зависимость восстановлена |
| [Rook class heavy fighter](https://steamcommunity.com/sharedfiles/filedetails/?id=3551101481) | 1.00 | Заявлена 9.0; оставлен |
| [Ship Variation Expansion for 9.0](https://steamcommunity.com/sharedfiles/filedetails/?id=3736474056) | 2.21 | Оставлен; старый вариант 8.x убран |
| [SirNukes Mod Support APIs](https://steamcommunity.com/sharedfiles/filedetails/?id=2042901274) | 1.95 | Оставлен; нужен другим модам и будущему каналу телеметрии |
| [Starns Better Cheat Menu](https://steamcommunity.com/sharedfiles/filedetails/?id=3440339883) | 1.02 | Оставлен; подтверждения полной совместимости с 9.0 не получено |
| [Terran Tessak Corvette](https://steamcommunity.com/sharedfiles/filedetails/?id=3424955901) | 1.06 | Заявлена 9.0; оставлен |
| [Unassigned Plus](https://steamcommunity.com/sharedfiles/filedetails/?id=3715487702) | raw 80002 | Пакет требует X4 ≥ 900 и заявляет 9.0; оставлен |
| [Logistics Optimization](https://steamcommunity.com/sharedfiles/filedetails/?id=3496466928) | 1.08 | Оставлен; пакет от 10.09.2026, полная проверка на 9.0 нужна |
| [[8.X] Ship Variation Expansion](https://steamcommunity.com/sharedfiles/filedetails/?id=2229061492) | 3.00 | Автор ограничил поддержку 8.x; перенесён из extensions в резервную папку |
| [Print Extension List](https://steamcommunity.com/sharedfiles/filedetails/?id=3770927339) | заглушка → 1.02 | Восстановлены отсутствовавшие файлы; заявлена X4 ≥ 8.00 |
| [UI Extensions and HUD](https://steamcommunity.com/sharedfiles/filedetails/?id=3477279743) | raw 9010; в описании 9.0.0.19.1 | Заявлена 9.x; оставлен |
| [X4 Fire and Smoke](https://steamcommunity.com/sharedfiles/filedetails/?id=2055992841) | 1.09 | Оставлен; есть сообщение игрока о работе в 9.0, без гарантии всех эффектов |
| [No Kha'ak Torture](https://steamcommunity.com/sharedfiles/filedetails/?id=3517982532) | 1.02 | Оставлен; полная работа изменений в 9.0 не подтверждена |
| [No Pirate Torture](https://steamcommunity.com/sharedfiles/filedetails/?id=3547746177) | 1.00 | Оставлен; оснований для автоматического удаления не найдено |

Официальные DLC: Split Vendetta, Cradle of Humanity, Tides of Avarice, Kingdom End, Timelines, Hyperion Pack, Envoy Pack. Все имеют version=900 в локальных content.xml.

### Дефект Sector Explorer

В установленном extensions/fs_exp/ext_01.dat, файл aiscripts/sectorexplorer.xml, строка 86, используется blacklisttype.travel.

В libraries/common.xsd из каталога 08.cat установленной игры перечислены только:

- blacklisttype.sectortravel
- blacklisttype.sectoractivity
- blacklisttype.objectactivity

Таким образом, это конкретная ошибка обращения к API игры, а не предположение по дате мода. Она затрагивает проверку запретных секторов. [Сообщения об этой ошибке](https://steamcommunity.com/sharedfiles/filedetails/comments/2074838459) содержат тот же путь, строку и выражение. Скрипт мода не исправлялся; он выключен в профиле. При возвращении к старому прохождению нужно проверить приказы кораблей, которым назначено его поведение.

## Что делают предложенные компоненты

| Компонент | Назначение | Нужен ли для панели |
|---|---|---|
| SirNukes Mod Support APIs | Внутриигровые API, включая двусторонние Windows Named Pipes | Уже установлен; подходит как транспорт собственного адаптера |
| X4_Python_Pipe_Server | Отдельная программа Windows, которая запускает Python-модули расширений | Нужен для штатной Windows-схемы x4-simpit; сам состояние корабля не извлекает |
| x4-simpit | MD/Lua-экспорт телеметрии в JSON, похожий на Elite Dangerous | Готовая основа для эксперимента; на X4 9 не проверена |
| Native Hotkey API, Nexus 2181 | Позволяет модам регистрировать до 48 игровых действий и назначать им клавиши | Не нужен для обычных команд X4; полезен для дополнительных действий |
| Simple Hotkeys, Nexus 2183 | Набор действий поверх Native Hotkey API | Ставится вместе с 2181, если нужны его команды; не заменяет API |
| Собственный Python-сервис | MIDI-ввод, команды игре, индикаторы Launchpad | Нужен в любом варианте |

Native Hotkey API работает через штатную систему ввода X4, без внешнего Python-процесса для горячих клавиш. Simple Hotkeys добавляет, например, следование за целью, запуск спутников и турелей, увеличение изображения и управление панелью информации карты. MIDI они сами не принимают: преобразование нажатий Launchpad в клавиши остаётся задачей Python. [Native Hotkey API](https://github.com/chemodun/X4-HotKeyAPI), [Simple Hotkeys](https://github.com/chemodun/X4-Simple-Hotkeys).

### Установка дополнительных горячих клавиш

1. Подписаться в Workshop на [Native Hotkey API](https://steamcommunity.com/sharedfiles/filedetails/?id=3750545906).
2. Подписаться на [Simple Hotkeys](https://steamcommunity.com/sharedfiles/filedetails/?id=3751021954).
3. Проверить зависимости Workshop. UI Extensions and HUD, SirNukes и Print Extension List уже есть; последний восстановлен.
4. Запустить игру, включить расширения, загрузить отдельное тестовое сохранение.
5. Открыть Options → Hotkey Management → Hotkey Bindings и назначить свободные клавиши нужным действиям. В главном меню до загрузки игры этого пункта нет.
6. В Python сопоставить MIDI-события с назначенными клавишами. Отправлять команды только при активном окне X4.

У Native Hotkey API номер 8.00.09 не означает ограничение X4 8: автор отдельно описывает поддержку 9.00. Для 9.00 требуется UI Extensions and HUD не ниже 9.0.0.7. Использовать согласованный набор Workshop; исходный content.xml из GitHub может ссылаться на идентификатор Nexus-версии UI Extensions, отличающийся от установленной Steam-версии.

## Эксперимент с x4-simpit

Последний коммит main — 683f975f1e0c14f47a64d9165334a4013ad121a3 от 13.09.2025, версия мода 0.3. Подтверждения работы на 9.00 в просмотренном README нет. Проверка кода показывает:

- Основная функция — экспорт состояния. Обработчик обратных сообщений только пишет их в лог.
- В Windows pipe_external.txt читает игровой канал x4simpit и пересылает данные во внешний канал x4simpit_out.
- Ряд полей условен: например, топливо и распределение энергии не являются настоящей телеметрией X4. Поле Flags нужно проверять отдельно: некоторые битовые значения складываются в нескольких независимых условиях, поэтому их нельзя без проверки считать точной копией Elite Dangerous Status.
- В коде есть нерешённые замечания о соединении и объединении сообщений.

Для подключения Python-панели правильный выход в штатной Windows-схеме: \\.\pipe\x4simpit_out. Канал \\.\pipe\x4simpit занят связью игры с посредником. [Windows-посредник](https://github.com/bekopharm/x4-simpit/blob/main/pipe_external.txt), [обработчик сообщений](https://github.com/bekopharm/x4-simpit/blob/main/lua/Simulated_Cockpit.lua), [формирование Status](https://github.com/bekopharm/x4-simpit/blob/main/lua/modules/Status.lua).

### Порядок установки для пробного запуска

1. Сохранить текущий профиль расширений. Использовать отдельную новую игру для тестов.
2. Скачать [x4-simpit](https://github.com/bekopharm/x4-simpit) и распаковать так, чтобы файл находился по пути G:\SteamLibrary\steamapps\common\X4 Foundations\extensions\x4-simpit\content.xml. Папка должна называться именно x4-simpit: это имя используется в коде.
3. Оставить установленный SirNukes Mod Support APIs 1.95. Linux-ветка bekopharm на Windows не нужна.
4. На [странице релизов SirNukes](https://github.com/bvbohnen/x4-projects/releases) скачать sn_x4_python_pipe_server_exe_v1.4.3.zip и распаковать в отдельную папку, например C:\Проекты\cockpit\tools\x4-pipe-server. Это внешний процесс, не игровое расширение. Название общего GitHub release v1.12 не является версией всех вложенных ZIP.
5. Запустить сервер один раз для создания permissions.json, закрыть его, добавить разрешение x4-simpit, сохранив существующие настройки, и запустить снова.

Пример корректного содержимого permissions.json:

~~~json
{
  "ws_2042901274": true,
  "x4-simpit": true
}
~~~

В README x4-simpit использовано True с заглавной буквы, но это невалидный JSON. Нужны именно true/false.

6. В X4 включить Mod Support APIs и Simulated Cockpit Telemetry. Для Named Pipes требуется Protected UI Mode = OFF. После изменения перезапустить игру. Это требование именно канала Named Pipes, даже если описание UI Extensions рекомендует защищённый режим для обычной работы меню.
7. Запустить внешний сервер, загрузить тестовую игру, подключить будущий Python-клиент к \\.\pipe\x4simpit_out и проверить появление событий Status.
8. Проверить щит, корпус, полётный режим и смену корабля вручную. При отсутствии данных исследовать лог, а не считать успешное появление папки доказательством работы телеметрии.

Для диагностического запуска можно добавить параметры -debug all -logfile cockpit-debug.log. Лог искать в C:\Users\besch\OneDrive\Документы\Egosoft\X4\76426932. Не включать подробное логирование постоянно без необходимости.

Вместо EXE можно использовать sn_x4_python_pipe_server_py_v1.4.3.zip. Для исходного сервера требуются pywin32; для штатного компонента горячих клавиш SirNukes — также pynput. EXE содержит свои зависимости. [Документация SirNukes](https://github.com/bvbohnen/x4-projects/blob/master/extensions/sn_mod_support_apis/Readme.md), [сервер и параметр --permissions-path](https://github.com/bvbohnen/x4-projects/blob/master/X4_Python_Pipe_Server/Main.py).

Эти новые компоненты пока не установлены: выполнена только очистка существующего набора и восстановление Print Extension List.

## Предпочтительная собственная реализация

Схема первого полезного прототипа:

~~~text
Launchpad S → MIDI → Python → клавиши → X4
Launchpad S ← MIDI-индикация ← Python ← Named Pipe ← небольшой MD/Lua-мод
HOTAS → X4
~~~

Для первого теста:

- Команды: карта, автопилот, travel mode, flight assist — через существующие назначения X4.
- Индикация: щит и корпус; подтверждённое состояние travel mode и flight assist; наличие соединения.
- Индикаторы обновляются из игры, в том числе после команд с клавиатуры или HOTAS. Сам факт нажатия кнопки не подтверждает изменение игрового режима.
- При потере телеметрии показывать отсутствие связи; при закрытии сервиса освобождать MIDI-порты и отпускать удержанные клавиши.

Собственный MD/Lua-мод экспортирует только нужные поля с понятными единицами и периодом обновления, например 5 раз в секунду. В Python остаются сопоставление команд, индикация и будущая тактильная отдача. x4-simpit можно использовать как справочник игровых вызовов, проверяя их на 9.00.

Если Python-сервис сам создаёт Windows Named Pipe через pywin32, отдельный X4_Python_Pipe_Server не обязателен: Named Pipes API поддерживает внешний сервер любого приложения, а штатный Python-host — дополнительный компонент для автоматического запуска модулей. Нужно реализовать ожидаемый протокол соединения и восстановления. [Назначение и интерфейс Named Pipes API](https://github.com/bvbohnen/x4-projects/blob/master/extensions/sn_mod_support_apis/documentation/Named_Pipes_API.md).

Прямые команды Python → MD/Lua можно добавить следующим этапом: с ограниченным набором команд и ответами об успехе или отказе. Готового универсального RPC для всех действий X4 перечисленные моды не предоставляют.

Для MIDI подойдёт mido с python-rtmidi, для Windows pipes — pywin32. [Документация Mido/RtMidi](https://mido.readthedocs.io/en/stable/backends/rtmidi.html). Native Hotkey API и Simple Hotkeys в этой схеме необязательны; они расширяют набор доступных клавиатурных действий.

## Особенность Launchpad S

В OVERVIEW.md подсветка названа RGB, но Launchpad S использует красный и зелёный каналы с их сочетаниями. Для теста удобно выбрать красный, зелёный и янтарный. Синий и произвольный RGB недоступны.

Матрица отправляет MIDI Note On при нажатии и сообщение с velocity=0 при отпускании. Для подсветки базовые значения velocity: 15 — красный, 60 — зелёный, 63 — янтарный. Верхние круглые кнопки используют Control Change; их нужно обрабатывать отдельно. Модель S не требует MIDI-протокола современных Launchpad X/Mini MK3.

Источник: [Novation Launchpad S Programmer’s Reference Manual](https://fael-downloads-prod.focusrite.com/customer/prod/s3fs-public/novation/downloads/10753/launchpad-s-prm.pdf).

## Проверки перед игровым тестом

Файловая проверка подтверждает:

- версия исполняемого файла X4 — 9.0.0.0, version.dat — 900;
- старый SVE отсутствует в extensions и сохранён в резервной папке;
- Sector Explorer и Enhanced Kill Credit выключены;
- Print Extension List содержит рабочую структуру версии 1.02, без атрибута error;
- восстановленные файлы совпадают по SHA-256 с подготовленной копией источников;
- остальные записи профиля расширений сохранены.

Игровую совместимость всех 22 включённых модов, фактическую телеметрию и реакцию Launchpad нужно подтвердить отдельным запуском. Восстановленный Print Extension List взят из [репозитория автора](https://github.com/chemodun/X4-PrintExtensionList/tree/cad09ad7d8e18623d6e6e73de00859cc11d2b6ee).

