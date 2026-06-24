# Prompt 003: Medical Source Seed List

## Title

Medical XR Crawl Seed Review

## Goal

Review and maintain the first approved crawl seed list for Nexus Crawler medical/XR trigger detection.

## Source of truth

```text
docs/MEDICAL_CRAWL_SEED_URLS.md
```

## Instructions

Use the seed list as the first controlled crawl batch.

The list should contain public URLs relevant to:

- FDA AR/VR medical device guidance
- ACGME residency and simulation requirements
- NIH grants and healthcare innovation funding
- ClinicalTrials pages involving VR/AR healthcare interventions
- PubMed or PMC clinical evidence pages
- Hospital job boards
- Medical education pages
- Hospital innovation labs
- Simulation center pages

## What to validate

For each URL, classify:

- Source category
- Expected trigger type
- Crawl priority
- Whether the page is public
- Whether the page should be crawled directly or only used as a discovery seed

## Output

Update `docs/MEDICAL_CRAWL_SEED_URLS.md` with:

- New approved URLs
- Removed URLs
- Notes about broken or weak sources
- Recommended first crawl batch

## Safety

Do not include URLs that require login, bypassing, scraping private systems, or evading anti-bot controls.
