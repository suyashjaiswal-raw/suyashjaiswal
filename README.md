# Auli market validation

Tooling for validating Auli in the US, UK and EU. The full plan is in the validation plan doc.

- `landing/index.html`: waitlist and price-test page. Open with `?m=us|uk|de|fr|nl`, `&v=a|b` for creative variants, and UTM parameters from ads. Edit `CONFIG` at the top of the script: replace the `[placeholder]` copy, set `endpoint` to where signups should be POSTed, and adjust price points. The page gates analytics behind consent in the UK and EU, and offers a "do not sell or share" opt-out in the US.
- `tracker/index.html`: experiment log with per-market budget, signup rate, cost per signup and a go / iterate / no-go read against the plan's thresholds. Data is stored in the browser; use Export CSV to back it up.

Both are static files: open them directly or host them anywhere (Vercel, GitHub Pages).
