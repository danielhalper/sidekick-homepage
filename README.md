# Sidekick homepage

Static homepage shared by two separately deployed sites:

- Production: https://sidekick.stepuptutoring.org/ (Vercel project `sidekick`, scope `stepuptutoring`).
- GitHub Pages: https://danielhalper.github.io/sidekick-homepage/ (published from `main`, repository root).

## Publish changes to both sites

1. Verify the page locally, commit changes on a task branch, and merge its pull request into `main`.
2. GitHub Pages deploys automatically. Wait for its build to complete.
3. From the merged checkout, run `npx vercel link --yes --project sidekick --scope stepuptutoring` if the directory is not already linked, then `npx vercel deploy --prod --yes --scope stepuptutoring`.
4. Verify the HTML on **both** public URLs matches the committed `index.html` before reporting completion.

Vercel is currently deployed through the CLI, not connected to Git. Pushing to GitHub alone does not update the production domain. `.vercelignore` limits Vercel uploads to the two public site files; local Vercel configuration and environment files are ignored by Git.

## Local preview

Run `python3 -m http.server 8765` and open http://localhost:8765/.
