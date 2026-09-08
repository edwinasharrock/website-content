# Deploying to Vercel

This is a plain static site (HTML + CSS, no build step, no server). Vercel serves it as-is.

The homepage is `index.html` at the top level, so once deployed, edwinasharrock.com loads straight to it. The other pages sit alongside it: `/work-with-me.html` and `/speaking.html`.

## Option A: drag and drop (no coding, easiest)
1. Go to vercel.com and log in (or sign up, it's free for this).
2. Click "Add New" → "Project".
3. Choose "Deploy without Git" and drag the whole `edwinasharrock-site-v2` folder onto the page.
4. Vercel builds it (should take seconds, since there's nothing to build) and gives you a live `*.vercel.app` link straight away.
5. Add your domain: Project → Settings → Domains → add `edwinasharrock.com` (and `www.edwinasharrock.com`) → follow the DNS instructions Vercel gives you at your domain registrar.

## Option B: GitHub (better if you'll keep updating the site yourself)
```
cd edwinasharrock-site-v2
git init
git add .
git commit -m "Site v2"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```
Then import the repo in Vercel: Add New → Project → pick the repo. Framework preset "Other", no build command, no output directory override needed.

## Option C: Vercel CLI
```
npm install -g vercel
cd edwinasharrock-site-v2
vercel
```
Follow the prompts, then `vercel --prod` to push it live.
