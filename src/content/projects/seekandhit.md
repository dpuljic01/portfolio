---
title: "SeekandHit — API Infrastructure Overhaul"
stack: ["Python", "FastAPI", "PostgreSQL", "Docker", "AWS", "OAuth2"]
outcome: "Eliminated $100k/year in Apigee licensing costs by replacing the vendor API gateway with an in-house FastAPI proxy and auth system."
order: 3
---

SeekandHit's API traffic was routed through Apigee, which had become the largest line item in their infrastructure budget without providing commensurate value. I designed and built a replacement API proxy in FastAPI, covering routing, rate limiting, and request transformation — removing the Apigee dependency entirely.

Alongside the proxy, I built an in-house authentication and authorisation system from scratch, implementing OAuth2 token flows and role-based access control. This gave the team full ownership of the auth layer, eliminated a third-party vendor lock-in, and cut response latency at the gateway level.

The project ran on AWS and was deployed via Docker containers, with automated tests covering all critical auth and routing paths.
