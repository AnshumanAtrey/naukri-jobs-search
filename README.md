# Naukri Jobs Scraper & API - Salary, Experience, Last 24 Hours

Naukri jobs scraper and API: search naukri.com, India's largest job board, live by job title, city, years of experience, pay in lakhs, remote or hybrid work and posting date, and get each job's title, company, places, experience asked, salary, key skills, company rating, posting date and link, newest first, internships and walk-in jobs included. Turn on full details for the description, job type, department, role, industry, education and applicants so far.

Use it as a Naukri API with no login and no API key, a naukri.com job scraper or a daily India job feed from the Apify Console, the Apify API, Python, JavaScript, n8n, Make or an AI agent, and export JSON, CSV or Excel. Every row's title holds the words you typed, Bangalore finds Bengaluru jobs, and a pasted Naukri search link keeps its filters. Available as an [Apify Actor](https://apify.com/anshumanatrey/naukri-jobs-search). $0.000017 per job, $0.000037 with full details, $0.0025 per run start at the default memory.

## What does it do?

- **Searches all of Naukri, live.** About 690,000 open jobs (692,506 on 2026-11-08), read from Naukri's own search at the moment of your run, newest first.
- **Titles that match.** Naukri's keyword search also returns jobs that only mention your words in their skills or text: of its 37,872 jobs for python developer, 4% to 9% of the newest had both words in the title. This actor keeps the ones whose title has every word, and Wider match (`searchDescriptions`) gives you Naukri's whole answer.
- **Pay, experience and key skills on every row.** Pay is shown on 52% to 69% of jobs (four samples on 2026-11-08), as Naukri's text ("15-24 Lacs PA") and as numbers in rupees a year. Experience comes as text and as fewest and most years, key skills on 99% of jobs.
- **Two posting dates.** `postedAt` is Naukri's date, which an employer's repost moves to now; `firstPostedAt` is the day Naukri first listed the job. 30% of the 500 newest jobs on Naukri were first posted a week or more earlier.
- **Naukri's own filters, typed the way people type.** Experience in years (3, a range such as 2-5, or 5+), minimum pay in lakhs (10 is 10 LPA), work from office, hybrid or remote, company type (startup, MNC, Govt/PSU), posted by a company or a consultant, last 24 hours to 30 days.
- **Places by any name.** Bangalore or Bengaluru, Gurgaon or Gurugram, Bombay or Mumbai, a state (Karnataka, or KA), Delhi NCR for the whole capital region, India, or a country abroad.
- **Checks job links.** Paste Naukri job links or 12-digit job IDs, and each comes back open with the job, or closed.

## How is it different from other Naukri scrapers?

- **The title matches what you typed.** The three most used Naukri actors pass your keyword to Naukri and return its answer as it comes (memo23 adds an optional filter on any word in the title, company or description): sorted by date, Naukri's answer for python developer starts with ServiceNow, AWS full stack and Java roles, because its search also reads key skills and text. Here every row's title holds every word, so 100 rows are 100 Python developer jobs.
- **Several titles and places in one run.** Type sales manager and operations executive, Mumbai and Pune, in one form; the leading actors take one keyword and one location.
- **Repost detection on every row.** `firstPostedAt` comes from the job's ID, so a two-month-old job an employer reposted today is visible as one.
- **Clean, flat rows.** Pay as numbers, rating and review count as two fields, places as text, skills as a list: no nested company or AmbitionBox objects to post-process.
- **Your search link, as you made it.** A pasted naukri.com search link keeps its words, place, experience, period, work mode, pay band, company type and company.
- **Exactly the number you asked for.** Number of jobs (`maxJobs`) is the number of rows you get, newest first, and you pay per row delivered.

## When should I use it?

- **Job seekers and job boards:** new jobs by title, city, experience and pay, every morning, with the salary shown and reposts flagged.
- **Recruiters and staffing firms:** who is hiring for a role right now, at what experience and pay, and which companies post most.
- **Sales and market research:** companies hiring for a function or a city as a buying signal, with their rating and size.
- **Data teams and AI agents:** one clean feed of India's jobs through the API or MCP.

## How much does it cost to scrape Naukri jobs?

Pay per event: $0.017 per 1,000 jobs, or $0.037 per 1,000 with full details, plus $0.0025 per run at the default 512 MB. Apify's free $5 monthly credit covers about 119,000 jobs in runs of 100. Platform usage is included, and there is no monthly fee.

