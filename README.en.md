# Aquarium Calculator

🇷🇺 [Русская версия](README.md)

**[Open the calculator →](https://timnurz.github.io/aquarium-stand/)**

A single HTML page with no server and no dependencies: enter your tank dimensions and get glass thickness, substrate, total weight, a stand with a plywood cutting plan, equipment sizing, biological load, water tests and a fertilizer recipe.

![Aquarium Calculator](screenshot.png)

## Six tabs

| Tab | What it shows |
|---|---|
| **Aquarium** | Glass thickness with a safety factor, rim bracing and cross-braces, number of stand doors, substrate table (volume and weight for 3 / 5 / 7 cm), total weight broken down by parts |
| **Stand** | Isometric view, frame, front and side views, shelf detail, top panel deflection check, plywood cutting plan per sheet, assembly order and hardware |
| **Equipment** | Filter sized by real flow, light in lumens, aeration, heating, reference table of 14 filter models, cycling order |
| **Biology** | Biofilter capacity by media surface area, feed and fish limit, nitrate and phosphate accumulation, popular fish table |
| **Tests** | 15 water parameters against reference ranges, CO₂ from pH and KH, threshold-based recommendations, water change calculator |
| **Fertilizers** | Salt recipe in grams: nitrogen is split between potassium nitrate, calcium nitrate and urea based on the potassium and calcium budget |

## How to use

1. Enter tank length, depth and height — or pick a preset.
2. For tanks 800 mm and longer, choose the number of stand doors (a sensible default is filled in: 3 for 1.2 m).
3. On the Stand tab set the height and the plywood sheet size.
4. Everything else recalculates automatically.

Your inputs and language choice are stored in the browser, so they are still there on your next visit. The interface switches between Russian and English with the **RU | EN** button in the header.

## What is calculated and how

- **Glass** — a plate supported on three sides. Bending strength 40 MPa, safety factor 3.8. Rim bracing reduces load by 20 %, a cross-brace by 30 %.
- **Stand top** — a simply supported beam. Allowable deflection 3 mm, allowable stress 8 MPa, plywood modulus 6 GPa.
- **Weight** — water is the volume minus glass and substrate, substrate is counted by bulk density, plus 10 % margin.
- **Filter** — 3–5 tank volumes per hour of real flow, which is 55 % of the rated flow.
- **Biology** — media surface area × 0.45 g of nitrogen per m² per day; 48 mg of nitrogen per gram of feed at 40 % protein; temperature factor Q₁₀ = 2.
- **CO₂** — derived from pH and carbonate hardness.
- **Fertilizers** — salt stoichiometry: potassium nitrate is 61 % nitrate, monopotassium phosphate 70 % phosphate, magnesium sulfate 10 % magnesium.

## What it does not do

- Glass thickness is an engineering estimate, not a manufacturer's specification. For tanks longer than 1.5 m, check it with a glass workshop.
- CO₂ is calculated assuming no other buffers in the water.
- Water changes assume the replacement water contains none of the substance being diluted.
- The fish table is based on nitrogen load only — no schooling needs, territory or comfort. It is an upper bound, not a recommendation.
- Plants and denitrification are not modelled, so real values are usually lower than calculated.

## Run locally

Download `index.html` and open it by double-clicking — it works offline.

Parameters can be passed in the URL:

```
https://timnurz.github.io/aquarium-stand/?l=1500&d=500&h=600&H=900#fert
```

- `l`, `d`, `h` — tank length, depth and height, mm
- `H` — stand height, mm
- after `#` — tab: `tank`, `stand`, `gear`, `bio`, `fert`, `udo`
- `lang=en` — open in English right away

## License

Do whatever you want: use it, change it, sell stands.

---

### For the author: how to update the site

1. Edit `aquarium-stand.html` locally.
2. Copy it to `site/index.html` (or run `publish.ps1`).
3. Upload `index.html` to GitHub — Pages rebuilds within a minute.
