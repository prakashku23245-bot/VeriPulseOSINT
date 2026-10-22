# Project Report: VeriPulse OSINT

## 1. Project Title
**VeriPulse OSINT:** Web-Based Fake Account & Username Authenticity Verification Platform

## 2. Abstract
The proliferation of bots, burners, and impersonation accounts across social media and developer ecosystems poses a significant threat to digital trust and brand integrity. VeriPulse OSINT is a client-side web application designed to evaluate the authenticity of a specific username. By synthesizing live cross-origin API telemetry, lexical entropy analysis, and deterministic platform footprint heuristics, the tool calculates the probability of an account being genuine versus a deceptive shell profile, presenting the findings in a highly visual, investigator-friendly dashboard.

## 3. Problem Statement
Identifying fake accounts manually requires investigators to comb through multiple platforms, calculate account ages, assess followers/activity ratios, and evaluate handle naming conventions. This process is time-consuming and fragmented. Furthermore, many existing tools are either closed-source enterprise solutions or require complex backend infrastructure and paid API keys to function.

## 4. Proposed Solution
VeriPulse OSINT solves this by providing a unified, zero-configuration dashboard that runs entirely in the user's browser. It automates the extraction of key forensic indicators and visualizes them using a 5-pillar trust methodology. 

### 4.1 Key Objectives
* **Cross-Platform Verification:** Check the username across 12 distinct networks (Developer, Social, Video, Forum).
* **Algorithmic Trust Scoring:** Provide an actionable 0-100 authenticity score and a corresponding fake/bot probability percentage.
* **Visual Data Representation:** Utilize radar charts, progress bars, and colored flags to make complex OSINT data easily digestible.
* **Investigator-in-the-loop:** Allow human analysts to override automated findings and recalculate scores in real-time.

## 5. System Architecture & Methodology
The application is built on a serverless, client-heavy architecture. 

### 5.1 The 5-Pillar Heuristic Engine
The tool evaluates authenticity based on five core metrics:
1. **Cross-Platform Breadth:** Real users tend to have a footprint spanning multiple ecosystems (e.g., coding, social, video).
2. **Lexical Naturalness:** Shannon entropy algorithms and regex matchers evaluate the handle for bot patterns (e.g., numeric suffixes, keyboard smashes) and scam lures (e.g., "giveaway", "official").
3. **Account Longevity:** Older accounts drastically reduce the probability of being disposable burners.
4. **Identity Coherence:** The consistency of public metadata (bios, names, avatars) across platforms.
5. **Activity vs. Ghost-Shell Ratio:** High numbers of empty "shell" accounts indicate automated bulk registration, whereas active engagement (repos, karma) indicates human usage.

### 5.2 Live CORS Probing
To anchor the heuristic data with factual evidence, the tool queries the GitHub and Reddit public APIs directly from the client. It safely aborts if the endpoints timeout or hit rate limits, falling back gracefully to the deterministic model.

## 6. Implementation Details
* **Frontend UI:** HTML5 structured with Tailwind CSS via CDN. The design language employs a "cybersecurity glassmorphic" aesthetic with dark tones (`obsidian`) and vibrant accents (`pulse-cyan`, `emerald`).
* **JavaScript Engine:** ES6+ JavaScript handles the asynchronous API fetching (`fetch`, `Promises`), state management, DOM manipulation, and mathematical scoring models.
* **Data Visualization:** The HTML `<canvas>` API is used to draw a dynamic, 5-axis pentagon radar chart that visually maps the 5-pillar scores.

## 7. Limitations
* **CORS Restrictions:** Because the tool operates in-browser without a proxy, it cannot make live API calls to platforms that strictly block CORS (e.g., LinkedIn, Instagram). For non-CORS platforms, the tool relies on a deterministic heuristic model for demonstration purposes.
* **Rate Limiting:** Unauthenticated requests to GitHub and Reddit are subject to strict IP-based rate limits.

## 8. Future Scope
* **Backend Proxy Integration:** Connecting the frontend to a Node.js or Python backend proxy would bypass CORS restrictions, allowing live scraping or API verification for all 12 platforms.
* **Image Forensics:** Integrating a reverse image search API for profile avatars to detect stock photos or AI-generated faces.
* **Historical Web Archives:** Connecting to the Wayback Machine API to check if a username was recently changed or wiped.

## 9. Conclusion
VeriPulse OSINT successfully demonstrates how advanced client-side processing can be leveraged to build a fast, visually appealing, and highly effective digital forensics tool. It streamlines the initial triage phase for Trust & Safety teams, OSINT researchers, and everyday users looking to verify digital identities.