| Event | Price | When it is charged |
|---|---|---|
| Job | $0.000017 | One saved job, and one checked link that is closed or not found |
| Job with details | $0.000037 | One saved job with full details on |
| Run start | $0.0025 per GB of memory | Charged by Apify when a run starts: once up to 1 GB and once more for each extra GB, so $0.0025 at the default 512 MB |

Naukri Jobs Scraper's Apify Store header shows the lowest discount-tier price, the GOLD price: $0.012 per 1,000 jobs. FREE and BRONZE users (Apify's Free and Starter plans) pay $0.000017 a job; with full details FREE pays $0.000037 and BRONZE $0.000035. SILVER (Scale) pays $0.000014 and $0.000028, and GOLD (Business) and the enterprise tiers $0.000012 and $0.000022. Each price is what that row costs on Apify at that plan's own rates, measured on Apify runs, plus a markup of 150% on the Free and Starter plans that falls to 110% on Business. The run start is a flat fee on every plan, $0.0025 per GB of memory, and the header never shows it.

| Run (Free and Starter price, default memory) | Cost |
|---|---|
| 100 newest jobs | $0.0042 |
| 100 jobs with full details | $0.0062 |
| 1,000 jobs | $0.020 |
| 15,000 jobs, the most Naukri shows for one search | $0.26 |

## How does the price compare with other Naukri scrapers?

Every actor on the Apify Store whose title names Naukri (naukri.com, not only NaukriGulf) and had 40 or more users in the last 30 days, from the Store's own search for naukri on 2026-11-08 (200 actors read), ordered by users. Free-plan prices from each actor's current pricing.

| Actor | Users, 30 days | Per job | Start fee | Input |
|---|---|---|---|---|
| valig/naukri-jobs-scraper | 2,799 | $0.0004, every row with details | $0.001 | One keyword and one location, Naukri's filters as codes |
| muhammetakkurtt/naukri-job-scraper | 1,133 | $0.0015, $0.003 detailed | $0.001 | One keyword or a search URL, every Naukri filter as ids, NaukriGulf too |
| blackfalcondata/naukri-jobs-feed | 736 | $0.00039 | $0.001 | Keywords, filters, incremental mode, notifications |
| memo23/naukri-scraper | 242 | $0.0008, +$0.001 extra data | $0.001 | Keywords or start URLs, NaukriGulf too, employer emails |
| getascraper/india-job-inventory-feed | 215 | $0.00199 | $0.00005 | 12 Indian job boards in one feed |
| themineworks/naukri-jobs | 134 | $0.0014 | $0.005 | Keywords, a browser warm-up, Apify proxy |
| epicscrapers/naukri-scraper | 49 | $0.004, $0.008 with details | $0.01 | Keywords |
| thirdwatch/naukri-jobs-scraper | 46 | $0.0015 | $0.00005 | Naukri and NaukriGulf, 60+ fields |
| themineworks/india-jobs-mcp | 43 | $0.035 a Naukri search | none | An MCP server with 14 tools |
| This actor | new | $0.000017, $0.000037 with details | $0.0025 per GB | Titles, places and Naukri's filters, live |

Where others are cheaper: this actor's run start, $0.0025, is above every other's ($0.001 or less), so a run of a single job costs less on most of them, and a run of fewer than 4 to 8 jobs (by plan, and with full details) costs less on valig or blackfalcondata. From 8 jobs a run, this actor costs the least on every plan, and per job it costs the least of all, with full details or without. Where others do more: muhammetakkurtt, memo23 and thirdwatch also read NaukriGulf; muhammetakkurtt exposes every Naukri filter (industry, department, role, education, top companies) by id; memo23 adds employer emails; blackfalcondata adds an incremental mode and Telegram, Slack and webhook alerts.

## Which inputs does it take?

Nothing is required. Type a job title and press Start, or press Start with the form empty for the newest jobs of every kind.

