# Home SOC Lab – Day 5: Linux Networking Fundamentals

## Objective

The objective of Day 5 was to develop a fundamental understanding of Linux networking. This included identifying network interfaces, viewing IP configuration, understanding routing, testing network connectivity, performing DNS lookups, examining listening ports and active connections, and learning how these concepts apply to Security Operations Centre (SOC) investigations.

---

## Commands Used

| Command       | Purpose                                                 |
| ------------- | ------------------------------------------------------- |
| `ip a`        | Display network interfaces and IP addresses.            |
| `ip route`    | Display the routing table and default gateway.          |
| `ping`        | Test network connectivity to an IP address or hostname. |
| `nslookup`    | Resolve a domain name into an IP address using DNS.     |
| `ss -tuln`    | Display listening TCP and UDP ports.                    |
| `ss -tun`     | Display active network connections.                     |
| `hostname`    | Display the system hostname.                            |
| `hostnamectl` | Display detailed system and hostname information.       |
| `wget`        | Download files from a web server.                       |
| `curl`        | Send requests to a web server and display the response. |

---

## Practical Tasks Completed

* Identified the IP address assigned to the Kali Linux virtual machine.
* Identified the loopback interface (`lo`) and understood its purpose.
* Viewed the routing table and identified the default gateway.
* Tested connectivity using both IP addresses and hostnames.
* Performed DNS lookups using `nslookup`.
* Investigated listening ports and active network connections using the `ss` command.
* Viewed the hostname and operating system information.
* Compared the functionality of `wget` and `curl`.

---

## Key Concepts Learned

### Loopback Interface

The `lo` interface is the loopback interface, allowing the computer to communicate with itself. Its IP address is typically `127.0.0.1`.

### Default Gateway

The default gateway forwards traffic to destinations outside the local network, allowing the system to communicate with external networks such as the internet.

### DNS

The Domain Name System (DNS) translates human-readable domain names into IP addresses. If DNS fails, a system may still be able to reach IP addresses directly while failing to access websites by name.

### TCP vs UDP

* **TCP** provides reliable communication by ensuring packets are delivered in the correct order.
* **UDP** prioritises speed over reliability and is commonly used for DNS, voice communication, and streaming.

### Listening Ports vs Active Connections

* **Listening ports** are services waiting for incoming connections.
* **Active connections** represent communication currently taking place between systems.

### `wget` vs `curl`

* `wget` is primarily used to download files.
* `curl` is used to communicate with web servers and inspect responses directly from the terminal.

---

## SOC Analyst Perspective

Today's exercises demonstrated several techniques commonly used during incident investigations.

A SOC analyst may use these commands to:

* Identify a system's network configuration.
* Verify internet and DNS connectivity.
* Determine whether suspicious services are listening for incoming connections.
* Identify active network communications.
* Confirm the identity of the system being investigated.
* Test web servers and investigate HTTP responses.

Understanding the purpose of each command helps distinguish normal system behaviour from potential indicators of compromise.

---

## Challenges Encountered

During the lab I initially confused the loopback IP address (`127.0.0.1`) with my assigned network IP address. I also spent time understanding the difference between testing connectivity using an IP address versus a hostname and how DNS is involved in name resolution.

I also discovered that `ss -tuln` only displayed the column headings because there were no listening services running on my Kali VM. This reinforced that an empty result is still a valid finding during an investigation.

---

## What I Learned

Day 5 significantly improved my understanding of Linux networking. I learned how to identify my system's IP address, understand the role of the default gateway, troubleshoot connectivity problems, and recognise when DNS may be the source of an issue. I also learned the differences between TCP and UDP, how to identify listening ports and active network connections, and when to use `wget` or `curl`. Most importantly, I began thinking about each command from the perspective of a SOC analyst, focusing not only on what the command does but also on what conclusions can be drawn from its output.
