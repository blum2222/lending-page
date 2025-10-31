# Intuition Design System (IDS)

Intuition Design System, IDS – дизайн-система для вёрстки лендингов, онлайн-изданий и любых цифровых продуктов для веба, в основе которых лежат нарративы.

## Quick Start

IDS – набор CSS-классов и JS-компонентов. Это не библиотека, а готовый шаблон вёрстки. Вы не подключаете IDS в проект как зависимость, не расширяете классы, не переопределяете свойства. Вместо этого вы копируете её исходный код и меняете его как захотите.

### For Non-Developers
Простейший способ начать проект – скачать архив репозитория. Вы увидите файл `index.html`, который одновременно является инструкцией и примером вёрстки. Открывайте файлы в редакторе кода и смело делайте из них что-то своё.

### For Developers
Делайте, что хотите. IDS работает в статике, у неё ноль зависимостей и ванильный JS. Если заметите ошибку, сделайте пулреквест.

## Documentation

Полная документация доступна в файле `index.html` или онлайн: [intuition-tech.github.io/ids](https://intuition-tech.github.io/ids)

## How to Preview a Pull Request

### Local Preview
Чтобы протестировать изменения из PR локально:

1. Склонируйте репозиторий:
   ```bash
   git clone https://github.com/intuition-tech/ids.git
   cd ids
   ```

2. Переключитесь на ветку PR:
   ```bash
   git fetch origin
   git checkout <branch-name>
   ```

3. Откройте `layout-sample.html` через live server:
   - Используйте VS Code с расширением Live Server
   - Или любой другой локальный сервер, например: `python -m http.server 8000`
   - Откройте в браузере: `http://localhost:8000/layout-sample.html`

### GitHub Pages Preview
Каждый Pull Request автоматически создаёт превью-деплой:
- В PR появится зелёная ссылка "View deployment"
- Нажмите на неё, чтобы увидеть изменения в действии
- Превью доступно на время, пока PR открыт

## Branch Protection (Recommended)

Для безопасной работы рекомендуется включить защиту основной ветки:

1. Перейдите в Settings → Branches
2. Нажмите "Add rule" для ветки `main`
3. Включите опции:
   - ✅ Require pull request reviews before merging
   - ✅ Require approvals (минимум 1)
   - ✅ Dismiss stale PR approvals when new commits are pushed
   - ✅ Require status checks to pass before merging
   - ✅ Require branches to be up to date before merging
4. Нажмите "Create rule"

## Contributing

1. Сделайте fork репозитория
2. Создайте ветку для ваших изменений: `git checkout -b feature/your-feature`
3. Внесите изменения
4. Откройте Pull Request
5. Дождитесь ревью и слияния

## License

IDS распространяется по лицензии MIT — можно бесплатно использовать и модифицировать, никаких ограничений.

## Support

Претензии не принимаем, подсказать не сможем, службы поддержки нет. Если вам интересно, но не очень понятно, как с этим работать – велкам на курс [«Как дизайнить кодом»](https://intuition.team/ru/how-to-design-with-code).