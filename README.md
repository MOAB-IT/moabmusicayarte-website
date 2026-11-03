# MOAB Música y Arte — Nonprofit Site

A bilingual (EN/ES) static website for MOAB Música y Arte, an independent nonprofit dedicated to music education. Built as plain HTML/CSS/JS with no build step — open `index.html` directly in a browser, or serve the folder with any static file server.

## Structure

```
.
├── index.html          Home page (hero, mission, impact, testimonials)
├── css/
│   └── styles.css      Shared stylesheet for all pages
├── js/
│   └── script.js       Shared behavior: language toggle, mobile nav
├── pages/
│   ├── about.html       About Us + Team
│   ├── programs.html    Programs overview + detail gallery
│   ├── events.html      Events gallery
│   ├── support.html     Donate / support options
│   └── faq-contact.html FAQ + Contact info (merged)
├── images/              Locally hosted images (logo, team, programs, events,
│                        gallery, icons, testimonials, support)
└── data/                Reserved for structured content (team, events, programs)
                         if the site is later migrated to a templated/data-driven build
```

## Notes

- **Images**: All images are hosted locally in `images/` (originally copied from the
  previous WordPress media library). Large photos were resized to max 1600px and
  re-compressed; full-page event flyers were converted from PNG to JPEG.
- **Donations**: Donate buttons use the Givebutter widget (`<givebutter-widget id="j2OKJa">`),
  loaded by the Givebutter library script in each page's `<head>`. The button's text and
  color are configured in the Givebutter dashboard. The membership button (Support page)
  still links to Zeffy, and the WhatsApp payment links still point to the original
  organization's accounts.
- **Language toggle**: Implemented via `data-i18n-en` / `data-i18n-es` spans and a small
  CSS/JS switch. The chosen language persists across page loads via `localStorage`.
- **No build tools required.** All pages share `css/styles.css` and `js/script.js` via
  relative paths (`../css/styles.css` and `../js/script.js` from inside `pages/`).
