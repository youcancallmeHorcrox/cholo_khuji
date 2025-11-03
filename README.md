# 🛰️ IP and Domain Geolocation Lookup Script

A simple **Bash-based geolocation lookup tool** that retrieves location and ISP information for a given IP address or domain name using the [ip-api.com](http://ip-api.com) API.

---

## 🚀 Features

- Supports both **IP addresses** and **domain names**
- Automatically resolves domain names to IP addresses
- Displays detailed location info:
  - City, Region, Country
  - Latitude & Longitude
  - Internet Service Provider (ISP)
- Error handling for invalid inputs
- Lightweight — requires only `curl` and `jq`

---

## 🧠 How It Works

1. User provides an **IP address** or **domain name** as a command-line argument.
2. If a domain is entered, it is resolved to its IP using the `host` command.
3. The script queries the **ip-api.com** REST API using `curl`.
4. JSON data is parsed using `jq` to extract location details.
5. Results are displayed in a readable format.

---

## ⚙️ Requirements

Make sure you have the following installed:
- `bash`
- `curl`
- `jq`
- `host` (usually included in the `bind-utils` or `dnsutils` package)

### Install `jq` (if missing)
```bash
sudo apt install jq      # Debian/Ubuntu
sudo yum install jq      # CentOS/RHEL
brew install jq          # macOS

...........................

💻 Usage

# Make the script executable
chmod +x geolocate.sh

# Look up by IP
./geolocate.sh 8.8.8.8

# Look up by domain
./geolocate.sh google.com

.......................

🧾 Example Output

The location of the IP address is Mountain View, California, United States
The coordinates of the IP address are: 37.4056,-122.0775
Their ISP is: Google LLC

