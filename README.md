# hoursboard-bot

`hoursboard-bot` is the crawler for **hoursboard** (working name), an independent job board for genuinely
part-time (16–32 h/week) roles in tech.

User-Agent: `hoursboard-bot/0.1 (+https://github.com/AndreyKocevski/hoursboard-bot)`

## What it fetches
Only the **public job-board JSON/XML endpoints** that applicant-tracking systems publish for exactly this purpose
(Greenhouse, Lever, Ashby, Workable, Recruitee, SmartRecruiters, Personio, Teamtailor). It does not log in, does not
scrape HTML listing pages, and does not crawl sites whose terms forbid automated access (e.g. LinkedIn, Indeed, Glassdoor).
To discover which ATS a company uses it may request a company's own `/careers`, `/jobs` or `/join` page once.

## How it behaves
- Respects `robots.txt` and any crawl delay.
- At most one request per second to Lever and a small, fixed concurrency elsewhere; most boards are fetched once a day.
- Stores structured fields (hours, pay, contract type, location eligibility) and a short excerpt, plus a link back to
  the employer's own application page. It never hosts applications for your roles.

## Opt out or contact
Open an issue in this repository with your company or board name. We stop fetching your board and remove your
listings within 24 hours. Corrections to a listing (wrong hours, role filled) are welcome the same way.
