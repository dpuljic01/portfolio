---
title: "INTIS — Microservices Migration"
stack: ["Python", "Django", "FastAPI", "Docker", "PostgreSQL", "CI/CD"]
outcome: "Improved deployment speed by 40% by leading containerisation and breaking a monolith into independently deployable services."
order: 2
---

INTIS operated a Django monolith that had grown to the point where individual team deployments were blocked by unrelated changes. I led the containerisation effort and drove the architectural migration toward FastAPI-based microservices, enabling teams to ship independently.

The migration was done incrementally — each service was extracted, containerised with Docker, and given its own CI/CD pipeline before the next piece was touched. This approach kept production stable throughout the transition and let the team build confidence in the new patterns before committing fully.

The 40% improvement in deployment speed came primarily from eliminating cross-team deployment dependencies and reducing build times through smaller, focused service images.
