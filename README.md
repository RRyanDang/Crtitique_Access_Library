# Critiquing Access at the North York Central Library

A static website version of the access critique report. Plain HTML and CSS, no JavaScript, no build tools required to host it.

## What is here

- `site/` — the website. This is the folder you publish.
- `build.pl` — regenerates `site/` from the page content held in the script. Optional: you can also just edit the HTML in `site/` directly.

## Pages

```
site/index.html                              Home
site/about/                                  About the Library
site/background/                             What You Should Know (hub)
site/background/key-terms/                   Key Terms
site/background/rights-and-law/              Rights and Law
site/background/design-frameworks/           Design Frameworks
site/listing/                                The Access Now Listing
site/findings/                               Areas of Improvement (hub)
site/findings/entrances/                     Entrances and Movement
site/findings/washrooms/                     Washrooms
site/findings/sensory/                       Sensory and Cognitive Access
site/findings/overlooked/                    What Was Overlooked
site/recommendations/                        Recommendations
site/references/                             References (hub)
site/references/text/                        Text Citations
site/references/images/                      Image and Media Citations
site/accessibility/                          Accessibility of This Site
```

## Publishing to GitHub Pages

1. Create a new repository on GitHub.
2. Copy the **contents of `site/`** into the repository root, so that `index.html` sits at the top level.
3. Commit and push to the `main` branch.
4. In the repository, go to **Settings → Pages**, set **Source** to "Deploy from a branch", choose `main` and `/ (root)`, and save.
5. The site appears at `https://<your-username>.github.io/<repository-name>/` after a minute or two.

All links between pages are relative, so the site works from a subfolder without any configuration.

## Adding images

1. Create `site/images/` and put the file there.
2. Find the commented-out `<figure>` block in the relevant page and uncomment it, or copy this pattern:

```html
<figure>
  <img src="../images/your-file.jpg" alt="Describe what matters in the image, in one sentence.">
  <figcaption>Caption. Photo by the author, September 2026.</figcaption>
</figure>
```

Rules to keep the site accessible:

- **Alt text** describes what the image shows that matters to the argument. A photo of a tight washroom should say it is tight, not "washroom".
- **Decorative images** get `alt=""` so screen readers skip them.
- Every image also needs an entry on the **Image and Media Citations** page, worded the same as its caption.

## Editing content

Each page is a single self-contained HTML file. The parts you will touch are inside `<main>`. Shared pieces — the header, nav, footer and prev/next links — are repeated in each file, so if you change the navigation you must change it in all 17 files, or edit `build.pl` and re-run `perl build.pl`.

## Colour

The accent colour `#0075ca` is sampled from the Toronto Public Library wordmark, with `#00538f` for hover and focus states. Both meet WCAG AA contrast against white. They are defined once at the top of `site/css/style.css`.
