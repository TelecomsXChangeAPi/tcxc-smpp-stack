<img src="https://user-images.githubusercontent.com/26701933/54167718-c5161f80-4473-11e9-82cc-f6ff64227d8e.png" width="40%" height="40%">

# Introduction

After years of dedication to development and continuous improvement, our team has crafted and refined these robust solutions. Tested under real-world traffic conditions in Tier 1 networks, they have proven their exceptional performance and resilience. Our SMPP stack, which can function either in conjunction with the TCXC Wholesale Digital Transformation Platform or as a standalone component (excluding Voice, Numbers functions), stands as a testament to our commitment to innovation and quality in communications technology.

# See It in action (Schedule a demo)
For further information or assistance, reach out to our team at support@telecomsxchange.com or visit [our contact page](www.telecomsxchange.com/contact).

# TCXC SMPP Stack

**SMPP Proxy Async**

Crafted in Node.js, the SMPP Proxy Async Server is an all-in-one solution proficient in handling SMS routing, billing, and AAA. This component has been battle-tested under real-world conditions, demonstrating its capability by effectively routing and billing millions of SMS messages. Its design is particularly tailored for low TPS setups due to single threading limitation by nodejs, making it an ideal and simple choice for environments where lower throughput is the norm.

**SMPP Go Archictiture (Recommended for high TPS environments and large scale)**
 
- **SMPP Load Balancer (Go Lang)**

The SMPP Load Balancer, written in Go Lang, is an efficient tool designed to manage and evenly distribute SMS traffic across multiple SMPP upstream proxy servers. It uses Go's inherent concurrency and simplicity to deliver robust performance, ensuring the highest levels of throughput and availability. Its features include dynamic load distribution, automated failover, and in-depth traffic analytics.

- **SMPP Proxy Async Upstream Proxies**

The SMPP Proxy Async Upstream Proxies, written in NodeJs is an important component within the SMPP Stack that provides asynchronous communication with upstream **Bind Balancer, Redis, AAA and Load balancer servers**. This allows for non-blocking, high-speed transmission and receiving of SMS messages, even when dealing with multiple upstream servers. This results in improved performance, minimized latency, and maximized message throughput.


- **SMPP Bind Balancer (Go Lang)**

Written in Go Lang, the SMPP Bind Balancer is a powerful component in the architicture that ensures optimal load balancing across multiple SMPP binds or connections. It can intelligently route incoming DLRs to the approperiate upstream async proxy, distribute the messaging load based on various factors such as capacity, connection state, or system resources, thereby improving system efficiency, enhancing message throughput, and reducing the risk of bottlenecks.

Key Features:

- Supports high TPS up to 7000/sec per node (with AAA)
- SMS routing/LCR
- Throttling control per buyer/IP-account/Route
- Prepaid and postpaid billing/charging
- Concatenated message billing / support (UDH/Message Payload)
- DLRs - Delivery report relay
- Realtime SMS control and call data records (SDRs) generation with TCXC AAA
- Send SDRs to mediation server via SFTP 
- Compatible with SMPP v3.4 and 5.0.
- Robust and resilient
- Supports RTL languages like Arabic and Chinese
- Accurate SMPP rate limiting per buyer account/ seller route
- Emojis Support
- Grafana Integration (DLR Speed, Avg Selling Price, Message Per Second, Traffic by Sender ID, Binding State Monitoring).

**Encodings**
Our SMPP implementation supports three encodings: ASCII (GSM 03.38), LATIN1, and UCS2. The data_coding for these encodings are 0x01, 0x03, and 0x08 respectively. The default encoding for data_coding:0 is ASCII.

**Routing Groups Support**

Key routing features include:

- Prefix length routing (MCC+MNC)
- Least cost routing
- Buyer tech prefix support
- Route ordering
- Load balancing/weight

# Billing
The SMPP Stack is seamlessly integrated with the TCXC AAA (billing system), providing functionalities like:

- Prepaid and postpaid modes
- Rating according to longest prefix "MCC+MNC"
- Least cost

# Hardware Tests
Our solution has been tested for performance, supporting up to 450,000,000 SMS per month. Find the detailed report below:

- On Dual Xeon E5-2690 v3 2.60 GHz, 30M Cache Processors (24 Cores / 48 Threads), the SMPP proxy can run 180+ messages per second with AAA (Authorization, Authentication, Accounting). To scale, you can run two SMPP proxies on the same hardware to double the capacity.

Remarkably, this solution is highly adaptable, able to run on any hardware that supports Ubuntu Pro OS, from Bare metal to AWS EC2, Azure, or OpenStack.

# Compatibility Tests
Our SMPP Proxy has been successfully tested with:

- InfoBIP
- Restcomm SMC
- MontyMobile
- AirTel
- X2One
- Mitto.ch
- TATA
- PlaySMS
- SQUIRETECH
- JASMIN
- Telin
- Haud SMSC

# Language Tests
We've successfully tested English, Arabic,Turkish, Japanese and Chinese languages.
