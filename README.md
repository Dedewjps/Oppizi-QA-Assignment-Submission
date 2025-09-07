# Oppizi Technical Test – Project Overview

This repository contains my complete solution for the Oppizi technical test, delivered in three parts.

## Part 1 – System Journeys & Architecture
- Produced an sequence diagram.
- Focus areas: clear data flow, integration points, and reusable services.

## Part 2 – API Testing (Open Charge Map API)
Validated Oppizi’s geolocation using the Open Charge Map (OCM) API.

**Endpoints tested**
- GET /referencedata/
- GET /poi/

**Checks performed**
- Response time < 1000 ms
- Status code 200
- Partial JSON Schema validation (Ajv in Cypress, JSON Schema tests in Postman)
- Business rules:
  - /referencedata: Countries include BR; ConnectionTypes non-empty with valid IDs and titles.
  - /poi: Results length <= maxresults; filtered by country; if Distance is present, it is within the requested radius (+0.5 km).

## Part 3 – Manual Testing (Route Reassignment Feature)
Manual test suite for the admin feature that reassigns routes across campaigns.

- Use-case-based test design: functional, negative, edge, and permission scenarios
- Test data table: campaigns, agents, routes, schedules
- Audit and email verification steps
- Sample bug report (with Summary and Description)
- Assumptions and risks
- Regression impact checklist

---
