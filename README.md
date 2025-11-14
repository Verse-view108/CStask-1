# CStask-1: Cybersecurity Internship Day 1 Task 1

## Overview
Task to develop network reconnaissance skills and assess service exposure on my PC (IP: 10.31.119.183) on November 13, 2025.

## Tools
- Nmap (v7.98)
- Wireshark
- Command Prompt (`netsh`, `netstat`)
- Task Manager

## Steps and Findings
1. **Installed Nmap**: Version 7.98.
2. **Found IP Range**: 10.31.119.183, range 10.31.119.0/24.
3. **Ran Nmap Scan**: `nmap -sS -p-` found ports 135, 139, 445, 2869, 5040, 49664–49680.
4. **Noted Ports**: IP: 10.31.119.183, ports listed above.
5. **Wireshark Analysis**: Confirmed SYN/ACK on open ports.
6. **Researched Services**: 
   - 135: RPC, 139: NetBIOS, 445: SMB, 2869: ICS/UPnP, 49664–49669: RPC.
   - 5040, 49670–49680: Unknown (check `netstat -ano | findstr :5040` for PID).
7. **Identified Risks**: 
   - 445: High risk (WannaCry), blocked but open—policy issue.
   - 135: Patch needed, 139: Disable if unused, 2869: Disable UPnP.
   - Unknowns: Investigate and block if unnecessary.
8. **Saved Results**: 
   - `port_scan_results.txt`, `service_scan_results.txt` in `C:\Users\ifocu`.
   - `nmap_scan.pcapng` from Wireshark.

## Challenges
- IP changed from 10.31.110.225.
- 445 block failed, likely policy-related.

## Recommendations
- Escalate 445 to IT.
- Monitor unknown ports.

## Acknowledgments
- Guided by Grok (xAI).
