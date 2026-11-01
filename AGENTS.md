# AGENTS.md

Instructions for any AI agent working on this repo (Claude, Gemini, Codex, etc.).

Static Hebrew (RTL) recipe site: plain HTML + `style.css`, no build step. See `README.md` for local preview and how to add a recipe.

## Adding a recipe

1. Copy the newest page in `recipes/` (e.g. `recipes/sfenj.html`) and keep its structure: hero image, `h1`, one summary line (temp/heat · time · pan), kashrut tag, then `h2` sections (מצרכים, אופן ההכנה, הערות) and a source line at the bottom. Extra ingredient groups (e.g. ציפוי) are their own `h2`.
2. Add a card to the right category in `index.html`.
3. Write steps in your own words; don't copy the source verbatim. Always credit the source.
4. Work on a branch named after the recipe and open a PR.

## Recipe images: graffiti style (required)

Every recipe image is a **generated graffiti illustration**, never a photo from the source site. All images must match the existing ones in `images/recipes/`.

- Size: 1200x805 JPEG, saved as `images/recipes/<recipe-slug>.jpg`.
- Generator: Antigravity CLI (`agy`) with model `gemini-4-argon-high`. Pass an existing image (e.g. `images/recipes/sfenj.jpg`) as a style reference. Run it as `agy --model gemini-4-argon-high --mode accept-edits -p "<prompt>"` (no `--dangerously-skip-permissions`).
- `agy` ignores the save path in the prompt and writes the image to `~/.gemini/antigravity-cli/brain/<session-id>/<name>.jpg`. Find it with `find ~/.gemini/antigravity-cli/brain -name '*.jpg' -mmin -10 -not -path '*/.system_generated/*'`. It may produce several versions; look at each and pick the best.
- Prompt template (fill in the subject and props):

  > A colorful pop graffiti street-art mural spray-painted on a weathered red brick wall. Bold black ink outlines, comic-style shading, bright paint splashes and drips in cyan, magenta, yellow, orange and purple, concrete floor at the bottom. Landscape 3:2. Subject: **<the dish, centered, appetizing>**. Around it: **<3–6 related ingredients or props>**. No text or letters anywhere.

- Resize/crop to 1200x805 (macOS: `sips --resampleWidth 1200` then `sips -c 805 1200`).
- Look at the result before committing: graffiti style, brick wall, no text, dish clearly recognizable.
- Hebrew `alt` text describes the dish and ends with `, ציור גרפיטי צבעוני על קיר לבנים`. The card image on `index.html` uses `alt=""`.
