# How podcasts use a term, and how far apart they are

An interactive map of how political podcasts talk about a term (for example *iran*, *israel*,
*trump*, *ukraine*, *democrat*, *socialist*), how far apart shows are in that usage, and how
this changes over time.

**[Open the dashboard](./index.html)**

## What it shows

- **Map:** each dot is one show in one period: the average of its episodes' use of the term.
  Closer dots use the term with more similar vocabulary. Selected shows get a trail through time.
- **Words that pull toward each side:** vocabulary that separates two shows or groups.
- **Distance over time:** noise-corrected distances with 90% bootstrap intervals.
- **Passages:** the words around real mentions, to read what a distance is made of.
- Menus switch the term, the period length (91 or 182 days) and which shows are on the map.

It describes **vocabulary and topics near a term, not stance or ideology**. Distances are
corrected for sampling noise (zero means "not distinguishable from noise"), and every chart
says what it compares against.

## Method in brief

- Episodes from about 50 political podcasts, transcribed with Whisper (medium, int8) from public
  RSS feeds, lemmatized with spaCy (nouns, proper nouns, adjectives).
- Each mention of a term is embedded with *à la carte* embeddings (Rodriguez, Spirling and
  Stewart 2023): the average word2vec vector of the words within 5 tokens, multiplied by a
  learned transform. The unit of analysis is the episode (mean of its mentions), so frequent
  shows do not dominate.
- A show needs at least 8 episodes with 3+ mentions in a period to be placed.

## Data published here

Only derived results: averages, distances, intervals, word lists, and short lemmatized word
windows around mentions with episode titles and dates. No audio or full transcripts.

Built for DACSS 758 (Text as Data), UMass Amherst.
