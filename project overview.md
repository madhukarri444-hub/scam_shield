# Scam Shield — Project Overview

## Problem

Older adults may receive fraudulent calls that pressure them to reveal OTPs, UPI PINs, banking details, install remote-access applications, or transfer money. Language barriers and urgency can make these calls difficult to assess.

## Proposed solution

Scam Shield analyzes call transcripts and highlights suspicious phrases in Telugu, Hindi, and English. It returns a risk indication and practical safety guidance.

## Prototype workflow

1. A transcript is supplied to the backend.
2. The scorer checks it against language-specific warning patterns.
3. Matching indicators contribute to a risk result.
4. The API returns the result and a safety recommendation.
5. A future audio module can convert speech to text before scoring.

## Intended users

- Older adults who may need simple, local-language safety warnings.
- Family members or caregivers who help users understand suspicious calls.
- Community digital-literacy educators.

## Design principles

- Explain which indicators caused a warning.
- Use simple, non-technical language.
- Avoid claiming that any call is definitely safe.
- Obtain consent before processing recordings or sending family alerts.
- Minimize collection and retention of personal data.

## Prototype boundary

The current transcript scorer is not equivalent to a live phone-call monitoring system. Speech recognition, real-time call integration, spoken alerts, and family SMS notifications should be described as future work unless they have actually been implemented and tested.
