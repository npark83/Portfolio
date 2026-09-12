# Your portfolio site

A single-file static site (`index.html`) with tabs for Home, Acting, Modeling,
Producing/Directing, Resume, and Headshots. No build step, no framework —
just open it in a browser to preview.

## 1. Fill in your content

Open `index.html` in a text editor.

**Home tab** — search for the `<!-- ===================== HOME` comment.
Replace the placeholder headshot box, name, tagline, bio paragraph, and the
Backstage / Actors Access links (`href="#"`). Add your IMDb link once you
have one, or delete the `.imdb-note` block if you don't want that section.

**Acting / Producing videos** — scroll to the `<script>` at the bottom and
edit the `actingVideos` and `producingVideos` arrays:

```js
const actingVideos = [
  { title: "Scene title", note: "Role — Project (Year)", url: "https://www.youtube.com/watch?v=..." },
];
```

Add or remove entries freely — the grid updates automatically. To show a
real thumbnail instead of the play-icon placeholder, add an `img` field and
swap the `.video-thumb` div for an `<img>` tag pointing to it (or a
YouTube thumbnail URL like `https://img.youtube.com/vi/VIDEO_ID/hqdefault.jpg`).

**Modeling photos** — edit the `modelingPhotos` array the same way, with
`credit` (photographer/brand) and `url` (where the image was used).

**Headshots** — replace the placeholder boxes in `.headshot-frame` with
real `<img>` tags, or add filenames to reference from an `/images` folder.

**Resume** — this section is plain HTML (not JS-driven), so edit the rows
directly under `<!-- ===================== RESUME`. Each row can wrap its
text in an `<a href="...">` link.

## 2. Add your images

Create an `images/` folder next to `index.html`, drop your photos in, and
reference them like:

```html
<img src="images/headshot-1.jpg" alt="Headshot">
```

## 3. Preview locally

Just double-click `index.html` — no server needed.

## 4. Deploy to GitHub Pages (your repo: npark83.github.io)

Your repo is a special "user site" repo, so whatever's on the `main` branch
at the root is served directly at `https://npark83.github.io/`.

Note: that repo currently has an `index.html` used for a "You've been
phished" landing page — this will replace it.

```bash
git clone https://github.com/npark83/npark83.github.io.git
cd npark83.github.io
# copy your new index.html (and images/ folder, if any) into this folder,
# overwriting the existing index.html
git add .
git commit -m "New portfolio site"
git push
```

Give it a minute or two, then visit `https://npark83.github.io/` — your
site should be live.

If it doesn't show up, check **Settings → Pages** on the repo to confirm
it's set to deploy from the `main` branch, root folder.