| Field | What it does |
|---|---|
| Job titles to find (`searchTerms`) | One per line. A job matches when its title has every word: frontend also finds Front-End. A pasted Naukri search link works too, with its filters |
| Where the job is (`location`) | Cities, states or countries: Bangalore, Delhi NCR, Karnataka, Dubai. Old and new city names both work. India keeps every job in India. Remote alone asks for remote jobs; next to a city it changes nothing |
| Remote or office (`workType`) | remote, hybrid or onsite (work from office), as Naukri states it for every job |
| Posted in the last (`postedWithin`) | 24 hours, 3, 7, 15 or 30 days (the default), any time, or your own period such as 48 hours |
| Experience (`experienceYears`) | Your years: 3, a range such as 2-5, 5+ or fresher. Keeps the jobs whose range overlaps it, as Naukri's Experience filter; internships state none, so it leaves them out |
| Minimum pay (`minSalaryLakhs`) | Lakhs a year: 10 is 10 LPA. Naukri also counts pay the employer entered but hides |
| Company type (`companyType`) | foreign-mnc, indian-mnc, mnc, corporate, startup, unicorn, govt-psu or others |
| Posted by (`postedBy`) | company or consultant |
| Number of jobs (`maxJobs`) | How many, newest first: 100 by default, 0 for every match (Naukri shows at most 15,000 a search) |
| Full details (`includeDetails`) | Adds the description as text and HTML, job type, department, role, industry, education, applicants, the employer's website and apply link |
| Leave out words (`excludeTerms`) | Drops jobs whose title has these words, such as senior or intern |
| Job type (`employmentType`) | full-time, part-time, contract, intern or temporary. Internships come from Naukri's internship search; other types are read from each job's page, up to 300 a run |
| Wider match (`searchDescriptions`) | Every job Naukri's own search finds for your words, also in its skills or text |
| Only these companies (`companies`) | Company names as Naukri writes them (Infosys, Accenture), a company page link, or a `companySlug` |
| Job links to check (`jobUrls`) | Naukri job links or 12-digit job IDs, to check whether they are still open, instead of searching |
| Connection (`proxyConfiguration`) | Off by default. Turn on Apify Proxy only when a run says Naukri refused its address |

Example input:

```json
{
  "searchTerms": ["python developer", "django developer"],
  "location": ["Bangalore", "Pune"],
  "experienceYears": "3",
  "minSalaryLakhs": 8,
  "postedWithin": "7 days",
  "maxJobs": 100
}
```

## What does the output look like?

One row per job, newest first. These rows are from a local run on 2026-11-08 at 02:28 UTC: python developer in Bangalore, 100 jobs saved in 13 s. A job with several cities shows the first in `location` and the others in `otherLocations`, so a Hyderabad job that also hires in Bengaluru is a Bangalore match.

| Job title (`title`) | Company name (`company`) | Main location (`location`) | Remote or office (`workType`) | Experience asked (`experience`) | Pay as shown (`salary`) | Posted on (`postedAt`) |
|---|---|---|---|---|---|---|
| Python Developer Lead | Hexaware Technologies | Hyderabad | hybrid | 7-12 Yrs |  | 2026-11-07 |
| Senior Backend Developer-Python (Immediate joiners & F2F Interview) | Choice Consultants | Bengaluru(HSR Layout) | onsite | 4-6 Yrs | 12-15 Lacs PA | 2026-11-06 |
| Python AWS developer | Virtusa | Hyderabad | onsite | 8-12 Yrs |  | 2026-11-06 |
| Python Fullstack Developer | Infosys | Hyderabad | hybrid | 5-8 Yrs |  | 2026-11-06 |
| Python developer | CGI | Hyderabad | onsite | 3-10 Yrs | 15-24 Lacs PA | 2026-11-06 |

One row as JSON:

```json
{
  "title": "Python developer",
  "company": "CGI",
  "location": "Hyderabad",
  "otherLocations": ["Chennai", "Bengaluru"],
  "workType": "onsite",
  "employmentType": null,
  "department": null,
  "salary": "15-24 Lacs PA",
  "postedAt": "2026-11-06T05:28:45Z",
  "jobUrl": "https://www.naukri.com/job-listings-python-developer-cgi-hyderabad-chennai-bengaluru-3-to-10-years-061126009900",
  "applyUrl": "https://www.naukri.com/job-listings-python-developer-cgi-hyderabad-chennai-bengaluru-3-to-10-years-061126009900",
  "status": "open",
  "platform": "naukri",
  "companySlug": "cgi-jobs-careers-217",
  "companyWebsite": null,
  "jobId": "061126009900",
  "checkedAt": "2026-11-08T02:27:48+00:00",
  "experience": "3-10 Yrs",
  "experienceMin": 3,
  "experienceMax": 10,
  "skills": ["AWS", "Python", "Development", "MongoDB", "NoSQL", "Python Development"],
  "salaryMin": 1500000,
  "salaryMax": 2400000,
  "salaryCurrency": "INR",
  "salaryPeriod": "year",
  "firstPostedAt": "2026-11-06",
  "companyRating": 4.0,
  "companyReviews": 6114,
  "vacancies": 2,
  "walkIn": false,
  "summary": "Troubleshoot issues related to application deployment,data modeling,query optimization etc. Job Requirements : . 3-10 years of experience in developing Python applications on AWS cloud platform\nExperience with containerization using Docker or Kubernetes is a plus",
  "companyLogo": "https://img.naukimg.com/logo_images/groups/v1/1402790.gif",
  "industry": null,
  "role": null,
  "roleCategory": null,
  "education": null,
  "applicants": null,
  "views": null,
  "postedBy": null
}
```

