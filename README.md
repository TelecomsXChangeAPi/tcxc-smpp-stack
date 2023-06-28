<img src="https://user-images.githubusercontent.com/26701933/54167718-c5161f80-4473-11e9-82cc-f6ff64227d8e.png" width="40%" height="40%">

# Introduction

After years of dedication to development and continuous improvement, our team has crafted and refined these robust solutions. Tested under real-world traffic conditions in Tier 1 networks, they have proven their exceptional performance and resilience. Our SMPP stack, which can function either in conjunction with the TCXC Wholesale Digital Transformation Platform or as a standalone component (excluding Voice, Numbers functions), stands as a testament to our commitment to innovation and quality in communications technology.

# Try it Now (Schedule a demo)
For further information or assistance, reach out to our team at support@telecomsxchange.com or visit [our contact page](www.telecomsxchange.com/contact).

# TCXC SMPP Stack

<img src="https://www.telecomsxchange.com/static/media/overview-4.3b256d14ec1b984ac7a0.png" width="500" height="300">

**SMPP Proxy Async**

Crafted in Node.js, the SMPP Proxy Async Server is an all-in-one solution proficient in handling SMS routing, billing, and AAA. This component has been battle-tested under real-world conditions, demonstrating its capability by effectively routing and billing millions of SMS messages. Its design is particularly tailored for low TPS setups due to single threading limitation by nodejs, making it an ideal and simple choice for environments where lower throughput is the norm.

**SMPP Go Archictiture (Recommended for high TPS environments and large scale)**
 
- **SMPP Load Balancer (Go Lang)**

The SMPP Load Balancer, written in Go Lang, is an efficient tool designed to manage and evenly distribute SMS traffic across multiple SMPP upstream proxy servers. It uses Go's inherent concurrency and simplicity to deliver robust performance, ensuring the highest levels of throughput and availability. Its features include dynamic load distribution, automated failover, and in-depth traffic analytics.

- **SMPP Proxy Async Upstream Proxies**

The SMPP Proxy Async Upstream Proxies, written in NodeJs is an important component within the SMPP Stack that provides asynchronous communication with upstream **Bind Balancer, Redis, AAA and Load balancer servers**. This allows for non-blocking, high-speed transmission and receiving of SMS messages, even when dealing with multiple upstream servers. This results in improved performance, minimized latency, and maximized message throughput.


- **SMPP Bind Balancer (Go Lang)**

Written in Go Lang, the SMPP Bind Balancer is a powerful component in the architicture that ensures optimal load balancing across multiple SMPP binds or connections. It can intelligently route incoming DLRs to the approperiate upstream async proxy, distribute the messaging load based on various factors such as capacity, connection state, or system resources, thereby improving system efficiency, enhancing message throughput, and reducing the risk of bottlenecks.

- **HTTP-SMPP Convertor**

The HTTP-SMPP Convertor, is designed to facilitate seamless communication across different interfaces. Its key function is to convert REST API SMS submissions into the SMPP protocol. This is particularly useful for clients interfacing with our platform over REST API, rather than a direct SMPP connection. 

The HTTP-SMPP Convertor works with AWS API Gateway and Lambda functions, It's also tighthly integrated  with TCXC HTTP Account types, ensuring a broad range of applicability.


# Key Features

Our solution provides a suite of features designed to ensure robust, efficient, and versatile SMS management. These include:

## Performance and Compatibility

- High TPS support: Up to 7000/sec per node (with AAA)
- Compatibility with SMPP v3.4 and 5.0
- Robust and resilient design

## Routing and Control

- SMS routing/Least Cost Routing (LCR)
- Throttling control per buyer/IP-account/Route
- Realtime SMS control and call data records (SDRs) generation with TCXC AAA
- Accurate SMPP rate limiting per buyer account/seller route

## Billing

- Prepaid and postpaid billing/charging
- Concatenated message billing / support (UDH/Message Payload)
- DLRs - Delivery report relay

## International Support 

- Supports RTL languages like Arabic and Chinese
- Fully integrated mapping system that seamlessly converts E.212 codes to E.164 format, and vice versa
- Emojis Support

## Reporting and Monitoring

- SDRs sent to mediation server via SFTP
- Grafana Integration (DLR Speed, Avg Selling Price, Message Per Second, Traffic by Sender ID, Binding State Monitoring)


**Encodings**
Our SMPP implementation supports three encodings: ASCII (GSM 03.38), LATIN1, and UCS2. The data_coding for these encodings are 0x01, 0x03, and 0x08 respectively. The default encoding for data_coding:0 is ASCII.

**Routing Groups Support**

Key routing features include:

- Prefix length routing (MCC+MNC)
- Least Cost
- Tech prefix
- Route Order (Priority)
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

# Compatibility Testing 

Our SMPP Proxy has demonstrated exceptional compatibility, as shown through successful testing with various industry platforms:

- **InfoBIP**
- **Restcomm SMC**
- **MontyMobile**
- **AirTel**
- **X2One**
- **Mitto.ch**
- **TATA**
- **PlaySMS**
- **SQUIRETECH**
- **JASMIN**
- **Telin**
- **Haud SMSC**

This extensive testing ensures seamless integration with these platforms, confirming our solution's broad applicability across diverse operational environments.


# Language Tests
We've successfully tested English, Arabic,Turkish, Japanese and Chinese languages.

# Code Access and Usage 

While our README repository is hosted on GitHub, it's important to understand that this does not imply open source availability. Instead, we operate on a royalty-based system where clients who have made the necessary payments are granted non-binary access to all components under a private github repository.

This model allows us to provide our clients with the ability to customize and adapt our solutions to their unique needs, all while maintaining a level of quality and support that we pride ourselves on. We are dedicated to providing you with the tools necessary to fully leverage our solutions within your own operational context.

