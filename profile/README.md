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

| Component                                                                   | Description                                   | Language |
|-----------------------------------------------------------------------------|-----------------------------------------------|----------|
| [**agent**](https://github.com/kubensage/agent)                             | Collects node-level metrics via CRI API       | Go       |
| [**relay**](https://github.com/kubensage/relay)                             | Aggregates and forwards metrics from agents   | Go       |
| [**exporter-prometheus**](https://github.com/kubensage/exporter-prometheus) | Exposes data for Prometheus scraping          | Go       |
| [**grafana-dashboards**](https://github.com/kubensage/grafana-dashboards)   | Prebuilt dashboards for metrics visualization | JSON     |
| [**common**](https://github.com/kubensage/common)                           | Shared utilities and types across modules     | Go       |

## 🌐 Why Kubensage?

* **Lightweight** – Designed for minimal resource impact on nodes.
* **Modular** – Use only the components you need.
* **Native** – Built entirely in Go, integrates naturally with Kubernetes and Prometheus.
* **Scalable** – Suitable for clusters of any size.
* **Open & Extensible** – Fully open-source with clean APIs for extension.

---

## 🧠 Philosophy

Kubensage is built on the principle of **clarity through simplicity**.
Rather than abstracting Kubernetes internals behind complex frameworks, it focuses on exposing raw, meaningful runtime
metrics in an accessible way — empowering operators and developers to understand exactly what’s happening inside their
clusters.