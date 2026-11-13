# Smart Tariff Comparison (prototype)

A small, self-contained web tool that estimates a household's annual electricity cost under four tariff structures, based on how much power the household uses and when.

**Live demo:** (https://github.com/Tugceaydinn/smart-tariff-comparison)

## What it does

- Takes annual usage (1,500–9,000 kWh), a household type (out during the day, home most of the day, or evening-heavy family) and optional EV charging with a charging time.
- Builds a 24-hour load profile and prices it under four tariffs: flat rate, day/night, smart time-of-use (night, day, peak) and an EV night saver.
- Shows the cheapest tariff, the saving against the flat rate, the hourly load coloured by price band, and the share of consumption in each band.

## Method

Annual cost = standing charge × 365 + the sum over 24 hours of (hourly kWh × unit rate for that hour's price band).

Hourly use = annual usage × a normalised 24-hour shape for the household type, plus EV charging spread evenly over the chosen window. Prices are before VAT and levies.

Price bands: night 23:00–08:00, peak 17:00–19:00, day for all other hours.

## Limitations

- **Load profiles are synthetic.** The shapes are stylised, with no seasonal or weekday/weekend variation, and are not real smart-meter data.
- **Tariff rates are illustrative placeholders.** Tariffs A to D are fictional and are not real supplier prices.
- This is a prototype for exploring the logic of tariff comparison. It should not be used to choose a real tariff.

## Next steps

- Replace the placeholder rates with current supplier rate cards (edit the `TARIFFS` object in `index.html`).
- Load real half-hourly smart-meter data and add seasonality.
- Test sensitivity of the ranking to changes in unit rates and standing charges.
- Validate results against existing supplier comparison tools.

## Run locally

Open `index.html` in a browser. There are no dependencies or build steps.

## Author

Tuğçe Aydın · tugceaydiinn@hotmail.com
