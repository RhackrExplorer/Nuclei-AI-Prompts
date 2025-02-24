## Nuclei AI Prompts

### Website: [Nuclei Prompts](https://nucleiprompts.com/)

### Fast Info Gathering
```sh
nuclei -list targets.txt -ai "Extract page title, detect tech and versions"
nuclei -list targets.txt -ai "Extract email addresses from web pages"
nuclei -list targets.txt -ai "Extract all subdomains referenced in web pages"
```

### Low Hanging Fruits
```sh
nuclei -list targets.txt -ai "Find sensitive information in HTML comments (debug notes, API keys, credentials)"
nuclei -list targets.txt -ai "Find exposed .env files leaking credentials, API keys, and database passwords"
nuclei -list targets.txt -ai "Find exposed configuration files such as config.json, config.yaml, config.php, application.properties containing API keys and database credentials."
nuclei -list targets.txt -ai "Find exposed database configuration files such as database.yml, db_config.php, .pgpass, .my.cnf leaking credentials."
nuclei -list targets.txt -ai "Find exposed Docker and Kubernetes configuration files such as docker-compose.yml, kubeconfig, .dockercfg, .docker/config.json containing cloud credentials and secrets."
nuclei -list targets.txt -ai "Find exposed SSH keys and configuration files such as id_rsa, authorized_keys, and ssh_config."
nuclei -list targets.txt -ai "Find exposed WordPress configuration files (wp-config.php) containing database credentials and authentication secrets."
nuclei -list targets.txt -ai "Identify open directory listings exposing sensitive files"
nuclei -list targets.txt -ai "Find exposed .git directories allowing full repo download"
nuclei -list targets.txt -ai "Find exposed .svn and .hg repositories leaking source code"
nuclei -list targets.txt -ai "Identify open FTP servers allowing anonymous access"
```

### Advanced Mixed Testing
```sh
nuclei -list targets.txt -ai "Detect debug endpoints revealing system information"
nuclei -list targets.txt -ai "Identify test and staging environments exposed to the internet"
nuclei -list targets.txt -ai "Find admin login endpoints, filter 404 response code"
nuclei -list targets.txt -ai "Detect exposed stack traces in error messages"
nuclei -list targets.txt -ai "Identify default credentials on login pages"
nuclei -list targets.txt -ai "Find misconfigured Apache/Nginx security headers"
```

### Sensitive Data Exposure
```sh
nuclei -list targets.txt -ai "Scan for exposed environment files (.env) containing credentials"
nuclei -list targets.txt -ai "Find open directory listings and publicly accessible files"
nuclei -list targets.txt -ai "Detect exposed .git repositories and sensitive files"
nuclei -list targets.txt -ai "Identify publicly accessible backup and log files (.log, .bak, .sql, .dump)"
nuclei -list targets.txt -ai "Detect exposed .htaccess and .htpasswd files"
nuclei -list targets.txt -ai "Check for SSH private keys leaked in web directories"
nuclei -list targets.txt -ai "Find exposed API keys and secrets in responses and URLs"
nuclei -list targets.txt -ai "Identify API endpoints leaking sensitive data"
nuclei -list targets.txt -ai "Find leaked database credentials in JavaScript files"
```

### SQL Injection (SQLi)
```sh
nuclei -list katana.jsonl -im jsonl -ai "Perform fuzzing on all parameters and HTTP methods using DSL, focusing on detecting SQL Injection vulnerabilities with pre-conditions."
nuclei -list katana.jsonl -im jsonl -ai "Detect SQL error messages indicating SQL injection vulnerabilities"
nuclei -list katana.jsonl -im jsonl -ai "Detect SQL errors in response when injecting common payloads into GET and POST requests"
```

### Cross-Site Scripting (XSS)
```sh
nuclei -list katana.jsonl -im jsonl -ai "Perform fuzzing on all parameters and HTTP methods using DSL, focusing on detecting XSS vulnerabilities (Reflected, Stored, and DOM-based) with pre-conditions."
nuclei -list katana.jsonl -im jsonl -ai "Find reflected XSS in 'q', 'search', 's', 'redirect', 'next', 'return', 'url' parameters"
nuclei -list katana.jsonl -im jsonl -ai "Find stored XSS in all parameters"
nuclei -list katana.jsonl -im jsonl -ai "Identify stored XSS in comment fields, usernames, profile descriptions"
```

### Server-Side Request Forgery (SSRF)
```sh
nuclei -list katana.jsonl -im jsonl -ai "Perform fuzzing on all parameters and HTTP methods using DSL, focusing on detecting SSRF vulnerabilities with pre-conditions."
nuclei -list katana.jsonl -im jsonl -ai "Find SSRF vulnerabilities in web applications"
nuclei -list katana.jsonl -im jsonl -ai "Identify SSRF vulnerabilities in query parameters"
```

### Local & Remote File Inclusion (LFI/RFI)
```sh
nuclei -list katana.jsonl -im jsonl -ai "Perform fuzzing on all parameters and HTTP methods using DSL, focusing on detecting LFI/RFI vulnerabilities with pre-conditions."
nuclei -list katana.jsonl -im jsonl -ai "Find LFI in 'file', 'path', 'template', 'inc', 'lang', 'page' parameters"
nuclei -list katana.jsonl -im jsonl -ai "Detect RFI by injecting external URLs into 'file' and 'load' parameters"
```

### Command Injection (RCE)
```sh
nuclei -list katana.jsonl -im jsonl -ai "Perform fuzzing on all parameters and HTTP methods using DSL, focusing on detecting Remote Code Execution (Command Injection) vulnerabilities with pre-conditions."
nuclei -list katana.jsonl -im jsonl -ai "Detect command injection in 'cmd', 'exec', 'ping', 'query', 'shell' parameters"
nuclei -list katana.jsonl -im jsonl -ai "Scan for OS command injection via HTTP headers (X-Forwarded-For, X-Forwarded-Host, User-Agent, Referer)"
```

### Cloud Security Issues
```sh
nuclei -list targets.txt -ai "Detect open Docker API endpoints allowing remote access"
nuclei -list targets.txt -ai "Detect exposed Kubernetes API servers allowing unauthenticated access"
nuclei -list targets.txt -ai "Find open Kubernetes Dashboard instances with weak or no authentication"
nuclei -list targets.txt -ai "Scan for cloud metadata endpoints accessible externally"
```

### Web Cache Poisoning
```sh
nuclei -list targets.txt -ai "Find web cache poisoning via 'Host', 'X-Forwarded-Host' and 'X-Forwarded-For' headers"
nuclei -list targets.txt -ai "Detect cache poisoning through 'X-Original-URL' and 'X-Rewrite-URL' headers"
nuclei -list targets.txt -ai "Identify cache poisoning by injecting payloads in 'Referer' and 'User-Agent'"
```

This markdown file provides structured Nuclei AI prompts categorized by security testing methodologies.
