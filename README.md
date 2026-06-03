# 🎯 Project-Zero-Day: Automated LLM Adversarial Red Teaming

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![LangChain](https://img.shields.io/badge/Framework-LangChain-green)
![Gemini Pro](https://img.shields.io/badge/Target-Gemini%20Pro-orange)
![Status](https://img.shields.io/badge/Status-Active%20Research-brightgreen)

## 📖 Executive Summary
**Project-Zero-Day** is an autonomous, multi-agent adversarial evasion framework. Its core objective is to continuously evaluate the safety, alignment, and robustness of Large Language Models—specifically targeting the **Gemini Pro** architecture—against novel, zero-day prompt injection and jailbreak attacks.


## 🧠 Architecture Overview
The framework operates on a continuous "Red Team Loop" utilizing an autonomous multi-agent system:

1. **The Attacker (Generator):** An agent equipped with datasets of known adversarial strategies (e.g., JailbreakChat) that programmatically mutates and obfuscates prompts (using techniques like base64 encoding, persona adoption, and adversarial suffixing).
2. **The Target (Gemini Pro):** The primary model under test, accessed via the official Google Generative AI SDK.
3. **The Judge (Evaluator):** An autonomous scoring agent that mathematically evaluates the Target's response, determining if the safety guardrails were successfully bypassed (Jailbreak = 1) or if the model safely refused (Refusal = 0).

## 🚀 Key Features
* **Automated Fuzzing:** Continuous, unsupervised prompt generation and testing.
* **Tree of Thoughts (ToT) Evasion:** The Attacker agent learns from the Judge's feedback, dynamically altering its strategy to find higher-success attack topologies.
* **Telemetry & Logging:** All prompts, responses, and bypass success rates are logged to an internal SQLite database for statistical analysis.

## 🗄️ Datasets
* **Status:** 🟢 **Active / Easy Availability**
* The framework utilizes publicly available adversarial corpuses, primarily drawing baseline topologies from **JailbreakChat** and the **Do-Not-Answer** dataset to seed the Attacker agent.

## 🛠️ Tech Stack
* **Language:** Python
* **Orchestration:** LangChain / LangGraph
* **APIs:** `google-generativeai`
* **Data Layer:** SQLite / Pandas

## ⚠️ Ethical Disclaimer & Responsible Disclosure
This tool is developed strictly for **defensive security research and educational purposes**. The goal is to harden LLMs and improve AI safety alignment. Any novel, severe bypasses discovered against Gemini Pro using this framework will not be published publicly. They will be responsibly disclosed directly to **Google**.

---
*Developed by a Senior Data Scientist / AI Security Researcher.*