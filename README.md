# Style.AI — Сайт и юридические документы

Лендинг для приложения Style.AI с юридическими документами, согласованный по стилю с мобильным приложением.

## Файлы

```
styleai_v2/
├── index.html          ← главная (EN)
├── index-ru.html       ← главная (RU)
├── privacy.html        ← Privacy Policy (EN)
├── privacy-ru.html     ← Политика конфиденциальности (RU)
├── terms.html          ← Terms of Service (EN)
├── terms-ru.html       ← Условия использования (RU)
├── cookies.html        ← Cookie Policy (EN)
├── cookies-ru.html     ← Cookie-политика (RU)
├── styles.css          ← стили главной
└── legal.css           ← стили юридических страниц
```

## Дизайн

Дизайн полностью согласован со стилем мобильного приложения Style.AI:
- Шрифт: Plus Jakarta Sans
- Акцентный цвет: коралл-оранжевый градиент `#ff6b47 → #ff8a5c`
- Чистый белый фон с мягкими тенями
- Pill-кнопки с градиентом и закруглённые карточки 20-24px
- Mockup телефона в hero-секции

## Деплой через GitHub + Cloudflare Pages

### Шаг 1: GitHub репозиторий (5 минут)

1. Иди на [github.com](https://github.com), создай аккаунт если нет
2. Жми **New repository**
3. Name: `trystyleai-web`, Public, без README/gitignore
4. На странице нового репо — **uploading an existing file**
5. Перетащи все 10 файлов в окно браузера
6. Commit message: `Initial commit — Style.AI landing and legal docs`
7. Жми **Commit changes**

### Шаг 2: Cloudflare Pages (5 минут)

1. В Cloudflare Dashboard → **Workers & Pages**
2. Жми **Get started** возле "Looking to deploy Pages?"
3. Выбери **Connect to Git**
4. Авторизуй GitHub, выбери `trystyleai-web`
5. Build settings:
   - Framework preset: **None**
   - Build command: *пусто*
   - Build output directory: `/`
6. **Save and Deploy** — через 30 сек URL `trystyleai-web.pages.dev`

### Шаг 3: Привязка домена (2 минуты)

1. В проекте Pages → **Custom domains**
2. **Set up a custom domain** → `trystyleai.app`
3. Cloudflare настроит DNS автоматически
4. Через 1-2 минуты сайт работает на `https://trystyleai.app`

### Шаг 4: Email forwarding (5 минут)

1. Cloudflare Dashboard → выбери домен `trystyleai.app`
2. Слева → **Email** → **Email Routing**
3. Включи Email Routing
4. Создай адреса:
   - `support@trystyleai.app` → твой Gmail
   - `privacy@trystyleai.app` → твой Gmail
   - `legal@trystyleai.app` → твой Gmail
5. Подтверди свой Gmail (придёт письмо)

## После публикации

1. **Обнови ссылку в Termly** — там сейчас стоит `styleai.app/cookies.html`, замени на `https://trystyleai.app/cookies.html`
2. **Проверь App Store Connect** — впиши:
   - Privacy Policy URL: `https://trystyleai.app/privacy.html`
   - Support URL: `https://trystyleai.app/`
   - Marketing URL: `https://trystyleai.app/`

## Что нужно сделать перед App Review

- [x] Опубликован сайт на trystyleai.app
- [x] Privacy Policy URL работает и открывается
- [x] Email-адреса работают (support@, privacy@, legal@)
- [ ] App Privacy questionnaire в App Store Connect заполнен и совпадает с Privacy Policy
- [ ] Info.plist содержит usage descriptions:
  - `NSCameraUsageDescription` — для фото в полный рост
  - `NSPhotoLibraryUsageDescription` — для загрузки готовых фото
- [ ] In-app есть способ удалить аккаунт
- [ ] Sign in with Apple реализован (требование Apple)
