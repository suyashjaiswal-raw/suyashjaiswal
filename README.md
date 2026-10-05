# Auli market validation

Tooling for validating Auli in the US, UK and EU (Netherlands, Ireland, Germany). The full plan is in the validation plan doc.

## `landing/index.html`
Waitlist and Auli+ price-test page, English only, dark with gold accents.

- Markets: `?m=us|uk|ie|nl|de` (guessed from the browser language if omitted).
- Audience: default is dog parents; `?a=shelter` shows the Auli for Shelters version (no price test, asks for organisation and dogs in care).
- Attribution: `?v=a|b` tags a creative variant; standard `utm_*` parameters are captured.
- Example: `landing/index.html?m=uk&v=b&utm_source=meta&utm_campaign=launch1`

Before launch, edit `CONFIG` at the top of the script:

1. Set `endpoint` to where signups and events should be POSTed as JSON (a Google Apps Script web app or Formspree both work). Until then events only log to the console.
2. Replace the placeholder Auli+ price points with your real hypotheses.
3. Link a real privacy policy. The EU/UK copy refers to one.

Things the page does not do for you: it does not send the double opt-in confirmation email (connect your email tool to the endpoint), and it only promises features that work in every market. Add vet booking, pharmacy, insurance or emergency services to a market's copy only once they are live there.

Analytics are consent-gated in the UK and EU; the US shows a "Do not sell or share" opt-out. Signups are always sent because they are the visitor's own request.

## `tracker/index.html`
Experiment log with per-market budget burn (US $3,600, UK $2,400, EU $2,400), signup rate, cost per signup, paid-plan rate, and a go / iterate / no-go read against the plan's thresholds. Data lives in the browser; use Export CSV to back it up or share.

Both are static files: open them directly or host them anywhere (Vercel, GitHub Pages).
