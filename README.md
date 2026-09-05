# TeslaSphere

TRMNL private plugin that shows **Tesla charging info via [Tessie](https://tessie.com)** — a full recreation of the community [Tessie recipe](https://trmnl.com/recipes/59557).

## Features (parity with Tessie recipe)

- Polls `GET https://api.tessie.com/{VIN}/state` with your Tessie API token
- Custom fields: **VIN** + **Token**
- Full layout: battery gauge (0–100%), range, energy added, time to charge limit, status, charging power, odometer
- Charge-limit marker on the gauge (`charge_limit_soc`)
- Vehicle name + last update in the title bar
- mi / km from `gui_settings.gui_distance_units`
- Half horizontal, half vertical, and quadrant layouts

## Install on TRMNL

### Option A — Private plugin (web UI)

1. [trmnl.com](https://trmnl.com) → Plugins → Private Plugin → New
2. Strategy: **Polling**
3. Polling URL: `https://api.tessie.com/{{ vin }}/state`
4. Polling headers: `content-type=application/json&authorization=Bearer {{ tessie_token }}`
5. Paste custom fields + markup from `src/` (see `src/settings.yml` and the `.liquid` files)
6. Save, enter your VIN + Tessie token, Force Refresh

### Option B — [trmnlp](https://github.com/usetrmnl/trmnlp) CLI

```bash
gem install trmnl_preview
git clone https://github.com/bobdivx/trmnl-teslasphere.git
cd trmnl-teslasphere
trmnlp serve          # local preview
trmnlp login && trmnlp push
```

## Tessie token

Create one at [my.tessie.com/settings/api](https://my.tessie.com/settings/api).

## Credits

Inspired by Stegzilla’s public Tessie recipe (#59557). Built for TRMNL Framework + Liquid.