Full details fill `employmentType`, `department`, `companyWebsite`, `industry`, `role`, `roleCategory`, `education`, `applicants`, `views` and `postedBy`, and add `description`, `descriptionHtml`, `reference`, `city`, `region` (the state) and `country`; for a job Naukri copied from a company career site, about 1 in 9, `applyUrl` becomes the employer's own job page. A checked link that is closed comes back with its `status` and link, and the other fields empty. A run also writes an `OUTPUT` record: how many jobs Naukri listed, how many matched and were saved, any notes on how your input was read, and the calls made.

## How fast is it?

Seconds. On Apify at the default 512 MB on 2026-11-08: the form as it opens (100 newest jobs) took 8 s, python developer 21 s (11 calls), python developer in Bangalore with 2-5 years 31 s (24 calls), java developer in Pune with a pay minimum and company type 4 s, 1,000 sales jobs 25 s (18 calls, 40 jobs a second, 69 MB of memory), 100 jobs with full details 35 s (105 calls) and 20 internships 4 s. The same python developer search took 18 s at 1 GB and 16 s at 2 GB, for 31% and 97% more cost, so 512 MB stays the default. Naukri's search returns 100 jobs a page, newest first; a rare title takes more pages, because Naukri's answer also holds jobs that only mention the words.

## Common questions

### Which posting date does it use?

Naukri Jobs Scraper uses the date Naukri shows and sorts by, `postedAt`, for the order and for Posted in the last (`postedWithin`), so its results line up with Naukri's own "1 Day Ago". An employer can post a job again, which moves that date to now: 30% of the 500 newest jobs on 2026-11-08 had been first posted a week or more earlier, 19% a month or more. `firstPostedAt` keeps the day Naukri first listed each job, read from its 12-digit ID, which starts with that day (887 of 887 jobs checked: a real date, never after `postedAt`). Keep only rows where the two dates are close to drop reposts.

### Why do I get fewer jobs than Naukri shows?

Naukri counts every job whose title, key skills or text holds your words: 37,872 for python developer on 2026-11-08, of which 4% to 9% of the newest had both words in the title. Naukri Jobs Scraper keeps the jobs whose title holds every word, and keeps a job posted twice (same company, title, place, experience and pay) once, the newest. Tick Wider match (`searchDescriptions`) to get every job Naukri's search finds. A run that saves no job says why: Naukri had no job with your words inside your other filters, or one filter alone left out the jobs with your words ("783 jobs had your words but not your other filters: the years of experience alone left out 783"), and how to loosen it.

### How do places work?

Naukri Jobs Scraper reads places the way people type them: Bangalore and Bengaluru, Gurgaon and Gurugram, Bombay and Mumbai find the same jobs; a state (Karnataka, or KA) finds jobs in its cities, from Naukri's own list of 5,810 Indian cities, also by the names Naukri's jobs print (Bhubaneswar, Nashik, Tumakuru, New Delhi, Mumbai Suburban), so 5,780 of 5,820 places on 3,981 jobs read on 2026-11-08 got their state or country; Delhi NCR finds Delhi, Noida, Gurugram, Ghaziabad and Faridabad; India keeps every job in India. A country abroad (United Arab Emirates) finds the jobs whose place names it; Naukri often writes only the city (Dubai), so type the city too. A Naukri job open to remote work names Remote as its place, so pick remote in Remote or office (`workType`) to get remote jobs, or type Remote alone in Where the job is (`location`). Remote typed next to a city changes nothing: the city's jobs come with every work type, and the run says so.

### How do I get only jobs above a salary?

Type the lowest yearly pay in lakhs in Minimum pay (`minSalaryLakhs`): 10 keeps jobs paying 10 LPA or more. Naukri Jobs Scraper sends it to Naukri's Salary filter, which also judges jobs whose employer entered a pay and chose not to show it, and leaves out any job whose shown pay is lower. Pay is shown on more than half of Naukri's jobs.

### Does it need a login or an API key?

