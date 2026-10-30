# Aquarium Calculator

🇷🇺 [Русская версия](README.md)

**[Open the calculator →](https://timnurz.github.io/aquarium-stand/)**

A single HTML page with no server, build step or dependencies. Enter the tank dimensions and get glass, substrate, weight, a stand with a plywood cutting plan, equipment sizing, biological load, water tests and fertilizer recipes. It works offline, on a phone, and saves your inputs.


![Aquarium Calculator](screenshot.png)

## What it is for

The calculator covers one aquarium and one stand. It suits planted tanks from nano to large: there are 8 presets, from 600 × 300 × 300 to 2400 × 600 × 700.

![A range of minimalist planted aquariums](<Ряд минималистичных аквариумов с растениями.png>)

Pick a preset in one click, then change length, depth, height and substrate layer; the number of doors is set on the Stand tab.

## Aquarium

**Inputs.** Tank length, depth and height; substrate layer 0 / 3 / 5 / 7 cm; a preset.

**Outputs.**

- Wall and bottom thickness with a safety factor of 3.8; rim bracing and cross-braces; glass parts, seam and dimensions.
- Gross volume from external dimensions and calculated water volume with glass and the selected substrate layer.
- Actual weight for the selected layer and maximum weight for loads: 5 cm substrate + 10 %.
- Mass of glass, water and substrate; substrate table for 3 / 5 / 7 cm.
- At the bottom — a glass calculation specification: formulas, coefficients and a 1200 × 500 × 500 example.

**How to read it.** Glass and stand always use the maximum weight, even when another layer is selected. The other tabs use the calculated water volume for the selected layer. This keeps the stand conservative while equipment and biology use the actual water volume.

## Stand

**Inputs.** Stand height, plywood sheet size and number of doors; the view can be switched.

**Outputs.**

- Isometric view, frame, front and side views, shelf detail.
- Top panel deflection check: allowable deflection 3 mm, stress 8 MPa, plywood modulus 6 GPa.
- Plywood cutting plan per sheet, parts count, assembly order and hardware.
- The calculation uses the maximum tank weight, not the selected substrate layer.

## Equipment

**Inputs.** Water volume comes from the Aquarium tab; choose a filter and press “Media” to put its volume into the biology calculation.

**Outputs.**

- Filter by real flow: 3–5 tank volumes per hour.
- Reference table of 40 models: canisters, hang-on-back and internal. Real flow: 55 % of the datasheet for canisters, 75 % for hang-on-back, 80 % for internal.
- Light: 20–35 lm/l and 0.3–0.5 W/l LED.
- Aeration: 0.5–1 l/min per 100 l.
- Heater: 0.8–1 W/l, in steps of 25 W.
- Baseline water change in the KPI: 10–20 % per week; the actual value is on the Biology tab.
- Startup order.

## Biology

**Inputs.** Filter media and volume, temperature, feed protein, feeding percentage and fish weight.

**Outputs.**

- Media surface area and biofilter capacity in g TAN per day.
- Feed and fish limit from the filter; actual load.
- NO₃ and PO₄ accumulation without plants, NO₃ : PO₄ ratio and the water change needed to hold 20 mg/l.
- Top-50 popular fish table: adult weight, feeding percentage, filter and volume limits.
- Cart: quantity → total weight → feed in grams; a totals row. The cart updates the “Fish” and “Feeding” fields in the Filter block, but they stay editable.

**Important.** This is a nitrogen-load calculation only — no schooling, territory or comfort. Plants and denitrification are not modelled.

## Tests

**Inputs.** Water parameters: pH, KH, GH, NH₃/NH₄, NO₂, NO₃, PO₄, K, Ca, Mg, Fe, Cu, TDS and EC; targets for NO₃, PO₄, K, Ca, Mg and Fe.

**Outputs.**

- Deviation from the planted-tank reference and threshold-based recommendations.
- CO₂ from pH and KH.
- Water changes to the norm and to your target; K and Ca are handled separately even when the general norm is not exceeded.
- Targets that are then used on the Fertilizers tab.

## Fertilizers

**Inputs.** Current tests and targets. On this tab they are arranged in two columns: “Nitrogen and phosphorus” + “Minerals” on the left, “Targets” on the right; the “Recipe” is full width below them.

**Outputs.**

- Salt recipe in grams: KNO₃, Ca(NO₃)₂, urea, KH₂PO₄, K₂SO₄, MgSO₄, CSM.
- Ready-solution doses in ml next to the grams.
- Fixed stock solutions: 0.5 l; 50 g of macro salts, 40 g K₂SO₄, 5 g micro; 100 / 80 / 10 g/l.
- Side substances: K, Ca and SO₄; for urea — NH₃, NH₄⁺ and TAN with a pH/temperature split.
- Potassium and calcium: nitrates are added only up to the target; if K or Ca is already above it, nitrogen goes in as urea and a water change is suggested.
- Stock shelf life.

## General principles

- **One page.** No server or dependencies; download `index.html` and open it offline.
- **Language.** On first open RU or EN follows the browser/device language; a manual choice with **RU | EN** is remembered. `?lang=ru` or `?lang=en` forces it.
- **Saving.** Inputs are stored in the browser's `localStorage`.
- **Mobile layout.** Compact spacing, scrollable tabs, one-column tables and cutting plans, iPhone safe areas.
- **Connections.** Dimensions and substrate update all tabs; the fish cart updates the filter fields; tests feed the fertilizer targets.

## Limitations

- Glass thickness is an engineering estimate, not a manufacturer's datasheet; for tanks longer than 1.5 m, have it checked by a glass workshop.
- CO₂ assumes no other buffers; water changes assume replacement water contains none of the substance.
- The fish table is an upper nitrogen bound, not a compatibility recommendation.
- Top-50 weights and feeding percentages are guides; clownfish is marine and shown for reference only.
- Filter specifications are typical datasheet values; real flow depends on media, hose and head height.
- Stock shelf life depends on water and storage conditions.
- Ammonia and ammonium from urea are a hydrolysis potential, not a toxicity model.
- Internal partitions are not modelled; plants and denitrification are not included.

## Run locally

Download `index.html` and open it by double-clicking — it works offline.

Parameters can be passed in the URL:

```
https://timnurz.github.io/aquarium-stand/?l=1500&d=500&h=600&H=900&soil=50#fert
```

- `l`, `d`, `h` — tank length, depth and height, mm
- `H` — stand height, mm
- `soil=50` — substrate layer, mm: 0 / 30 / 50 / 70
- `sheet=2440,1220` — plywood sheet size
- `color=black` — black finish
- after `#` — tab: `tank`, `stand`, `gear`, `bio`, `fert`, `udo`
- stand sub-tabs: `#tumba`, `#frame`, `#front`, `#side`, `#detail`
- `lang=ru` or `lang=en` — force the language

## License

The project may be used, modified and distributed freely. It is provided “as is”, without warranty: the author is not liable for calculation results or built structures.

Personal and commercial use is allowed. A link to the source is appreciated but not required.

## Development

The source is `aquarium-stand.html`. To publish, run `publish.ps1`; it copies the file to `site/index.html`. Upload the contents of `site/` — `index.html`, `README.md`, `README.en.md`, `screenshot.png` and the planted-aquariums image — to the repository root. GitHub Pages updates automatically after the commit.

For a local check, open `index.html` in a browser.
