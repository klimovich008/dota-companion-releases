# Dota Lobby Companion

**[English](#english)** | **[Русский](#русский)**

---

## English

A Windows app for Dota 2: player cards during the draft, notes, local match history. Patches the Minify mod, reads `console.log`, lives in the system tray.

Download: [latest release](https://github.com/klimovich008/dota-companion-releases/releases/latest) → `DotaCompanion-win-x64.zip`.

The full path from zero to working player cards. Every step is verified inside the app: the **DotaCompanion** window → **Setup checklist** block shows a green check for each completed step.

### Step 1. Dota 2 and Workshop Tools

1. Install **Dota 2** in Steam (if you haven't already).
2. Install **Dota 2 Workshop Tools** (Minify needs them to build the patch):
   - Steam → Library → right-click **Dota 2** → **Properties** → **DLC** tab → tick **Dota 2 Workshop Tools**.
   - Wait for the download to finish (~a few GB).

### Step 2. Dota launch options

1. Steam → Library → right-click **Dota 2** → **Properties** → **General** → the **Launch Options** field.
2. Append (keeping whatever is already there):
   ```
   -console -condebug
   ```
   - `-condebug` — makes Dota write `console.log`, which the app reads its data from. **Nothing works without it.**
   - `-console` — enables the in-game console (useful, but optional).

### Step 3. Install Minify

1. Download **dota2-minify**: https://github.com/Egezenn/dota2-minify (Releases → installer or portable zip).
2. Install / unpack it and run `Minify.exe` once.

### Step 4. Install this app

1. Download `DotaCompanion-win-x64.zip` from the [latest release](https://github.com/klimovich008/dota-companion-releases/releases/latest).
2. Unpack it into its own folder (e.g. `C:\Games\DotaCompanion\`).
3. Run `DotaCompanion.exe`.
   - Windows SmartScreen will warn about an unknown publisher → **More info** → **Run anyway** (the exe is unsigned, that's expected).
4. A control window opens; the app lives in the tray (closing the window minimizes to tray, exit via right-click on the tray icon → Exit).

### Step 5. Hook the mod into Minify

1. In the app window find the **Minify** row — the path is usually detected automatically.
   - If it says "not found" — paste the path to your Minify folder (the one containing the `mods` folder) or pick it with the `...` button.
2. Press **Patch (enable)** — the `Lobby Context Probe` mod is copied into Minify.

### Step 6. Enable the mod and patch Dota in Minify

1. Open **Minify** (with Dota closed).
2. In the mod list tick **Lobby Context Probe**.
3. Press the patch button in Minify and wait for the build to finish.
4. Launch Dota **with the button in Minify** (it adds `-language minify` itself).
   - Or add `-language minify` to your Steam launch options and start Dota as usual.

### Step 7. Verify

Open the DotaCompanion window → **Setup checklist**. Everything should be green:

| Item | Meaning |
|---|---|
| Dota 2 installation found | Dota located on disk |
| Workshop Tools DLC installed | the DLC from step 1 is installed |
| Minify found | the Minify path is known |
| Probe mod copied into Minify | step 5 done |
| Probe mod enabled inside Minify | the checkbox from step 6 is ticked |
| Minify patch built into Dota | the patch was built in Minify |
| Dota launched with -condebug | step 2 done, Dota restarted |
| Dota launched with Minify patch | Dota running with `-language minify` |
| console.log is being written | the log is actually being written |
| Probe data captured | data is flowing — everything works |

Then just play: player cards appear **from the draft stage onward** (there is no data in the lobby before the match starts — that's how Dota works).

### Common problems

- **"Dota log: NOT WRITING"** — Dota was started without `-condebug` (step 2) or wasn't restarted after adding it.
- **Checklist is green but the cards are empty** — you are in the lobby/menu; data only appears in the draft and during the match.
- **"Already running" on launch** — the app is already in the tray, no need to start it twice.
- **Everything broke after a Dota update** — a game update wipes the Minify patch: open Minify and patch again (step 6).
- **Port busy / dev server** — don't run the exe and `npm start` from the repo at the same time: they share port 17375.

---

## Русский

Windows-приложение для Dota 2: карточки игроков в драфте, заметки, локальная история матчей. Патчит Minify-мод, читает `console.log`, живёт в трее.

Скачать: [последний релиз](https://github.com/klimovich008/dota-companion-releases/releases/latest) → `DotaCompanion-win-x64.zip`.

Полный путь с нуля до работающих карточек игроков. Каждый шаг проверяется в приложении: окно **DotaCompanion** → блок **Setup checklist** показывает зелёную галку за каждый выполненный шаг.

### Шаг 1. Dota 2 и Workshop Tools

1. Установите **Dota 2** в Steam (если ещё нет).
2. Установите **Dota 2 Workshop Tools** (нужны Minify для сборки патча):
   - Steam → Библиотека → правый клик по **Dota 2** → **Свойства** → вкладка **DLC** → поставьте галку **Dota 2 Workshop Tools**.
   - Дождитесь докачки (~несколько ГБ).

### Шаг 2. Параметры запуска Dota

1. Steam → Библиотека → правый клик по **Dota 2** → **Свойства** → **Общие** → поле **Параметры запуска**.
2. Допишите (к тому, что уже есть):
   ```
   -console -condebug
   ```
   - `-condebug` — заставляет Dota писать `console.log`, из которого приложение читает данные. **Без него ничего работать не будет.**
   - `-console` — включает игровую консоль (полезно, но необязательно).

### Шаг 3. Установить Minify

1. Скачайте **dota2-minify**: https://github.com/Egezenn/dota2-minify (Releases → установщик или portable-zip).
2. Установите / распакуйте и запустите `Minify.exe` один раз.

### Шаг 4. Установить наше приложение

1. Скачайте `DotaCompanion-win-x64.zip` из [последнего релиза](https://github.com/klimovich008/dota-companion-releases/releases/latest).
2. Распакуйте в отдельную папку (например `C:\Games\DotaCompanion\`).
3. Запустите `DotaCompanion.exe`.
   - Windows SmartScreen предупредит о неизвестном издателе → **Подробнее** → **Выполнить в любом случае** (exe не подписан, это нормально).
4. Откроется окно управления; приложение живёт в трее (закрытие окна сворачивает в трей, выход — через правый клик по иконке → Exit).

### Шаг 5. Подключить мод к Minify

1. В окне приложения найдите строку **Minify** — путь обычно определяется сам.
   - Если написано «not found» — вставьте путь к папке Minify (та, в которой папка `mods`) или выберите её кнопкой `...`.
2. Нажмите **Patch (enable)** — мод `Lobby Context Probe` скопируется в Minify.

### Шаг 6. Включить мод и пропатчить Dota в Minify

1. Откройте **Minify** (Dota при этом закройте).
2. В списке модов поставьте галку **Lobby Context Probe**.
3. Нажмите кнопку патча в Minify и дождитесь окончания сборки.
4. Запустите Dota **кнопкой из Minify** (он добавит `-language minify` сам).
   - Либо добавьте `-language minify` в параметры запуска Steam и запускайте Dota как обычно.

### Шаг 7. Проверка

Откройте окно DotaCompanion → **Setup checklist**. Всё должно быть зелёным:

| Пункт | Что значит |
|---|---|
| Dota 2 installation found | Dota найдена на диске |
| Workshop Tools DLC installed | DLC из шага 1 установлен |
| Minify found | путь к Minify известен |
| Probe mod copied into Minify | шаг 5 выполнен |
| Probe mod enabled inside Minify | галка из шага 6 стоит |
| Minify patch built into Dota | патч в Minify собран |
| Dota launched with -condebug | шаг 2 выполнен, Dota перезапущена |
| Dota launched with Minify patch | Dota запущена с `-language minify` |
| console.log is being written | лог реально пишется |
| Probe data captured | данные пошли — всё работает |

Дальше просто играйте: карточки игроков появляются **со стадии драфта** (в лобби до начала матча данных нет — так устроена Dota).

### Частые проблемы

- **«Dota log: NOT WRITING»** — Dota запущена без `-condebug` (шаг 2) или не перезапущена после его добавления.
- **Чеклист зелёный, но карточки пустые** — вы в лобби/меню; данные появляются только в драфте и в матче.
- **«Already running» при запуске** — приложение уже в трее, второй раз запускать не нужно.
- **После обновления Dota всё пропало** — обновление игры сбрасывает патч Minify: откройте Minify и пропатчите заново (шаг 6).
- **Порт занят / dev-сервер** — не запускайте одновременно exe и `npm start` из репозитория: они делят порт 17375.
