# Moment Match prototype

Slot-level contextual targeting for the Media.net ad server. Built for the Media.net APM case study (topic 4: integrate contextual targeting into the existing ad server).

**Live demo:** https://aashish3061.github.io/moment-match-prototype/

## What it shows

Today one page label decides the ads for every slot on a long article. Moment Match decides per slot, using the paragraphs right above it.

- **Sense:** each slot gets IAB Content Taxonomy 3.1 topics, a keyword query, a reader mindset and a content tone (valence, arousal), read from the text only.
- **Decide:** every ad is scored against the slot. A conflict guard blocks clashing ad and paragraph pairs (severe cases, such as an airline ad on an air-incident story, page-wide), a topic floor on the text above the slot and a relevance bar filter weak matches, and the slot falls back to today's page-level choice if nothing qualifies.
- **Prove:** every decision is logged, and the OpenRTB 2.6 bid request carries slot signals in `imp[].ext.data` (cattax 9).

## How to use it

1. Pick a sample article: travel guide, breaking news or car buying.
2. Click any ad slot to compare today's page-level ad with Moment Match in the slot inspector.
3. Try the controls: MoSCoW feature flags, the relevance cap (lambda) and bar (tau), the tone experiment arms, and the phase-2 ranker switch (slot-target attention, simulated).
4. Change the rollout stage to see the experiment readout and gate decision for each stage.

## Notes

- Articles, brands, bids and experiment results are fictional or simulated, and labelled as such in the page.
- IAB Content Taxonomy 3.1 IDs are real.
- Single self-contained HTML file, no build step. Open `index.html` in a browser or serve the folder with any static host.
