# Pad Footing Design to ACI 318

A browser calculator for an isolated rectangular pad footing under a concentric column, designed to ACI 318-25 or 318-19 in SI units. Enter the column, service and factored loads, soil data, footing size and bars, click Calculate, and it works through soil bearing, stability, flexure, one-way and punching shear, column bearing, dowels and detailing. Every step shows the formula, the numbers used and the code clause, and each check is marked pass or fail.

## What it checks

- Materials, 75 mm cover for concrete cast against earth (Table 20.5.1.3.1) and depth above the bottom bars of at least 150 mm (13.3.1.2)
- Soil bearing under service loads, including the footing and backfill weight, moments at the base from horizontal loads, a net or gross allowable pressure, and the kern check for full contact (13.3.1.1)
- Overturning and sliding with a factor of safety of 1.5
- Net factored soil pressure, linear under biaxial moment
- Flexure at the column face in both directions, minimum steel 0.0018Ag (8.6.1.1), the strain limit (8.3.3.1) and band steel in the short direction of a rectangular footing (13.3.3.3)
- One-way shear at d from the column face in both directions, Table 22.5.5.1 row (c), with the size effect neglected as 13.2.6.2 allows (or applied, if you choose)
- Punching shear at d/2 with the moment transferred by eccentric shear (22.6, 8.4.4.2)
- Bearing on the column and the footing (22.8.3.2), dowel area (16.3.4.1) and dowel development in compression (25.4.9.2)
- Bar spacing (8.7.2.2, 25.2.1) and development length from the column face (25.4.2.3)

The results page draws the service and factored corner pressures with the critical sections, a plan of the bottom bars and a section through the footing, and ends with a summary table and a bar schedule. After each calculation, the input panel shows the footing area needed, the smallest thickness that passes shear, and the bars each direction needs. You can export the full calculation as a PDF or an Excel workbook.

## How to use it

Open `index.html` in a web browser. Nothing needs installing, and everything runs on your computer, so no data leaves the page. The PDF and Excel libraries are in the `lib` folder, which must stay next to `index.html`.

Axes: x runs along L and y along B. A moment about y tilts the pressure along L. Service loads are used for the soil checks and factored loads for the concrete design.

To put it online, turn on GitHub Pages for this repository (Settings, then Pages, then deploy from the main branch).

## Limits

- Rectangular footing with the column at its centre, full soil contact and a linear pressure.
- One bottom mat of straight bars, no shear reinforcement, normal-weight concrete, uncoated bars, nonseismic design.
- Moments and horizontal loads are taken to act in the same sense, which gives the largest corner pressure.
- The full factored column moments are taken as transferred by eccentric shear in the punching check, which is conservative.
- Not covered: pile caps, combined or strap footings, a column off the footing centre, partial soil contact, uplift or tension in the column, settlement, hooked bar anchorage and seismic design.
- For ACI 318-25, the 2025 lower bound on one-way shear Vc is not used, which is conservative, and straight-bar development follows the 318-19 form. Check against the 2025 text before relying on them.

This is a design aid. Results should be checked by a qualified engineer.

## Third-party libraries

- [jsPDF](https://github.com/parallax/jsPDF) and [jsPDF-AutoTable](https://github.com/simonbengtsson/jsPDF-AutoTable), MIT licence
- [SheetJS Community Edition](https://github.com/SheetJS/sheetjs), Apache 2.0 licence
- [DejaVu Sans](https://dejavu-fonts.github.io/) font, subset and embedded for PDF output, free licence

Developed by Aarakshya Kandel
