# VeriPulse OSINT

**Username Authenticity & Fake Account Auditor**

VeriPulse OSINT is a client-side, web-based intelligence tool designed to audit exact usernames across multiple platforms. It evaluates whether an account belongs to a genuine, established individual or if it exhibits the characteristics of a fake, bot, burner, or scam profile.

By combining live cross-origin (CORS) API telemetry, lexical entropy analysis, and a 12-platform footprint heuristic, VeriPulse provides a comprehensive authenticity score and interactive threat analysis dashboard.

## Features

*   **12-Platform Footprint Matrix:** Audits the presence and strength of a given username across 12 major networks including GitHub, Reddit, LinkedIn, X (Twitter), Instagram, YouTube, Medium, Keybase, TikTok, Telegram, Twitch, and Pinterest.
*   **Live API Telemetry:** Directly queries public endpoints (GitHub and Reddit) from the browser to extract real account age, karma, repositories, and historical anchors.
*   **Lexical & Entropy Engine:** Calculates Shannon entropy, numeric density (e.g., `user948104821`), and scans for deceptive social engineering patterns (e.g., `_giveaway`, `_official`).
*   **5-Pillar Authenticity Radar:** Visualizes trust metrics across five dimensions:
    1. Cross-Platform Breadth
    2. Lexical Naturalness
    3. Account Longevity
    4. Identity Coherence
    5. Activity vs. Ghost-Shell Ratio
*   **Investigator-in-the-Loop Override:** Manually recalibrate the authenticity score by clicking any platform's status badge to toggle between `Confirmed Active`, `Ghost / Shell`, or `Unclaimed` as you verify profiles manually.
*   **Forensic Dossier Export:** Generate and download a comprehensive text dossier or raw JSON telemetry file for your investigation reports.

## Getting Started

VeriPulse OSINT is a fully client-side tool requiring no backend infrastructure or API keys for its core heuristics.

1.  Download or clone the repository containing `index.html`.
2.  Open `index.html` directly in any modern web browser (Chrome, Firefox, Edge, Safari).
3.  Enter a target username in the search bar and select the expected persona (e.g., Developer, Brand, Crypto).
4.  Click **Verify Authenticity** to run the audit.

## Tech Stack

*   **HTML5 / JavaScript (ES6):** Core application logic and OSINT heuristics.
*   **Tailwind CSS:** Styling, layout, and dark-mode glassmorphic UI.
*   **HTML Canvas API:** Rendering the interactive 5-axis pentagon radar chart.
*   **Phosphor Icons:** Scalable iconography.

## Important Notes & Limitations

*   **CORS Limitations:** Because this tool runs entirely in the browser, it can only fetch live data from APIs that support Cross-Origin Resource Sharing (CORS) without authentication (currently optimized for GitHub and Reddit). 
*   **Heuristic Nature:** The presence on platforms outside of the live APIs is calculated using a deterministic heuristic model based on username hashes and lexical quality for demonstration and UI testing purposes. In a production environment, this should be connected to a backend proxy or OSINT API (like Pipl, WhatsMyName, or Social Searcher) for live verification across all 12 sites.
*   **Ethical Use:** This tool is intended for Trust & Safety, cybersecurity research, and personal verification. Do not use this tool to harass or stalk individuals.

## License

This project is provided for educational and research purposes.