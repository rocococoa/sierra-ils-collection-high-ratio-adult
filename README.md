# Sierra ILS Collection Development - High Ratio-Adult Automated Report
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/python-%233670A0.svg?style=for-the-badge&logo=python&logoColor=ffdd54)

## Summary
**What it does:** This automated report highlights adult print and media titles with high demand (a minimum 4:1 hold-to-item ratio) and those with holds but zero holdable copies. The ratio calculation only includes actively holdable items.

**Impact:** Delivers a weekly automated report of in-demand titles to help the Collection Development team quickly respond to customer demand and easily assess and optimize inventory levels.

## Features and Deliverables

**Excel Report:**
<img width="1464" height="880" alt="High Ratio Adult" src="https://github.com/user-attachments/assets/15c7a5f3-031f-4157-b8ca-39d3687013cf" />

Beyond identifying titles with a 4:1 hold-to-item ratio or holds on titles zero holdable copies, the report streamlines decision-making by including:

- Total frozen holds: Tracks outstanding demand that is currently paused.
- Publication year: Provides immediate context on the age and relevance of the material.
- Pending orders: Shows how many orders have already been placed and are awaiting fulfillment.
- Billed item data: Flags when an item has been billed, and includes circ data for the item.


<img width="1466" height="887" alt="High-Ratio-Adult" src="https://github.com/user-attachments/assets/ad1334a0-2f85-4951-888a-c7b2609ad501" />

**Automated Email:**

<img width="489" height="605" alt="Adult High Ratio Email" src="https://github.com/user-attachments/assets/b1622850-9d7d-436e-9c0c-18a92f2f79c4" />

## Data Pipeline Architecture
This repository features an automated data pipeline that generates, formats, and distributes Excel reports via email. The system integrates Windows Task Scheduler, a Batch script, SQL, and Python to handle the end-to-end workflow without manual intervention. The automated process is fully productionized within a Windows environment.

**Workflow Overview:**

[Windows Task Scheduler] ──> [orchestrator.bat] ──> [main.py] ──> [Sub-modules & SQL] ──> [Report delivered to Email Inbox]

**Repository Contents & Security Note:**

To comply with data security policies, the core Python automation scripts have been omitted from this public repository. Instead, this repository provides:
- The SQL Data-Extraction Script: The exact logic used to pull and aggregate Sierra ILS production data.
- Manual Alternative: If you do not have an automated environment, you can run the provided SQL script manually in pgAdmin and export the results directly to a spreadsheet.

## Acknowledgments
The automated pipeline is built off the brilliant work of Gem Stone-Logan. For more information on implementing the automated system, please see her IUG presentations, [Automating Reports with Python.](https://www.gemstonelogan.com/presentations.html)
