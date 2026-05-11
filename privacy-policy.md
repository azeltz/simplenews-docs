# SimpleNews Privacy Policy

Last Updated: May 10, 2026

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

SimpleNews uses a Cloudflare Worker (rss-aggregator.amiracle.workers.dev) as a lightweight proxy to aggregate RSS feeds and content. The following data is transmitted to this backend:

• Anonymous user identifier — a randomly generated UUID created on first launch and stored in your device's Keychain. This is not linked to your name, email, Apple ID, or any personal account. It is used to personalize which feeds are returned to you.
• Feed source preferences — the list of RSS feed IDs you have enabled, so the backend can fetch the right sources for you.
• Google News keywords — topic keywords you enter for custom Google News feeds.
• Twitter/X account handles — the list of X (Twitter) accounts you choose to follow within the app.
• Apple Push Notification (APNs) device token (v1.2) — an opaque identifier issued by Apple, used solely to deliver breaking-news push notifications. Sent only if you enable Breaking News Alerts in Settings. The token is stored in an isolated database table on our backend and is never joined to your anonymous user identifier or any other data we store about you. It is automatically deleted from our backend when (a) you disable Breaking News Alerts in Settings, (b) you uninstall the app and Apple reports the token as expired, or (c) you have not received a push in an extended period.
• Notification preferences (v1.2) — your selected breaking-alert mode (Off / Smart / Everything), the topics, topic feeds, or specific sources you want alerts about, your timezone, and whether you have the daily digest enabled. Used solely to decide whether to send you a given breaking-news push.

Important: Our Cloudflare Worker backend acts as a proxy and aggregator. It does not persist your browsing history, article reading habits, saved articles, interest profile, or screen time data. The user identifier is used only to associate your feed preferences with your requests. The APNs device token is kept in a separate, isolated table and is never linked to your user identifier.

Article Content Caching (v1.2)

When you tap an article to read it in the in-app reader, our backend fetches that article's URL once and caches a cleaned, reader-friendly version. Subsequent reads of the same article (by you or other users) are served from this shared cache. Because the fetch is performed by our backend rather than your device, the publisher's website sees our backend's IP address rather than yours when you read via the in-app reader. Opening the article in Safari directly (or via the oEmbed previews listed below) still uses your device's IP as before.

The cleaned content is shared across users — it is not associated with any user identifier. We also store article cluster metadata (which sources are covering the same story, computed from public titles and descriptions) so your feed shows less duplication. Clustering uses only the public article content; it never uses any signal from you.

Data Processed Entirely On-Device

• Article tagging and categorization — performed by bundled Core ML models. No article content is sent to any AI or cloud service for tagging.
• AI news summaries — generated using Apple's on-device Foundation Models framework (iOS 26+). Summary generation happens entirely on your device.
• Daily digest notifications — composed entirely on-device using the AI summary above, and delivered as local iOS notifications. The summary text never leaves your phone, and the digest never reaches our backend.
• Breaking news alerts (v1.2) — sent as Apple Push Notifications from our backend, but their content matching is determined by your preferences stored on the backend (per the section above). The notification payload contains only the article title, a short description, and the article identifier or URL — no other information about you. Tapping a breaking alert opens the article in the app, or in Safari as a fallback if the article is not in your loaded feed.

Third-Party Services

SimpleNews interacts with the following third-party services:

| Service | Purpose | Data Sent |
|---------|---------|-----------|
| Apple Push Notification service (APNs) | Delivering Breaking News Alerts | The APNs device token (issued by Apple), the notification title, body, and article identifier. Apple does not see your other preferences. |
| Article publisher websites | Fetching article content for reader mode and preview images | The article's URL. When fetched by our backend for the shared reader cache, our backend's IP is visible to the publisher; for direct opens (Safari, oEmbed) your device's IP is visible. |
| Twitter/X oEmbed API | Rendering embedded tweets | The tweet URL |
| TikTok oEmbed API | Rendering embedded TikTok posts | The post URL |
| YouTube oEmbed API | Rendering embedded videos | The video URL |
| Reddit oEmbed API | Rendering embedded Reddit posts | The post URL |
| Spotify oEmbed API | Rendering embedded Spotify content | The content URL |
| Vimeo oEmbed API | Rendering embedded videos | The video URL |

No user identifier or personal data is sent to any of these third-party services. Only the content URL required for embedding (or the push payload required for delivery) is transmitted. Your device's IP address is inherently visible to any server your device connects to directly.

SimpleNews does not include any analytics SDKs, advertising frameworks, crash reporting services, or tracking pixels.

Apple Watch and Widget

• The Apple Watch companion app communicates with your iPhone over Apple's WatchConnectivity framework (a direct device-to-device link). Data exchanged includes saved article IDs, your user identifier, and the AI summary text.
• The home screen widget and watch complication fetch headlines from our backend using a generic identifier (widget or watch), not your personal user ID. They do not register for push notifications and do not receive Breaking News Alerts.

Data Sharing

We do not sell, rent, trade, or share your personal data with any third parties. Your data is used solely to provide the app's functionality.

Apple's role in push notifications: when you enable Breaking News Alerts, our backend transmits the notification payload (title, body, article identifier, and your APNs device token) to Apple's Push Notification service for delivery to your device. Apple holds your APNs token by definition (they issued it) and routes the notification to your device. Apple does not see any other SimpleNews data — only the routing information for the push itself. This is the standard Apple-mediated mechanism for any iOS push notification.

Data Retention and Deletion

Since most of your data is stored locally on your device:

• Uninstalling SimpleNews removes all locally stored data, including your settings, saved articles, read history, interest profile, usage data, and article cache.
• The anonymous user identifier stored in your Keychain may persist after uninstallation (this is standard iOS Keychain behavior). It is automatically removed if you reset your device or erase Keychain data.
• Feed preferences and X account lists associated with your anonymous user ID on our backend can be deleted upon request by contacting us at the email below.
• APNs device tokens and notification preferences (v1.2) are deleted from our backend immediately when you disable Breaking News Alerts in Settings, and automatically when Apple reports the token as expired or invalid (typically within a few days of uninstalling the app). Unlike the anonymous user ID, the device token is never persisted after you opt out.

Children's Privacy

SimpleNews does not knowingly collect data from children under the age of 13. The app does not require account creation or collect any personal information.

Changes to This Policy

We may update this privacy policy from time to time. Any changes will be reflected by updating the "Last Updated" date at the top of this page.

Contact

If you have questions or concerns about this privacy policy, or if you would like to request deletion of any backend data associated with your anonymous identifier, please contact us at:

[azeltzdev@gmail.com]


# About SimpleNews

SimpleNews is a privacy-focused news aggregator that brings articles from your favorite sources into one clean, personalized feed. All article tagging, ranking, and AI summaries are powered by on-device intelligence — your reading habits never leave your phone. No ads, no tracking, no accounts. Just your news, your way.
