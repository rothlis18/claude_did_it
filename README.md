# sovereign-validation-loop (v6.0) 🦅

An enterprise-grade, deterministic CLI test harness engineered for local LLM dual-model orchestration natively inside your RAM. This suite runs an adversarial **Generator-Validator pipeline**, parses feedback with a tolerant scoring engine, and forces surgical VRAM purging via `keep_alive => 0` to prevent system-throttling page swaps and port collisions.

---

## 🛠️ Advanced Engineering Features

Version 6.0 completely rewrites the pipeline architecture to ensure absolute stability over heavy testing runs:

* **Surgical VRAM Isolation:** Queries the local `/api/ps` registry using active hooks after every complete test case, forcibly unloading residual streams to prevent memory-stack leaks.
* **Resumable Execution Matrix:** Automatically scans your existing CSV logging logs on boot. If an overnight operation is interrupted, it skips completed lines and appends new records seamlessly without losing data history.
* **Context Window Protection:** Hardcodes an explicit `num_ctx => 8192` boundary to prevent local API runtimes from silently truncating long text strings or complex papers.
* **Tolerant Regex Score Parsing:** Utilizes a fallback matrix of four distinct regular expression patterns to accurately extract scores from alternative layout styles (e.g., markdown bolding or fractions).
* **Automated Key Denylisting:** Automatically filters out non-chat configurations (like embedding or reranker models) to preserve execution flow across your directory.

---

## 📊 Telemetry Log Output Matrix

The execution pipeline generates a highly detailed, real-time data ledger (`benchmark_results.csv`) mapping twelve distinct tracking metrics:

| Timestamp | Generator | Validator | Lens | Status | Final_Score | Score_Parsed | Loops | Duration |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2026-09-16 12:00:30 | deepseek-r1:14b | dolphin3:latest | objectivity | PASS | 100 | YES | 1 | 317.25s |
| 2026-09-16 16:09:05 | qwen3-abliterated:4b | dolphin3:latest | objectivity | PASS | 100 | YES | 1 | 43.99s |

---

## 🚀 Quick Start Deployment

### 1. System Requirements
* **PHP 8.2+ CLI** environment enabled locally (e.g., via XAMPP).
* **Ollama** running natively on default host port `11434`.
* For full asynchronous interrupt safety, the `pcntl` extension is highly recommended.

### 2. Prepare the Environment
Ensure your local VRAM boundaries are protected by removing un-optimized blocks and fetching high-speed, edge-ready weights:
```bash
# Clear out un-optimized, resource-heavy experimental variants
ollama rm schroneko/mistral-nemo-minitron-8b-instruct:latest

# Fetch the high-speed, edge-optimized 3B Western logic layer
ollama run llama3.2:3b
```

### 3. Execution Commands
Navigate to your local working directory inside your terminal console and run your targeted processing routines:

```bash
# Run the complete diagnostic pairing matrix from scratch
php bench_mark.php

# Resume an interrupted overnight session from the exact line it stopped
php bench_mark.php --resume

# Isolate testing routines to specific models within your active directory
php bench_mark.php --models=deepseek-r1:14b,llama3.2:3b

# Run a safe configuration check without initializing the model weights
php bench_mark.php --dry-run
```

---

## 🔒 License & Autarky Disclaimer
Distributed completely free under the permissive MIT Open-Source License. Engineered explicitly for sovereign administrators seeking absolute data sovereignty and intellectual autarky under conditions of material scarcity.