Naukri Jobs Scraper needs no Naukri login and no API key: it reads the same public search and job pages any visitor's browser reads. You need only an Apify account.

### Does it work on Apify's free plan?

Naukri Jobs Scraper works on Apify's free plan, which pays $0.000017 a job plus the $0.0025 run start at the default 512 MB. The free $5 monthly credit pays for about 119,000 jobs in runs of 100, at $0.0042 a run.

### How often should I run it?

Running Naukri Jobs Scraper once a day keeps a job feed fresh: set Posted in the last (`postedWithin`) to 24 hours and Number of jobs (`maxJobs`) to 0 to get every job of the day for your titles and places. Set it up under Schedules in Apify Console, and match rows on `jobId` to skip jobs you already have.

### What happens if Naukri refuses the run?

Naukri limits how much one address may ask for: in tests on 2026-11-08 an address answered several hundred calls in a few minutes, then got "recaptcha required" for minutes to hours: one address's job pages stayed refused for more than seven hours while its searches answered. A run of 100 jobs makes 2 to 24 calls, plus one per job with details, so a run rarely meets the limit: 11 runs on Apify's addresses on 2026-11-08 made 241 calls, 130 of them for job details, and none was refused. Runs on Apify share addresses, though. Naukri Jobs Scraper then tries again, keeps every job it read, says so in its message and `OUTPUT`, and saves jobs without details when only the details were refused. To move a run to fresh addresses, turn on Apify Proxy in Connection (`proxyConfiguration`).

### How do I get every job of one company?

Type the company's name, as Naukri writes it, in Only these companies (`companies`), such as Infosys or Tata Consultancy Services, or paste its Naukri company page link, and set Number of jobs (`maxJobs`) to 0. Naukri Jobs Scraper finds the company in Naukri's company list and reads only its jobs.

### How do I check a list of job links?

Paste Naukri job links or 12-digit job IDs into Job links to check (`jobUrls`), one per line, instead of searching. Naukri Jobs Scraper reads each job's page: an open job comes back with all its fields, an expired one as closed. Naukri answers a job that closed and an ID that never existed the same way, so both come back closed.

### How do I call it from the API, Python, JavaScript, n8n or an AI agent?

Naukri Jobs Scraper runs from the Apify API, Python, JavaScript, n8n, Make or an AI agent over MCP. Each way uses your Apify token (Apify Console, Settings, API & Integrations) and takes the input as JSON keyed by the field names, such as `searchTerms` and `maxJobs`.

**API.** One call runs the actor and returns its rows (Apify waits up to 300 seconds; for runs of thousands of jobs, use a client below):

```bash
curl -X POST "https://api.apify.com/v2/acts/anshumanatrey~naukri-jobs-search/run-sync-get-dataset-items" \
  -H "Authorization: Bearer <YOUR_APIFY_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{"searchTerms": ["python developer"], "location": ["Bangalore"]}'
```

**Python** (`pip install apify-client`):

```python
from apify_client import ApifyClient

client = ApifyClient("<YOUR_APIFY_TOKEN>")
run = client.actor("anshumanatrey/naukri-jobs-search").call(run_input={"searchTerms": ["python developer"]})
for row in client.dataset(run.default_dataset_id).iterate_items():  # apify-client 3+; on 2.x use run["defaultDatasetId"]
    print(row["title"], row["company"], row["location"], row["experience"], row["salary"], row["jobUrl"])
```

**JavaScript** (`npm install apify-client`):

```js
import { ApifyClient } from 'apify-client';

const client = new ApifyClient({ token: '<YOUR_APIFY_TOKEN>' });
const run = await client.actor('anshumanatrey/naukri-jobs-search').call({ searchTerms: ['python developer'] });
const { items } = await client.dataset(run.defaultDatasetId).listItems();
for (const row of items) console.log(row.title, row.company, row.location, row.experience, row.salary, row.jobUrl);
```

**n8n and Make.** In n8n, add the Apify node, pick Run an Actor and get dataset, choose this actor and paste the input JSON: the rows come out as n8n items. In Make, the Apify app's Run an Actor and Get Dataset Items modules do the same.

**AI agents (MCP).** Add `https://mcp.apify.com?tools=anshumanatrey/naukri-jobs-search` to your MCP client and sign in with Apify, or send `Authorization: Bearer <YOUR_APIFY_TOKEN>`. The agent gets this actor as a tool and sees every input field by its JSON key.

### Am I charged for closed jobs?

