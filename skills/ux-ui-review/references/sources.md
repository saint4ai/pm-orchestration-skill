# Источники истины + курированные репозитории (карта)

> Все URL ниже верифицированы (WebFetch). Гейт 2 процесса: по контексту продукта выбери релевантные, отсеки остальное.

## Фундамент — «север» (консультировать ВСЕГДА)

**Юзабилити и когнитивка**
- Nielsen Norman — 10 эвристик: https://www.nngroup.com/articles/ten-usability-heuristics/
- Laws of UX (Jakob, Hick, Miller, Fitts, Doherty, Aesthetic-Usability, Goal-Gradient): https://lawsofux.com/
- Refactoring UI (иерархия, спейсинг, типографика, ограничение выборов): https://www.refactoringui.com/
- GOV.UK Design Principles («начни с нужд», «делай меньше», «просто», инклюзивно): https://www.gov.uk/guidance/government-design-principles

**Стандарты a11y и дизайн-систем**
- WCAG 2.2 AA (юр-стандарт до ~2028): https://www.w3.org/TR/WCAG22/
- Material Design 3 (токены, цвет-роли, контраст, адаптив): https://m3.material.io/
- Apple HIG (Clarity / Deference / Depth, идиомы платформы): https://developer.apple.com/design/human-interface-guidelines/
- W3C WAI-ARIA Authoring Practices (клавиатура/ARIA-паттерны для dialog/menu/tabs/combobox): https://www.w3.org/WAI/ARIA/apg/

**EdTech / обучение** (если продукт — обучение): NN/g e-learning — онбординг контекстный (не «push»-туториалы) https://www.nngroup.com/articles/onboarding-tutorials/ · видео+транскрипт/главы ≤10 мин https://www.nngroup.com/articles/instructional-video-guidelines/ · ошибки «причина+как исправить» https://www.nngroup.com/articles/error-message-guidelines/ · видимый прогресс · соц-связь ↓drop-off · plain-language с глоссингом жаргона.

## Курированные репозитории (инструменты — фильтровать по контексту)

### ✅ Ядро (брать почти всегда для веб-продукта)
| Репо | URL | Когда консультировать |
|---|---|---|
| **ux-patterns-for-developers** | github.com/thedaviddias/ux-patterns-for-developers (+ uxpatterns.dev) | ~92 паттерна с a11y/testing/«best for ÷ avoid»: формы, modal-vs-page, empty/loading/error, навигация, cognitive-load. |
| **18F/ux-guide + usability-test-guide** | github.com/18F/ux-guide · github.com/18F/methods | IA, plain-language, **сценарий теста на новичка** («что это за сайт?»). |
| **WCAG 2.2 + WAI-ARIA APG + radix-ui/primitives + shadcn-ui/ui** | w3.org/TR/WCAG22 · w3.org/WAI/ARIA/apg · github.com/radix-ui/primitives · github.com/shadcn-ui/ui | Канон a11y + доступные веб-компоненты (focus/ARIA/клавиатура). Эталон сборки. |
| **frontend-design** (Anthropic) | github.com/anthropics/skills | Планка «distinctive, не generic-AI». |
| **ui-ux-pro-max** — ТОЛЬКО UX-чек-листы | github.com/nextlevelbuilder/ui-ux-pro-max-skill | 99 UX-гайдлайнов (a11y/навигация/формы/layout). НЕ style/palette-движок. |
| **ckm:design-system + ckm:ui-styling** | (claudekit, тот же репо) | Токены primitive→semantic→component + доступный styling. |

### 🟡 По домену
| Репо | URL | Когда |
|---|---|---|
| **adrianhajdin/saas-app** (LMS) | github.com/adrianhajdin/saas-app | Эталон LMS-IA (каталог→курс→модуль→урок, прогресс, resume, онбординг) — если продукт обучающий. |
| **vercel react-best-practices** | github.com/vercel-labs/agent-skills | Перф React/Next (LCP/TTI/гидрация) — на этап РЕАЛЬНОЙ сборки фронта, не для статичного мокапа. |
| **shadcn-examples** | github.com/shadcn-examples/shadcn-examples | Примеры production-компонентов — справочно. |
| **react-accessibility / react-a11y** | github.com/vipulpathak113/react-accessibility · github.com/Lissone/react-a11y | Дружелюбные WCAG-интро/код — вторичны к самому WCAG 2.2. |

### ❌ Отсекать (по контексту learner-facing/контентный веб)
| Что | Почему |
|---|---|
| **style/palette-движок ui-ux-pro-max** (`--design-system` → claymorphism/Baloo) + мобайл-нативные правила (haptics/safe-area/gestures) | Детско-игровой + iOS/Android-идиомы. Бренд-код и веб — выше. |
| **satnaing/shadcn-admin** | Admin-SaaS-плотность — админ-facing (может пригодиться для будущей АДМИНКИ, не для учащегося). |
| **ixartz/SaaS-Boilerplate** | B2B-SaaS-инфра (мульти-тенант/биллинг/орги), нет урок-логики. |
| **ckm:design / ckm:slides / ckm:banner-design** | Лого/CIP/баннеры/презы — маркетинг-артефакты, не UX платформы. |
| **brand-guidelines (Anthropic) · theme-factory · ckm:brand** | Чужой бренд / пресет-темы / бренд-голос — у проекта свой бренд-код. |

## Фильтр контекста (как решать «брать / отсекать»)
**Берём**, если ресурс повышает ясность / IA / a11y / learner-flow для ТИПА нашего продукта. **Отсекаем**, если он: только нативный-мобайл (а у нас веб), admin-SaaS-плотность (а мы learner/контент-facing), маркетинг-конверсия (а это не лендинг), декоративный «вау» без юзабилити, или предполагает высокую техграмотность юзера. Контекст всегда уточняй по конкретному проекту.
