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

Sure! Here's a wide range of **examples**—from beginner tools to more advanced recon and fingerprinting methods—that help you **find technologies used in websites**.

---

## 🔹 **1. WhatWeb (Kali Linux Tool)**

### Install (if not already):

```bash
sudo apt install whatweb
```

### Examples:

```bash
whatweb https://tesla.com
whatweb -v https://github.com
whatweb -a 3 https://cnn.com         # aggressive scan
whatweb -U Mozilla https://netflix.com   # spoof user agent
```

---

## 🔹 **2. BuiltWith (Web-based)**

### Examples:

* Visit: [https://builtwith.com](https://builtwith.com)
* Try:

  * [https://builtwith.com/facebook.com](https://builtwith.com/facebook.com)
  * [https://builtwith.com/shopify.com](https://builtwith.com/shopify.com)
  * [https://builtwith.com/zomato.com](https://builtwith.com/zomato.com)

---

## 🔹 **3. Wappalyzer CLI (Node-based)**

### Install:

```bash
npm install -g wappalyzer
```

### Example:

```bash
wappalyzer https://nytimes.com
wappalyzer --delay 1000 https://forbes.com
```

---

## 🔹 **4. Online APIs (Python-based Example)**

### Example using [Wappalyzer API](https://www.wappalyzer.com/api/):

```python
import requests

headers = {
    'x-api-key': 'YOUR_WAPPALYZER_API_KEY'
}
url = 'https://api.wappalyzer.com/v2/lookup/?urls=https://github.com'

response = requests.get(url, headers=headers)
print(response.json())
```

---

## 🔹 **5. Using `curl` to check HTTP headers (Manual way)**

```bash
curl -I https://example.com
```

🔍 Look for:

* `Server: Apache`
* `X-Powered-By: PHP/7.4.3`
* `Via: Cloudflare`

---

## 🔹 **6. `httprobe` + `whatweb` for mass scanning**

Example:

```bash
cat websites.txt | httprobe | xargs -n1 -P10 whatweb
```

---

## 🔹 **7. Nikto (Web server scanner)**

```bash
nikto -h https://example.com
```

It shows:

* Apache version
* HTTP headers
* Server modules

---

## 🔹 **8. Nmap with http-enum script**

```bash
nmap -p 80,443 --script http-enum example.com
```

---

## 🔹 **9. Firefox/Chrome Dev Tools**

Steps:

1. Open the website
2. Press `F12` or Right Click > Inspect
3. Look in:

   * Network tab → Server headers
   * Console tab → JavaScript libraries (React, Vue, etc.)
   * Source tab → CMS paths (like `wp-content`, `theme`, etc.)

---

## 🔹 **10. EyeWitness (for screenshots + tech info)**

```bash
git clone https://github.com/FortyNorthSecurity/EyeWitness.git
cd EyeWitness
./EyeWitness.py --web -f urls.txt --no-prompt
```

---

## 🔹 **11. Online Tools — More Examples**

### 🕵️‍♂️ **Netcraft**

* [https://sitereport.netcraft.com/](https://sitereport.netcraft.com/)
* Example:

  * [https://sitereport.netcraft.com/?url=bbc.com](https://sitereport.netcraft.com/?url=bbc.com)

### 🔍 **SecurityHeaders**

* [https://securityheaders.com/](https://securityheaders.com/)
* Shows headers like `X-Powered-By`, `Server`, `Framework`.

---

## ✅ Example Output from Tools

### WhatWeb:

```bash
whatweb https://wordpress.com
```

**Output:**

```
WordPress.com [200 OK] Country[US], IP[192.0.78.17], PHP[8.0.28], WordPress, Google-Analytics, Jetpack
```

---

## 💡 Bonus: Passive DNS & CDN detection tools

* `dnsx` — DNS records
* `cdnx` — CDN fingerprinting
* `subfinder` — to discover tech on subdomains too

---

Would you like a **script** that can scan multiple websites and show technologies side-by-side in a table? I can write one in Python or Bash depending on your preference.

