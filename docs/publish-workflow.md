# Publish Branch Workflow

This directory is published to `https://github.com/stonly/math-motion` from a dedicated branch named `publish-assets`.

## What belongs in the repo

Only these artifacts are tracked on the publish branch:

- `katex-sidebar.zip`
- `docs/` and everything inside it
- `.gitignore`

Everything else in this working directory is intentionally ignored so the remote repository stays limited to the packaged extension and the hosted docs.

## Local repo shape

`/Users/stonly/Projects/Personal/math-motion` is a nested git repository. It is separate from the parent `/Users/stonly/Projects/Personal` repository.

## Updating the published files

1. Rebuild or replace `katex-sidebar.zip`.
2. Edit files in `docs/` if the privacy policy or publish notes changed.
3. Check the publish repo status:

```bash
git status --short
```

4. Stage the allowed files:

```bash
git add .gitignore docs katex-sidebar.zip
```

5. Commit the update:

```bash
git commit -m "Update published extension package"
```

6. Push the publish branch:

```bash
git push origin publish-assets
```

## GitHub Pages

If you want the docs site live from this repo, configure GitHub Pages to deploy from:

- Branch: `publish-assets`
- Folder: `/docs`

That will host `docs/index.html` as the privacy-policy page while keeping the ZIP file in the same repository.
