# Dev Pulse

Weekly GitHub activity reports for [@unhappychoice](https://github.com/unhappychoice), powered by [github-weekly-reporter](https://github.com/deariary/github-weekly-reporter).

## Live Reports

https://unhappychoice.github.io/weekly-report

## Profile Card

Add this to your [GitHub Profile README](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme):

```html
<a href="https://github.com/unhappychoice/weekly-report">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://unhappychoice.github.io/weekly-report/card-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://unhappychoice.github.io/weekly-report/card.svg" />
    <img alt="Weekly Report" src="https://unhappychoice.github.io/weekly-report/card.svg" />
  </picture>
</a>
```

## How It Works

1. **Daily** (automatic): A scheduled workflow collects your GitHub events at midnight (Asia/Tokyo).
2. **Weekly** (manual): Trigger the workflow with `mode: weekly` from the [Actions tab](https://github.com/unhappychoice/weekly-report/actions) to generate a full report with AI narrative.
3. The report is deployed to GitHub Pages automatically.

## Configuration

Edit `.github/workflows/weekly-report.yml` to change:

| Setting | Current | Description |
|---------|---------|-------------|
| `username` | `unhappychoice` | GitHub user to report on |
| `language` | `en` | Report language (en, ja, zh-CN, zh-TW, ko, es, fr, de, pt, ru) |
| `timezone` | `Asia/Tokyo` | IANA timezone for date calculations |
| `theme` | `brutalist` | Report theme (brutalist, minimal, editorial) |
| `SITE_TITLE` | `Dev Pulse` | Site title in the header and hero |
| `llm-provider` | `openrouter` | LLM provider for AI narrative |
| `llm-model` | `stepfun/step-3.5-flash:free` | Model name |

## Base URL

The report's canonical URL, OG images, and sitemap are generated using `BASE_URL`.
By default this is derived automatically from the repository name:

```
https://unhappychoice.github.io/weekly-report
```

If you use a **custom domain**, add `BASE_URL` to the workflow env:

```yaml
env:
  SITE_TITLE: 'Dev\nPulse'
  BASE_URL: 'https://your-custom-domain.com'
```

Then configure the custom domain in **Settings > Pages > Custom domain**.

## Changing the LLM API Key

1. Go to **Settings > Secrets and variables > Actions**
2. Update the `OPENROUTER_API_KEY` secret

## Manual Report Generation

Go to [Actions](https://github.com/unhappychoice/weekly-report/actions), click **Weekly Report**, then **Run workflow** with `mode: weekly`.

---

Supported by [deariary](https://deariary.com)
