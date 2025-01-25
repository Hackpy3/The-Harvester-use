# The-Harvester-use
**theHarvester** is a powerful reconnaissance tool used to collect information about domains, such as email addresses, subdomains, IPs, URLs, and more. It supports various data sources (search engines, social networks, etc.) to help gather intelligence for penetration testing or security assessments.

---
**Key Parameters**:
   - `-d [domain]`: Specifies the target domain.
   - `-l [limit]`: Limits the number of results (if supported by the source).
   - `-b [source(s)]`: Specifies the data source(s) to query (e.g., Google, Bing, etc.).
   - `-f [filename]`: Saves the output to a file (optional).
   - `-h`: Displays help and usage instructions.
   -  `[options]`: Additional flags to customize the scan.

## **1. Basic Options**

### Help Menu
```bash
theharvester -h
```
- Displays the help menu with all options and their descriptions.

### Example: Basic Domain Search
```bash
theharvester -d example.com -b google
```
- Gathers information about `example.com` using Google as the data source.

---

## **2. Data Sources (`-b` Option)**

TheHarvester supports a variety of sources. Some common ones include:

- `google`: Searches Google.
- `bing`: Searches Bing.
- `duckduckgo`: Searches DuckDuckGo.
- `crtsh`: Certificate Transparency logs.
- `linkedin`: Gathers data from LinkedIn.
- `hackertarget`: Uses HackerTarget for reconnaissance.

### Example: Using a Specific Source
```bash
theharvester -d example.com -b bing
```
- Queries Bing for data about `example.com`.

### Example: Using Multiple Sources
```bash
theharvester -d example.com -b google,bing,crtsh
```
- Searches multiple sources for comprehensive results.

---

## **3. Gathering Specific Information**

### Example: Emails Only
```bash
theharvester -d example.com -b google -f emails
```
- Filters results to show only email addresses.

### Example: Subdomains Only
```bash
theharvester -d example.com -b google -f subdomains
```
- Filters results to show only subdomains.

---

## **4. Saving Results**

### Save Results to a File
```bash
theharvester -d example.com -b google -f output.txt
```
- Saves the output to `output.txt`.

### Save Results in JSON Format
```bash
theharvester -d example.com -b google -f output.json
```
- Outputs results in JSON format.

---

## **5. Advanced Options**

### Example: Limit the Number of Results
```bash
theharvester -d example.com -b google -l 50
```
- Limits the results to 50 entries per source.

### Example: Use a Proxy Server
```bash
theharvester -d example.com -b google --proxy http://proxy:8080
```
- Routes the queries through a proxy server.

### Example: Enable Virtual Host Search
```bash
theharvester -d example.com -b google -v
```
- Searches for virtual hosts.

---

## **6. API Usage**

Some sources require an API key (e.g., Shodan, Hunter.io).

### Example: Configure and Use an API Key
1. Add your API key in the configuration file:
   ```bash
   nano ~/.theHarvester/settings.yaml
   ```
2. Use the corresponding data source:
   ```bash
   theharvester -d example.com -b shodan
   ```

---

## **7. Real-World Scenarios**

### Scenario 1: Gather Email Addresses
```bash
theharvester -d targetcompany.com -b google
```
- Finds email addresses related to `targetcompany.com` using Google.

### Scenario 2: Find Subdomains
```bash
theharvester -d targetcompany.com -b crtsh
```
- Finds subdomains using certificate transparency logs.

### Scenario 3: Comprehensive Reconnaissance
```bash
theharvester -d targetcompany.com -b google,bing,crtsh -l 100 -f results.txt
```
- Uses multiple sources, limits results to 100 entries, and saves output to `results.txt`.

### Scenario 4: Use API for Shodan Data
```bash
theharvester -d targetcompany.com -b shodan
```
- Retrieves network information from Shodan.

---
Here are additional **examples of using different options** in TheHarvester to customize scans for various use cases:

---

### **1. Collect Emails, Subdomains, and IPs**
```bash
theharvester -d example.com -b google -f collected_data.txt
```
- Collects emails, subdomains, and IP addresses for `example.com` and saves them to `collected_data.txt`.

---

### **2. Search Specific Emails with Regex**
```bash
theharvester -d example.com -b google --regex ".*@example.com"
```
- Filters emails specifically matching the domain `example.com`.

---

### **3. Set a Custom Timeout for Queries**
```bash
theharvester -d example.com -b google --timeout 10
```
- Sets a 10-second timeout for queries to avoid delays or long waits.

---

### **4. Save Results in All Supported Formats**
```bash
theharvester -d example.com -b google -f results -e all
```
- Saves results in all supported formats (TXT, JSON, XML).

---

### **5. Perform Passive Subdomain Enumeration**
```bash
theharvester -d example.com -b crtsh --dns-resolve False
```
- Passively collects subdomain information without performing DNS resolution.

---

### **6. Use a Custom User-Agent**
```bash
theharvester -d example.com -b google --user-agent "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36"
```
- Uses a custom user-agent string for web scraping to mimic a browser request.

---

### **7. Display Only Collected Subdomains**
```bash
theharvester -d example.com -b bing -f subdomains_list.txt -v
```
- Searches Bing for subdomains of `example.com`, includes verbose output, and saves subdomains to `subdomains_list.txt`.

---

### **8. Perform a Search with Tor Proxy**
```bash
theharvester -d example.com -b google --proxy socks5h://127.0.0.1:9050
```
- Routes all traffic through the Tor network by specifying the Tor proxy.

---

### **9. Generate a Comprehensive Report**
```bash
theharvester -d example.com -b google,bing,crtsh --report-format pdf --output report.pdf
```
- Uses multiple sources, generates a report in PDF format, and saves it as `report.pdf`.

---

### **10. Limit Results for Faster Recon**
```bash
theharvester -d example.com -b google -l 10
```
- Limits the search to 10 results per data source for quicker reconnaissance.

---

### **11. Use DNS Brute Force for Subdomains**
```bash
theharvester -d example.com -b bing --dns-brute
```
- Brute-forces subdomains of `example.com` using common wordlists.

---

### **12. Identify Web Server Technologies**
```bash
theharvester -d example.com -b google --take-over
```
- Checks for potential subdomain takeovers and identifies associated technologies.

---

### **13. Perform a DNS Reverse Lookup**
```bash
theharvester -d example.com -b google --dns-reverse
```
- Conducts a reverse DNS lookup for identified IP addresses.

---

### **14. Collect Data with Shodan API**
```bash
theharvester -d example.com -b shodan
```
- Uses the Shodan API to gather additional network and infrastructure data for `example.com`.

---

### **15. Use a Randomized Delay Between Queries**
```bash
theharvester -d example.com -b google --random-agent --delay 5
```
- Uses a random user-agent and adds a 5-second delay between queries to avoid detection or rate-limiting.

---

### **Combined Example with Multiple Options**
```bash
theharvester -d example.com -b google,bing,crtsh --dns-resolve False -l 50 --proxy http://127.0.0.1:8080 --user-agent "Mozilla/5.0" -f results.json
```
- Searches across Google, Bing, and crt.sh:
  - Disables DNS resolution.
  - Limits to 50 results per source.
  - Uses a proxy and custom user-agent.
  - Saves results in JSON format as `results.json`.

---

These examples demonstrate the flexibility of TheHarvester. Let me know if you'd like examples tailored to a specific scenario!
