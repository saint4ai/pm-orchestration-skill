# pm-orchestration — скилл для Claude Code

Одна сессия Claude работает руководителем проекта (PM): ставит задачи, принимает работу своим
прогоном тестов, выкатывает принятое. Код пишут исполнители — соседние сессии Claude, дешёвая
модель через файл задач (GLM, Kilo, Codex) и облачный агент через GitHub.

## Установка

```bash
git clone <этот репозиторий> ~/.claude/skills/pm-orchestration
```

Или в проект: `<проект>/.claude/skills/pm-orchestration`. Claude подхватит скилл сам; вызвать
явно — `/pm-orchestration`.

## Запуск

Скажи сессии: «Ты PM проекта. Исполнители: сессия X, GLM через `.kilo/tasks/glm-task.md`.
Прочитай скилл pm-orchestration и заведи, чего не хватает, по `references/setup.md`».

## Состав

| Файл | Что внутри |
|---|---|
| `SKILL.md` | роли, каналы, правила параллельной работы, цикл PM, что решает владелец |
| `references/channels.md` | как писать соседям, файлу задач, облачному агенту, владельцу |
| `references/task-spec-template.md` | шаблон задачи и возврата на доработку |
| `references/acceptance.md` | приёмка: гейт на чистой копии, порча, фронты диффа |
| `references/executor-prompt-template.md` | промпт облачному исполнителю и строка для исполнителя-файла |
| `references/lessons.md` | реальные грабли и правила из них |
| `references/setup.md` | что завести в проекте до первой партии |
