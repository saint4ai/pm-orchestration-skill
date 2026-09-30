# Скиллы Claude Code: PM с исполнителями и UX/UI-ревью

Два скилла, которые работают вместе.

| Скилл | Что делает |
|---|---|
| `skills/pm-orchestration` | одна сессия Claude — руководитель проекта (PM): ставит задачи поэтапно, принимает работу своим прогоном, выкатывает принятое. Код пишут исполнители — соседние сессии Claude, дешёвая модель через файл задач (GLM, Kilo, Codex), облачный агент через GitHub |
| `skills/ux-ui-review` | ревью и дизайн интерфейса на фундаменте NN/g, WCAG 2.2, Laws of UX, Material 3, Apple HIG: 7 измерений, находка засчитывается при ≥2 независимых подтверждениях. PM зовёт его при приёмке любого среза с интерфейсом |

## Установка

```bash
git clone https://github.com/saint4ai/pm-orchestration-skill ~/pm-orchestration-skill
mkdir -p ~/.claude/skills
ln -s ~/pm-orchestration-skill/skills/pm-orchestration ~/.claude/skills/pm-orchestration
ln -s ~/pm-orchestration-skill/skills/ux-ui-review ~/.claude/skills/ux-ui-review
```

Ссылки, а не копии: `git pull` в `~/pm-orchestration-skill` обновляет оба скилла.
Для одного проекта — те же ссылки в `<проект>/.claude/skills/`.

## Запуск

Скажи сессии: «Ты PM проекта. Исполнители: сессия X, GLM через `.kilo/tasks/glm-task.md`.
Прочитай скилл pm-orchestration и заведи, чего не хватает, по `references/setup.md`».

## Состав

| Файл | Что внутри |
|---|---|
| `pm-orchestration/SKILL.md` | роли, каналы, правила параллельной работы, цикл PM, что решает владелец |
| `pm-orchestration/references/phased-tasks.md` | фазы → срезы → шаги, порядок, кому какую задачу, нумерация N / Nb, партии выката, три скептика, пульт |
| `pm-orchestration/references/task-spec-template.md` | шаблон задачи и возврата на доработку |
| `pm-orchestration/references/acceptance.md` | приёмка: гейт на чистой копии, порча, фронты диффа, интерфейс |
| `pm-orchestration/references/channels.md` | как писать соседям, файлу задач, облачному агенту, владельцу |
| `pm-orchestration/references/executor-prompt-template.md` | промпт облачному исполнителю и строка для исполнителя-файла |
| `pm-orchestration/references/lessons.md` | реальные грабли и правила из них |
| `pm-orchestration/references/setup.md` | что завести в проекте до первой партии |
| `ux-ui-review/SKILL.md` | 12 принципов, 7 измерений ревью, что отсекать из дизайн-скиллов |
| `ux-ui-review/references/framework.md` | рубрика и метод ревью |
| `ux-ui-review/references/sources.md` | источники истины и курация репозиториев |
| `ux-ui-review/references/project-rules.md` | правила из приёмок: макет, все языки, текст как функция, проверка в браузере |