Naukri Jobs Scraper charges for a closed job only when you paste its link to check. A search returns open jobs only, and a pasted link that turns out closed is one Job row, because it was checked and answered.

### Is it legal to use?

Naukri Jobs Scraper reads public job postings, the pages any visitor sees without logging in. It is not affiliated with Naukri or Info Edge. You are responsible for how you use the data, including Naukri's terms and the privacy laws that apply to you.

## Limitations

- Naukri shows at most 15,000 jobs for one search (150 pages of 100). A search with no words, place or company reads the jobs posted in the last 30 days, because Naukri answers its whole list unevenly (four calls in a row listed 511,439 to 692,506 jobs); the newest 15,000 of all Naukri are under two days old.
- Naukri's list gives an internship no posting date, so its `postedAt` is the day it was first listed (from its ID). Naukri orders internships by a later repost date it does not show, so a reposted internship can rank lower here than on Naukri (2 of Naukri's 20 newest marketing internships on 2026-11-08). Full details carry the real date.
- Job type is on the job's own page only, except internships, which Naukri marks in its list. Picking full-time, part-time, contract or temporary opens each job whose title matches, up to 300 a run.
- Company type and who posted a job are Naukri's own filters; the list does not show them, so they are not checked again here (who posted it comes with full details).
- Naukri limits each address; a refused run keeps what it read and says so (see above). Full details make one call per job, so large runs with details meet the limit sooner.
- Pay is shown on about half to two thirds of jobs; the rest say "Not disclosed".
- A job that states no experience is left out once you type an Experience (`experienceYears`). On Naukri that is every internship: its list states none (32 of 32 internships on 2026-11-08, against every one of 3,987 other jobs stating a range), so leave Experience empty when you pick intern in Job type (`employmentType`).
- A place abroad that Naukri writes without its country (Dubai, London) has no country in the row: India leaves it out, and the country's name does not find it, so type the city. A part of a city that is not on Naukri's city list (Powai, Koramangala) has no state either, so a search for its state leaves the job out unless the job also names its city; a search for the place itself finds it.
- A job posted twice by one company at one place, with the same experience and pay, is delivered once, the newest.
- Titles and descriptions are as the employer wrote them, almost all in English.

## Who maintains it?

Built and maintained by **Anshuman Atrey** ([@AnshumanAtrey](https://github.com/AnshumanAtrey)), who publishes a portfolio of data and OSINT actors on Apify Store. For a feature request or a bug, message [LinkedIn](https://linkedin.com/in/anshumanatrey) (fastest), open an issue on the GitHub repo, or write through [atrey.dev](https://atrey.dev).

## Sibling actors

| Actor | What it searches |
|---|---|
| [Greenhouse Jobs Scraper](https://apify.com/anshumanatrey/greenhouse-jobs-search) | Jobs from every company on Greenhouse, searched live |
| [Lever Jobs Scraper](https://apify.com/anshumanatrey/lever-jobs-search) | Jobs from 2,300+ companies on Lever (jobs.lever.co), searched live |
| [Workday Jobs Scraper](https://apify.com/anshumanatrey/workday-job-search) | Jobs from every company on Workday (myworkdayjobs.com), searched live |
| [Ashby Jobs Scraper](https://apify.com/anshumanatrey/ashby-jobs-search) | Jobs from every company on Ashby (jobs.ashbyhq.com), searched live |
| [SmartRecruiters Jobs Scraper](https://apify.com/anshumanatrey/smartrecruiters-jobs-search) | Jobs from 2,900+ companies on SmartRecruiters, searched live |
| [Workable Jobs Scraper](https://apify.com/anshumanatrey/workable-job-search) | Jobs from every company on Workable, in one search |
| [Cornerstone Jobs Scraper](https://apify.com/anshumanatrey/cornerstone-jobs-search) | Jobs from every company on Cornerstone (csod.com), searched live |
| [Deel Jobs Scraper](https://apify.com/anshumanatrey/deel-jobs-search) | Jobs from every company on Deel ATS (jobs.deel.com), with pay |

For the people behind a company: [LinkedIn Profile Finder](https://apify.com/anshumanatrey/linkedin-harvester) turns an email into a public LinkedIn profile.

## Documentation

- Apify Store: https://apify.com/anshumanatrey/naukri-jobs-search
- GitHub repo: https://github.com/AnshumanAtrey/naukri-jobs-search (MIT license, see [LICENSE](LICENSE))
- The engine behind it: https://github.com/AnshumanAtrey/ats-jobs-engine

## Last updated

2026-11-08 (version 1.0)
