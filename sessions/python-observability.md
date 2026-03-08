# Thoughtful Observability: Monitoring the Python Infrastructure

https://www.socallinuxexpo.org/scale/23x/presentations/thoughtful-observability-monitoring-python-infrastructure

- **Date**: Saturday, March 7, 2026
- **Time**: 11:15 - 12:15
- **Location**: Ballroom F
- **Speaker(s)**: Jacob Coffee, Infrastructure Engineer, Python Software Foundation

> "Python infrastructure, which includes PyPI, documentation hosting, mailing lists, and bug tracking, serves millions of developers worldwide every day. When something breaks, we need to know immediately. But observability at scale comes with real costs, both in tools and in engineering time."
>
> The presentation discusses real-world lessons from managing observability for Python Software Foundation infrastructure, balancing comprehensive monitoring against budget and operational constraints. The speaker covers leveraging self-hosted Grafana/Loki alongside Datadog (provided through their open source program), offering principles applicable to both self-hosted open source solutions and commercial platforms.

## Overview

Real-world lessons from building cost-conscious observability for the Python Software Foundation's globally critical infrastructure, balancing self-hosted Grafana/Loki with commercial tooling on a nonprofit budget.

## Key Points

- "Seeing is not understanding"
- PyPI
  - 3.4 Billion downloads packages downloaded per day (now over 4 Billion)
  - 36 TB of packages
  - More traffic than google
- "We don't have the luxury of noise" because of the small team. Alerts compete with real work
- "Noise trains you to ignore alerts"
- Community as observability
  - Messages and friction reports as observability data
  - People remember context that dashboards cannot
