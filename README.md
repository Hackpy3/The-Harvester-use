# The-Harvester-use
**theHarvester** is a powerful reconnaissance tool used to collect information about domains, such as email addresses, subdomains, IPs, URLs, and more. It supports various data sources (search engines, social networks, etc.) to help gather intelligence for penetration testing or security assessments.

---

### **Outline of theHarvester Usage**
1. **Basic Syntax**:
   ```bash
   theHarvester -d [domain] -l [limit] -b [data source(s)]
   ```

2. **Key Parameters**:
   - `-d [domain]`: Specifies the target domain.
   - `-l [limit]`: Limits the number of results (if supported by the source).
   - `-b [source(s)]`: Specifies the data source(s) to query (e.g., Google, Bing, etc.).
   - `-f [filename]`: Saves the output to a file (optional).
   - `-h`: Displays help and usage instructions.

3. **Supported Data Sources**:
   Common sources include:
   - `google`: Google search engine
   - `bing`: Bing search engine
   - `crtsh`: Certificate transparency logs
   - `linkedin`: LinkedIn profiles (requires an API key)
   - `shodan`: Shodan (requires an API key)

   For the complete list of sources, check:
   ```bash
   theHarvester -h
   ```

---

### **Examples of Using theHarvester**

#### 1. **Basic Domain Search**:
   Search for information about `example.com` using Google and limit the results to 100:
   ```bash
   theHarvester -d example.com -l 100 -b google
   ```

#### 2. **Search Multiple Sources**:
   Query multiple sources (e.g., Google and Bing):
   ```bash
   theHarvester -d example.com -l 100 -b google,bing
   ```

#### 3. **Save Output to a File**:
   Save results to an HTML file for later review:
   ```bash
   theHarvester -d example.com -l 100 -b google -f output.html
   ```

#### 4. **Using Shodan (API Key Required)**:
   If you have a Shodan API key, you can integrate it to gather IP-related information:
   ```bash
   theHarvester -d example.com -l 100 -b shodan
   ```

#### 5. **Full Reconnaissance Example**:
   Collect all possible information about `target.com` using every available source:
   ```bash
   theHarvester -d target.com -l 500 -b all
   ```

---

### **Output Example**:
For the command:
```bash
theHarvester -d example.com -l 50 -b google
```
The output might look like this:
```
[-] Emails found:
    admin@example.com
    support@example.com

[-] Subdomains found:
    mail.example.com
    dev.example.com

[-] IPs found:
    192.168.1.1
    192.168.1.2
```

---

### **Tips**:
1. Always ensure you comply with legal and ethical guidelines when using reconnaissance tools.
2. Some sources (e.g., Shodan, LinkedIn) require API keys. You can configure these in theHarvester’s configuration file.

Let me know if you need help with specific commands or configuration!
