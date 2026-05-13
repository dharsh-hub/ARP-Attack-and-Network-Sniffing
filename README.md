# ARP Spoofing and Network Sniffing Experiment
## AIM

To perform ARP spoofing attack simulation and observe network sniffing behavior using Ettercap and Wireshark in a controlled LAN environment.

## TOOLS USED
Kali Linux

Ettercap (GUI)

Wireshark

Two virtual machines (Target systems in same network: 10.0.2.2 and 10.0.2.3)
## PROCEDURE / STEPS
### Step 1: Network Setup

Two systems (victims) were connected in the same virtual network:

Target 1: 10.0.2.2
Target 2: 10.0.2.3
### Step 2: Host Discovery using Ettercap

Ettercap was launched and the network was scanned to identify active hosts in the LAN.

### Step 3: Selecting Targets

Both detected hosts were added as:

Target 1
Target 2
### Step 4: ARP Poisoning Attack

ARP spoofing (MITM simulation) was initiated so that traffic between both targets is intercepted by the attacker machine.

### Step 5: Packet Monitoring

Wireshark was used to capture and analyze ARP packets to observe spoofing behavior and network anomalies.

## OBSERVATIONS FROM SCREENSHOTS
### Screenshot 1: Ettercap Host Discovery
<img width="1918" height="1068" alt="Screenshot 2026-05-13 114621" src="https://github.com/user-attachments/assets/d9b250af-40f0-490b-a14f-91fa2253e3fa" />

### Explanation:
This screenshot shows Ettercap detecting active devices in the local network. Two hosts were identified with IP addresses 10.0.2.2 and 10.0.2.3, both mapped to MAC address 52:54:00:12:35:00. These hosts are added to the host list, meaning Ettercap has successfully scanned the LAN and identified reachable systems for further attack simulation.
The system is now intercepting communication between these two hosts by sending fake ARP replies. This makes both systems believe the attacker’s MAC address is the correct destination.
### Understanding:
This step confirms that both target machines are active in the same network and can communicate, which is necessary for ARP spoofing to work.This is the core phase of a Man-in-the-Middle (MITM) attack where traffic between two systems is silently redirected through the attacker machine.

### Screenshot 2: Wireshark ARP Packet Capture
<img width="1918" height="1038" alt="image (1)" src="https://github.com/user-attachments/assets/fb995404-e33e-4f62-9391-b1b2e04d241e" />

### Explanation:
This screenshot shows Wireshark capturing ARP traffic on interface eth0. Multiple ARP reply packets are visible where IP 10.0.2.2 is mapped to MAC 08:00:27:b1:79:92. It also shows warnings like “duplicate use of IP detected”, which is a clear sign of ARP spoofing activity.

### Understanding:
These duplicate ARP entries confirm that the network is receiving conflicting MAC address information, which is typical during ARP poisoning attacks.

## RESULT

The ARP spoofing and network sniffing experiment was successfully performed using Ettercap and Wireshark. The attack was simulated in a controlled environment, and ARP poisoning behavior was observed clearly through packet analysis.
