# israelelizondo.com — Setup Guide

Your portfolio site. Three files matter: `index.html` (homepage), `roborowdy.html` (project page), `style.css` (all styling). The `CNAME` file tells GitHub Pages to use your custom domain. Keep it.

## Step 1: Create the GitHub repo

1. Sign up / log in at github.com
2. Click **New repository**
3. Name it exactly: `YOURUSERNAME.github.io` (replace with your actual GitHub username)
4. Set it to **Public**, then click **Create repository**

## Step 2: Upload these files

Easiest way (no command line needed):

1. On the new repo page, click **uploading an existing file**
2. Drag in: `index.html`, `roborowdy.html`, `style.css`, `CNAME`
3. Click **Commit changes**

Within a minute or two, your site is live at `https://YOURUSERNAME.github.io`

## Step 3: Connect israelelizondo.com (Namecheap DNS)

1. Log in to Namecheap → **Domain List** → **Manage** next to israelelizondo.com
2. Go to the **Advanced DNS** tab
3. Delete any existing A or CNAME records Namecheap added by default (parking page records)
4. Add these five records:

| Type  | Host | Value                  | TTL       |
|-------|------|------------------------|-----------|
| A     | @    | 185.199.108.153        | Automatic |
| A     | @    | 185.199.109.153        | Automatic |
| A     | @    | 185.199.110.153        | Automatic |
| A     | @    | 185.199.111.153        | Automatic |
| CNAME | www  | YOURUSERNAME.github.io | Automatic |

## Step 4: Tell GitHub about the domain

1. In your repo: **Settings → Pages**
2. Under **Custom domain**, type `israelelizondo.com` and save
3. Wait for the DNS check to pass (can take a few minutes to a few hours)
4. Once available, check **Enforce HTTPS**

Done. israelelizondo.com now loads your site with free HTTPS.

## Before going live: personalize

Search the HTML files for these placeholders and replace them:

- `YOUR_EMAIL_HERE` (index.html, contact section)
- `YOUR_LINKEDIN_HERE` (index.html, contact section)
- `YOUR_GITHUB_HERE` (index.html, contact section)

And replace the striped image placeholders (the boxes that say "ADD PHOTO / ADD IMAGE")
with real images:

1. Upload your image files to the repo (a folder called `img/` keeps things tidy)
2. Replace the placeholder div, for example:

   `<div class="ph">ADD PHOTO: ...</div>`

   becomes:

   `<img src="img/roborowdy-hero.jpg" alt="RoboRowdy robot at the print farm" style="width:100%; display:block;">`

Your best image candidates: FEA stress plots, topology optimization comparisons,
NX assembly renders, and the Realize Live stage photos.

## Updating the site later

Edit files directly on github.com (click the file → pencil icon → commit), or
re-upload changed files. Every commit republishes the site automatically.
