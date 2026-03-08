# Migrating to OpenTelemetry

https://www.socallinuxexpo.org/scale/23x/presentations/migrating-opentelemetry

- **Date**: Saturday, March 7, 2026
- **Time**: 12:30 - 13:30
- **Location**: Ballroom F
- **Speaker(s)**: Xpaul Vigil, Staff DevOps Engineer, Crexi

> The presentation addresses the practical complexities of transitioning to OpenTelemetry in heterogeneous environments. Rather than treating migration as a straightforward technical task, the speaker emphasizes adopting "self-service adoption as the core strategy" instead of centralized platform management.
>
> Key challenges discussed include maintaining semantic conventions across programming languages, managing context propagation reliably, and preventing "configuration drift and sprawl." The speaker highlights unexpected complications around "cost management—cardinality explosions, sampling tradeoffs, attribute hygiene."
>
> The core solution involved building "a home-grown, self-service solution built on Pulumi" using infrastructure-as-code principles. This approach provides "opinionated templates, safe defaults, automated wiring of collectors and exporters, and guardrails."
>
> Attendees will gain insight into migration planning, platform design for team adoption, and maintaining observability consistency as systems evolve.

## Overview

A practical account of migrating a heterogeneous production environment to OpenTelemetry by building a self-service, Pulumi-based IaC platform that gives teams opinionated defaults and automated collector wiring.

## Key Points

- Observability spend 📈
- Use OTel for everything
- BYOC (Bring Your Own Cloud) vendor
- eBPF works on k8s, not Fargate ECS
- Firehose to get logs out
- dev:SRE at 15:1
- Some non-otel features not available on new platform
