# Rules for coding agents in this repo

## Who you are working with
I am learning data analytics and operations research while building this project. I must be able to explain every line in an interview.

## How to write code
- Keep code simple and readable over clever. Plain pandas before advanced tricks.
- Comment every block with WHAT it does and WHY.
- Do only what the prompt asks. No extra features, no refactors I did not request.
- Use the folder structure below. Do not create new top-level folders without asking.
- After any calculation, print a sanity check (row counts, totals, value ranges).
- Set and print a random seed for anything random (simulation, sampling, model training).
- If something is ambiguous, ask me instead of guessing.
- End each task with a short summary: files changed, what I should verify, and any assumption you made.

## Git workflow
- Never commit directly to main. Each step gets its own branch, named like `day1-load-data`.
- Small commits with clear messages saying what changed and why.
- When a step is done, push the branch and open a pull request so CodeRabbit can review it. Do not merge it yourself.

## Data rules
- Never commit anything in data/raw/. Raw data is downloaded from the source in DATA_REGISTER.md.
- Never invent numbers. Every figure in a write-up must come from code in this repo, or from a cited source in DATA_REGISTER.md.
- Any assumption that is not in the data (a cost, a response rate, a capacity) must be a named constant in one config file, with its source or the word ASSUMPTION, and must be included in the sensitivity analysis.
- Never treat sales in a stockout hour as demand: those hours are censored.
- Split train and test by time (an earlier period vs a later one), never randomly.
- Work on a documented subset (list the store-product IDs in data/processed/) so results are reproducible.

## Folder structure
- data/raw/          downloaded source files (gitignored)
- data/processed/    cleaned files produced by src/ scripts
- notebooks/         numbered analysis notebooks (01_, 02_, ...)
- src/               reusable Python scripts (download, cleaning, models)
- app/               Streamlit dashboard (reads only small files in data/processed/)
- reports/           decision memo and exported charts
- notes/             learning log, SQL log, setup guide, project map
