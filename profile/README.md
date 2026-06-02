<p align="center">
  <strong>CAGE: Cybersecurity Agent Gym & Evaluation</strong>
</p>

<p align="center">
  Building reproducible benchmarks and runtime infrastructure for evaluating autonomous agents on realistic cybersecurity tasks.
</p>

<p align="center">
  <a href="https://github.com/cage-org/cage">Framework</a> ·
  <a href="https://github.com/cage-org/pentest_bench">PentestBench</a> ·
  <a href="https://github.com/cage-org/post-exploitation-range">Post-Exploitation Bench</a>
</p>

<p align="center">
  <img src="./assets/table_compare.png" alt="Comparison with existing cybersecurity benchmarks" width="845">
</p>

Existing cybersecurity-agent benchmarks often capture only part of the story: puzzle-style challenges, known vulnerability reproduction, or one-off exploit attempts. We built CAGE and PentestBench because real authorized security testing is a longer process. It asks an agent to explore, gain access, continue from that access, and leave evidence that can be checked and compared.

---

## What is CAGE?

CAGE is an open-source evaluation stack for measuring how autonomous agents behave in controlled cybersecurity environments.

The project connects three layers that are usually fragmented:

- 🧪 **Benchmarks** for external pentesting, CVE exploitation, CTF-style tasks, and post-exploitation scenarios.
- ⚙️ **Runtime infrastructure** for agent execution, target lifecycle management, model proxying, scoring, resume, and inspection.
- 📊 **Evaluation workflows** that turn large runs into auditable traces, dashboards, and benchmark-specific reports.

CAGE is built for researchers and engineers who need more than a toy benchmark: isolated targets, repeatable runs, model-call traces, failure analysis, and clear scoring artifacts.

---

## Core Repositories

<table>
  <tr>
    <td width="28%"><strong>⚙️ <a href="https://github.com/cage-org/cage">cage</a></strong></td>
    <td>
      The core framework for running cybersecurity-agent evaluations. It manages experiment configs, agents, Dockerized targets, model proxy logs, scoring, resumable runs, and the inspection web UI.
      <br><br>
      <strong>Start here if you want to run experiments, inspect results, or build a new benchmark.</strong>
    </td>
  </tr>
  <tr>
    <td><strong>🎯 <a href="https://github.com/cage-org/pentest_bench">pentest_bench</a></strong></td>
    <td>
      The main external penetration-testing benchmark. It evaluates agents on public-facing attack surfaces, web exploitation workflows, prompt levels, pass-k runs, and benchmark-owned scoring.
      <br><br>
      <strong>Start here if you want to evaluate agents on realistic pentest tasks.</strong>
    </td>
  </tr>
  <tr>
    <td><strong>🕸️ <a href="https://github.com/cage-org/post-exploitation-range">post-exploitation-range</a></strong></td>
    <td>
      Target ranges and task assets for internal and post-exploitation evaluation: foothold usage, host discovery, privilege escalation, lateral movement, and multi-step operational reasoning.
      <br><br>
      <strong>Start here if you care about what agents do after initial compromise.</strong>
    </td>
  </tr>
</table>

---

## Repository Map

| Repository | Focus | Role |
|---|---|---|
| [`cage`](https://github.com/cage-org/cage) | Runtime, proxy, agents, scoring, dashboard, operations | Core framework |
| [`pentest_bench`](https://github.com/cage-org/pentest_bench) | External penetration-testing tasks | Primary benchmark |
| [`post-exploitation-range`](https://github.com/cage-org/post-exploitation-range) | Internal range and post-exploitation scenarios | Primary benchmark asset |
| [`CVE-Bench`](https://github.com/cage-org/CVE-Bench) | Vulnerability-specific exploitation tasks | Benchmark suite |
| [`NYUCTF-Bench`](https://github.com/cage-org/NYUCTF-Bench) | CTF-style security challenges | Benchmark suite |
| [`AutoPenbench`](https://github.com/cage-org/AutoPenbench) | Automated pentest benchmark assets and experiments | Research assets |

---

## Where Should I Start?

### I want to run an existing benchmark

Start with [`cage`](https://github.com/cage-org/cage).

You will configure models, prepare benchmark data, run a small smoke experiment, and inspect results through the CAGE web UI.

### I want to evaluate pentesting agents

Start with [`pentest_bench`](https://github.com/cage-org/pentest_bench), then run it through [`cage`](https://github.com/cage-org/cage).

PentestBench focuses on external attack workflows: web targets, prompt levels, repeated passes, scoring artifacts, and dashboard summaries.

### I want to evaluate post-exploitation ability

Start with [`post-exploitation-range`](https://github.com/cage-org/post-exploitation-range).

This repository covers the internal-range side of evaluation: whether an agent can reason beyond a single public-facing vulnerability.

### I want to build a new benchmark

Start with the benchmark-authoring docs in [`cage`](https://github.com/cage-org/cage).

CAGE benchmarks define target setup, prompts, scoring, dashboards, and experiment configuration through a common framework.

---

## What We Care About

- **Reproducibility**: isolated targets, explicit run IDs, structured artifacts.
- **Observability**: model request logs, proxy traces, trial metadata, dashboard views.
- **Scalability**: pass-k runs, worker pools, resumable experiments, failure recovery.
- **Realism**: multi-step targets, benchmark-owned scoring, and operational task structure.
- **Auditability**: enough evidence to explain success, failure, and model behavior.

---

## Documentation

Most user and developer documentation lives in [`cage`](https://github.com/cage-org/cage):

- **Getting Started**: clone, model setup, dataset setup, first run.
- **Running Experiments**: `project.yml`, dry runs, small/full runs, resume, dashboard inspection.
- **Writing Benchmarks**: benchmark interface, targets, scorers, dashboard generation.
- **Developing CAGE**: runtime, agents, proxy, orchestration, web app.
- **Operations**: Docker cleanup, orphaned resources, run IDs, large-run monitoring.

---

## Responsible Use

CAGE is intended for controlled research and evaluation environments.

Only run agents against systems you own or have explicit permission to test. Benchmark targets should be isolated, disposable, and operated in accordance with applicable laws and policies.

---

## Project Status

CAGE is under active development. APIs, benchmark schemas, and datasets may change as the evaluation stack matures.
