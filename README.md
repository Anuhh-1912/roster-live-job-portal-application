# Roster: Live Job Portal

Roster is a job portal that shows **real, current job openings** pulled from public job boards. Every listing shows the **workplace**, the **average salary** (when the employer shares it) and the **time commitment**. Open a role to read the full description and prepare your application with a resume.

The whole project is a single `index.html` file. There is nothing to install and no build step.

## Screenshots

| Home: live jobs, search and filters | Job details |
|---|---|
| ![Home page](screenshots/01-home.png) | ![Job details](screenshots/02-job-details.png) |

| Application form with resume upload | Application ready |
|---|---|
| ![Apply form](screenshots/03-apply-form.png) | ![Application ready](screenshots/04-application-ready.png) |

## Features

- **Live job listings** from several public job boards, updated whenever you open the site
- **Clear job list** showing workplace, average salary and time commitment for each role
- **Search** by job title, skill, company or location, plus quick shortcuts (Remote, Full-time, Nurse, Sales and more)
- **Filters** for category, time commitment, workplace, job board, date posted and minimum yearly salary
- **Sorting** by newest, highest average salary or company name
- **Job details page** with the full role description, company information and other open roles from the same employer
- **Application form** that asks for your details and a resume (PDF, DOC, DOCX or RTF, up to 5 MB), with clear validation messages
- **Reusable profile**: your details and resume are remembered on your device for next time
- **My jobs**: save roles and track your applications as Prepared or Submitted
- **Downloads**: get your resume and an application summary at any time
- **Responsive** layout for phones, tablets and desktops

## Job sources

| Source | Type | Notes |
|---|---|---|
| [Remotive](https://remotive.com) | Remote jobs worldwide | Often includes salary |
| [Arbeitnow](https://www.arbeitnow.com) | Europe and remote | |
| [Jobicy](https://jobicy.com) | Remote jobs worldwide | Includes salary ranges |
| [Federal Employment Agency of Germany](https://www.arbeitsagentur.de) | Government job board | Listings are in German. Availability depends on your browser and network. |
| [Adzuna](https://developer.adzuna.com) (optional) | India, US, UK and more | Needs a free key, see below |

If a source can't be reached, Roster simply shows the others. Results are cached in your browser for 3 hours to stay within the free usage limits of these job boards.

> Google Jobs has no public data feed, and USAJOBS requires a registered key plus request headers that browsers cannot send, so neither is included.

## Run it

**Option 1: open the file.** Download or clone this repository and double-click `index.html`.

**Option 2: VS Code.** Open the folder, install the *Live Server* extension, then right-click `index.html` and choose **Open with Live Server**.

**Option 3: publish it free with GitHub Pages.**
1. Push this repository to GitHub.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then **Save**.
4. After a minute your site is live at `https://<your-username>.github.io/<repository-name>/`.

An internet connection is required because the jobs are loaded live.

## Add India, US or UK jobs (optional)

1. Create a free account at [developer.adzuna.com](https://developer.adzuna.com) and copy your **App ID** and **App Key**.
2. Open `index.html` and find this line near the top of the script:

   ```js
   const CONFIG = { adzuna: { appId: "", appKey: "", country: "in" } };
   ```

3. Paste your credentials and set `country` (`in`, `us`, `gb`, `au`, `ca`, `de`, `fr` and others).

> Your key will be visible to anyone who views the page. Only add it to a copy you run privately, or use a key you are happy to rotate.

## How applications work

Roster helps you prepare and track applications. Employers only receive an application through **their own official page**, so Roster does not send anything to them on your behalf.

1. Press **Apply now** and fill in your details.
2. Attach your resume.
3. Roster saves the application and shows a ready-to-use pack: your resume, a summary and a cover letter you can copy.
4. Press **Continue to the employer's page** to submit there, then mark the application as submitted.

## Privacy

Everything you enter stays **in your own browser** (local storage on your device). Roster has no server and does not upload your details or resume anywhere.

## Project structure

```
roster-job-portal/
├── index.html        The complete application
├── README.md         This file
└── screenshots/      Images used in this README
```

## Known limitations

- Average salary is only shown when the employer publishes pay. Some boards, such as Arbeitnow, rarely do.
- Listings from the German government job board are in German.
- Saved jobs and resumes are stored per browser and per device.

## Credits

Job data is provided by Remotive, Arbeitnow, Jobicy and the Federal Employment Agency of Germany. Each listing links back to its original posting. Please respect each provider's terms of use if you build on this project.
