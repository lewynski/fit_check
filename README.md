# FIT CHECK

*Build an outfit. Receive a verdict.*

&nbsp;

Fit Check is a single-page styling tool. Choose a top, bottoms, shoes and an accessory in any color, see the outfit on a mannequin, and receive a score out of 100 together with the reasoning behind it.

It is a static site: one HTML file, no dependencies, no build step.

---

## Features

**Two wardrobes.** Men's and women's builds, each with its own silhouette and its own garments. Women's options include the blouse, crop top, dress, leggings, mini and midi skirts, heels and flats. Men's options include dress shoes.

**Occasion-aware judging.** The same outfit is assessed differently for Casual, Work, Date night, Party or Gym.

**A reasoned verdict.** Every score arrives with a grade, a one-line verdict and a list of stylist notes. The score is divided into three parts: Style, Color and Occasion.

**Suggest a swap.** Finds the single change that improves the score most and applies it.

**Lookbook.** Save up to eight outfits and reload them later.

**Presets and random fit.** Five starting outfits per gender, plus a random generator.

**Light and dark themes.** Follows the system setting. Fully responsive; on phones the mannequin and score remain pinned while you choose.

---

## How an outfit is judged

| Dimension | What is assessed |
| --- | --- |
| **Style** | Whether the pieces sit at a similar level of formality; classic pairings (jeans and sneakers, chinos and loafers, blazer and jeans); athletic pieces mixed with dress pieces; accessory fit. |
| **Color** | Neutral and earth-tone palettes; one color pop against neutrals; competing loud colors; known clashes (red and green, navy and black, brown and black); light and dark contrast between top and bottoms. |
| **Occasion** | The average dress level against the target range for the chosen occasion; shoe suitability; workout readiness for Gym. |

Scores are bounded between 4 and 98. Grades run from A+ (90 and above) to F (below 38).

---

## Running locally

No installation is required.

```bash
git clone https://github.com/<your-username>/fit-check.git
cd fit-check
open index.html
```

Alternatively, serve the folder with any static server:

```bash
npx serve .
```

---

## Deployment

### Vercel

1. Push this repository to GitHub.
2. Sign in to [vercel.com](https://vercel.com) with your GitHub account.
3. Choose **Add New, then Project**, and import the repository.
4. Leave the framework preset as **Other**. No build command or output directory is needed.
5. Select **Deploy**.

Every subsequent push to `main` redeploys automatically.

### GitHub Pages

In the repository, open **Settings, then Pages**, set the source to the `main` branch and the root folder, and save.

---

## Project structure

```
fit-check/
├── index.html    The complete application: markup, styles and script
└── README.md
```

---

## Customizing

All data lives at the top of the script in `index.html`.

| To change | Edit |
| --- | --- |
| Garments, shoes or accessories | `TOPS`, `BOTTOMS`, `SHOES`, `EXTRAS` |
| Available colors | `COLORS` (`t` marks neutral `n`, earth `e` or bright `b`) |
| Color clashes | `CLASH` |
| Occasion formality ranges | `RANGES` |
| Starting outfits | `PRESETS` |
| Scoring rules | The `judge` function |

Each garment carries a formality value `f` from 0 (very casual) to 9 (formal) and a sportiness value `s` from 0 to 1. The judge reads these two numbers.

---

## Notes

Saved outfits and the last outfit viewed are stored in the visitor's own browser using `localStorage`. They are not shared between devices or visitors.

Typefaces are loaded from Google Fonts: Big Shoulders Display, DM Sans and DM Mono. Without a connection, the page falls back to system fonts.

---

## Typography and design

Set in Big Shoulders Display for headings, DM Sans for text and DM Mono for labels. The score card follows the form of a woven garment care label; the mannequin stands beside a measuring ruler.

---

<sub>Fit Check. Built with Claude.</sub>
