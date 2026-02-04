# Cross-Cloud Behavioral Detections

## Overview

This repository contains a practical, architect-level collection of **behavioral security detections** for public cloud environments.

The focus is on **identity abuse**, **privilege escalation**, and **attacker tradecraft**, rather than isolated events or generic alerting.

The detections are designed to operate on **native cloud audit logs** and to be adaptable across SIEMs and detection platforms.

---

## Why Behavioral Detections

Most cloud security incidents do not begin with malware.
They begin with **valid credentials used in invalid ways**.

Traditional detections focus on:
- Individual API calls
- Known bad indicators
- Static thresholds

Attackers, however, operate through:
- Legitimate identities
- Expected APIs
- Sequences of actions that only become suspicious when viewed together

This repository focuses on **behavior over events**.

---

## Design Principles

### Identity as the Primary Control Plane
In modern cloud environments, identity and access management is the true perimeter.

Each detection prioritizes:
- Role assumptions
- Service account usage
- Privilege changes
- Identity context (time, source, frequency)

---

### Sequence-Based Detection
Single events are weak signals.

Detections in this repository are built around:
- Action sequences
- Temporal proximity
- Changes in behavior relative to a baseline

---

### Cloud-Native and Portable
All detections are based on:
- AWS CloudTrail
- Azure Entra ID and Activity Logs
- GCP Audit Logs

They are intentionally written to remain:
- Understandable without vendor-specific abstractions
- Portable across detection engines

---

### Operational Reality
Each detection includes:
- Rationale
- Expected false positives
- Practical tuning guidance

A detection that cannot be tuned is operational debt.

---

## Repository Structure

