# Labs

## First observation

Used PowerShell to check processes and network connections.

Example commands:

Get-Process  
Get-NetTCPConnection  

Goal:
Understand how processes interact with network.

---

## 🔍 Lab 1 — Process & Network Observation

### Goal

Understand how processes interact with the system and network.

---

### Step 1 — List processes

Command:

Get-Process

Observation:
- System has many running processes
- Each process has ID (PID)
- Some processes belong to system, some to user

---

### Step 2 — Check network connections

Command:

Get-NetTCPConnection

Observation:
- Shows active connections
- Includes local and remote addresses
- Shows which ports are used

---

### Step 3 — Link process to network

Command:

Get-NetTCPConnection | Select-Object LocalAddress,LocalPort,RemoteAddress,State,OwningProcess

Observation:
- Each connection has OwningProcess (PID)
- This allows mapping network → process

---

### Key Insight

Processes do not work in isolation.  
They interact with network, and this can be monitored.

This is the base for:
- SOC analysis
- Threat detection
- Malware investigation
