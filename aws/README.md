# AWS Behavioral Detections

This directory contains behavioral security detections based on **AWS CloudTrail** logs.

The detections focus on identifying **identity misuse and control plane abuse**, rather than isolated API events.

---

## Detection Focus Areas

The AWS detections in this repository primarily address:

- STS AssumeRole misuse and anomalous role chaining
- IAM privilege escalation through policy and trust modifications
- Enumeration behavior followed by access expansion
- Identity activity occurring outside expected time, source, or frequency baselines

---

## Detection Approach

You will not find one-to-one mappings of API calls to alerts.

Instead, detections are designed to:
- Combine multiple related actions
- Apply temporal correlation
- Evaluate behavior relative to known baselines

This approach reduces alert fatigue and improves signal quality in real environments.

---

## Log Sources

All detections are built using the following AWS log sources:

- AWS CloudTrail (management events)
- STS events
- IAM API activity

---

## Operational Notes

These detections are intentionally opinionated.

They assume:
- IAM administrative activity is rare and identifiable
- Privilege escalation is a high-confidence signal when correlated with access behavior
- Most false positives can be reduced through identity baselining

---

## Status

AWS detections are the initial focus of this repository.
Additional detections and correlation examples will be added iteratively.

