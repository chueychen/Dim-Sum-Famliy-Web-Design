# Dim Sum Family

A single-page website for a Cantonese dim sum restaurant, built with HTML and CSS only. No JavaScript and no external libraries.

**Live site:** https://chueychen.github.io/Dim-Sum-Famliy-Web-Design/

## About

I'm a huge dim sum fan, so I built this website for a fictional Cantonese tea house in Washington, DC's Chinatown. It introduces the families of dim sum and the legendary "Big Four" of the tea house table, shows the restaurant's location and opening hours, and lets visitors request a table through a reservation form. Dim sum originated in Guangdong, and its English names come directly from Cantonese pronunciation. That's why each dish on this site shows its Chinese name next to the English one, to help visitors understand where these dishes come from and the history behind them.

## Page Sections

**Hero** welcomes visitors with a short introduction and a "Reserve a Table" link that jumps to the reservation form.

**Our Menu** introduces the seven families of dim sum you'll find in a Cantonese tea house: Steamed Savories, Buns, Rice Rolls, Baked, Fried, Desserts, and Congee, shown as two rows of photo cards.

**The Big Four** tells the story of the "Four Heavenly Kings" of dim sum (har gow, siu mai, char siu bao, and egg tart), a phrase Cantonese tea houses have used since the 1930s. Each dish has its own article with a photo and a description of how it's made and what makes a good one.

**Visit Us** shows the restaurant's address, phone number, and opening hours for dim sum lunch and dinner.

**Reservations** contains a form for booking a table, grouped into three sections: Your Details, Reservation Details, and Anything Else.

## Features

- **Sticky header with dropdown navigation:** the header stays visible while scrolling. The navigation has two menus, Our Food and Visit, each with a dropdown of links to sections on the page. The dropdowns open on hover and with keyboard focus using `:focus-within`, so they work without JavaScript.
- **Reservation form:** submits to `/demonstration` using POST. It includes required and optional text fields, a phone field with a format hint, a date field, two select dropdowns, a radio group, and a pre-checked checkbox. Required fields are labeled with the word "Required" and enforced by the browser.
- **Accessible labels:** every form field has an associated `<label>`, and related fields are grouped with `<fieldset>` and `<legend>`. Instructions such as the phone format are written inside the label.
- **Two-column and one-column form layouts:** labels sit beside their fields on wider screens and above them on phones. Radio buttons and the checkbox always use a two-column layout, with the input on the left and its text on the right, even on phones. On wider screens, they line up with the other input fields instead of sitting at the far left of the form, and the two seating options appear side by side next to their group label.
- **Keyboard friendly:** the whole page, including the dropdown menus and the form, can be used with Tab, Shift+Tab, Enter, Space, and the arrow keys. Focus outlines are styled but never removed.
- **12-column card grid:** the menu has two card rows, one with 3 cards and one with 4 cards, both aligned to the same 12-column grid.
- **Bilingual headings:** headings and dish names include Simplified Chinese, marked with `lang="zh-Hans"`.
- **Consistent theme:** colors and fonts are defined once as CSS custom properties in `:root`, so the whole page shares the same look and can be updated in one place.

## Responsive Breakpoints

| Screen width | Menu cards | Big Four layout | Visit cards | Reservation form | Footer |
|---|---|---|---|---|---|
| Below 40rem | 1 per row | Image above text | Stacked | One column | Single column |
| 40rem to 48rem | 2 per row | Image above text | Stacked | One column | Single column |
| 48rem to 64rem | 2 per row | Image left, text right | Side by side | Two columns | Single column |
| 64rem and above | 3 per row / 4 per row | Image left, text right | Side by side | Two columns | Two columns |

## Design Principles

**Visual hierarchy:** heading sizes step down clearly from the page title to section headings, dish names, and card titles at every screen width. Page and section titles also use the brand color and italics to stand apart. In the form, each fieldset legend is larger and set in the display font, while hints are smaller and gray.

**Balance:** the hero is centered and symmetrical. In The Big Four section, each dish pairs a fixed-width photo on the left with a text block on the right, vertically centered so both sides carry similar visual weight.

**Proximity:** related content sits close together and unrelated content is spaced apart. Each card keeps its photo and name tightly grouped, and the space between Big Four dishes is larger than the space within each one. In the form, a label and its field are closer together than one field is to the next, and the three fieldsets are separated by even larger gaps. The fieldset being filled in is highlighted with `:focus-within`.

**Emphasis:** the "Reserve a Table" link and the submit button are solid brand-color blocks, drawing attention to the main action of the page. Chinese dish names use the brand color to stand out next to the black English names.

## File Structure

```
├── index.html
├── css/
│   ├── shared.css      Colors, fonts, base styles, header, navigation, and footer
│   ├── index.css       Hero and menu card grid
│   ├── big-four.css    The Big Four intro and dish articles
│   └── visit.css       Visit Us section and reservation form
└── images/
```

## Running Locally

The site should be viewed through a web server rather than by opening the HTML file directly, so that the form submits to `/demonstration` correctly. With [Node.js](https://nodejs.org/) installed, run this in the project folder:

```
npx serve
```

Then open the address shown in the terminal, usually `http://localhost:3000`.

On Windows PowerShell, if you see an error about running scripts being disabled, use `npx.cmd serve` instead.

## Testing the Form

Submitting the form returns a 404 error, which is expected because there is no server to receive the data. To confirm what was sent, open DevTools, go to the Network tab, turn on "Preserve log", submit the form, and select the `demonstration` request. The submitted fields appear under Payload. Remember to turn "Preserve log" off when you're done.

## Known Limitation

Because the dropdown menus are built with CSS only, on touch devices such as phones a menu may stay open after a link is tapped. Tapping anywhere else on the page closes it. Closing the menu automatically would require JavaScript, which this project does not use.

## Built With

- HTML
- CSS (Grid, Flexbox, custom properties, media queries, sticky positioning)

## Credits

All photos by Chaoyi Chen.

Created for the Web Design and User Experience Engineering course.

&copy; 2026 Chaoyi Chen. All rights reserved.