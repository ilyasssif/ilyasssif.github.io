# Step-by-Step Deployment & Profile Sync Checklist

All core files have been generated directly in this directory:
- `index.html`: Complete, modern Entity Home with Google Knowledge Graph `Person` Schema.
- `HAXGYM_ARTICLE.md`: Publication-ready technical writeup about your JAX reinforcement learning work.
- `WIKIDATA_SETUP.md`: Pre-configured Wikidata entity fields and properties.

---

### Step 1: Deploy Your Website to GitHub Pages (2 Minutes)

You can host this website completely for free on GitHub Pages at `https://re3gi.github.io`:

1. Go to [https://github.com/new](https://github.com/new).
2. Set the repository name to: **`re3gi.github.io`**
3. Keep it **Public** and leave "Add a README" unchecked. Click **Create repository**.
4. In your terminal in this directory (`google panel`), run:

```bash
git init
git add index.html
git commit -m "feat: launch entity home portfolio for Ilyass Sif"
git branch -M main
git remote add origin https://github.com/re3gi/re3gi.github.io.git
git push -u origin main
```

Within 60 seconds, your website will be live at: **`https://re3gi.github.io`**!

---

### Step 2: Sync Your Existing Online Profiles

#### A. GitHub Profile
1. Go to [https://github.com/settings/profile](https://github.com/settings/profile).
2. **Name:** `Ilyass Sif` (already set)
3. **Bio:** `Computer Science & Machine Learning Developer. Creator of HaxGym (JAX RL).`
4. **Website / Blog URL:** Enter `https://re3gi.github.io/` (currently empty).
5. Click **Update profile**.

#### B. Hugging Face Profile
1. Go to [https://huggingface.co/settings/profile](https://huggingface.co/settings/profile).
2. Change **Full name** from `ilyass` to: **`Ilyass Sif`**
3. In **Website / Homepage**, enter: `https://re3gi.github.io/`
4. In **GitHub username**, enter: `re3gi`
5. Save changes.

---

### Step 3: Publish Your Technical Article
1. Create a free account on [Dev.to](https://dev.to) or [Medium](https://medium.com).
2. Copy the contents of [`HAXGYM_ARTICLE.md`](./HAXGYM_ARTICLE.md).
3. Publish it under the name **Ilyass Sif** with tags: `#machinelearning`, `#python`, `#ai`, `#reinforcementlearning`.
4. This creates a valuable external backlink and mentions your full name in connection with machine learning.

---

### Step 4: Create the Wikidata Item
Follow the step-by-step guide in [`WIKIDATA_SETUP.md`](./WIKIDATA_SETUP.md).

---

### Step 5: Submit to Google Search Console
1. Go to [Google Search Console](https://search.google.com/search-console).
2. Add your website property: `https://re3gi.github.io/` (verification is automatic if using GitHub Pages or a Google account).
3. Request indexing of the homepage so Googlebot crawls the `Person` JSON-LD schema immediately.
