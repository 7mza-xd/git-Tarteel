# Tarteel (ترتيل)

An Arabic, right-to-left educational website for Quran learning and Islamic educational activities, built with **HTML5, Bootstrap 5.3 (RTL) and vanilla JavaScript**.

**COMP3700 – Introduction to Web Computing · Course Project, Part III** · Sultan Qaboos University · Fall 2026

🌐 **Live site:** https://tarteel.site.je

![Tarteel homepage with image gallery and moving welcome banner](docs/screenshots/home.png)

## Highlights

- **Responsive Bootstrap layout** – grid, collapsible navbar, cards, tables, modals, toasts and progress bars on every page.
- **Dynamic tables** – programs and lectures are stored in arrays of objects, drawn into tables by JavaScript, and can be **searched** and **extended** with validated forms.
- **Questionnaire** – nine form controls with custom regular-expression validation, live feedback, a progress bar and a summary modal.
- **Zakat calculator** – nisab, debts and holding-year conditions with instant results.
- **Quran word-ordering game** – rebuild verses from shuffled words.
- **Homepage extras** – moving welcome banner with live date and time, and a photo gallery that changes every 3 seconds.

## Screenshots

| Programs table, search and add | Lectures table |
|---|---|
| ![Programs](docs/screenshots/programs-table.png) | ![Lectures](docs/screenshots/lectures-table.png) |

| Questionnaire validation | Zakat calculator |
|---|---|
| ![Questionnaire](docs/screenshots/questionnaire-validation.png) | ![Calculator](docs/screenshots/zakat-calculator.png) |

![Quran word-ordering game](docs/screenshots/quran-game.png)

## Pages

| Page | What it contains |
|---|---|
| `index.html` | Hero, program highlights, links to the interactive tools, photo gallery, moving banner |
| `programs.html` | Program cards, registration modals, programs table with search and add form |
| `lectures.html` | Lecture cards, lectures table with search and add form |
| `questionnaire.html` | Feedback form with validation, progress bar and summary modal |
| `cal.html` | Zakat calculator |
| `funpage.html` | Quran verse word-ordering game |
| `contact-us.html` | Contact form with validation |
| `about-us.html` | About the platform |
| `admin.html` | Administration overview layout |

## How the main features work

### Dynamic tables (`js/dynamic-tables.js`)
- Two constructors: `TarteelProgram` and `TarteelLecture`.
- Two arrays (`tarteelPrograms`, `tarteelLectures`) start from default data and are saved in the browser's `localStorage`.
- Two display functions, `displayTarteelPrograms()` and `displayTarteelLectures()`, fill the empty tables in the HTML and apply the search text.
- Adding a row validates the form, pushes a new object into the array, saves it and redraws the table immediately; duplicate programs and past lecture dates are rejected.

### Questionnaire (`js/questionnaire.js`)
| Field | Rule |
|---|---|
| Full name | At least two words, each 2+ Arabic/English letters, 5–60 characters |
| Phone | Omani mobile: optional `+968`/`00968`, then 7 or 9, then 7 digits |
| Email | Strict address pattern, no double dots, 2+ letter ending |
| Comments | 10–500 characters containing real letters |

The drop-down, rating and agreement checkbox must also be completed. Fields turn green or red with Bootstrap's `is-valid` / `is-invalid` classes.

### Zakat calculator (`js/cal.js`)
```
nisab      = 85 g gold (or 595 g silver) × price per gram
net wealth = cash + gold/silver savings + trade goods − debts
zakat      = net wealth × 2.5%   only if net wealth ≥ nisab AND one lunar year has passed
```
This is a simplified educational estimate, not a religious ruling.

### Homepage (`js/home.js`)
A banner after the footer scrolls across the bottom with the website name, today's date and a clock refreshed every second. The gallery rotates three images every 3000 ms with a Bootstrap fade.

## Project structure

```
Tarteel_Bootstrap_JS/
├── index.html  programs.html  lectures.html  about-us.html  contact-us.html
├── questionnaire.html  cal.html  funpage.html  admin.html
├── css/
│   └── tarteel-theme.css        Tarteel brand colours on top of Bootstrap
├── js/
│   ├── tarteel-ui.js            shared Bootstrap toast helper
│   ├── dynamic-tables.js        constructors, arrays, tables, add + search
│   ├── questionnaire.js         questionnaire validation and progress bar
│   ├── cal.js                   zakat calculator
│   ├── funpage.js               word-ordering game
│   ├── home.js                  banner and gallery
│   ├── contact-validation.js    contact form validation
│   └── registration-validation.js  registration modal validation
├── images/                      site and gallery images
└── docs/screenshots/            images used in this README
```

## Run locally

No build step is needed.

1. Download or clone the repository.
2. Open `index.html` in a modern browser.

An internet connection is required for the Bootstrap CDN (`bootstrap@5.3.3`) and the Tajawal Google Font.

## Notes and limitations

- Rows added to the tables are stored in the visitor's browser (`localStorage`); they are not shared between devices.
- All forms validate in the browser only. Saving data on a server with PHP and MySQL is planned for Part IV.

## Team

- Hamza Mohammed Al Busafi
- Yousif said Al Badi
- Alkhalil Ibrahim Al Shabibi

Course: COMP3700 – Introduction to Web Computing, Department of Computer Science, Sultan Qaboos University.
