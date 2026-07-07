# Week 1 - Splunk Installation & Fundamentals

## Objective
Set up a Splunk SIEM lab on Windows 11 and learn the basic concepts of Splunk

## Environment

- Operating System: Windows 11
- SIEM Tool: Splunk Enterprise
- Installation Type: Local Installation

## Topics Covered

- Installed Splunk Enterprise
- Logged into the Splunk Web Interface
- Learned the Splunk architecture
- Created an index
- Explored the Search & Reporting app
- Learned basic SPL commands

## Skills Learned

- Splunk Architecture
- Search Head
- Index
- Source
- Sourcetype
- SPL Basics

## Basic SPL Commands
```spl
search *

index=main

table host source

stats count

sort -count

fields host source

rename host AS Computer
```

## Deliverables

- Splunk successfully installed
- Basic searches executed
- Notes created
- Screenshots collected

## Screenshot
<img width="1920" height="1020" alt="Screenshot 2026-07-06 134230" src="https://github.com/user-attachments/assets/e16c8062-0b56-45f4-8af3-802b8b2a8df6" />


## Status

✅ Week 1 Completed

