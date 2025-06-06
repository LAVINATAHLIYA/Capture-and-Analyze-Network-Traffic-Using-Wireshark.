# Network Traffic Analysis Report

## Protocol Definitions

### ARP (Address Resolution Protocol)
**Purpose**: Maps IP addresses to MAC addresses on local networks  
**Layer**: Data Link (Layer 2)  
**Characteristics**:
- Uses broadcast requests and unicast replies
- No authentication mechanism
- Cache entries typically expire after 2-4 minutes

### HTTP (Hypertext Transfer Protocol)
**Purpose**: Transfers web page data between clients and servers  
**Layer**: Application (Layer 7)  
**Characteristics**:
- Plaintext protocol (no encryption)
- Uses port 80 by default
- Stateless but supports cookies for session tracking

### TLS (Transport Layer Security)
**Purpose**: Encrypts communication between networked devices  
**Layer**: Between Transport and Application (L4-L7)  
**Characteristics**:
- Successor to SSL (now deprecated)
- Uses port 443 for HTTPS
- Provides encryption, authentication, and integrity

---
