![Python](https://img.shields.io/badge/python-3.10+-blue)
![Node.js](https://img.shields.io/badge/node.js-18+-green)


# Cloudflare 1020 Bypass Examples (Python & Node.js)
[![HasData_bannner](banner.png)](https://hasdata.com/?utm_source=github&utm_medium=syndication&utm_campaign=cloudflare-1020)

This repo contains working examples of bypassing **Cloudflare 1020** errors using **Playwright + Stealth** with **residential proxies**, **rotating headers**, and **basic anti-bot evasion tricks**. Works in **Node.js** and **Python**.

## Table of Contents

1. [Requirements](#requirements)
2. [Project Structure](#project-structure)
3. [Bypass Examples](#bypass-examples)
   * [Playwright Basic](#playwright-basic)
   * [Playwright + Stealth](#playwright--stealth)
   * [Residential Proxy Rotation](#residential-proxy-rotation)
   * [User-Agent + Header Spoofing](#user-agent--header-spoofing)
   * [Human-like Behavior](#human-like-behavior)
   * [Full Flow Example](#full-flow-example)

## Requirements

**Python 3.10+** or **Node.js 18+**

### Python Setup

Required packages:

- `requests`
- `playwright`
- `playwright-stealth`

Install:

```bash
pip install playwright
playwright install
pip install playwright-stealth
```

### Node.js Setup

Required packages:

- `playwright`
- `playwright-extra`
- `playwright-extra-plugin-stealth`

Install:

```bash
npm install playwright playwright-extra playwright-extra-plugin-stealth
```

## Project Structure

```
cf1020-bypass-examples/
│
├── python/
│   ├── basic_playwright.py
│   ├── stealth_playwright.py
│   ├── proxy_rotation.py
│   ├── header_rotation.py
│   ├── human_behavior.py
│   ├── full_flow_example.py
│
├── nodejs/
│   ├── basic_playwright.js
│   ├── stealth_playwright.js
│   ├── proxy_rotation.js
│   ├── header_rotation.js
│   ├── human_behavior.js
│   ├── full_flow_example.js
│
└── README.md
```

Each script shows a different tactic for avoiding Cloudflare 1020. No frameworks, no noise — just straight working examples.

## Bypass Examples


### Playwright Basic

Basic page load using vanilla Playwright (likely to trigger CAPTCHA or 1020).
| Parameter     | Description            | Example                 |
| ------------- | ---------------------- | ----------------------- |
| `url`         | Target URL to load     | `'https://example.com'` |
| `timeout`     | Maximum wait time (ms) | `60000`                 |
| `output_file` | File to save page HTML | `'page.html'`           |


### Playwright + Stealth

Hide `webdriver` flag, spoof plugins, patch headless indicators.

| Parameter    | Description                  | Example                 |
| ------------ | ---------------------------- | ----------------------- |
| `target_url` | URL to visit and scrape      | `'https://example.com'` |
| `headless`   | Run browser in headless mode | `True`                  |
| `timeout`    | Maximum wait time (ms)       | `60000`                 |


### Residential Proxy Rotation

Add a pool of rotating residential proxies for better IP reputation.

| Parameter       | Description                                   | Example                                 |
| --------------- | --------------------------------------------- | --------------------------------------- |
| `target_url`    | URL to visit with rotating headers            | `'https://example.com'`                 |
| `user_agents`   | List of User-Agent strings to rotate          | `['Mozilla/5.0...', 'Chrome/91.0...']`  |
| `extra_headers` | Additional HTTP headers to include (optional) | `{'Accept-Language': 'en-US,en;q=0.9'}` |
| `rotate_every`  | Number of requests before changing header     | `1` (rotate every request)              |


### User-Agent + Header Spoofing

Randomized headers and modern user agents for each session.
| Parameter     | Description                              | Example                                 |
| ------------- | ---------------------------------------- | --------------------------------------- |
| `target_url`  | URL to visit with rotated headers        | `'https://example.com'`                 |
| `user_agents` | List of User-Agent strings to rotate     | `["Mozilla/5.0...", "Safari/537.36"]`   |
| `headers`     | Additional HTTP headers to include       | `{"Accept-Language": "en-US,en;q=0.9"}` |
| `proxy`       | Proxy server address (optional)          | `'http://user:pass@proxy.com:8080'`     |
| `timeout`     | Max time to wait for page load (seconds) | `30`                                    |


### Human-like Behavior

Add mouse movement, scrolling, and timed delays.
| Parameter                     | Description                 | Example                                      |
| ----------------------------- | --------------------------- | -------------------------------------------- |
| `page`                        | Playwright page object      | `page.goto('https://example.com')`           |
| `sleep`                       | Pause execution for realism | `time.sleep(1.5)` / `await sleep(1500)` (ms) |
| `mouse.move(x, y)`            | Move mouse cursor to (x, y) | `page.mouse.move(100, 100)`                  |
| `mouse.click(x, y)`           | Click at coordinates (x, y) | `page.mouse.click(200, 300)`                 |
| `keyboard.press(key)`         | Simulate keyboard key press | `page.keyboard.press('PageDown')`            |
| `mouse.wheel(deltaX, deltaY)` | Scroll page by delta        | `page.mouse.wheel(0, 400)`                   |


### Full Flow Example

All combined: stealth, headers, proxies, behavior — in one script.

| Parameter     | Description                                       | Example                                          |
| ------------- | ------------------------------------------------- | ------------------------------------------------ |
| `proxy`       | Proxy server URL with auth                        | `'http://user:pass@proxy.example:8000'`          |
| `user_agent`  | Browser user agent string                         | `'Mozilla/5.0 (Windows NT 10.0; Win64; x64)...'` |
| `target_url`  | URL to navigate and scrape                        | `'https://example.com'`                          |
| `headless`    | Whether to run browser in headless mode           | `True` (Python) / `true` (Node.js)               |
| `delay_range` | Range (seconds) for random delays between actions | `0.5 to 2 seconds`                               |


## Disclaimer

These examples are for **educational purposes** only. Learn more about [the legality of web scraping](https://hasdata.com/blog/is-web-scraping-legal?utm_source=github&utm_medium=syndication&utm_campaign=cloudflare-1020).



## 📎 More Resources

* [How to Bypass Cloudflare 1020](https://hasdata.com/blog/bypass-cloudflare-1020?utm_source=github&utm_medium=syndication&utm_campaign=cloudflare-1020)
* [Join the community on Discord](https://discord.com/invite/kckPcEdGWs)
* [Star this repo if helpful ⭐](#)
