# ترتيل | Tarteel

A small Arabic website for Quran circles, Islamic lectures and summer Quran memorization centers. It's built with plain HTML and CSS only, no JavaScript and no build step.

## Pages

| File | What it is |
|---|---|
| `indexxx.html` | Home page |
| `programs.html` | The four summer centers, with a registration form inside each card |
| `lectures.html` | Upcoming lectures with date, time and a map link |
| `about-us.html` | Who we are: mission, vision, schedule |
| `contact-us.html` | Contact form, WhatsApp and email |

## Stylesheets

- `indexxx.css` is the base for every page: colors, fonts, header, buttons, cards and footer.
- `programs.css` is only for the programs page.
- `pages.css` is shared by the about, contact and lectures pages.

Every page loads `indexxx.css` first, then its own file if it has one.

## Running it

Put everything in one folder and open `indexxx.html` in a browser. The contact page also expects `whatsapp-image.png` and `email-image.png` in the same folder.

## Good to know

- **The forms don't send anything.** The programs form only changes how the card looks, and the contact form has no backend. To actually receive messages you'll need a form service or a small server.
- **Use a recent browser.** The nav hover, form states and scroll animations use newer CSS (`:has()`, anchor positioning, scroll timelines). Chrome or Edge 125+ shows everything. Other modern browsers work, with a simpler nav hover.
- **Sizes scale with the screen.** Everything is in `rem`, and the root font size follows the window width. To make the whole site bigger or smaller, change the `html { font-size }` line in `indexxx.css`.
- Fonts (Tajawal and Amiri Quran) come from Google Fonts, so you need an internet connection.

## Colors

| | |
|---|---|
| Primary green | `#075342` |
| Dark green | `#184443` |
| Orange | `#D47233` |
| Soft peach | `#F3D9CC` |
| Background | `#F8F5EF` |
