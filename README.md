# 🧭 Kubensage

**Kubensage** is an open-source observability toolkit built for Kubernetes environments.
It provides a modular set of Go-based components designed to collect, process, and expose runtime metrics from
containers and nodes with minimal overhead.
The goal of Kubensage is to simplify performance analysis and runtime introspection across clusters — making
observability transparent, efficient, and extensible.

---

## 🚀 Overview

Modern Kubernetes clusters run thousands of containers, each generating valuable runtime data through the **Container
Runtime Interface (CRI)**.
Kubensage bridges this gap by providing a **lightweight, composable observability pipeline** that integrates seamlessly
with existing monitoring stacks such as **Prometheus** and **Grafana**.

Each component in Kubensage plays a focused role, allowing operators to deploy only what they need.
The system is designed for **high efficiency**, **low resource footprint**, and **easy integration** with both native
and external observability tools.

---

## 🧩 Architecture

Kubensage follows a **distributed and extensible architecture** composed of several interoperable components:

### 🛰️ Agent

The **Kubensage Agent** is deployed on Kubernetes nodes.
It interfaces directly with the **CRI API** to collect low-level container and runtime metrics.
Metrics are streamed via **gRPC** to one or more Kubensage Relays for processing and aggregation.

### 🔁 Relay

The **Kubensage Relay** acts as a smart proxy between agents and consumers.
It receives metrics streams from multiple nodes, parses and normalizes the data, and forwards it through supported
transport protocols (such as gRPC or HTTP).
This separation improves scalability and simplifies data routing within large clusters.

### 📡 Exporter Prometheus

The **Kubensage Exporter Prometheus** component exposes metrics received from relays through a **Prometheus-compatible
HTTP endpoint**,
making them easily scrapeable and ready for integration with any Prometheus-based observability stack.

### 📊 Grafana Dashboards

A curated set of **Grafana dashboards** is included to visualize the collected metrics.
These dashboards provide insights into node health, container activity, runtime performance, and system-level trends —
ready to import and customize.

### ⚙️ Common

The **Common** module contains shared Go utilities, data structures, and logic used across all Kubensage components.
It ensures code consistency and reusability throughout the ecosystem.

---

## 🌐 Why Kubensage?

* **Lightweight** – Designed for minimal resource impact on nodes.
* **Modular** – Use only the components you need.
* **Native** – Built entirely in Go, integrates naturally with Kubernetes and Prometheus.
* **Scalable** – Suitable for clusters of any size.
* **Open & Extensible** – Fully open-source with clean APIs for extension.

---

## 📦 Getting Started

You can find each Kubensage component in its dedicated repository:

| Component                                        | Description                                   | Language |
|--------------------------------------------------|-----------------------------------------------|----------|
| [**agent**](./agent)                             | Collects node-level metrics via CRI API       | Go       |
| [**relay**](./relay)                             | Aggregates and forwards metrics from agents   | Go       |
| [**exporter-prometheus**](./exporter-prometheus) | Exposes data for Prometheus scraping          | Go       |
| [**grafana-dashboards**](./grafana-dashboards)   | Prebuilt dashboards for metrics visualization | JSON     |
| [**common**](./common)                           | Shared utilities and types across modules     | Go       |

---

## 🧠 Philosophy

Kubensage is built on the principle of **clarity through simplicity**.
Rather than abstracting Kubernetes internals behind complex frameworks, it focuses on exposing raw, meaningful runtime
metrics in an accessible way — empowering operators and developers to understand exactly what’s happening inside their
clusters.