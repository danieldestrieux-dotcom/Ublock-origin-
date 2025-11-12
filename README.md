# DanielTech's Hybrid uBlock Origin Configuration

[![uBlock Origin Version](https://img.shields.io/badge/uBlock%20Origin-1.67.0+-brightgreen.svg)](https://github.com/gorhill/uBlock)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive and aggressive uBlock Origin configuration designed for **maximum compatibility and seamless browsing**, even on websites with sophisticated anti-adblock systems.

> **⚠️ Important:** This configuration prioritizes functionality over absolute privacy. It strategically allows certain trackers to bypass detection. If you prioritize maximum privacy, consider a more restrictive configuration.

## 🎯 Philosophy & Goal

The primary goal of this configuration is to eliminate the frustration of encountering "Please disable your ad blocker" messages, broken layouts, and access-denied errors on popular websites, especially streaming platforms and social media networks.

It achieves this by using a "hybrid" approach: combining powerful blocklists with custom, aggressive anti-detection bypass rules.

## ✨ Key Features

-   ✅ **Maximum Compatibility:** Engineered to work flawlessly with YouTube, Netflix, Disney+, HBO Max, Facebook, Twitter, Reddit, Twitch, and many more.
-   🚫 **Aggressive Anti-Detection Bypass:** Uses advanced scriptlets (`##+js`) to neutralize adblock detection scripts on major platforms.
-   🤫 **Strategic Tracker Allowlisting:** Selectively permits certain non-intrusive trackers (e.g., from Google) to make the blocking behavior appear more "human" and avoid detection.
-   🛡️ **Comprehensive Blocking:**
    -   Blocks crypto-miners and malicious scripts.
    -   Includes extensive anti-fingerprinting rules.
    -   Aggressively blocks pop-ups, ads, and analytics networks.
-   📋 **Permissive Whitelist:** Pre-configured with exceptions for major services to prevent accidental breakage.

## ⚠️ The Privacy Trade-Off (Read Carefully)

This is **NOT** a maximum-privacy or "hardcore" configuration. To achieve its high level of compatibility, it makes a deliberate trade-off:

> **It sacrifices some level of privacy for enhanced functionality.**

Specifically, it may allow scripts from domains like `google-analytics.com` or `googletagmanager.com` on certain pages to prevent adblock detection. While this is limited and targeted, it is a conscious decision to prioritize user experience over absolute tracking prevention.

**Use this configuration if:** You are tired of broken websites and prioritize a seamless, uninterrupted browsing experience.

**Do NOT use this configuration if:** Your primary goal is to block all possible trackers and maintain the highest level of privacy, regardless of website functionality.

## 📥 Installation

1.  Download the `config.txt` file from this repository.
2.  Open uBlock Origin's dashboard (click the uBlock icon > the gear icon ⚙️).
3.  Navigate to the **Settings** tab.
4.  Scroll down to the section labeled **Backup and restore**.
5.  Click the button labeled **Restore from file...**.
6.  Select the `config.txt` file you downloaded.
7.  uBlock Origin will automatically reload with the new configuration.

## 📖 Configuration Breakdown

The custom filters (`userFilters`) are organized into the following sections:

### 1. Crypto-Miner Blocking
A robust list of rules to block known cryptocurrency mining domains and scripts, preventing them from using your CPU resources.

### 2. Anti-Fingerprinting
Targets common fingerprinting libraries and scripts to make your browser harder to track uniquely.

### 3. Anti-Adblock Detection Bypass (The Core Feature)
This is the most critical section. It contains:
-   **Anti-Bot System Allowlists:** Uses `$badfilter` to prevent other blocklists from breaking essential anti-bot services like Cloudflare and reCAPTCHA.
-   **Strategic Tracker Allowlisting:** Permits specific Google and Yandex analytics scripts to avoid detection patterns.
-   **Platform-Specific Bypasses:** Uses `##+js(set, ...)` and `##+js(aopr, ...)` scriptlets to disable adblock detection variables on major platforms.

### 4. Aggressive Pop-up & Ad Blocking
Redundant but effective rules to block aggressive pop-up ad networks and redirects that sometimes slip through standard blocklists.

### 5. Performance Enhancements
A very extensive list of analytics and advertising domains to be blocked, which can improve page load times.

### 6. Essential Exceptions
Whitelist rules (`@@||...`) to ensure that core functionality on sites like Google, Facebook, and various CDNs (like Cloudflare and Google Fonts) works correctly.

### 7. Security Rules (CSP)
Content Security Policy (CSP) modifications to ensure that file-hosting services like Mediafire, Dropbox, and Mega.nz function properly.

## 🔧 Customization & Maintenance

-   **Fragile Rules:** The anti-detection bypass rules are inherently **fragile**. Websites frequently update their detection methods, which can cause these rules to break.
-   **Maintenance:** If a website suddenly shows an adblock warning, this is the first section you should check. You may need to find the new detection variable and update the rules manually.
-   **Privacy vs. Compatibility:** You can increase privacy by removing the "Strategic Tracker Allowlisting" rules, but this will likely cause websites to detect your adblocker again.

## 🤝 Contributing

Found a broken bypass? Have a suggestion for a less intrusive rule? Contributions are welcome. Please open an issue or submit a pull request with a clear description of the problem and your proposed solution.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Credits

-   Original configuration and concept by **DanielTech**.
-   Built upon the powerful and flexible [uBlock Origin](https://github.com/gorhill/uBlock) by Raymond Hill.
-   Relies on the excellent work of various community-maintained filter lists.
