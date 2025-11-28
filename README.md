# Real-Time Risk Scoring Dashboard

A streaming analytics system that assigns risk scores to live event data.

## Overview

This application polls a public API at regular intervals to fetch event data. Each event is processed through a rule-based scoring engine that evaluates fields like value thresholds, keyword matches, and location risk. Events are stored in SQLite with their calculated risk scores and displayed in a real-time dashboard with color-coded severity levels.

## Features

- Periodic API polling every 5-10 seconds
- Rule-based risk scoring engine
- Real-time dashboard with live updates
- SQLite persistence for event history
- Color-coded severity visualization
- Filtering and search capabilities

## Technical Stack

Python, Flask, SQLite, Pandas, HTML/CSS/JavaScript

## Installation
```bash
pip install -r requirements.txt
python app.py
```

Access the dashboard at http://localhost:5000

## Architecture
```
risk_dashboard/
├── app.py              # Flask application and API
├── scoring.py          # Risk scoring logic
├── db.sqlite           # Event storage
├── templates/
│   └── index.html
└── static/
    └── script.js
```

## Scoring Logic

Example rule-based scoring:
```python
score = 0
if value > threshold:
    score += 5
if 'error' in description.lower():
    score += 3
if location in high_risk_regions:
    score += 2
```

Scores are normalized to 0-10 scale and mapped to severity levels.

## Use Case

Demonstrates real-time data processing, streaming analytics, automated scoring systems, and operational dashboard design relevant to security operations, monitoring platforms, and risk management systems.
