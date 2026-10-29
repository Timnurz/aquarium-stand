# Aquarium Calculator

🇷🇺 [Русская версия](README.md)

**[Open the calculator →](https://timnurz.github.io/aquarium-stand/)**

A single HTML page with no server and no dependencies: enter your tank dimensions and get glass thickness, substrate, total weight, a stand with a plywood cutting plan, equipment sizing, biological load, water tests and fertilizer recipes. It works offline, switches between Russian and English, and has a mobile layout.

![Aquarium Calculator](screenshot.png)

## A range of minimalist planted aquariums

![A range of minimalist planted aquariums](<Ряд минималистичных аквариумов с растениями.png>)

The calculator is built for a series of small planted tanks, from nano to large. The presets already include a range of minimalist planted aquariums:

| Dimensions, mm | Scenario |
|---|---|
| 600 × 300 × 300 | nano planted tank, one section |
| 800 × 350 × 400 | small planted tank |
| 1000 × 400 × 500 | medium planted tank |
| 1200 × 500 × 500 | classic 120 cm |
| 1500 × 500 × 600 | large planted tank |
| 1800 × 600 × 600 | extra large |
| 2000 × 600 × 700 | very large |
| 2400 × 600 × 700 | maximum preset |

For each option the calculator covers glass, stand, filter, light, CO₂, biological load and fertilizers. Pick a preset in one click, then change any dimension.

## What is new

- **Top-50 popular fish** from the [Tetra list](https://blog.tetra.net/ru/ru/50-samyh-populyarnyh-akvariumnyh-rybok-s-nazvaniyami-i-foto): adult weight, recommended feeding percentage, cart and total feed.
- **Fish cart**: quantity → total weight → feed in grams; the “Fish” and “Feeding” fields in the Filter block update automatically but stay editable.
- **40 filters** in the reference table: canisters, hang-on-back and internal, including Aquael Fan 1/2/3 Plus, Aquael Versamax, Tetra EasyCrystal, Eheim Liberty, AquaClear and Sunsun.
- **Filter type** with type-specific real flow: 55 % of the datasheet for canisters, 75 % for hang-on-back, 80 % for internal.
- **Fertilizers in grams and millilitres**: the main recipe shows the ready-solution dose next to the dry-salt mass.
- **Fixed stock recipes**: 0.5 l of solution, 50 g of macro salts, 40 g of potassium sulfate, 5 g of micro; concentrations 100 / 80 / 10 g/l.
- **Two-column fertilizer layout**: “Nitrogen and phosphorus” + “Minerals” on the left, “Targets” on the right; the “Recipe” is full width below.
- **Side substances**: K, Ca, SO₄ and, for urea, NH₃, NH₄⁺ and TAN with a pH/temperature split.
- **K and Ca targets**: nitrates are added only up to the target; if K or Ca is already above it, nitrogen goes in as urea and a water change is suggested.
- **Frame isometric view**: the wide right face of an upright is drawn before the shelves and the narrow front face after them, so shelves and uprights no longer show through each other.
- **Mobile layout**: compact spacing, scrollable tabs, one-column tables and cutting plans, iPhone safe areas.

## Six tabs

| Tab | What it shows |
|---|---|
| **Aquarium** | Glass thickness with a safety factor, rim bracing and cross-braces, number of stand doors, substrate table (volume and weight for 3 / 5 / 7 cm), total weight broken down by parts |
| **Stand** | Isometric view, frame, front and side views, shelf detail, top panel deflection check, plywood cutting plan per sheet, assembly order and hardware |
| **Equipment** | Filter sized by real flow, light in lumens, aeration, heating, reference table of 40 filter models (canisters, hang-on-back, internal), cycling order |
| **Biology** | Biofilter capacity by media surface area, feed and fish limit, nitrate and phosphate accumulation, top-50 fish with weight, feeding percentage, cart and totals |
| **Tests** | 15 water parameters against reference ranges, CO₂ from pH and KH, threshold-based recommendations, water changes to norm and to target |
| **Fertilizers** | Salt recipe in grams and ml, fixed 0.5 l stock solutions, side K/Ca/SO₄, ammonia and ammonium from urea |

## How to use

1. Enter tank length, depth and height — or pick a preset from the range above.
2. For tanks 800 mm and longer, choose the number of stand doors (a sensible default is filled in: 3 for 1.2 m).
3. On the Stand tab set the height and the plywood sheet size.
4. On the Equipment tab choose filter type and model; the “Media” button fills the media volume into the biology calculation.
5. On the Biology tab add fish to the cart. The total weight and weighted average feeding percentage are copied into the “Fish” and “Feeding” fields of the Filter block.
6. On the Tests tab set current values and targets. Water changes are calculated both to the norm and to your target.
7. On the Fertilizers tab get salt grams, ready-solution millilitres and side substances.

Everything else recalculates automatically. Your inputs and language choice are stored in the browser, so they are still there on your next visit. The interface switches between Russian and English with the **RU | EN** button in the header.

## What is calculated and how

- **Glass** — a plate supported on three sides. Bending strength 40 MPa, safety factor 3.8. Rim bracing reduces load by 20 %, a cross-brace by 30 %.
- **Stand top** — a simply supported beam. Allowable deflection 3 mm, allowable stress 8 MPa, plywood modulus 6 GPa.
- **Weight** — water is the volume minus glass and substrate, substrate is counted by bulk density, plus 10 % margin.
- **Filter** — 3–5 tank volumes per hour of real flow. In the reference table real flow is 55 % of the datasheet for canisters, 75 % for hang-on-back and 80 % for internal filters.
- **Biology** — media surface area × 0.45 g of nitrogen per m² per day; 48 mg of nitrogen per gram of feed at 40 % protein; temperature factor Q₁₀ = 2.
- **Fish and feed** — per fish: `quantity × weight × percentage / 100`; total weight is the sum of `quantity × weight`; the average percentage is weighted by weight. The cart updates the “Fish” and “Feeding” fields in the filter.
- **CO₂** — derived from pH and carbonate hardness.
- **Fertilizers** — salt stoichiometry: potassium nitrate is 61 % nitrate, monopotassium phosphate 70 % phosphate, magnesium sulfate 10 % magnesium.
- **Potassium and calcium** — nitrates are used only up to the K and Ca targets. If a value is already above target, the corresponding nitrate is not used and the remaining nitrogen goes in as urea.
- **Stock solutions** — 0.5 l of solution; 50 g for macro salts, 40 g for potassium sulfate, 5 g for micro. Concentrations 100 / 80 / 10 g/l; millilitres = grams / concentration × 1000.
- **Side substances** — K, Ca and SO₄ are calculated from the salts. For urea the calculator reports TAN (ammonia + ammonium nitrogen), and the split into free NH₃ and NH₄⁺ from pH and temperature via pKa.
- **Water changes** — a fraction of the volume, assuming the replacement water contains none of the substance. K and Ca targets are handled separately even when the general norm is not exceeded.

## What it does not do

- Glass thickness is an engineering estimate, not a manufacturer's specification. For tanks longer than 1.5 m, check it with a glass workshop.
- CO₂ is calculated assuming no other buffers in the water.
- Water changes assume the replacement water contains none of the substance being diluted.
- The fish table is based on nitrogen load only — no schooling needs, territory or comfort. It is an upper bound, not a recommendation.
- Adult weight and feeding percentages in the top-50 are guides. The Tetra list contains both broad groups and specific variants; the table keeps the article order. Clownfish is marine and is included for reference only.
- Filter specifications are typical datasheet values; real flow depends on media, hose and head height.
- Stock shelf life depends on water and storage. Guide: macro several months, iron and micro about a month, urea 1–2 weeks.
- Ammonia and ammonium from urea are a hydrolysis potential; the toxicity model and nitrification rate are not calculated.
- Plants and denitrification are not modelled, so real values are usually lower than calculated.

## Run locally

Download `index.html` and open it by double-clicking — it works offline.

Parameters can be passed in the URL:

```
https://timnurz.github.io/aquarium-stand/?l=1500&d=500&h=600&H=900#fert
```

- `l`, `d`, `h` — tank length, depth and height, mm
- `H` — stand height, mm
- `sheet=2440,1220` — plywood sheet size
- `color=black` — black finish
- after `#` — tab: `tank`, `stand`, `gear`, `bio`, `fert`, `udo`
- stand sub-tabs: `#tumba`, `#frame`, `#front`, `#side`, `#detail`
- `lang=en` — open in English right away

## License

Do whatever you want: use it, change it, sell stands.

---

### For the author: how to update the site

1. Edit `aquarium-stand.html` locally.
2. Run `publish.ps1` — it copies the source to `site/index.html`.
3. There is no `site` folder in the repository: the contents of `site` are the GitHub Pages root. Upload `index.html`, `README.md`, `README.en.md`, `screenshot.png` and `Ряд минималистичных аквариумов с растениями.png` to the repository root.
4. GitHub Pages rebuilds within a minute.
