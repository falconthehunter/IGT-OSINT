IGT: Information Gathering Toolkit (minimal)



A high-speed, asynchronous social media username scanner that generates smart variations to find user profiles across multiple platforms. Powered by aiohttp for concurrent HTTP requests and rich for elegant CLI output and HTML reporting.


---

📋 Table of Contents

Features

Prerequisites

Installation

Configuration

Usage

Outputs

Customization

Error Handling & Logs

Contributing

License



---

🚀 Features

Smart Username Variations: Generates 100+ variations (leet, prefixes, suffixes, numbers, separators).

Multi-Platform Support: Scan up to 8 platforms—Facebook, Instagram, Twitter/X, Snapchat, Telegram, TikTok, Threads.

Async & Concurrent: Utilizes asyncio and aiohttp with configurable concurrency.

Rich CLI: Progress bars, spinners, and summary tables via the rich library.

HTML Report: Real-time pie charts and detailed results in a standalone HTML file.

Error Logging: Captures and logs HTTP/parsing errors.



---

⚙️ Prerequisites

Python 3.8+

Basic Python knowledge



---

🛠️ Installation

1. Clone the Repository:

git clone https://github.com/falconthehunter/IGT-OSINT.git
cd IGT-OSINT


2. Create & Activate Virtual Environment:

python3 -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate   # Windows


3. Install Dependencies:

pip install -r requirements.txt




---

🔧 Configuration

1. Platform Definitions: Edit or create plt.json based on provided sample:

[
  {
    "name": "twitter",
    "url": "https://twitter.com/{}",
    "validation": { "text_absent": "Sorry, that page doesn\u2019t exist!" }
  },
  {
    "name": "instagram",
    "url": "https://www.instagram.com/{}/",
    "validation": { "absent": "Sorry, this page isn\u2019t available." }
  }
  // ... add or update platforms
]


2. User Agents: Customize USER_AGENTS in IGT.py to rotate request headers.


3. Concurrency: Adjust DEFAULT_CONCURRENCY to optimize performance vs. rate limits.




---

▶️ Usage

Run the scanner:

python3 IGT.py

Prompt: Enter the base username (e.g., johndoe).

Process: The script generates variations, scans each platform concurrently, and displays a live progress bar.


Sample Output:

IGTPro Social Scan Turbo Edition — Facebook | Instagram | Twitter | Snapchat | Telegram | TikTok | Threads
Enter the username to scan: johndoe
Generating 100+ smart username variations...
Scanning johndoe across 8 platforms and 120 variations (~960 checks)...

[Scanning...  50%] ■■■■□□□□□□  • 00:15 / 00:30 remaining

[green][+] HTML result saved to results/johndoe_scan_20250519_142530.html[/green]

╭─ Scan Summary ─────────────────────────────────────────────────────────╮
│ Platform   │ Found │ Not Found                                         │
│ Instagram  │   5   │    115                                            │
│ Twitter    │   3   │    117                                            │
│ ...                                                                    │
╰────────────────────────────────────────────────────────────────────────╯

7 found / 960 checked in 32.5 seconds.


---

📂 Outputs

results/ directory:

errors.log: Logged exceptions and errors.

<username>_scan_<timestamp>.html: Interactive HTML report with charts and details.




---

🛠️ Customization

Adding Platforms: Add JSON entries in plt.json.

Variation Rules: Modify generate_variations() for custom patterns.

Report Styling: Tweak CSS or Chart.js config in save_html().



---

🐞 Error Handling & Logs

All HTTP and parsing errors are appended to results/errors.log.

Non-fatal errors won’t stop the scan; they’ll be recorded and skipped.



---

🤝 Contributing

Contributions are welcome! Please:

1. Fork the repo


2. Create a feature branch feature/awesome-feature


3. Commit your changes


4. Open a Pull Request




---

📜 License

This project is licensed under the MIT License. See LICENSE for details.


---

> Built with ❤️ and Python by the Anhar Hussan.



