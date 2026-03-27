# SimpleNews Privacy Policy

Last Updated: March 27, 2026

Overview

SimpleNews is a news aggregation app that prioritizes your privacy. The vast majority of your data is stored locally on your device and never leaves it. This policy explains what data we collect, how it's used, and your rights.

Data We Collect

Data Stored Locally on Your Device

The following data is stored entirely on your device using UserDefaults, App Groups, the Keychain, and the app's cache directory. This data is never sent to any external server.

• App settings and preferences — your display options, enabled features, notification schedule, and onboarding status.
• Saved articles — articles you bookmark, including their title, description, source, URL, image URL, and publish date.
• Read article history — a set of article identifiers used to track which articles you've already seen.
• Interest profile — topic relevance scores (e.g., "sports: +3.0") generated when you like or dislike articles, used solely to rank your feed on-device.
• Screen time usage — time spent per app section per day, stored for a rolling 30-day window. Used only to enforce your own self-set time limits.
• Article cache — up to 200 recent articles cached temporarily for offline access (auto-pruned after 7 days).
• Subscription login sessions — if you log into paywalled sites (e.g., WSJ, NYT) within the app, browser cookies are stored in an app-sandboxed data store. These are never accessible to us.
• Blocked tags — topic filters you configure, shared with the widget and watch app via an on-device App Group container.
• Imported articles — any articles you manually add via URL.

Data Sent to Our Backend

SimpleNews uses a Cloudflare Worker (rss​-aggregator​.amiracle​.workers​.dev) as a lightweight proxy to aggregate RSS feeds and content. The following data is transmitted to this backend:

• Anonymous user identifier — a randomly generated UUID created on first launch and stored in your device's Keychain. This is not linked to your name, email, Apple ID, or any personal account. It is used to personalize which feeds are returned to you.
• Feed source preferences — the list of RSS feed IDs you have enabled, so the backend can fetch the right sources for you.
• Google News keywords — topic keywords you enter for custom Google News feeds.
• Twitter/X account handles — the list of X (Twitter) accounts you choose to follow within the app.

Important: Our Cloudflare Worker backend acts as a proxy and aggregator. It does not persist your browsing history, article reading habits, saved articles, interest profile, or screen time data. The user identifier is used only to associate your feed preferences with your requests.

Data Processed Entirely On-Device

• Article tagging and categorization — performed by bundled Core ML models. No article content is sent to any AI or cloud service.
• AI news summaries — generated using Apple's on-device Foundation Models framework (iOS 26+). Summary generation happens entirely on your device.
• Notifications — all notifications (daily digest and breaking alerts) are local notifications scheduled on your device. No push notification tokens are registered or sent to any server.

Third-Party Services

SimpleNews interacts with the following third-party services:

| Service | Purpose | Data Sent |
|---------|---------|-----------|
| Article publisher websites | Fetching article content for reader mode and preview images | The article's URL (your device IP is visible to the publisher) |
| Twitter/X oEmbed API | Rendering embedded tweets | The tweet URL |
| TikTok oEmbed API | Rendering embedded TikTok posts | The post URL |
| YouTube oEmbed API | Rendering embedded videos | The video URL |
| Reddit oEmbed API | Rendering embedded Reddit posts | The post URL |
| Spotify oEmbed API | Rendering embedded Spotify content | The content URL |
| Vimeo oEmbed API | Rendering embedded videos | The video URL |

No user identifier or personal data is sent to any of these third-party services. Only the content URL required for embedding is transmitted. Your device's IP address is inherently visible to any server your device connects to.

SimpleNews does not include any analytics SDKs, advertising frameworks, crash reporting services, or tracking pixels.

Apple Watch and Widget

• The Apple Watch companion app communicates with your iPhone over Apple's WatchConnectivity framework (a direct device-to-device link). Data exchanged includes saved article IDs, your user identifier, and the AI summary text.
• The home screen widget and watch complication fetch headlines from our backend using a generic identifier (widget or watch), not your personal user ID.

Data Sharing

We do not sell, rent, trade, or share your personal data with any third parties. Your data is used solely to provide the app's functionality.

Data Retention and Deletion

Since your data is stored locally on your device:

• Uninstalling SimpleNews removes all locally stored data, including your settings, saved articles, read history, interest profile, usage data, and article cache.
• The anonymous user identifier stored in your Keychain may persist after uninstallation (this is standard iOS Keychain behavior). It is automatically removed if you reset your device or erase Keychain data.
• Feed preferences and X account lists associated with your anonymous user ID on our backend can be deleted upon request by contacting us at the email below.

Children's Privacy

SimpleNews does not knowingly collect data from children under the age of 13. The app does not require account creation or collect any personal information.

Changes to This Policy

We may update this privacy policy from time to time. Any changes will be reflected by updating the "Last Updated" date at the top of this page.

Contact

If you have questions or concerns about this privacy policy, or if you would like to request deletion of any backend data associated with your anonymous identifier, please contact us at:

[azeltzdev@gmail.com]


# About SimpleNews

SimpleNews is a privacy-focused news aggregator that brings articles from your favorite sources into one clean, personalized feed. All article tagging, ranking, and AI summaries are powered by on-device intelligence — your reading habits never leave your phone. No ads, no tracking, no accounts. Just your news, your way.
