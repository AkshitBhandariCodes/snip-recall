# SnipWise extension: clean Mac handoff

This folder contains the extension source and a fresh package lock. It was exported from the public extension at commit `76932aa` after removing the hidden VS Code auto-run task, the obfuscated `init` build script, the disguised `fa-brand-400.orc` script, and injected code in `tailwind.config.js`. The original Git history is deliberately absent. Do not pull or merge the current public repository into this copy without a new security review.

## Build and try it on Apple Silicon

Install a current Node.js LTS release, then run in this folder:

```sh
npm ci --ignore-scripts --no-audit --no-fund
npm run build
```

Open `chrome://extensions` in Chrome, enable Developer mode, choose **Load unpacked**, and select the generated `dist` folder. Copy a harmless phrase from a webpage, then inspect the SnipWise popup and dashboard. The extension's actual browser behavior still needs this manual check; a successful build alone does not prove capture works.

## Where to build Recall

- `public/manifest.json` and `public/content.js`: extension permissions and browser copy capture.
- `src/background/service-worker.ts`: capture messages, clip persistence, and library operations.
- `src/lib/db.ts` and `src/types/index.ts`: IndexedDB access and clip types.
- `src/dashboard/Dashboard.tsx`: dashboard UI where a Recall view can be added.

Saved clips live in each Chrome profile's local IndexedDB. This source does not sync snippets between the Mac and Windows PCs, and it does not capture the entire operating system clipboard. AI Recall, Anakin.io, and GenieX are not integrated yet.

For model work, keep local retrieval in the extension and send only user-selected, relevant URLs to an Anakin.io adapter running outside the public extension bundle. The Anakin.io API key must stay in a local service or trusted backend, never in `src`, `public`, or `dist`. The Apple Silicon GenieX CPU container described in the shared guide can be explored separately for image understanding; there is no GenieX connection in this repository yet. Keep downloaded models and input images in ignored `models/` or `data/` folders.
