# Awesome-Distributed-Application-Runtimes

## Top Distributed Application Runtimes Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Service Mesh, Sidecar Proxies & Distributed Building Blocks*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Distributed Application Runtimes**. These tools enable developers to build resilient microservices by abstracting away the complexity of service discovery, traffic management, security, and state management—from service meshes that intercept network traffic to distributed runtimes that provide language-agnostic building blocks.



**Examples** include Dapr, Istio, Linkerd, Kuma, Consul, Traefik Mesh, and OpenShift Service Mesh (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, sidecar proxies, and open distributed infrastructure—ideal for platform engineers, developers, and organizations seeking transparent, vendor-independent microservices tooling.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **AWS App Mesh**

  **AWS's managed service mesh** for Kubernetes and EC2 workloads. **Note**: AWS announced end-of-support for App Mesh on September 30, 2026—migrate to alternatives like Istio or Amazon VPC Lattice. **The managed choice** for AWS-native microservices.



- **Kong Mesh**

  **Enterprise service mesh** built on Kuma with support and advanced features. **The commercial Kuma choice**—adds global control plane, enterprise policies, and 24/7 support.



- **Red Hat OpenShift Service Mesh**

  **Enterprise service mesh** based on Istio, integrated with OpenShift. **Version 3.4** adds **Kubernetes User Namespaces** support, **Zero Trust Workload Identity Manager** (technology preview), and the **TrafficExtension API** for safer Envoy extensions . **The OpenShift-native choice** for Red Hat customers.



## Open-Source GitHub Projects



- **Dapr**

  **Distributed Application Runtime for building microservices** (Apache-2.0) — **the building-block standard** . **Portable, event-driven runtime** that codifies best practices into open APIs called **building blocks**: **service-to-service invocation** (retries, mTLS), **publish/subscribe** (at-least-once delivery, consumer groups), **state management** (pluggable stores), **workflows** (long-running processes), **actors**, **secrets**, **configuration**, **distributed lock**, **cryptography**, **jobs**, and **conversation** (LLM abstraction with PII obfuscation) . **Language-agnostic**—works with any framework on any Kubernetes cluster, VM, or edge environment . **CNCF graduated project** used by ZEISS Vision since 2020 and Elation Health for event-driven architecture . **Dapr v1.17** adds workflow versioning and state retention policies ; **v1.18** adds history context propagation and dead-letter topics . **The reference implementation for distributed application building blocks**—**choose when you want to abstract away infrastructure complexity without adopting a full service mesh**.



- **Istio**

  **The most widely adopted service mesh** (Apache-2.0) — **the enterprise standard** . **Ambient mode** (sidecar-less) with **ztunnel** for L4 and **waypoint proxies** for L7. **Istio 1.31** adds **zone-aware load balancing** (automatic same-zone routing), **mesh-wide default traffic policy**, **dynamic forward proxy for unknown hosts**, **FIPS 140-3 compliance policy**, and **weighted waypoint canaries** for gradual rollout . **Multi-cluster stability improvements** and **trust domain matching** in AuthorizationPolicy . **The reference implementation for comprehensive service mesh**—**choose when you need advanced traffic management, security, and observability at scale**.



- **Linkerd**

  **The simplicity-focused service mesh** (Apache-2.0) — **the operational simplicity choice** . **Ultra-light Rust microproxies**. **Linkerd 2.20** adds **rate-limit-aware load balancing** (respects HTTP 429 and gRPC RESOURCE_EXHAUSTED), **control plane memory reduction up to 85%** on busy clusters, **improved inbound metrics**, and **native sidecars as default** . **Automated trust anchor rotation** (Enterprise) and **Windows VM support** outside Kubernetes . **The reference implementation for simple, performant service mesh**—**choose when you want the service mesh feature set without operational complexity**.



- **Kuma**

  **The universal service mesh** (Apache-2.0) — **the multi-zone, multi-cloud choice** . **Built on Envoy** with support for Kubernetes and VMs. **Kuma 2.14** includes ongoing stability fixes for multi-zone federation, mTLS, and mesh policies . **The foundation of Kong Mesh**. **Best for**: teams wanting a CNCF-backed mesh that spans Kubernetes and VM workloads with a single control plane.



- **Consul**

  **Service networking platform** (BUSL-1.1 for enterprise features) — **the service discovery heritage choice** . **Consul 2.0** adds **multi-port service mesh support** (beta, Enterprise), **CyberArk Workload Identity Manager as external CA**, **global RPC rate limiting**, and **API gateway auto-scaling** . **Best for**: teams already using Consul for service discovery who want to extend into mesh capabilities.



- **Traefik Mesh**

  **Lightweight service mesh** (Apache-2.0) — **the simple alternative** . **Built on Traefik Proxy**. **No sidecars**—uses a per-node proxy. **Traefik Mesh v1.4.7** is compatible with Kubernetes v1.24+ . **Best for**: teams wanting basic mesh functionality with minimal overhead.



### Additional Strong Open-Source Options



- **Envoy** — **The sidecar proxy standard** (Apache-2.0). **The data plane beneath Istio, Kuma, and many commercial meshes**. **Best for**: building custom meshes or understanding the underlying proxy.

- **Linkerd Viz** — **Observability extension for Linkerd** (Apache-2.0). **The metrics and dashboard companion**.

- **Kiali** — **Observability console for Istio** (Apache-2.0). **The mesh management UI** .

- **Contour** — **Kubernetes ingress controller using Envoy** (Apache-2.0). **The north-south traffic choice**.

- Community **n8n** workflows for mesh alerting and service catalog synchronization.



**Frameworks for building custom systems**: Combine **Dapr** for distributed building blocks with **Istio** for advanced traffic management, **Linkerd** for simplicity-focused mesh, **Kuma** for multi-zone spanning, and **Envoy** for custom proxy development—creating a comprehensive distributed runtime stack.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Distributed application runtimes handling service traffic must follow security best practices, including mTLS, authorization policies, and audit logging.

- **The "service mesh vs. distributed runtime" distinction matters.** **Service meshes** (Istio, Linkerd, Kuma, Consul) intercept network traffic to provide security, observability, and traffic control—they operate at the network layer . **Distributed runtimes** (Dapr) provide APIs for state management, pub/sub, and workflows—they operate at the application layer . **Most mature architectures use both**: a mesh for network security and a runtime for application building blocks.

- **Istio vs. Linkerd: complexity vs. simplicity.** **Istio** offers the most comprehensive feature set—ambient mode, advanced traffic management, and extensive policy controls . **Linkerd** focuses on operational simplicity—lighter proxies, automated trust rotation, and significantly reduced control plane memory . **Choose Istio for maximum capability; Linkerd for maximum manageability.**

- **Dapr is not a service mesh replacement.** Dapr's **service invocation** building block provides retries and mTLS, but it doesn't provide the L7 traffic management, observability, and policy enforcement that a mesh does . **Dapr is for application-level concerns; a mesh is for network-level concerns.**

- **Consul 2.0's multi-port support is a significant gap closure.** Services like Kafka and CockroachDB that expose multiple ports can now run on Consul mesh without workarounds . **This makes Consul viable for a broader class of distributed systems.**

- Self-hosted open-source solutions require proper control plane management, certificate rotation, and ongoing maintenance. **Service meshes add operational complexity**—budget for platform engineering expertise regardless of mesh choice.



---



**Made for platform engineers, developers, and organizations building transparent distributed application solutions.**  

Let's make Distributed Application Runtimes more open, data-driven, and resilient.
