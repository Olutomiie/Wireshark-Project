<div align="center">

# 🔐 Wireshark-Project 
## Identify the Attacker's IP

**Networkwalks Cybersecurity Program | Batch B084**

*Practical Network Traffic Analysis & Port Scan Investigation*

</div>

---

## 📌 Project Overview

This project involved investigating captured network traffic using **Wireshark**, a network protocol analyser, to identify suspicious connection attempts and determine the source and target of a port-scanning activity.

The exercise focused on analysing TCP SYN packets, identifying IP addresses, examining source ports, investigating port responses, and distinguishing between open and closed ports.

The objective was to develop practical network traffic analysis skills and understand how security analysts use packet-level evidence to investigate suspicious network behaviour.

## 🎯 Project Objectives

By completing this lab, I aimed to:

- Capture and inspect network traffic.
- Filter TCP SYN packets using Wireshark.
- Identify the attacker's IP address.
- Identify the target IP address.
- Determine the source port.
- Establish the number of ports probed.
- Identify open ports on the target.
- Examine responses from closed ports.
- Determine the number of closed ports.
- Identify the type of network activity.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Wireshark | Network traffic capture and analysis |
| TCP/IP | Understanding network communication |
| Wireshark Display Filters | Filtering and analysing packets |

---

# 🔍 STEP-BY-STEP INVESTIGATION

## Step 1: Capture the Network Traffic

**Objective:** Capture network packets for investigation using Wireshark.

I initiated the traffic capture and inspected the packets generated during the lab exercise.

The capture contained a total of **305 packets**.

This provided the dataset for subsequent analysis.

**Result:** 305 packets captured.

### Screenshot – Traffic Capture

![Traffic Capture](images/01-traffic-capture.png)

---

## Step 2: Filter and Identify SYN Packets

**Objective:** Isolate TCP SYN packets from the captured traffic.

I used the following Wireshark display filter:

```text
tcp.flags.syn == 1
```

This filter displays packets with the TCP SYN flag set.

The filter returned **73 packets**.

SYN packets are important when investigating connection attempts because they are involved in initiating TCP connections.

**Result:** 73 matching packets.

### Screenshot – SYN Packet Filtering

![SYN Packet Filter](images/02-syn-packet-filter.png)

---

## Step 3: Identify the Attacker's IP Address

**Objective:** Determine the source IP address responsible for the scanning activity.

By examining the source IP addresses in the relevant packets, I identified the system initiating the connection attempts.

**Identified Attacker IP:**

```text
192.168.10.66
```

### Screenshot – Attacker IP Identification

![Attacker IP](images/03-attacker-ip.png)

---

## Step 4: Identify the Target IP Address

**Objective:** Determine the destination system receiving the connection attempts.

I examined the destination IP address associated with the scanning traffic.

**Identified Target IP:**

```text
192.168.10.20
```

This helped establish the direction of the network activity.

### Screenshot – Target IP Identification

![Target IP](images/04-target-ip.png)

---

## Step 5: Identify the Source Port

**Objective:** Determine the source port associated with the identified traffic.

By inspecting the TCP header information, I identified the source port used in the connection attempts.

**Identified Source Port:**

```text
52311
```

### Screenshot – Source Port Identification

![Source Port](images/05-source-port.png)

---

## Step 6: Determine the Number of Ports Probed

**Objective:** Establish how many destination ports were targeted during the scanning activity.

I examined the destination port information within the captured traffic to determine the number of ports probed.

**Result:**

```text
40 ports probed
```

### Screenshot – Ports Probed

![Ports Probed](images/06-ports-probed.png)

---

## Step 7: Identify Open Ports

**Objective:** Determine which ports on the target system responded as open.

The investigation identified the following open ports:

| Port | Common Service |
|---|---|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |

These ports are commonly associated with remote administration and web services.

**Result:** 3 open ports identified.

### Screenshot – Open Ports

![Open Ports](images/07-open-ports.png)

---

## Step 8: Examine Responses from Closed Ports

**Objective:** Identify how the target system responded to connection attempts directed at closed ports.

The investigation revealed the following TCP response:

```text
RST, ACK
```

A TCP RST (Reset) with ACK (Acknowledgment) response commonly indicates that the target is rejecting a connection attempt because the destination port is not accepting connections.

This response provided useful evidence for distinguishing closed ports from open ports.

### Screenshot – Closed Port Response

![Closed Port Response](images/08-closed-port-response.png)

---

## Step 9: Determine the Number of Closed Ports

**Objective:** Establish how many of the probed ports were identified as closed.

From the investigation results:

```text
Total ports probed: 40
Open ports: 3
Closed ports: 37
```

The findings indicate that 37 ports were identified as closed.

### Screenshot – Closed Ports

![Closed Ports](images/09-closed-ports.png)

---

## Step 10: Identify the Attack Type

**Objective:** Classify the network activity based on the observed packet behaviour and port responses.

After analysing the TCP SYN packets, source and destination addresses, port activity, and responses from the target, I identified the activity as:

**PORT SCANNING**

Port scanning is a reconnaissance technique used to discover accessible ports and potentially identify services running on a target system.

It can be used during authorised security assessments as well as by malicious actors during reconnaissance.

### Screenshot – Attack Type Identification

![Attack Type](images/10-attack-type.png)

---

# 📊 INVESTIGATION FINDINGS

The following table summarises the results of the investigation.

| No. | Investigation Parameter | Result |
|---|---|---|
| 01 | Total packets captured | 305 |
| 02 | SYN packets identified | 73 |
| 03 | Attacker IP | 192.168.10.66 |
| 04 | Target IP | 192.168.10.20 |
| 05 | Source port | 52311 |
| 06 | Ports probed | 40 |
| 07 | Open ports | 22, 80, 443 |
| 08 | Closed port response | RST, ACK |
| 09 | Closed ports | 37 |
| 10 | Attack type | Port Scanning |

---

# 🏆 ASSESSMENT RESULT

I successfully completed all ten assessment tasks and achieved a perfect score.

<div align="center">

## 100% – OUTSTANDING

# 100 / 100 MARKS

**10 out of 10 tasks completed successfully.**

![Assessment Result](images/11-assessment-result.png)

</div>

---

# 💡 KEY LEARNING OUTCOMES

Through this hands-on exercise, I strengthened my understanding of:

- Network traffic capture and packet inspection.
- TCP SYN flags and connection initiation.
- Wireshark display filters.
- Source and destination IP address identification.
- TCP source and destination ports.
- Port scanning and reconnaissance techniques.
- Identifying open and closed ports.
- TCP RST and ACK responses.
- Evidence-based network security investigation.

## 🔎 Key Takeaway

One of my major takeaways from this exercise is that network traffic contains valuable evidence.

By examining packet headers, connection attempts, port numbers, and responses, it becomes possible to identify patterns that may indicate suspicious network behaviour.

The exercise also reinforced the importance of understanding what happens behind the scenes when devices communicate over a network.

---

<div align="center">

**Documented by Tomilayo Amzat**

#Cybersecurity #Wireshark #NetworkSecurity #SOC #Networkwalks

</div>
