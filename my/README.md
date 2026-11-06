# Моя версия cinecode (graddata/cinecode2)

Форк [sarpstar/cinecode](https://github.com/sarpstar/cinecode), снятый с версии `67f9807` (2026-11-03). Всё моё лежит в папке `my/`, файлы оригинала не менялись, поэтому обновления из оригинала вливаются без конфликтов.

## Что в `my/`

| Папка | Что это |
|---|---|
| `formats/hud-explainer/` | мой формат: тёмный HUD, моноширинный шрифт, терминал в начале, ритм на 120 BPM, синтезированный эмбиент, зелёная полоса с тезисом в конце |
| `film-k8s-self-healing/` | исходник ролика «Desired State» про самовосстановление Kubernetes: `film.html` пересобирает его целиком, `STATE.md` хранит карточку и решения |

## Remotes на этой машине

- `origin` = `https://github.com/graddata/cinecode2.git` (моя копия, сюда пушим)
- `upstream` = `https://github.com/sarpstar/cinecode.git` (оригинал, только чтение, push отключён)

## Забрать обновления из оригинала

```bash
cd ~/.claude/skills/cinecode
git fetch upstream
git log --oneline main..upstream/main
git merge upstream/main
git push origin main
```

После этого открыть новый чат Claude Code, чтобы загрузилась новая версия.

Команда скилла «обнови cinecode» делает `git pull`, то есть тянет из моего форка (`origin`), а не из оригинала. Чтобы получить новое от автора, нужен `merge upstream/main` выше.

Старый фильм подтянуть к новым инструментам (его собственные файлы не меняются):

```bash
py -3 ~/.claude/skills/cinecode/scripts/init_film.py ~/Documents/Films/k8s-self-healing --update-tools
```

## Откатиться

```bash
git -C ~/.claude/skills/cinecode log --oneline -5
git -C ~/.claude/skills/cinecode reset --hard <коммит>
```

Последняя проверенная версия оригинала: `67f9807`.

## Поставить на другой машине

```bash
git clone https://github.com/graddata/cinecode2.git ~/.claude/skills/cinecode
git -C ~/.claude/skills/cinecode remote add upstream https://github.com/sarpstar/cinecode.git
mkdir -p ~/.cinecode/formats && cp -r ~/.claude/skills/cinecode/my/formats/hud-explainer ~/.cinecode/formats/
```

Нужны Node 22+, Python 3.9+, ffmpeg, Chrome. Папка скилла должна называться `cinecode`. Хуки скилла (guard) начинают работать с новой сессии.

## Новый ролик в моём формате

В Claude Code: «новый фильм в формате hud-explainer про <тема>». Формат переносит язык (вид, палитру, шрифт, камеру, ритм, хук, концовку, звук), а сцены, тексты и музыка каждый раз новые.

Пересобрать сам ролик K8s: скопировать `my/film-k8s-self-healing/` в папку фильма, созданную `init_film.py <name> --quick`, и запустить `py -3 tools/make.py final`.
