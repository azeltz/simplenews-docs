# simplenews.github.io
SimpleNews is a personal news aggregator for iOS and Apple Watch. It fetches articles from 20+ public RSS feeds via a Cloudflare Workers backend, enriches them with on-device ML classification and AI summarization, and presents a scored, personalized feed.

The app requires network access to fetch articles. The watch companion displays headlines and supports save/unsave. The widget shows the latest headlines on the home screen and lock screen. Watch complications show condensed headlines on watch faces.

No login is required. A random device UUID is used for per-user feed personalization — no personal information is collected.

The "Social" tab embeds Instagram, Reddit, and LinkedIn in WKWebViews for quick access — these are standard web views, not custom browsers.
