# Матриця відповідності ЛР №4
Джерело: заочна методичка 2026, с. 24–30. Максимум 100. Оцінку не виставлено.
| Завдання | Максимум | Стан |
|---|---:|---|
| 1. Копія проєкту | 10 | Створено власний репозиторій, код завантажено |
| 2. main.html | 55 | Усі 11 груп виправлень виконано |
| 3. form.html | 30 | Усі 3 групи виправлень виконано |
| 4. Звіт | 5 | DOCX/PDF, код до/після, результати й висновки |
| Разом | 100 | Це максимум рубрики, не присвоєна оцінка |

| Критерій | Макс. | Вимога | Стан і доказ |
|---|---:|---|---|
| 1.1 | 6 | Власний репозиторій і завантажені зміни | Виконано; докази збережено. https://github.com/ZaGOR-1/hmi-lab04-accessibility; sources/provenance.json; verification/remote.json; report.docx/pdf |
| 1.2 | 4 | Посилання на власний репозиторій у звіті | Виконано; докази збережено. https://github.com/ZaGOR-1/hmi-lab04-accessibility; sources/provenance.json; verification/remote.json; report.docx/pdf |
| 2.1 | 5 | Змістовний title | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.2 | 5 | Британська англійська en-GB | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.3 | 5 | Skip link і переміщення фокусу | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.4 | 5 | Ієрархія заголовків | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.5 | 5 | Орієнтири header, nav, main, footer | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.6 | 5 | Природний порядок Tab | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.7 | 5 | Контраст кольорів | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json; verification/contrast.json |
| 2.8 | 5 | Альтернативні тексти | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.9 | 5 | Семантичні елементи й blockquote | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.10 | 5 | Назви посилань | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 2.11 | 5 | Списки посилань футера | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 3.1 | 10 | Пов’язані мітки полів | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 3.2 | 10 | Обов’язковість із винятками | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 3.3 | 10 | Групування доставки | Виконано; докази збережено. changes.json; before-after.md; verification/after-summary.json; verification/keyboard-checks.json |
| 4.1 | 3 | 14 змін до/після з результатами перевірки | Виконано; докази збережено. report.docx; report.pdf; report-content.md; verification/artifact-checks.json; verification/visual-review.json |
| 4.2 | 2 | Висновки | Виконано; докази збережено. report.docx; report.pdf; report-content.md; verification/artifact-checks.json; verification/visual-review.json |

## Додаткові обов’язкові перевірки
| Перевірка | Фактичний стан |
|---|---|
| Незмінені матеріали ЛР №1–3 | SHA-256 до/після; artifact-checks.json |
| Оригінали, ресурси, початкові коміти | provenance.json; original/; baseline у Git |
| Axe-core до/після | Запущено: main 8 типів / 130 вузлів → 0; form 6 / 23 → 0 |
| HTML-валідатор | Запущено: 45 помилок → 0 повідомлень |
| Tab, Shift+Tab, Enter, Space, стрілки | 17 сценаріїв Playwright; це керування клавіатурою у браузері, не особисте тестування людиною |
| Справжній екранний зчитувач | НЕ ПЕРЕВІРЕНО; needs-human-input.md |
| WAVE / розширення axe DevTools | НЕ ЗАПУСКАЛИСЯ; використано axe-core |
| Повна відповідність WCAG | Не заявляється; непевні axe-результати описано окремо |
| ZIP після розпакування | zip-integrity.json |
