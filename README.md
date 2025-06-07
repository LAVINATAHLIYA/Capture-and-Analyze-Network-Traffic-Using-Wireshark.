# Capture-and-Analyze-Network-Traffic-Using-Wireshark
# Wireshark Network Analysis Task

## 🚀 Steps Performed

### 1. Setup & Capture
- Installed Wireshark 4.2.0
- Selected active interface (Wi-Fi/Ethernet)
- Captured traffic for 5 minutes while:
  - Browsing HTTP/HTTPS sites
  - Pinging 8.8.8.8
  - Accessing local network resources

### 2. Protocol Analysis
**ARP**:
- Used filter: `arp`
- Observed 12 ARP requests/responses
- Verified MAC/IP bindings

**HTTP**:
- Used filter: `http`
- Analyzed 9 HTTP packets including:
  - GET/POST requests
  - Server responses (200 OK, 404 Not Found)

**TLS**:
- Used filter: `tls`
- Examined TLS 1.3 handshake:
  - Client Hello (Packet #112)
  - Server Hello (Packet #115)
  - Key Exchange (x25519)

### 3. Security Review
- Checked for:
  - Cleartext credentials (HTTP)
  - Weak ciphers (TLS)
  - ARP spoofing attempts

## 🔍 Key Findings

### ARP
✅ Normal operation  
⚠️ No anti-spoofing mechanisms  

### HTTP
❌ Visible data:
- Usernames (in login forms)
- Session cookies  
❌ Server versions exposed:
- `Apache/2.4.41 (Ubuntu)`

### TLS
✅ Strong encryption:
- Cipher: `TLS_AES_256_GCM_SHA384`  
✅ Valid certificates  
⚠️ Supports older TLS 1.2 (should disable)

## 📂 Files Included
- `capture.pcapng` - Raw packet capture
- `analysis.md` - Detailed findings
- `screenshots/` - Proof images

## 💡 Recommendations
1. **Immediate**:
   ```nginx
   # Force HTTPS redirect
   server {
       listen 80;
       return 301 https://$host$request_uri;
   }

