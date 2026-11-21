# Loggy

**A spending tracker for people chasing credit card miles and cashback in Singapore.**

The name is a play on "log it": you log each purchase, and Loggy keeps count.

**[▶ Try the Loggy demo](https://claude.ai/artifact/F1PNYS1eRSi19eDcTSa6WU)**: it opens in your browser with sample cards and spending, and works best on a phone. Add purchases, edit cards and switch the charts; nothing is saved, and it resets when you reload.

Many Singapore miles cards earn 4 miles per dollar (mpd) only up to a monthly cap, then drop to 0.4 mpd, and cashback cards have their own caps and minimum spends. With several cards, each with its own cap, reset date and quirks, it's easy to lose track and overshoot a cap without noticing. Loggy shows how much bonus room each card has left this cycle, and doubles as a simple personal finance tracker.

It's built for people who already know which card to use for which purchase. They don't need help choosing; they need help keeping count.

<p>
  <img src="screenshots/caps.jpg" width="250" alt="Caps tab: a bill due reminder, this month's spending and estimated miles, and each card's bonus cap bar">
  <img src="screenshots/spending.jpg" width="250" alt="Spending tab: a donut chart of November spending by category, with amounts and percentages">
  <img src="screenshots/add-spend.jpg" width="250" alt="Add spend form: amount, card, category, bonus or base rate, and an option to split the bill">
</p>

*Screenshots use made-up sample data.*

## Features

**Caps and rewards**
- A cap bar per card showing how much 4 mpd spend is left this cycle, turning amber near the cap and red when it's reached
- Calendar-month or statement-month cycles, using each card's own statement date
- Separate sub-caps on one card (for example, contactless and online)
- Earning blocks: points awarded per S$1 or per S$5, so S$9 earns on only S$5
- Minimum spend before the bonus rate unlocks
- Cashback cards, with caps stated as either S$ of spend or S$ of cashback, and uncapped cards (for example, a flat 1.6%)
- A live check while adding a purchase: "Fits, S$510 left" or "Only S$40 of this fits under the cap"
- A starter set of five common Singapore 4 mpd cards

**Spending**
- Spending by category or by card for any month, shown as a donut chart
- Your own categories, alongside defaults like Food, Shopping, Travel and Subscriptions
- PayNow transfers, which count toward total spending but earn nothing
- **Split bills:** when you pay S$100 for a dinner shared by five, the card's cap counts S$100 while your own spending counts S$20

**Reminders and small touches**
- Each card's bill due date, with a reminder on the home screen 5 days before and a one-tap monthly Google Calendar reminder
- A guide tab with each card's notes on what earns the bonus
- Paper planes fly off when you log a miles purchase, and coins burst out for cashback (skipped if your phone is set to reduce motion)
- Light and dark mode, sized for phones

## How this was built

I designed Loggy and built it with [Claude](https://claude.ai), Anthropic's AI assistant, which wrote the code.

My role was product owner:

- **Found the problem.** I play the miles game myself, and tracking caps across several cards in my head and in spreadsheets was tedious and error-prone. I couldn't find an existing app that tracked per-card cap usage the way I wanted.
- **Defined the product.** I decided who it's for (people who already know which card to use) and what to leave out (detailed merchant category code lookups, beyond a short guide).
- **Supplied the domain rules.** These are the rules the cap maths follows: statement vs calendar cycles, S$5 earning blocks, minimum spend, PayNow earning nothing, cashback caps stated in S$ of cashback, and uncapped cards.
- **Shaped the features through use.** I added cashback cards so more people could use it, spending categories and charts for a fuller view of spending, split bills for group meals, and bill reminders. I also cut things that didn't earn their place: I rolled back a visual redesign and removed a summary figure I didn't find useful.
- **Tested every version** and asked for changes until it behaved the way I wanted.

## Technical notes

- A single HTML file with plain JavaScript and CSS, no framework and no build step
- The chart is drawn as inline SVG; colours come from a colour-blind-checked palette, with separate values for light and dark mode
- It runs as a Claude artifact on claude.ai, and each person's cards and spending are saved privately to their own account

**The source code is not public. It's available on request, and I'm happy to walk through how it works.**

## Disclaimer

Card caps, rates and rules change often. Check them against your bank's current terms. Loggy is a personal tracking tool, not financial advice.
