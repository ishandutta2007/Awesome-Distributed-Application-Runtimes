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

| Platform | Pricing Model | Free Tier & Limits | Details |
| :--- | :--- | :--- | :--- |
| **AWS App Mesh** | Free software; pay for underlying AWS compute resources (EC2/Fargate sidecars). | Free tier: Standard AWS Free Tier applies to compute/network. No direct App Mesh fees. | **AWS's managed service mesh** for Kubernetes and EC2 workloads. **Note**: AWS announced end-of-support for App Mesh on September 30, 2026—migrate to alternatives like Istio or Amazon VPC Lattice. |
| **Kong Mesh** | Commercial subscription via Kong Konnect or enterprise licenses (~$250/mesh zone/mo in Konnect or annual enterprise contracts starting ~$30,000+/yr). | Free tier available via Kong Konnect (1 control plane, limited API requests/eval limits); free fully functional OSS alternative available via [Kuma](https://github.com/kumahq/kuma). | **Enterprise service mesh** built on Kuma with global control plane, multi-zone policy management, enterprise RBAC, and 24/7 enterprise SLA support. |
| **Red Hat OpenShift Service Mesh** | Included with Red Hat OpenShift Container Platform (OCP) and Platform Plus subscriptions (typically starting ~$10,000+/yr per socket/core pair). | No permanent free tier; 60-day full-featured self-managed evaluation trial available via Red Hat Customer Portal. | **Enterprise service mesh** based on Istio, integrated with OpenShift. Version 3.4 adds Kubernetes User Namespaces support, Zero Trust Workload Identity Manager, and TrafficExtension API. |
| **Tetrate Istio Subscription (TIS)** | Commercial subscription per cluster pack (typically starting around $65,000/year for a 5-cluster package on AWS Marketplace). | Tetrate offers the 100% upstream Tetrate Istio Distro (TID) for free; TIS commercial tier provides extended CVE windows and enterprise support. | **Enterprise upstream Istio & Envoy distribution** with extended 14-month CVE maintenance, FIPS-verified builds, enterprise SLA support, and advanced management tooling. |

## Open-Source GitHub Projects

Sorted by GitHub Stars (descending):

- **etcd** [![GitHub stars](https://img.shields.io/github/stars/etcd-io/etcd?style=social&color=white)](https://github.com/etcd-io/etcd/stargazers)
  **Distributed reliable key-value store for the most critical data of a distributed system** (Apache-2.0). **The consensus and state backbone** of Kubernetes and cloud-native control planes. Provides strongly consistent (Raft-based) distributed coordination, distributed locking, service registration, and watch mechanisms. **Best for**: foundational coordination, leader election, and distributed configuration state.

- **gRPC** [![GitHub stars](https://img.shields.io/github/stars/grpc/grpc?style=social&color=white)](https://github.com/grpc/grpc/stargazers)
  **High-performance, open source universal RPC framework** (Apache-2.0). **The inter-service communication backbone** across distributed architectures. Offers pluggable support for load balancing, tracing, health checking, and authentication over HTTP/2 transport with Protocol Buffers schema contracts. **Best for**: polyglot, low-latency, and high-throughput point-to-point service invocation.

- **Apache Dubbo** [![GitHub stars](https://img.shields.io/github/stars/apache/dubbo?style=social&color=white)](https://github.com/apache/dubbo/stargazers)
  **High-performance, Java-centric RPC and microservices framework** (Apache-2.0). Provides rich built-in distributed application runtime capabilities including service registration & discovery, dynamic traffic routing, load balancing, multi-protocol communication (Triple/gRPC/REST), and service governance across large-scale enterprise deployments. **Best for**: enterprise-scale microservice governance and cross-language RPC runtimes.

- **Istio** [![GitHub stars](https://img.shields.io/github/stars/istio/istio?style=social&color=white)](https://github.com/istio/istio/stargazers)
  **The most widely adopted service mesh** (Apache-2.0) — **the enterprise standard**. Features **Ambient mode** (sidecar-less) with **ztunnel** for L4 and **waypoint proxies** for L7. Istio provides **zone-aware load balancing**, **mesh-wide default traffic policies**, **dynamic forward proxy**, **FIPS 140-3 compliance policies**, and **weighted waypoint canaries**. **The reference implementation for comprehensive service mesh**—**choose when you need advanced traffic management, security, and observability at scale**.

- **Consul** [![GitHub stars](https://img.shields.io/github/stars/hashicorp/consul?style=social&color=white)](https://github.com/hashicorp/consul/stargazers)
  **Service networking platform** (BUSL-1.1 for enterprise features) — **the service discovery heritage choice**. Provides multi-cloud service discovery, configuration key-value storage, and full-featured service mesh. Supports multi-port service mesh, external CA integration, global RPC rate limiting, and API gateway capabilities across heterogeneous Kubernetes and VM workloads. **Best for**: teams already using Consul for service discovery who want to extend into mesh capabilities.

- **Envoy** [![GitHub stars](https://img.shields.io/github/stars/envoyproxy/envoy?style=social&color=white)](https://github.com/envoyproxy/envoy/stargazers)
  **Cloud-native high-performance edge/middle/service proxy** (Apache-2.0). **The universal data plane standard** beneath Istio, Kuma, and many modern commercial meshes. Offers advanced dynamic configuration via xDS APIs, robust L7 filters, resilience primitives (circuit breaking, retries, rate limiting), and deep observability. **Best for**: building custom service meshes or programmable data plane proxies.

- **Dapr** [![GitHub stars](https://img.shields.io/github/stars/dapr/dapr?style=social&color=white)](https://github.com/dapr/dapr/stargazers)
  **Distributed Application Runtime for building microservices** (Apache-2.0) — **the building-block standard**. **Portable, event-driven runtime** that codifies best practices into open APIs called **building blocks**: **service-to-service invocation** (retries, mTLS), **publish/subscribe** (at-least-once delivery, consumer groups), **state management** (pluggable stores), **workflows** (long-running processes), **actors**, **secrets**, **configuration**, **distributed lock**, **cryptography**, **jobs**, and **conversation** (LLM abstraction). Language-agnostic runtime working on any Kubernetes cluster, VM, or edge environment. **Choose when you want to abstract away infrastructure complexity without adopting a full service mesh**.

- **Cilium** [![GitHub stars](https://img.shields.io/github/stars/cilium/cilium?style=social&color=white)](https://github.com/cilium/cilium/stargazers)
  **eBPF-based Networking, Observability, and Service Mesh** (Apache-2.0). Replaces traditional iptables and sidecars with Linux kernel-level eBPF programs, offering sidecar-free service mesh (mutual TLS, L7 traffic management, tracing) with ultra-low latency and low compute overhead. **Best for**: high-performance cloud-native networking, sidecar-free mesh, and deep kernel-level security observability.

- **Temporal** [![GitHub stars](https://img.shields.io/github/stars/temporalio/temporal?style=social&color=white)](https://github.com/temporalio/temporal/stargazers)
  **Open-source durable execution platform** (MIT). Provides a distributed orchestration and workflow runtime that ensures application code runs reliably despite network failures, process crashes, or infrastructure outages. Offers SDKs in Go, Java, TypeScript, Python, and .NET. **Best for**: mission-critical distributed workflows, reliable saga patterns, financial transactions, and stateful application orchestration.

- **Linkerd** [![GitHub stars](https://img.shields.io/github/stars/linkerd/linkerd2?style=social&color=white)](https://github.com/linkerd/linkerd2/stargazers)
  **The simplicity-focused service mesh** (Apache-2.0) — **the operational simplicity choice**. Built on ultra-light Rust microproxies (`linkerd2-proxy`). Provides automatic mTLS, rate-limit-aware load balancing, low-overhead L7 metrics, and native Kubernetes integration without complex configuration. **The reference implementation for simple, performant service mesh**—**choose when you want the service mesh feature set without operational complexity**.

- **Kuma** [![GitHub stars](https://img.shields.io/github/stars/kumahq/kuma?style=social&color=white)](https://github.com/kumahq/kuma/stargazers)
  **The universal service mesh** (Apache-2.0) — **the multi-zone, multi-cloud choice**. Built on Envoy with first-class support for both Kubernetes and VM environments. Provides multi-zone federation, policy-driven traffic routing, mTLS, and zero-trust security with a single unified control plane. **The open-source foundation of Kong Mesh**. **Best for**: teams wanting a CNCF-backed mesh that spans Kubernetes and VM workloads.

- **Contour** [![GitHub stars](https://img.shields.io/github/stars/projectcontour/contour?style=social&color=white)](https://github.com/projectcontour/contour/stargazers)
  **Kubernetes ingress controller using Envoy proxy** (Apache-2.0). Provides a dynamic reverse proxy and ingress control plane using the `HTTPProxy` custom resource definition to support multi-team ingress delegation, canary rollouts, and load balancing. **Best for**: Kubernetes north-south ingress and edge traffic management powered by Envoy.

- **Kiali** [![GitHub stars](https://img.shields.io/github/stars/kiali/kiali?style=social&color=white)](https://github.com/kiali/kiali/stargazers)
  **Observability and service mesh management console for Istio** (Apache-2.0). Provides live topology visualization, health status, metrics correlation, and automated configuration verification for Istio service mesh deployments. **Best for**: interactive service topology graphing, traffic troubleshooting, and Istio configuration validation.

- **Traefik Mesh** [![GitHub stars](https://img.shields.io/github/stars/traefik/mesh?style=social&color=white)](https://github.com/traefik/mesh/stargazers)
  **Lightweight service mesh** (Apache-2.0) — **the simple alternative**. Built on Traefik Proxy. Uses a per-node proxy model rather than sidecars per pod, minimizing resource footprint for smaller Kubernetes clusters. **Best for**: teams wanting basic service mesh functionality with minimal resource overhead.

### Frameworks & Extensions for Custom Distributed Systems

- Combine **Dapr** for application-level distributed building blocks (state, pub/sub, workflows) with **Istio** or **Linkerd** for network-level traffic management and mTLS.
- Integrate **Temporal** for durable distributed transaction workflows and saga orchestration.
- Leverage **Cilium** for eBPF-accelerated kernel-level mesh networking or **Envoy** for custom proxy data plane pipelines.
- Deploy **Kiali** for deep visibility and visual tracing across your service mesh topology.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format and star-badge sorting order).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Distributed application runtimes handling service traffic must follow security best practices, including mTLS, authorization policies, and audit logging.
- **The "service mesh vs. distributed runtime" distinction matters.** **Service meshes** (Istio, Linkerd, Kuma, Consul, Cilium) intercept network traffic to provide security, observability, and traffic control—they operate at the network layer. **Distributed runtimes** (Dapr, Temporal) provide APIs for state management, pub/sub, actors, and workflows—they operate at the application layer. **Most mature architectures use both**: a mesh for network security and a runtime for application building blocks.
- **Istio vs. Linkerd: complexity vs. simplicity.** **Istio** offers the most comprehensive feature set—ambient mode, advanced traffic management, and extensive policy controls. **Linkerd** focuses on operational simplicity—lighter proxies, automated trust rotation, and significantly reduced control plane memory. **Choose Istio for maximum capability; Linkerd for maximum manageability.**
- **Dapr is not a service mesh replacement.** Dapr's **service invocation** building block provides retries and mTLS, but it doesn't provide the L7 traffic management, observability, and policy enforcement that a mesh does. **Dapr is for application-level concerns; a mesh is for network-level concerns.**
- **Consul 2.0's multi-port support is a significant gap closure.** Services like Kafka and CockroachDB that expose multiple ports can now run on Consul mesh without workarounds. **This makes Consul viable for a broader class of distributed systems.**
- Self-hosted open-source solutions require proper control plane management, certificate rotation, and ongoing maintenance. **Service meshes add operational complexity**—budget for platform engineering expertise regardless of mesh choice.

---

**Made for platform engineers, developers, and organizations building transparent distributed application solutions.**  
Let's make Distributed Application Runtimes more open, data-driven, and resilient.
