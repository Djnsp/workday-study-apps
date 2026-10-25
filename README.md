# Workday Study Apps — GitHub Pages setup

This package contains the Extend Study Lab (250 questions) and the newer Integration Practice Lab (259 questions). The homepage opens either app. All app code, styling, and question data are included in the two HTML files; no installation or build command is needed.

## 1. Extract the download

On Windows, right-click `Workday_Study_Apps_GitHub.zip`, choose **Extract All**, and open the extracted `workday-study-apps` folder.

| File | Purpose |
| --- | --- |
| `index.html` | Homepage with links to both apps |
| `extend/index.html` | Complete Extend app |
| `integration/index.html` | Complete Integration app |
| `.nojekyll` | Publishes the static files directly |
| `README.md` | These instructions |

You can double-click the homepage to use both apps locally before uploading.

## 2. Create a GitHub repository

Sign in to https://github.com and create a repository named `workday-study-apps`. For the standard GitHub Free Pages setup, choose **Public** and initialize it with a README so the `main` branch exists.

The standard Pages setup publishes the apps and their embedded question banks on the internet. Choose this setup only if you intend that audience. A private repository does not by itself make its Pages website private. The ChatGPT-hosted versions retain their own access settings.

## 3. Upload the extracted contents

In the new repository, select **Add file → Upload files**. Drag in the contents of the extracted folder: `index.html`, `extend`, `integration`, `.nojekyll`, and `README.md`. Commit them to `main` using a message such as `Add study apps`. If GitHub instead opens a pull request, merge it into `main`.

Upload the extracted files and folders, not the ZIP. Do not put the enclosing `workday-study-apps` folder inside the repository. At the repository's top level you should see `index.html`, `extend`, and `integration`.

If `.nojekyll` is missing from the upload, choose **Add file → Create new file**, name it `.nojekyll`, and commit it. It can be empty. Keep the supplied folder names unchanged.

## 4. Enable GitHub Pages

Open **Settings → Pages** and set:

| Setting | Value |
| --- | --- |
| Source | Deploy from a branch |
| Branch | main |
| Folder | /(root) |

Click **Save**. Publication can take up to 10 minutes. Use **Visit site** on the Pages settings screen to open the actual address assigned by GitHub.

For a repository named `workday-study-apps`, the usual URL pattern is:

```text
https://YOUR-USERNAME.github.io/workday-study-apps/
```

Replace `YOUR-USERNAME` with your GitHub username. Direct app URLs use `/extend/` and `/integration/` after the repository name. The relative links in this package also work if you choose a different repository name.

## Updating or adding apps

- To update Extend, replace `extend/index.html` with the new complete HTML and commit.
- To update Integration, replace `integration/index.html` and commit.
- To add another self-contained HTML app, create a new folder such as `extend-advanced`, put its HTML inside as `index.html`, and add a link to the root homepage: `<a href="./extend-advanced/index.html">Open advanced app</a>`.
- For an app with separate JavaScript, CSS, or data files, copy all required assets into its folder and preserve relative paths. Do not copy just its HTML entry file.
- For two separate repositories instead, upload the desired app's `index.html` at that repository's root with `.nojekyll`, then use the same Pages settings.

GitHub Pages republishes after commits to the configured source. No GitHub Actions workflow file, package manager, or terminal command is required for these apps.

## Progress and references

The two apps use different browser-storage keys. Progress belongs to the browser and website origin; it does not automatically move from the ChatGPT site or downloaded HTML to GitHub Pages. Export a backup in each existing app, then import it into the corresponding GitHub-hosted app.

The Extend export retains the supplied-document source labels but removes private ChatGPT Library hyperlinks. The uploaded PDFs, spreadsheet, and course manuals are not bundled. Official Workday reference links remain available and may require sign-in.

The examples and questions are independent study material, not an official certification bank. The answer keys are part of the HTML, so these apps are for practice rather than supervised assessments.

## Troubleshooting

| Problem | Check |
| --- | --- |
| GitHub shows the ZIP as a download | Extract it and upload the actual files. |
| Homepage gives 404 | Confirm root `index.html`, branch `main`, and folder `/(root)`. |
| App link gives 404 | Confirm `extend/index.html` and `integration/index.html` exist with exactly those lowercase names. |
| Old version still appears | Wait for the Pages deployment to finish, then refresh the browser. |
| Pages deployment fails | Open the repository's Actions tab and inspect the Pages run's reported error. |
| Progress appears empty | Import a backup from the original app; different website addresses have separate browser storage. |
| Official reference needs login | Use your authorized Workday account; the embedded app lessons still work offline. |

## Official GitHub instructions

Instructions checked October 25, 2026:

- [Create a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [Configure the publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Upload files to a repository](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)
