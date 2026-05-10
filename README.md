# 📖 Setup Guide — How to Install Your Modern README

This guide walks you through setting up your beautiful new GitHub Profile README in **under 10 minutes**.

---

## ⚡ Quick Overview

Your new README includes these features:

| Feature | Description |
|---------|-------------|
| 🌊 **Animated Header** | Wave-style gradient banner with your name |
| ⌨️ **Typing Animation** | Auto-rotating text showing your roles |
| 🎨 **40+ Tech Badges** | Colorful icons for every tool you use |
| 📊 **Live GitHub Stats** | Auto-updating repo counts, languages, streaks |
| 🏆 **Trophy Display** | GitHub achievement trophies |
| 📈 **Activity Graph** | Visual contribution graph |
| 🐍 **Snake Animation** | Animated snake eating your contributions (advanced) |
| 💬 **Random Dev Quote** | Different quote each time someone visits |
| 🌊 **Wave Footer** | Matching animated footer |

---

## 🚀 Step-by-Step Installation

### Step 1: Create the Special Repository (2 min)

GitHub uses a "magic" repository for Profile READMEs. The repo name **MUST** match your username exactly.

1. Go to **https://github.com/new**
2. Repository name: **`MdAshrafuddinnoyon`** (case-sensitive, exactly your username)
3. Description: *"My GitHub Profile README"*
4. Set to **Public**
5. Check ✅ **"Add a README file"**
6. Click **Create repository**

> 💡 **You'll see a special "✨ secret" message confirming this is your profile repo!**

---

### Step 2: Replace the Default README (3 min)

1. Open the newly-created repository
2. Click on **`README.md`** file
3. Click the **pencil/edit icon** (top right)
4. **Delete all existing content**
5. **Copy the entire contents** of the new `README.md` file I provided
6. **Paste** into the editor
7. Scroll down and click **"Commit changes..."**
8. Add commit message: *"feat: add modern profile README"*
9. Click **"Commit changes"**

✅ **Visit your profile** at https://github.com/MdAshrafuddinnoyon — your new README is live!

---

### Step 3: Setup Snake Animation (Optional, 5 min)

The animated snake is the coolest feature, but requires a GitHub Action workflow. Skip this if you want to keep things simple.

1. In your `MdAshrafuddinnoyon` repository, click **Actions** tab
2. Click **"set up a workflow yourself"** or **"New workflow"**
3. Name the file: **`snake.yml`**
4. Paste this code:

```yaml
name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */24 * * *"  # Runs every 24 hours
  workflow_dispatch:
  push:
    branches:
      - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: Generate snake animation
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

5. Click **"Commit changes"** in the top right
6. Go back to **Actions** tab
7. Click **"Generate Snake Animation"** workflow
8. Click **"Run workflow"** button (manually trigger first run)
9. Wait 30 seconds — refresh your profile and you'll see the animated snake!

---

## 🔧 Customization Tips

### Change Color Themes

The README uses `tokyonight` theme. To change, find these lines and replace:

```markdown
?theme=tokyonight
```

**Available themes**: `dark`, `radical`, `merko`, `gruvbox`, `tokyonight`, `onedark`, `cobalt`, `synthwave`, `highcontrast`, `dracula`

---

### Update Typing Animation Text

Find this line in your README:

```
&lines=Founder+%26+CEO+%40+WebSearchBD+Ltd.;WordPress+%2B+AI+Development+Expert;...
```

To add new lines, separate with `;` and use `+` for spaces, `%26` for `&`, `%2B` for `+`.

**Example**: `&lines=Hello+World;I+love+coding;Building+great+things`

---

### Update Stats / Numbers

Edit these lines as your numbers grow:

```markdown
💼 **5+ years** of proven experience  
🌍 **322+ clients** across **19+ countries**  
🚀 **350+ projects** delivered  
💰 **$3,800+** revenue from Lovable.dev
```

Pro tip: Update every 6 months as you grow.

---

### Add Your Real Buy Me A Coffee / Sponsor Links

I added placeholders. Replace these with your actual links:

```markdown
[![Buy Me a Coffee](...)]( https://buymeacoffee.com/ashrafnoyon )  ← Replace
[![Sponsor](...)]( https://github.com/sponsors/MdAshrafuddinnoyon )  ← Set up GitHub Sponsors first
```

If you don't have these set up, **delete the entire Support My Work section**.

---

## 📸 Add a Profile Picture (Optional)

Replace the GIF in the About Me section with your own image:

```markdown
<img align="right" alt="Coding" width="380" src="YOUR_IMAGE_URL_HERE"/>
```

**Where to host images:**
- Upload to your repo: `/MdAshrafuddinnoyon/assets/profile.png`
- Then use: `https://raw.githubusercontent.com/MdAshrafuddinnoyon/MdAshrafuddinnoyon/main/assets/profile.png`

---

## ✅ Final Checklist

After setup, verify these work on your profile:

- [ ] Wave header banner displays at top
- [ ] Typing animation rotates through your titles
- [ ] All tech stack badges show correctly
- [ ] GitHub Stats card loads (may take 30 sec first time)
- [ ] Top Languages card displays
- [ ] Streak stats show your contribution streak
- [ ] Activity graph renders
- [ ] Trophy section shows trophies
- [ ] All social links work
- [ ] Snake animation displays (if you set it up)
- [ ] Footer wave displays at bottom

---

## 🎯 What's Different From Your Old README?

| Old README | New README |
|------------|------------|
| ❌ Broken social links (`https://github.com/https://github.com/...`) | ✅ Clean working links |
| ❌ GitHub stats with full URL as username (broken) | ✅ Just username — stats actually load |
| ❌ Old services (only WordPress, Shopify) | ✅ Updated services (Lovable.dev, n8n, AI tools) |
| ❌ "Currently working on Codmanbd" (outdated) | ✅ "Building AI-powered SaaS apps" (current) |
| ❌ Plain text, basic design | ✅ Animated banner, badges, graphs, trophies |
| ❌ No personal stats or numbers | ✅ Highlights 350+ projects, 322+ clients |
| ❌ "Currently learning JavaScript" (outdated) | ✅ "Learning Claude Code, MCP, AI Agents" |
| ❌ No founder/CEO positioning | ✅ Founder & CEO @ WebSearchBD prominent |

---

## 🆘 Troubleshooting

**Stats card not loading?**  
Wait 30 seconds — vercel.app caches need to fetch your data the first time. Refresh after a minute.

**Snake animation not showing?**  
The workflow needs to run successfully at least once. Go to Actions tab, click "Run workflow" manually.

**Badges look wrong color?**  
shields.io badges sometimes have brand color requirements. Check the color hex in `?style=for-the-badge&logoColor=white`.

**Profile views counter not updating?**  
komarev.com has a small delay (1-2 minutes per view). It's working, just patient.

---

## 💡 Pro Tips for Maximum Impact

1. **Pin 6 strategic repos** — they show below your README
2. **Star quality repos** — appears in your activity feed
3. **Commit weekly** — keeps your contribution graph green
4. **Update README quarterly** — refresh stats, learning, what you're working on
5. **Add release notes** to repos — increases discoverability

---

## 📚 Additional Customizations You Can Add Later

Want to take it further? Here are advanced features:

- **Spotify currently playing widget**
- **Latest blog posts auto-imported**
- **Recent YouTube videos display**
- **Visitor location map**
- **Twitter/X post embeds**
- **WakaTime coding stats**

Let me know if you want any of these added!

---

🎉 **Enjoy your stunning new GitHub profile!** 

If you have questions or want adjustments, just ask.
