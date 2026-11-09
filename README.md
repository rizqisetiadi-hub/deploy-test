# Deploy test

A single-file, dependency-free page used to verify the workflow from local folder
to public URL: write code locally → commit to Git → push to GitHub → serve via
GitHub Pages.

The page runs a handful of environment checks in the browser and reports whether
it is being opened from disk (`file://`) or served over HTTP, which is the
difference between "local preview" and "actually published".

## Run locally

Open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Publish

1. Push this repo to GitHub.
2. Settings → Pages → Source: `main`, folder `/ (root)`.
3. The page appears at `https://<username>.github.io/<repo>/` within a minute.

## What the checks tell you

| Check | Meaning |
| --- | --- |
| JavaScript | The script tag executed — no console errors, no CSP blocking |
| Protocol | `file://` means local only; `https://` means it is genuinely served |
| Host | The domain actually serving the page |
| Viewport | Responsive layout is receiving real dimensions |
| Stylesheet | CSS parsed and applied |

## License

MIT — see [LICENSE](LICENSE). Anyone may use, modify and redistribute this code.
