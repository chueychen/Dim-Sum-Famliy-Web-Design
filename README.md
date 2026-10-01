# Dim Sum Family

A two-page website introducing Cantonese dim sum, built with HTML and CSS only. No JavaScript and no external libraries.

**Live site:** https://chueychen.github.io/Dim-Sum-Famliy-Web-Design/

## About

I'm a huge dim sum fan, so I built this website to introduce the family of Cantonese dim sum and the legendary "Big Four" of the tea house table. Dim sum originated in Guangdong, and its English names come directly from Cantonese pronunciation. That's why each dish on this site shows its Chinese name next to the English one, to help visitors understand where these dishes come from and the history behind them.

## Pages

**Home (`index.html`)** introduces the seven families of dim sum you'll find in a Cantonese tea house: Steamed Savories, Buns, Rice Rolls, Baked, Fried, Desserts, and Congee. The categories are shown as two rows of cards.

**The Big Four (`big-four.html`)** tells the story of the "Four Heavenly Kings" of dim sum (har gow, siu mai, char siu bao, and egg tart), a phrase Cantonese tea houses have used since the 1930s. Each dish has its own section with a photo and a description of how it's made and what makes a good one.

The two pages link to each other through the navigation bar in the header, and the "Meet the Big Four" button on the homepage leads to the second page.

## Features

- **Shared header and footer:** both pages use identical header and footer HTML, styled by a single shared stylesheet.
- **Page-specific stylesheets:** each page loads its own CSS file for elements that are unique to it.
- **12-column card grid:** the homepage has two card sections, one with 3 cards per row and one with 4 cards per row, both aligned to the same 12-column grid.
- **Responsive design:** layouts adapt at rem-based breakpoints, from a single column on phones to multi-column layouts on wider screens.
- **Bilingual headings:** headings and dish names include Simplified Chinese, marked with `lang="zh-Hans"`.
- **Consistent theme:** colors and fonts are defined once as CSS custom properties in `:root`, so both pages share the same look and can be updated in one place.

## Responsive Breakpoints

| Screen width | Homepage cards | Big Four layout | Footer |
|---|---|---|---|
| Below 40rem | 1 card per row | Image above text | Single column |
| 40rem to 48rem | 2 cards per row | Image above text | Single column |
| 48rem to 64rem | 2 cards per row | Image left, text right | Single column |
| 64rem and above | 3 per row / 4 per row | Image left, text right | Two columns |

## Design Principles

**Visual hierarchy:** heading sizes step down clearly from the page title to section headings, card titles, and Chinese subtitles. The page titles also use the brand color and italics to stand apart.

**Balance:** the homepage hero is centered and symmetrical. On the Big Four page, each section pairs a fixed-width photo on the left with a text block on the right, vertically centered so both sides carry similar visual weight.

**Proximity:** related content sits close together and unrelated content is spaced apart. Each card keeps its photo and name tightly grouped, and on the Big Four page, the space between dishes is larger than the space within each one.

**Emphasis:** the "Meet the Big Four" button is the only solid color block in the homepage content, drawing attention to the link to the second page. Chinese dish names use the brand color to stand out next to the black English names.

## File Structure

```
├── index.html
├── big-four.html
├── css/
│   ├── shared.css      Header, footer, colors, fonts, and base styles
│   ├── index.css       Homepage hero and card grid
│   └── big-four.css    Big Four intro and dish sections
└── images/
```

## Running Locally

The site needs to be viewed through a web server rather than by opening the HTML file directly. With [Node.js](https://nodejs.org/) installed, run this in the project folder:

```
npx serve
```

Then open the address shown in the terminal, usually `http://localhost:3000`.

On Windows PowerShell, if you see an error about running scripts being disabled, use `npx.cmd serve` instead.

## Built With

- HTML
- CSS (Grid, Flexbox, custom properties, media queries)

## Credits

All photos by Chaoyi Chen.

Created for the Web Design and User Experience Engineering course.

&copy; 2026 Chaoyi Chen. All rights reserved.
