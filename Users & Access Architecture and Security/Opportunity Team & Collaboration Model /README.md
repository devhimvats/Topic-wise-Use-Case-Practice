# Default Opportunity Team & Collaboration Model in Salesforce

## Overview

In real sales organizations, multiple stakeholders such as Sales Managers, Pre-Sales Engineers, and other specialists are repeatedly involved in Opportunity execution. Manually adding them to every Opportunity leads to inconsistency, missed stakeholders, and inefficient collaboration.

This Use Case demonstrates how to implement **Default Opportunity Teams** and **Opportunity Teams** in Salesforce to standardize collaboration and reduce manual effort while maintaining flexibility for deal-specific needs.

---

## Business Problem

Sales teams faced the following issues:
- Repeated manual addition of the same stakeholders to every Opportunity
- Inconsistent team structure across Opportunities
- Missed stakeholders due to human error
- Reduced collaboration efficiency during deal execution

---

## Solution Approach

A hybrid collaboration model was implemented:

### 1. Default Opportunity Team (Automation Layer)
Automatically adds standard stakeholders (e.g., Sales Manager, Pre-Sales Engineer) to every newly created Opportunity.

### 2. Opportunity Team (Dynamic Layer)
Allows additional stakeholders to be added manually based on deal-specific requirements.

---

## Implementation Steps

### Step 1: Enable Opportunity Teams
- Navigate to **Setup**
- Search for **Opportunity Team Settings**
- Enable:
  - Opportunity Teams
  - Default Opportunity Teams
    
![Enable Opportunity Teams](Users & Access Architecture and Security/Opportunity Team & Collaboration Model /Assets/Enable Opportunity Team.png)
---

### Step 2: Configure Default Opportunity Team
For each Sales user:
- Define default team members:
  - Sales Manager → Read Only access
  - Pre-Sales Engineer → Read/Write access

---

### Step 3: Create Opportunity
- Create a new Opportunity record
- Verify that default team members are automatically added

---

### Step 4: Validate Access
- Confirm correct team members are added
- Validate access levels:
  - Sales Manager → Read Only
  - Pre-Sales Engineer → Read/Write

---

## Results & Outcome

- Eliminated repetitive manual effort in Opportunity setup
- Ensured consistent stakeholder involvement across all deals
- Improved collaboration accuracy and visibility
- Reduced human errors in team assignment

---

## Key Learnings

- Default Opportunity Teams enforce standardized collaboration
- Opportunity Teams provide flexibility for deal-specific collaboration
- Teams are a **collaboration layer**, not a replacement for security
- Object-level permissions are still required for access to work

---

## Important Notes

- Default Teams are user-specific, not org-wide
- Teams do not grant object-level permissions
- Access depends on:
  - Profile / Permission Sets (Object Access)
  - OWD and Sharing Model (Record Access)

---

## Architecture Insight

| Layer | Purpose |
|------|--------|
| Object Security | Controls access to Opportunity object |
| OWD & Sharing Rules | Controls record visibility |
| Opportunity Teams | Enables targeted collaboration |
| Default Teams | Automates repetitive team setup |

---

## Future Enhancements

- Implement Omni-Channel for automated case and opportunity routing
- Use Flow automation to dynamically assign team members based on Opportunity criteria
- Extend same model to Account Teams for enterprise-level relationship management

---

## Summary

This implementation demonstrates how Salesforce can be configured to balance:
- Security (controlled access)
- Collaboration (team-based structure)
- Efficiency (automation via default teams)

It reflects a real-world sales process design where collaboration is structured, scalable, and consistent.
