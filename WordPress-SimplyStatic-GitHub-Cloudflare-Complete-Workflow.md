# WordPress → Simply Static → VS Code → GitHub → Cloudflare Pages
## Complete Reusable Workflow Guide

## Quick Index

Use this index as the starting point when you need a specific answer fast. The section numbers are stable, so you can also use `Ctrl+F` and search for the exact section title or keyword.

### Start Here

| Need | Go to |
|---|---|
| Understand what this workflow is for | [1. Project Overview](#1-project-overview) |
| See the final architecture | [2. Final Architecture](#2-final-architecture) |
| Check the tools used | [3. Technology Stack](#3-technology-stack) |
| Understand why this workflow was chosen | [4. Why This Approach Was Used](#4-why-this-approach-was-used) |
| Understand the core mental model | [5. The Important Mental Model](#5-the-important-mental-model) |
| Get the short version | [78. Quick Memory Version](#78-quick-memory-version) |
| Follow the final recommended process | [82. Final Recommended Workflow](#82-final-recommended-workflow) |
| Review the biggest lessons learned | [83. Biggest Lessons from the Nexa Project](#83-biggest-lessons-from-the-nexa-project) |

### Build and Export from WordPress

| Need | Go to |
|---|---|
| Build the WordPress website | [6. Phase 1 - Build the WordPress Website](#6-phase-1-—-build-the-wordpress-website) |
| Install Simply Static | [7. Phase 2 - Install Simply Static](#7-phase-2-—-install-simply-static) |
| Understand the failed ZIP export | [8. First Export Attempt - ZIP](#8-first-export-attempt-—-zip) |
| Use the final local directory export method | [9. Final Simply Static Export Method - Local Directory](#9-final-simply-static-export-method-—-local-directory) |
| Configure URL replacement | [10. URL Replacement Settings](#10-url-replacement-settings) |
| Recover files from `htdocs` | [19. Recovering the Complete Static Site from htdocs](#19-recovering-the-complete-static-site-from-htdocs) |
| Prepare the final local static folder | [20. Final Local Cloudflare Project Folder](#20-final-local-cloudflare-project-folder) |

### Pages, Routes, and Folder Structure

| Need | Go to |
|---|---|
| Fix missing pages | [11. Missing Pages Problem](#11-missing-pages-problem) |
| Understand anchors vs pages | [12. Do Not Treat Anchors as Separate Pages](#12-do-not-treat-anchors-as-separate-pages) |
| Check the correct static folder structure | [13. Correct Static Folder Structure](#13-correct-static-folder-structure) |
| Verify pages before deployment | [14. Verify Every Important Page Before Deployment](#14-verify-every-important-page-before-deployment) |
| Fix Cloudflare showing only the home page | [15. Important Troubleshooting Lesson - Cloudflare Only Showed Home](#15-important-troubleshooting-lesson-—-cloudflare-only-showed-home) |
| Test every live route | [36. Test Every Route](#36-test-every-route) |

### Video and Media Fixes

| Need | Go to |
|---|---|
| Optimize videos with HandBrake | [21. Video Optimization with HandBrake](#21-video-optimization-with-handbrake) |
| Preserve video filenames | [22. Preserve Existing Video Filenames](#22-preserve-existing-video-filenames) |
| Use JPG poster images | [23. JPG Poster Images](#23-jpg-poster-images) |
| Understand the Elementor static video issue | [24. Critical Elementor Static Video Problem](#24-critical-elementor-static-video-problem) |
| Fix empty Elementor videos | [25. Fix for Empty Elementor Videos](#25-fix-for-empty-elementor-videos) |
| Understand custom HTML videos | [26. Custom HTML Videos Were Different](#26-custom-html-videos-were-different) |
| Fix mobile hidden video issues | [27. Mobile Video Problem - elementor-hidden-mobile](#27-mobile-video-problem-—-elementor-hidden-mobile) |
| Use full-screen video CSS | [28. Useful Full-Screen Video CSS](#28-useful-full-screen-video-css) |

### Cloudflare Pages and Wrangler

| Need | Go to |
|---|---|
| Start Cloudflare Pages setup | [29. Phase 3 - Cloudflare Pages](#29-phase-3-—-cloudflare-pages) |
| Understand why Wrangler was used | [30. Why Wrangler Was Used](#30-why-wrangler-was-used) |
| Open Command Prompt in the static root | [31. Open Command Prompt in the Static Root](#31-open-command-prompt-in-the-static-root) |
| Log in to Cloudflare with Wrangler | [32. Cloudflare Login with Wrangler](#32-cloudflare-login-with-wrangler) |
| Create the Cloudflare Pages project | [33. Create the Cloudflare Pages Project](#33-create-the-cloudflare-pages-project) |
| Deploy manually | [34. Manual Cloudflare Deployment](#34-manual-cloudflare-deployment) |
| Confirm the successful Nexa deployment | [35. Successful Nexa Deployment](#35-successful-nexa-deployment) |
| Find Cloudflare account ID and token steps | [49. Cloudflare Account ID](#49-cloudflare-account-id), [50. Cloudflare API Token](#50-cloudflare-api-token) |

### VS Code, Git, and GitHub

| Need | Go to |
|---|---|
| Understand VS Code as the static editor | [37. Phase 4 - VS Code Becomes the Main Static Editor](#37-phase-4-—-vs-code-becomes-the-main-static-editor) |
| Decide the source of truth | [38. Important Source-of-Truth Decision](#38-important-source-of-truth-decision) |
| Understand the danger of re-exporting | [39. Warning About Re-Exporting from WordPress](#39-warning-about-re-exporting-from-wordpress) |
| Start Git and GitHub setup | [40. Phase 5 - Git and GitHub](#40-phase-5-—-git-and-github) |
| Check if the folder is already inside another Git repo | [41. Check Whether the Static Folder Is Already Inside Another Git Repository](#41-check-whether-the-static-folder-is-already-inside-another-git-repository) |
| Make the static folder its own Git repo | [42. Make the Static Folder Its Own Git Repository](#42-make-the-static-folder-its-own-git-repository) |
| Connect the local project to GitHub | [43. Connect the Local Project to GitHub](#43-connect-the-local-project-to-github) |
| Check Git status | [44. Git Status](#44-git-status) |
| Keep `.wrangler/` out of Git | [45. .wrangler/ Should Not Be Committed](#45-wrangler-should-not-be-committed) |
| Check for large GitHub files | [46. Check for Very Large GitHub Files](#46-check-for-very-large-github-files) |
| Make the first commit | [47. First Git Commit](#47-first-git-commit) |

### GitHub Actions and Automatic Deployment

| Need | Go to |
|---|---|
| Start automatic GitHub to Cloudflare deployment | [48. Phase 6 - Automatic GitHub -> Cloudflare Deployment](#48-phase-6-—-automatic-github-→-cloudflare-deployment) |
| Add GitHub repository secrets | [51. GitHub Repository Secrets](#51-github-repository-secrets) |
| Create the workflow folder | [52. GitHub Actions Workflow Folder](#52-github-actions-workflow-folder) |
| Add the GitHub Actions workflow | [53. GitHub Actions Workflow](#53-github-actions-workflow) |
| Commit the GitHub Action | [54. Commit the GitHub Action](#54-commit-the-github-action) |
| Understand what happens after a push | [55. What Happens After a Push](#55-what-happens-after-a-push) |

### Daily Workflow, Backups, and Commands

| Need | Go to |
|---|---|
| Follow the normal update process | [56. Normal Day-to-Day Workflow](#56-normal-day-to-day-workflow) |
| Deploy manually in an emergency | [57. Manual Emergency Deployment](#57-manual-emergency-deployment) |
| Use common Git commands | [58. Useful Git Commands](#58-useful-git-commands) |
| Back up before risky changes | [59. Backup Before Risky Changes](#59-backup-before-risky-changes) |
| Use reusable command snippets | [79. Reusable Commands](#79-reusable-commands) |
| Run the pre-deployment checklist | [80. Pre-Deployment Checklist](#80-pre-deployment-checklist) |

### Troubleshooting Index

| Problem | Go to |
|---|---|
| Home page works but other pages do not | [60. Troubleshooting - Home Works but Other Pages Do Not](#60-troubleshooting-—-home-works-but-other-pages-do-not) |
| Video does not play | [61. Troubleshooting - Video Does Not Play](#61-troubleshooting-—-video-does-not-play) |
| Desktop video works but mobile does not | [62. Troubleshooting - Desktop Video Works but Mobile Does Not](#62-troubleshooting-—-desktop-video-works-but-mobile-does-not) |
| Poster image does not show | [63. Troubleshooting - Poster Does Not Show](#63-troubleshooting-—-poster-does-not-show) |
| Video file is too large | [64. Troubleshooting - Video Is Too Large](#64-troubleshooting-—-video-is-too-large) |
| Wrangler Git warning appears | [65. Troubleshooting - Wrangler Git Warning](#65-troubleshooting-—-wrangler-git-warning) |
| Wrong Git folder is being used | [66. Troubleshooting - Wrong Git Folder](#66-troubleshooting-—-wrong-git-folder) |
| `.wrangler/` appears in Git | [67. Troubleshooting - .wrangler/ Appears in Git](#67-troubleshooting-—-wrangler-appears-in-git) |
| GitHub push does not deploy | [68. Troubleshooting - GitHub Push Does Not Deploy](#68-troubleshooting-—-github-push-does-not-deploy) |
| GitHub Action authentication fails | [69. Troubleshooting - GitHub Action Authentication Fails](#69-troubleshooting-—-github-action-authentication-fails) |
| Live changes are not visible | [70. Troubleshooting - Live Changes Are Not Visible](#70-troubleshooting-—-live-changes-are-not-visible) |

### Next Website Planning

| Need | Go to |
|---|---|
| Recommended process for the next website | [71. Recommended Process for the Next Website](#71-recommended-process-for-the-next-website) |
| Cleaner GitHub-first future option | [72. Cleaner Future Option - GitHub First](#72-cleaner-future-option-—-github-first) |
| Recommended folder organization | [73. Recommended Project Folder Organization](#73-recommended-project-folder-organization) |
| Recommended naming | [74. Recommended Naming](#74-recommended-naming) |
| Security rules | [75. Security Rules](#75-security-rules) |
| When this architecture is a good choice | [76. When This Architecture Is a Good Choice](#76-when-this-architecture-is-a-good-choice) |
| When not to use this architecture | [77. When Not to Use This Architecture](#77-when-not-to-use-this-architecture) |
| Nexa Advisory project reference details | [81. Nexa Advisory Reference Snapshot](#81-nexa-advisory-reference-snapshot) |

### Keyword Finder

Search these exact terms with `Ctrl+F`:

| Search for | When you need |
|---|---|
| `Simply Static` | Export settings, local directory export, WordPress conversion |
| `htdocs` | Recovering the full static site from InfinityFree |
| `URL Replacement` | Fixing wrong local/live URLs |
| `index.html` | Static folder structure and route problems |
| `elementor-hidden-mobile` | Mobile video visibility problems |
| `HandBrake` | Video compression and optimization |
| `poster` | Video fallback images |
| `Wrangler` | Manual Cloudflare deployment |
| `CLOUDFLARE_API_TOKEN` | GitHub Actions authentication |
| `.wrangler` | Files that should not be committed |
| `git status` | Checking changed files |
| `git remote` | Checking GitHub connection |
| `GitHub Actions` | Automatic deployment setup |
| `secrets` | GitHub repository secret setup |
| `source of truth` | Deciding whether WordPress or VS Code is the master |
| `pre-deployment` | Final checklist before publishing |

> **Purpose**
>
> This document records the full process used for the **Nexa Advisory** demo website so the same workflow can be reused later for a completely different WordPress website.
>
> It covers:
>
> - the website and technology stack;
> - how the WordPress site was built;
> - how Simply Static was used;
> - what went wrong with the ZIP export;
> - how the final static website folder was prepared;
> - how we checked page routing;
> - how videos were optimized and fixed;
> - how Cloudflare Pages was configured;
> - how Wrangler was used;
> - how the static site was moved into VS Code;
> - how Git and GitHub were connected;
> - how GitHub Actions was linked to Cloudflare;
> - how normal future updates now work;
> - the mistakes and troubleshooting lessons from the Nexa project;
> - the cleaner process recommended for the next website.

---

# 1. Project Overview

The project was a demo corporate website for:

```text
Nexa Advisory
```

The website was built as a premium professional advisory/corporate site with:

```text
Home
About
Services
Case Studies
Contact
Demo
```

The site used:

- full-screen video sections;
- custom navigation;
- responsive desktop/mobile layouts;
- custom HTML;
- custom CSS;
- custom JavaScript;
- Elementor;
- background video;
- JPG poster/fallback images;
- corporate content sections;
- call-to-action sections.

The website was originally developed using WordPress, but the final public demo website was converted into a static website.

---

# 2. Final Architecture

The final architecture became:

```text
WORDPRESS / ELEMENTOR
        ↓
SIMPLY STATIC
        ↓
STATIC HTML / CSS / JS / MEDIA
        ↓
LOCAL STATIC PROJECT FOLDER
        ↓
VISUAL STUDIO CODE
        ↓
GIT
        ↓
GITHUB
        ↓
GITHUB ACTIONS
        ↓
WRANGLER
        ↓
CLOUDFLARE PAGES
        ↓
LIVE DEMO WEBSITE
```

For Nexa Advisory:

```text
Cloudflare Pages project:
nexa-advisory

Production branch:
main

Production URL:
https://nexa-advisory.pages.dev

GitHub repository:
NiyaazZSB/Nexa-Advisory-Wordpress-site-backup
```

---

# 3. Technology Stack

## Website Builder

```text
WordPress
Elementor
```

WordPress/Elementor was used to visually construct the website.

---

## Front-End Technologies

```text
HTML
CSS
JavaScript
```

A large portion of the final design and behavior was also built using custom code.

---

## Static Site Export

```text
Simply Static
```

Simply Static converted the WordPress website into files that could run without WordPress hosting.

---

## Code Editor

```text
Visual Studio Code
```

Once the static site was working, VS Code became the main editing environment.

---

## Video Optimization

```text
HandBrake
```

HandBrake was used to reduce the size of MP4 background videos.

---

## Version Control

```text
Git
GitHub
```

Git tracks the history of changes.

GitHub stores the project online.

---

## Hosting

```text
Cloudflare Pages
```

Cloudflare Pages hosts the static website.

---

## Deployment Tool

```text
Wrangler
```

Wrangler is the Cloudflare command-line deployment tool used during setup and manual deployment.

---

## Continuous Deployment

```text
GitHub Actions
Cloudflare Wrangler Action
```

After automation was configured, every push to GitHub could automatically update the live Cloudflare Pages site.

---

# 4. Why This Approach Was Used

The goal was to have:

- free or extremely low-cost demo hosting;
- HTTPS;
- a professional public demo link;
- good performance;
- desktop and mobile support;
- GitHub version control;
- easy future changes;
- automatic deployments;
- no requirement for paid WordPress hosting for a brochure/demo site.

This architecture is especially useful for:

```text
business brochure websites
portfolio websites
marketing sites
landing pages
demo client websites
proof-of-concept websites
static corporate websites
```

It is not automatically suitable for features that require a live WordPress/PHP/database backend.

Examples:

```text
WooCommerce checkout
WordPress login
member portals
WordPress comments
database-driven forms
server-side plugins
dynamic WordPress search
```

---

# 5. The Important Mental Model

Think about the workflow like this:

```text
WordPress = visual design/build environment

Simply Static = converter/exporter

Static folder = actual final website files

VS Code = editing environment after export

GitHub = project history + remote repository

Cloudflare Pages = public website hosting
```

Visitors to the final Cloudflare site do not access the WordPress installation.

They receive:

```text
HTML
CSS
JavaScript
JPG
PNG
MP4
fonts
other static assets
```

---

# 6. Phase 1 — Build the WordPress Website

The first stage is normal WordPress development.

A local WordPress environment can be used, for example:

```text
LocalWP
```

Example local site:

```text
http://my-company.local
```

Build the website normally using Elementor.

Example pages:

```text
/
about/
services/
case-studies/
contact/
demo/
```

Complete:

- desktop layout;
- mobile layout;
- navigation;
- content;
- buttons;
- images;
- videos;
- custom CSS;
- custom JavaScript.

Do as much design work as possible before exporting.

---

# 7. Phase 2 — Install Simply Static

Inside WordPress:

```text
Plugins
→ Add New
→ Search for "Simply Static"
→ Install
→ Activate
```

Then open Simply Static from the WordPress admin area.

For the Nexa project, Simply Static 3.8.x was used during the process.

---

# 8. First Export Attempt — ZIP

The first idea was to generate a ZIP archive.

Simply Static successfully crawled almost the whole site, but the ZIP export failed near the end.

The export had processed thousands of URLs/files, but Simply Static reported that some files could not be added to the ZIP archive.

This became an important lesson:

> For large WordPress/Elementor static exports, a Local Directory export can be more reliable than depending on a giant ZIP archive.

---

# 9. Final Simply Static Export Method — Local Directory

The more reliable method used was:

```text
Simply Static
→ Deployment Method
→ Local Directory
```

A dedicated export directory was used.

Example future location:

```text
C:\Websites\MyCompany-Static\
```

Simply Static then directly created the static website files in that directory.

During the successful Nexa export, roughly:

```text
1843 URLs were fetched
1842 files were transferred
```

The exact number is not important for future projects.

The important point is that the Local Directory export completed successfully.

---

# 10. URL Replacement Settings

A portable relative-path configuration was used.

The important Simply Static settings were approximately:

```text
Replacing URLs:
Relative Path

Path:
/

Force URL replacements:
ON
```

This produced links like:

```html
<a href="/about/">
```

and assets like:

```html
src="/wp-content/uploads/2026/08/example.jpg"
```

This is helpful because the static files can be moved from one domain/host to another without changing every URL.

---

# 11. Missing Pages Problem

The first successful static export did not contain every important page.

Initially the export mostly had:

```text
index.html
wp-content/
wp-includes/
```

Some page folders were missing.

To fix this, Simply Static's **Additional URLs / Include** area was used.

We explicitly added:

```text
http://nexa-advisory.local/
http://nexa-advisory.local/about/
http://nexa-advisory.local/services/
http://nexa-advisory.local/case-studies/
http://nexa-advisory.local/contact/
http://nexa-advisory.local/demo/
```

Then the static site was regenerated.

After that, the export contained folders such as:

```text
about/
services/
case-studies/
contact/
demo/
wp-content/
wp-includes/
index.html
```

---

# 12. Do Not Treat Anchors as Separate Pages

An anchor such as:

```text
/services/#digital-transformation
```

is normally still part of:

```text
/services/
```

It should not normally be added as a separate page in Simply Static.

---

# 13. Correct Static Folder Structure

The final static website should look roughly like this:

```text
Static Website/
│
├── index.html
│
├── about/
│   └── index.html
│
├── services/
│   └── index.html
│
├── case-studies/
│   └── index.html
│
├── contact/
│   └── index.html
│
├── demo/
│   └── index.html
│
├── wp-content/
└── wp-includes/
```

This is extremely important.

A folder existing does not mean the page exists.

For example:

```text
about/
```

is not enough.

You need:

```text
about/index.html
```

---

# 14. Verify Every Important Page Before Deployment

Open Command Prompt inside the static site folder.

In Windows File Explorer:

1. Open the static folder.
2. Click the address bar.
3. Type:

```text
cmd
```

4. Press Enter.

Then check the page files:

```cmd
dir about\index.html
dir services\index.html
dir case-studies\index.html
dir contact\index.html
```

Or:

```cmd
dir about\index.html && dir services\index.html && dir case-studies\index.html && dir contact\index.html
```

If the result says:

```text
File Not Found
```

do not deploy yet.

Fix the export/copy first.

---

# 15. Important Troubleshooting Lesson — Cloudflare Only Showed Home

When the site was first deployed to Cloudflare Pages:

```text
/
```

worked.

But:

```text
/about/
/services/
/case-studies/
/contact/
```

appeared to keep showing the Home page.

At first this looked like a Cloudflare routing problem.

It was not.

The local static folder had page directories such as:

```text
about/
```

but those directories were empty.

There was no:

```text
about/index.html
```

To confirm this, we ran:

```cmd
dir /b about
```

Nothing was returned.

That proved the directory was empty.

---

# 16. Temporary InfinityFree Hosting Stage

Before switching to Cloudflare Pages, InfinityFree was used as a temporary test host.

InfinityFree's site root was:

```text
/htdocs/
```

The static files were uploaded into:

```text
/htdocs/
```

The working structure became approximately:

```text
/htdocs/index.html
/htdocs/about/index.html
/htdocs/services/index.html
/htdocs/case-studies/index.html
/htdocs/contact/index.html
/htdocs/demo/index.html
/htdocs/wp-content/
/htdocs/wp-includes/
```

---

# 17. How the InfinityFree Files Were Uploaded

Because the static export contained many files, the upload was split into ZIP files.

Examples used:

```text
site-pages.zip
wp-content.zip
wp-includes.zip
```

These were uploaded to InfinityFree using the File Manager.

Then they were extracted into:

```text
/htdocs/
```

This worked for the temporary test version.

---

# 18. Why We Moved Away from the Free InfinityFree Domain

The free demo address was:

```text
nexa-advisory.kesug.com
```

The site worked on desktop and on phone Wi-Fi.

However, some mobile-data connections returned:

```text
ERR_NAME_NOT_RESOLVED
```

This meant the issue was related to domain/DNS/mobile network resolution rather than the website HTML.

Changing HTML or JavaScript would not solve that problem.

For future static demo websites, Cloudflare Pages is the preferred route.

InfinityFree can be treated as optional.

---

# 19. Recovering the Complete Static Site from `htdocs`

Later, the Cloudflare local project folder was missing some page files.

The InfinityFree `/htdocs` version was known to be working correctly.

So the full `htdocs` website was downloaded.

The important rule was:

> Copy everything **inside** `htdocs`, not the `htdocs` folder itself.

Correct:

```text
Cloudflare Project/
├── index.html
├── about/
├── services/
├── case-studies/
├── contact/
├── wp-content/
└── wp-includes/
```

Incorrect:

```text
Cloudflare Project/
└── htdocs/
    ├── index.html
    ├── about/
    └── services/
```

The folder containing `index.html` must be the deployment root.

---

# 20. Final Local Cloudflare Project Folder

For Nexa, a dedicated folder was used:

```text
Nexa Static Cloudfare backup
```

The intended contents were:

```text
Nexa Static Cloudfare backup/
│
├── index.html
├── about/
│   └── index.html
├── services/
│   └── index.html
├── case-studies/
│   └── index.html
├── contact/
│   └── index.html
├── demo/
│   └── index.html
├── wp-content/
└── wp-includes/
```

This folder eventually became:

- the Cloudflare deployment root;
- the VS Code project;
- the Git repository;
- the GitHub repository content.

---

# 21. Video Optimization with HandBrake

Several background videos were originally large files.

HandBrake was used to optimize them for the web.

The working starting configuration was roughly:

```text
Format:
MP4

Web Optimized:
ON

Encoder:
H.264 (x264)

Resolution Limit:
720p HD

Framerate:
Same as source

Framerate Mode:
Constant Framerate

Quality:
RF 24

Encoder Preset:
Fast

Tune:
None

Profile:
Main

Level:
4.0

Audio:
None for silent background videos
```

For short background videos:

```text
1–3 MB = excellent
3–5 MB = acceptable
larger = consider stronger compression
```

Do not destroy quality just to reach an arbitrary file size.

---

# 22. Preserve Existing Video Filenames

When replacing an existing website video, it is useful to keep the exact filename.

Example:

```text
Original:
Mixkit-Example-Video.mp4

Optimized:
Mixkit-Example-Video.mp4
```

Keep the original elsewhere as a backup.

Then the HTML path does not need to change.

---

# 23. JPG Poster Images

Every major background video was given a JPG poster/fallback image.

Examples:

```text
about-ocean-poster.jpg
services-laptop-poster.jpg
case-studies-hero-poster.jpg
contact-hero-poster.jpg
```

Example:

```html
<video
    autoplay
    muted
    playsinline
    loop
    preload="auto"
    poster="/wp-content/uploads/2026/08/example-poster.jpg"
    src="/wp-content/uploads/2026/08/example-video.mp4">
</video>
```

The behavior becomes:

```text
page opens
↓
JPG poster appears
↓
MP4 loads
↓
video starts
↓
video loops
```

No custom JavaScript is required just to provide the poster fallback.

---

# 24. Critical Elementor Static Video Problem

One of the biggest issues discovered after the WordPress export was Elementor background video behavior.

Elementor sometimes generated:

```html
<video
    class="elementor-background-video-hosted"
    role="presentation"
    autoplay
    muted
    playsinline
    loop>
</video>
```

Notice that there is no:

```text
src=
```

On normal WordPress, Elementor JavaScript may inject the video URL.

On the static site this was unreliable.

---

# 25. Fix for Empty Elementor Videos

Change the empty video to a direct source.

Example:

```html
<video
    class="elementor-background-video-hosted"
    role="presentation"
    autoplay
    muted
    playsinline
    loop
    preload="auto"
    poster="/wp-content/uploads/2026/08/example-poster.jpg"
    src="/wp-content/uploads/2026/08/example-video.mp4">
</video>
```

This makes the static HTML independent of Elementor injecting the URL later.

---

# 26. Custom HTML Videos Were Different

Some custom sections already had:

```html
<video autoplay muted loop playsinline>
    <source
        src="/wp-content/uploads/2026/08/example.mp4"
        type="video/mp4">
</video>
```

In those cases the direct source already existed.

Only poster/loading attributes needed to be added.

Example:

```html
<video
    autoplay
    muted
    loop
    playsinline
    preload="metadata"
    poster="/wp-content/uploads/2026/08/example-poster.jpg">

    <source
        src="/wp-content/uploads/2026/08/example.mp4"
        type="video/mp4">

</video>
```

---

# 27. Mobile Video Problem — `elementor-hidden-mobile`

The Case Studies hero worked on desktop but showed no video/poster on mobile.

The container included:

```html
<div class="elementor-background-video-container elementor-hidden-mobile">
```

The class:

```text
elementor-hidden-mobile
```

explicitly hides the container on mobile.

Because the poster was inside the same video container, the poster was hidden too.

If the video/poster should be visible on mobile, change:

```html
<div class="elementor-background-video-container elementor-hidden-mobile">
```

to:

```html
<div class="elementor-background-video-container">
```

Only do this where mobile playback/poster display is desired.

---

# 28. Useful Full-Screen Video CSS

A useful background video pattern:

```css
.elementor-background-video-container video {
    width: 100% !important;
    height: 100% !important;

    object-fit: cover !important;
    object-position: center center !important;
}
```

This allows the video to behave like a full-cover background.

---

# 29. Phase 3 — Cloudflare Pages

The goal was to host the static website using Cloudflare Pages.

For this demo, a custom domain was not required.

Cloudflare automatically provides a free address such as:

```text
https://project-name.pages.dev
```

For Nexa:

```text
https://nexa-advisory.pages.dev
```

---

# 30. Why Wrangler Was Used

The static WordPress export had thousands of files.

Instead of depending on Cloudflare dashboard drag-and-drop, Wrangler was used.

Wrangler could upload the entire directory from Command Prompt.

---

# 31. Open Command Prompt in the Static Root

In File Explorer, open:

```text
Nexa Static Cloudfare backup
```

Click the address bar.

Type:

```text
cmd
```

Press Enter.

The prompt should now show the static site folder path.

Example:

```text
C:\...\Nexa Static Cloudfare backup>
```

This is important.

Later:

```text
.
```

means:

> deploy the current folder.

---

# 32. Cloudflare Login with Wrangler

Run:

```cmd
npx wrangler login
```

If Wrangler needs to be installed, Windows may show:

```text
Need to install the following packages:
wrangler@...
Ok to proceed? (y)
```

Enter:

```text
y
```

A browser opens for Cloudflare authorization.

After success:

```text
Successfully logged in.
```

Wrangler may ask unrelated optional setup questions such as AI coding skill installation.

Those are not required for the website deployment.

---

# 33. Create the Cloudflare Pages Project

Run:

```cmd
npx wrangler pages project create nexa-advisory
```

For another website:

```cmd
npx wrangler pages project create YOUR-PROJECT-NAME
```

When asked:

```text
Enter the production branch name:
```

use:

```text
main
```

For Nexa, the result was the Pages project:

```text
nexa-advisory
```

---

# 34. Manual Cloudflare Deployment

The final working manual deployment command was:

```cmd
npx wrangler pages deploy . --project-name=nexa-advisory --branch=main --commit-dirty=true
```

Reusable version:

```cmd
npx wrangler pages deploy . --project-name=YOUR-PROJECT-NAME --branch=main --commit-dirty=true
```

Explanation:

```text
.
```

means the current folder.

```text
--project-name=nexa-advisory
```

chooses the Cloudflare project.

```text
--branch=main
```

deploys as the production branch.

```text
--commit-dirty=true
```

allows the deployment even if Git contains uncommitted changes.

---

# 35. Successful Nexa Deployment

Cloudflare successfully uploaded:

```text
3646 files
```

The deployment completed and Cloudflare provided a unique deployment URL.

The permanent production project URL is:

```text
https://nexa-advisory.pages.dev
```

---

# 36. Test Every Route

Always test:

```text
https://PROJECT.pages.dev/
https://PROJECT.pages.dev/about/
https://PROJECT.pages.dev/services/
https://PROJECT.pages.dev/case-studies/
https://PROJECT.pages.dev/contact/
```

Also test:

```text
desktop
mobile on Wi-Fi
mobile on 4G/5G
```

Do not assume Home working means the entire static export is correct.

---

# 37. Phase 4 — VS Code Becomes the Main Static Editor

Once the site is successfully exported and deployed, open the project in VS Code.

From Command Prompt:

```cmd
code .
```

You can now edit:

```text
index.html
about/index.html
services/index.html
case-studies/index.html
contact/index.html
CSS
JavaScript
JPG images
MP4 videos
```

---

# 38. Important Source-of-Truth Decision

Once manual static changes begin, decide which project is the master copy.

## Option A — WordPress remains the master

```text
WordPress changes
↓
Simply Static export
↓
reapply static fixes
↓
deploy
```

Useful if Elementor will continue to be used heavily.

---

## Option B — VS Code static project becomes the master

```text
WordPress initial build
↓
Simply Static once
↓
VS Code becomes main project
↓
GitHub
↓
Cloudflare
```

This is ideal if you are comfortable maintaining HTML/CSS/JS directly.

---

# 39. Warning About Re-Exporting from WordPress

A fresh Simply Static export can overwrite manual fixes such as:

```text
direct video src values
JPG poster paths
mobile video fixes
custom HTML
custom CSS
custom JavaScript
GitHub workflow files
```

Before replacing the static folder:

```cmd
git add .
git commit -m "Backup before WordPress re-export"
git push
```

Then you have a recoverable version in GitHub.

---

# 40. Phase 5 — Git and GitHub

A GitHub repository was created:

```text
NiyaazZSB/Nexa-Advisory-Wordpress-site-backup
```

The static site folder was then linked to it.

---

# 41. Check Whether the Static Folder Is Already Inside Another Git Repository

Before running `git init`, check:

```cmd
git rev-parse --show-toplevel
```

During Nexa, the command initially returned the parent:

```text
...\Word press Nexa Advisory wordpress demo
```

instead of:

```text
...\Nexa Static Cloudfare backup
```

That meant the static site was inside a bigger Git repository.

We did not want to push the whole parent directory.

---

# 42. Make the Static Folder Its Own Git Repository

While inside:

```text
Nexa Static Cloudfare backup
```

run:

```cmd
git init
```

Then verify:

```cmd
git rev-parse --show-toplevel
```

It should return the static project directory itself.

---

# 43. Connect the Local Project to GitHub

The GitHub remote used for Nexa was:

```text
https://github.com/NiyaazZSB/Nexa-Advisory-Wordpress-site-backup.git
```

Command:

```cmd
git remote add origin https://github.com/NiyaazZSB/Nexa-Advisory-Wordpress-site-backup.git
```

Verify:

```cmd
git remote -v
```

Expected structure:

```text
origin  ... (fetch)
origin  ... (push)
```

---

# 44. Git Status

Run:

```cmd
git status --short
```

Before the first commit, untracked files appear with:

```text
??
```

Example:

```text
?? about/
?? case-studies/
?? contact/
?? index.html
?? services/
?? wp-content/
?? wp-includes/
```

---

# 45. `.wrangler/` Should Not Be Committed

Wrangler created local state:

```text
.wrangler/
```

This appeared in Git status.

It should not be committed.

Create:

```text
.gitignore
```

Recommended contents:

```gitignore
.wrangler/
node_modules/
Thumbs.db
.DS_Store
```

---

# 46. Check for Very Large GitHub Files

Before pushing a site with large videos, check that no files are extremely large.

Windows command:

```cmd
powershell -NoProfile -Command "Get-ChildItem -Recurse -File | Where-Object {$_.Length -gt 95MB} | Select-Object FullName,@{N='MB';E={[math]::Round($_.Length/1MB,1)}}"
```

If no result appears, this check did not find files larger than 95 MB.

Large web videos should generally already have been compressed using HandBrake.

---

# 47. First Git Commit

Run:

```cmd
git add .
```

Then:

```cmd
git status --short
```

New staged files will show:

```text
A
```

Commit:

```cmd
git commit -m "Initial Nexa Advisory static site"
```

Set the production branch:

```cmd
git branch -M main
```

Push:

```cmd
git push -u origin main
```

---

# 48. Phase 6 — Automatic GitHub → Cloudflare Deployment

The Cloudflare project was originally created as a Direct Upload/Wrangler project.

Instead of rebuilding the project, GitHub Actions was used to automate Wrangler deployments.

The flow became:

```text
VS Code
↓
Git commit
↓
Git push
↓
GitHub Actions
↓
Wrangler
↓
Cloudflare Pages
↓
Live website updated
```

---

# 49. Cloudflare Account ID

The Cloudflare account details can be checked using:

```cmd
npx wrangler whoami
```

The Cloudflare Account ID was needed by GitHub Actions.

---

# 50. Cloudflare API Token

A Cloudflare API token was created for deployment.

Important:

> Never put the token directly into the repository, HTML, JavaScript or workflow file.

Store it as an encrypted GitHub secret.

---

# 51. GitHub Repository Secrets

Inside GitHub:

```text
Repository
→ Settings
→ Secrets and variables
→ Actions
→ Repository secrets
```

Two secrets were configured:

```text
CLOUDFLARE_ACCOUNT_ID
CLOUDFLARE_API_TOKEN
```

Their actual values must remain private.

---

# 52. GitHub Actions Workflow Folder

Inside the static project, create:

```text
.github/
└── workflows/
    └── pages-deployment.yaml
```

The `.github` folder is in the project root.

---

# 53. GitHub Actions Workflow

The Nexa deployment workflow follows this pattern:

```yaml
name: Deploy Nexa Advisory to Cloudflare Pages

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    permissions:
      contents: read
      deployments: write

    name: Deploy to Cloudflare Pages

    steps:
      - name: Checkout repository
        uses: actions/checkout@v6

      - name: Deploy to Cloudflare Pages
        uses: cloudflare/wrangler-action@v3
        with:
          apiToken: ${{ secrets.CLOUDFLARE_API_TOKEN }}
          accountId: ${{ secrets.CLOUDFLARE_ACCOUNT_ID }}
          command: pages deploy . --project-name=nexa-advisory --branch=main
          gitHubToken: ${{ secrets.GITHUB_TOKEN }}
```

For another website, replace:

```text
nexa-advisory
```

with the new Cloudflare project name.

---

# 54. Commit the GitHub Action

After creating the workflow:

```cmd
git add .
```

```cmd
git commit -m "Add automatic Cloudflare Pages deployment"
```

```cmd
git push
```

Then open:

```text
GitHub repository
→ Actions
```

The deployment should start automatically.

---

# 55. What Happens After a Push

The workflow is now:

```text
git push
↓
GitHub detects push to main
↓
GitHub Actions starts
↓
repository is checked out
↓
Wrangler deploys current repository
↓
Cloudflare Pages updates
```

---

# 56. Normal Day-to-Day Workflow

Once everything is configured, editing becomes simple.

Open the project:

```cmd
code .
```

Make changes in VS Code.

Then:

```cmd
git add .
```

Commit:

```cmd
git commit -m "Describe what changed"
```

Example:

```cmd
git commit -m "Improve mobile Services section"
```

Push:

```cmd
git push
```

That is the normal publish workflow.

No manual Cloudflare upload is required for everyday changes.

---

# 57. Manual Emergency Deployment

The manual Wrangler deployment still works if required:

```cmd
npx wrangler pages deploy . --project-name=nexa-advisory --branch=main --commit-dirty=true
```

For another site:

```cmd
npx wrangler pages deploy . --project-name=YOUR-PROJECT-NAME --branch=main --commit-dirty=true
```

This is useful for troubleshooting.

---

# 58. Useful Git Commands

Check changes:

```cmd
git status
```

Short status:

```cmd
git status --short
```

Stage all changes:

```cmd
git add .
```

Commit:

```cmd
git commit -m "Your message"
```

Push:

```cmd
git push
```

Recent history:

```cmd
git log --oneline
```

Remote:

```cmd
git remote -v
```

Repository root:

```cmd
git rev-parse --show-toplevel
```

---

# 59. Backup Before Risky Changes

Before a large change:

```cmd
git add .
git commit -m "Backup before major change"
git push
```

Then make the risky change.

This gives you a known working version in GitHub.

---

# 60. Troubleshooting — Home Works but Other Pages Do Not

Check:

```cmd
dir about\index.html
dir services\index.html
dir case-studies\index.html
dir contact\index.html
```

If those files are missing, fix the static folder before blaming Cloudflare.

---

# 61. Troubleshooting — Video Does Not Play

Inspect the HTML.

If you see:

```html
<video ...></video>
```

with no:

```text
src=
```

add the direct source manually.

Example:

```html
<video
    class="elementor-background-video-hosted"
    role="presentation"
    autoplay
    muted
    playsinline
    loop
    preload="auto"
    poster="/wp-content/uploads/2026/08/poster.jpg"
    src="/wp-content/uploads/2026/08/video.mp4">
</video>
```

---

# 62. Troubleshooting — Desktop Video Works but Mobile Does Not

Search for:

```text
elementor-hidden-mobile
```

If the video container has the class, Elementor is hiding it on phones.

Remove the class only if the design should show the video/poster on mobile.

---

# 63. Troubleshooting — Poster Does Not Show

Check:

```text
Does poster="..." exist?
Does the JPG exist at the exact path?
Is the filename correct?
Is the container hidden on mobile?
Is another layer covering the video?
```

---

# 64. Troubleshooting — Video Is Too Large

Use HandBrake again.

Start with:

```text
H.264
720p
Same as source FPS
CFR
RF 24
Web Optimized ON
No audio
```

---

# 65. Troubleshooting — Wrangler Git Warning

Wrangler may display:

```text
Your working directory is a git repo and has uncommitted changes
```

For an intentional manual deployment, use:

```cmd
npx wrangler pages deploy . --project-name=PROJECT --branch=main --commit-dirty=true
```

---

# 66. Troubleshooting — Wrong Git Folder

Run:

```cmd
git rev-parse --show-toplevel
```

If it returns a parent directory instead of the static project root, do not push.

Initialize Git in the correct folder:

```cmd
git init
```

Then verify again.

---

# 67. Troubleshooting — `.wrangler/` Appears in Git

Add:

```text
.wrangler/
```

to:

```text
.gitignore
```

---

# 68. Troubleshooting — GitHub Push Does Not Deploy

Check GitHub:

```text
Actions
```

Verify the workflow exists:

```text
.github/workflows/pages-deployment.yaml
```

Verify:

```yaml
on:
  push:
    branches:
      - main
```

Make sure the push was actually made to:

```text
main
```

---

# 69. Troubleshooting — GitHub Action Authentication Fails

Check the GitHub repository secrets:

```text
CLOUDFLARE_ACCOUNT_ID
CLOUDFLARE_API_TOKEN
```

Do not place the secret values directly into YAML.

---

# 70. Troubleshooting — Live Changes Are Not Visible

Check:

```text
GitHub
→ Actions
```

Make sure the latest action succeeded.

Then hard refresh the live website.

---

# 71. Recommended Process for the Next Website

The Nexa project involved some experimentation.

For the next website, use a cleaner sequence.

```text
1. Build website locally in WordPress/Elementor.

2. Finish desktop and mobile design.

3. Optimize large images and videos.

4. Install Simply Static.

5. Export using Local Directory.

6. Add important page URLs explicitly if necessary.

7. Verify every page contains index.html.

8. Fix Elementor video src issues.

9. Add JPG posters.

10. Create a clean static project folder.

11. Open the static project in VS Code.

12. Initialize Git in that exact static folder.

13. Create a GitHub repository.

14. Push the static project to GitHub.

15. Create/configure Cloudflare Pages.

16. Configure automatic GitHub deployment.

17. Test every page.

18. Test mobile Wi-Fi.

19. Test mobile 4G/5G.

20. From then onward edit in VS Code.

21. git add → git commit → git push.

22. GitHub Actions updates Cloudflare automatically.
```

---

# 72. Cleaner Future Option — GitHub First

For Nexa, Cloudflare Direct Upload was created before GitHub automation.

For a brand-new site, an even cleaner process may be:

```text
WordPress
↓
Simply Static
↓
VS Code static project
↓
GitHub repository
↓
Cloudflare Pages Git integration
```

If Cloudflare's native Git integration is available and appropriate at that time, it can remove the need for a custom GitHub Action.

However, if you want to reproduce the exact Nexa setup, use:

```text
GitHub Actions
+
Wrangler
+
Cloudflare Pages
```

---

# 73. Recommended Project Folder Organization

For future projects:

```text
Projects/
└── ClientName/
    │
    ├── wordpress-source/
    │
    │   └── WordPress/local backups
    │
    ├── original-media/
    │   ├── videos/
    │   └── images/
    │
    └── static-site/
        │
        ├── .git/
        ├── .github/
        ├── .gitignore
        ├── index.html
        ├── about/
        ├── services/
        ├── contact/
        ├── wp-content/
        └── wp-includes/
```

This keeps:

```text
WordPress files
original media
production static files
Git history
```

separate.

---

# 74. Recommended Naming

GitHub repository:

```text
client-name-static-site
```

or:

```text
client-name-wordpress-static
```

Cloudflare project:

```text
client-name
```

which normally gives:

```text
client-name.pages.dev
```

---

# 75. Security Rules

Never commit:

```text
passwords
FTP credentials
Cloudflare API tokens
private keys
.env files containing secrets
database credentials
```

Store secrets in:

```text
GitHub Secrets
environment variables
Cloudflare secret storage
```

---

# 76. When This Architecture Is a Good Choice

Use this workflow for:

```text
business brochure sites
company portfolios
landing pages
client demos
proof-of-concepts
marketing websites
static corporate sites
```

---

# 77. When Not to Use This Architecture

Do not blindly use a static export when the live website requires:

```text
WooCommerce
WordPress login
memberships
complex server-side forms
WordPress comments
database-driven content
frequent CMS editing by non-developers
server-side personalization
```

Those should use proper dynamic hosting or another application architecture.

---

# 78. Quick Memory Version

If you forget everything else, remember:

```text
BUILD
WordPress + Elementor

EXPORT
Simply Static → Local Directory

CHECK
Every page needs index.html

FIX
Elementor video src
JPG posters
mobile hidden classes

EDIT
VS Code

VERSION
Git + GitHub

HOST
Cloudflare Pages

AUTOMATE
GitHub Actions + Wrangler
```

Normal update:

```cmd
git add .
git commit -m "Update website"
git push
```

GitHub Actions then updates Cloudflare automatically.

---

# 79. Reusable Commands

## Cloudflare login

```cmd
npx wrangler login
```

## Create project

```cmd
npx wrangler pages project create YOUR-PROJECT-NAME
```

Production branch:

```text
main
```

## Manual deployment

```cmd
npx wrangler pages deploy . --project-name=YOUR-PROJECT-NAME --branch=main --commit-dirty=true
```

## Initialize Git

```cmd
git init
```

## Check Git root

```cmd
git rev-parse --show-toplevel
```

## Add GitHub remote

```cmd
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

## Verify remote

```cmd
git remote -v
```

## Initial push

```cmd
git add .
git commit -m "Initial static site"
git branch -M main
git push -u origin main
```

## Future updates

```cmd
git add .
git commit -m "Describe changes"
git push
```

---

# 80. Pre-Deployment Checklist

Before an important deployment:

- [ ] Correct project folder is open.
- [ ] `index.html` exists in the root.
- [ ] `about/index.html` exists.
- [ ] `services/index.html` exists.
- [ ] `case-studies/index.html` exists.
- [ ] `contact/index.html` exists.
- [ ] Images use valid paths.
- [ ] Videos are optimized.
- [ ] Videos use direct `src` where needed.
- [ ] JPG posters exist.
- [ ] Mobile video containers are not unintentionally hidden.
- [ ] Navigation links point to valid pages.
- [ ] No passwords/API tokens are committed.
- [ ] `.wrangler/` is ignored.
- [ ] Git contains only intended changes.
- [ ] Changes are committed.
- [ ] Changes are pushed.
- [ ] GitHub Action succeeds.
- [ ] Production URL opens.
- [ ] Every page opens.
- [ ] Mobile Wi-Fi test passes.
- [ ] Mobile 4G/5G test passes.

---

# 81. Nexa Advisory Reference Snapshot

Use this section only as a reminder of the project that established the workflow.

## Project

```text
Nexa Advisory
```

## Main pages

```text
/
about/
services/
case-studies/
contact/
demo/
```

## Static working folder

```text
Nexa Static Cloudfare backup
```

## GitHub repository

```text
NiyaazZSB/Nexa-Advisory-Wordpress-site-backup
```

## Cloudflare Pages project

```text
nexa-advisory
```

## Production branch

```text
main
```

## Live URL

```text
https://nexa-advisory.pages.dev
```

## Manual deployment command

```cmd
npx wrangler pages deploy . --project-name=nexa-advisory --branch=main --commit-dirty=true
```

## Normal automated deployment workflow

```cmd
git add .
git commit -m "Describe changes"
git push
```

Then:

```text
GitHub
↓
GitHub Actions
↓
Wrangler
↓
Cloudflare Pages
↓
Live website updated
```

---

# 82. Final Recommended Workflow

For future demo websites:

```text
WORDPRESS / ELEMENTOR
Build the website
        ↓
SIMPLY STATIC
Export to a local directory
        ↓
VERIFY
Check all page index.html files
        ↓
OPTIMIZE
Compress MP4s + create JPG posters
        ↓
STATIC FIXES
Fix Elementor video src/mobile issues
        ↓
VS CODE
Maintain the final static project
        ↓
GIT
Track changes
        ↓
GITHUB
Store the repository
        ↓
AUTOMATIC DEPLOYMENT
GitHub Actions / Wrangler
        ↓
CLOUDFLARE PAGES
Serve the live demo
```

The everyday publishing process becomes:

```text
Edit in VS Code
↓
Save
↓
git add .
↓
git commit
↓
git push
↓
GitHub Actions
↓
Cloudflare Pages
↓
Live update
```

---

# 83. Biggest Lessons from the Nexa Project

1. **Use Simply Static Local Directory instead of relying on a huge ZIP if ZIP generation fails.**

2. **Explicitly include important WordPress page URLs if Simply Static misses them.**

3. **A page folder is useless without its `index.html`.**

4. **Verify page files before deploying.**

5. **Static Elementor background videos may require a direct `src`.**

6. **Use JPG posters for a better loading experience.**

7. **Compress web background videos before hosting them.**

8. **Check for `elementor-hidden-mobile` when mobile backgrounds disappear.**

9. **The deployment root must directly contain `index.html`.**

10. **Use a dedicated static working folder.**

11. **Check the Git repository root before pushing.**

12. **Ignore `.wrangler/`.**

13. **Never commit Cloudflare secrets.**

14. **Use GitHub as your recovery/history system.**

15. **Once the static version becomes the master copy, be careful with future WordPress re-exports.**

16. **Cloudflare Pages is a much cleaner fit for a static demo than depending on a free hosting subdomain with inconsistent mobile DNS behavior.**

17. **After GitHub Actions is working, normal publishing is simply `git push`.**

---

# End of Guide

This document should be kept with the project or in a personal development-reference folder.

For a future website, copy this guide and replace the Nexa-specific values with:

```text
new project name
new GitHub repository
new Cloudflare project
new page names
new media filenames
new local folder
```

The underlying workflow remains the same.
