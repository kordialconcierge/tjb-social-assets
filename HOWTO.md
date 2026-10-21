# Daily image upload flow

1. Generate images for the day in /workspace/rollout-YYYY-MM-DD.
2. Copy them into a dated folder here: `YYYY-MM-DD/postN_{main,feed_1080x1350,story_1080x1920}.jpg`.
3. `git add . && git commit -m "Assets YYYY-MM-DD" && git push` (main branch).
4. Use the commit-SHA URL in Buffer: `https://raw.githubusercontent.com/kordialconcierge/tjb-social-assets/<commit-sha>/YYYY-MM-DD/<file>` (get it with `git rev-parse HEAD`). The `/main/` URL can return a cached 404 for a few minutes after a push; SHA URLs work immediately and never change.
5. Before scheduling, verify each URL: HTTP 200, `image/*` content-type, byte size equals the local file.
6. Mapping: LinkedIn + X -> main; Facebook Page + Threads + Instagram feed -> feed_1080x1350; Instagram story -> story_1080x1920.

Note: everything in this repo is public. Only commit images meant to be posted.
