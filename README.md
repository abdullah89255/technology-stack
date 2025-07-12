# technology-stack
To find the **technology stack** (frameworks, CMS, libraries, server info, etc.) used by a website, you can use several **manual**, **online**, or **tool-based** methods. Here's a complete breakdown:

---

## ✅ **1. Use Online Tools (Fastest and Easiest)**

### 🔍 [**BuiltWith**](https://builtwith.com/)

* Enter the website URL → Get a full tech stack: CMS, JS libraries, server, analytics, ads, etc.
* Example: `https://builtwith.com/nytimes.com`

### 🔍 [**Wappalyzer**](https://www.wappalyzer.com/)

* Works similarly to BuiltWith.
* Also available as a **browser extension** for Chrome/Firefox.
* It shows real-time data on technologies used.

---

## ✅ **2. Use Browser Extensions**

### 🧩 **Wappalyzer Extension** (recommended)

* Adds an icon to your browser.
* Click it while browsing any site → instantly see frameworks, CMS, JS libraries, etc.

### 🧩 **WhatRuns Extension**

* Similar to Wappalyzer.
* Also shows fonts, plugins, trackers, themes, etc.

---

## ✅ **3. Use Command-Line Tools**

### 🛠️ **Wappalyzer CLI**

Install via NPM:

```bash
npm install -g wappalyzer
```

Then:

```bash
wappalyzer https://example.com
```

### 🛠️ **WhatWeb** (Great for Kali Linux)

```bash
sudo apt install whatweb
whatweb https://example.com
```

**Example Output:**

```
https://example.com [200 OK] Country[US], IP[93.184.216.34], Apache[2.4.29], HTML5, PHP[7.2.24]
```

---

## ✅ **4. Inspect the Website Manually**

### 🔧 Check `HTML source code`:

* Right-click > View Page Source → Look for:

  * `wp-content` → WordPress
  * `drupal.js` → Drupal
  * `cdn.shopify.com` → Shopify
  * `assets.wix.com` → Wix
  * Google Analytics/Tag Manager → `gtag.js` or `googletagmanager.com`

### 🔧 Check `Developer Tools` (F12 → Network / Console):

* JS libraries like `React`, `Angular`, or `Vue` may show up.
* See server headers: click any request and check `Response Headers`.

---

## ✅ **5. Use Online Scanners**

* [https://nerdydata.com/](https://nerdydata.com/) — search source code across websites.
* [https://www.siteanalyzer.com/](https://www.siteanalyzer.com/) — includes tech, SEO, etc.

---

## ✅ **6. Passive Recon Tools (Advanced)**

* **Netcraft**: [https://sitereport.netcraft.com/](https://sitereport.netcraft.com/)
* **Censys / Shodan**: IP-based tech fingerprinting.
* Example with Shodan:

  ```bash
  shodan host example.com
  ```

---

## Summary Table

| Method                   | Best For                   | Skill Required |
| ------------------------ | -------------------------- | -------------- |
| BuiltWith / Wappalyzer   | Instant tech stack view    | Beginner       |
| WhatWeb / Wappalyzer CLI | Fast scanning in terminal  | Intermediate   |
| View Source / Dev Tools  | Manual inspection          | Intermediate   |
| Shodan / Censys          | Fingerprinting via IP/Port | Advanced       |

---

Would you like a **Bash script or Python tool** that checks tech stacks from a list of websites? I can create one for you.
