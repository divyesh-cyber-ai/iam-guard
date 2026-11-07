
# 🛡️ IAM Guard

### See beyond permissions. Understand risk.

**IAM Guard** is a Python-based AWS IAM policy security analyzer designed to identify risky permissions, evaluate access against declared intent, and generate clear security findings.

The goal is to go beyond simply identifying what a policy allows and understand whether those permissions are appropriate for their intended purpose.

---

## 🎯 The Problem

AWS Identity and Access Management (IAM) controls who can access cloud resources and what actions they can perform.

However, incorrectly configured permissions can introduce security risks:

- Excessively broad permissions.
- Unnecessary administrative access.
- Dangerous actions granted to ordinary users.
- Permissions that exceed an application's intended responsibilities.
- Potential privilege escalation paths.

A policy can be syntactically valid and still introduce serious security risks.

**IAM Guard aims to help identify these risks and make them easier to understand.**

---

## 🧠 Our Approach

IAM Guard is being designed around three primary analysis engines.

| Engine | Responsibility |
|---|---|
| Security Analysis Engine | Identifies risky IAM permissions using deterministic security rules. |
| Intent Analysis Engine | Evaluates whether granted permissions match their declared purpose. |
| Decision Engine | Combines findings and contextual information into an overall security assessment. |

Supporting components handle policy parsing, analysis context, and reporting.

### Architecture

```text
             IAM Policy JSON
                    |
                    ▼
             Policy Parser
                    |
                    ▼
         Security Analysis Engine
                    |
                    ▼
            Intent Analysis Engine
                    |
                    ▼
              Decision Engine
                    |
                    ▼
             Security Assessment
                    |
                    ▼
           Findings & Recommendations
```

The architecture is modular so individual components can be developed and tested independently.

---

## 🏗️ Project Structure

```text
iam-guard/
│
├── iam_guard/
│   ├── __init__.py
│   │
│   ├── parser/
│   │
│   ├── security_engine/
│   │   └── rules/
│   │
│   ├── intent_engine/
│   │
│   ├── decision_engine/
│   │
│   ├── context/
│   │
│   └── reporting/
│
├── tests/
├── examples/
│
├── README.md
├── LICENSE
└── .gitignore
```

### Component Responsibilities

- **parser:** Handles IAM policy JSON input.
- **security_engine:** Performs deterministic permission-risk analysis.
- **security_engine/rules:** Contains individual security checks.
- **intent_engine:** Compares permissions against declared purpose.
- **decision_engine:** Combines findings, intent, and context into an assessment.
- **context:** Maintains relevant information during analysis.
- **reporting:** Produces security findings and recommendations.
- **tests:** Contains automated tests.
- **examples:** Contains sample policies and usage examples.

---

## ⚙️ Planned Capabilities

The following capabilities are part of the development direction:

- IAM policy JSON parsing.
- Detection of risky permission configurations.
- Identification of overly broad access.
- Analysis of potentially dangerous actions.
- Permission-versus-intent evaluation.
- Context-aware security assessments.
- Clear security findings and recommendations.

---

## 🚧 Development Status

**Current stage: Initial architecture established.**

The initial project structure has been created and merged into the main branch.

The analysis engines and their functionality are still under development.

| Component | Status |
|---|---|
| Project structure | ✅ Created |
| Policy parser | ⏳ Planned |
| Security analysis engine | ⏳ Planned |
| Intent analysis engine | ⏳ Planned |
| Decision engine | ⏳ Planned |
| Reporting system | ⏳ Planned |
| Automated tests | ⏳ Planned |

---

## 🛠️ Technology

- **Python** – Core implementation language.
- **AWS IAM** – Identity and access management policy domain.
- **Git & GitHub** – Version control and collaboration.
- **pytest** – Planned testing framework.

---

## 🎯 Project Objective

Build a modular security analysis tool that helps developers and cloud security practitioners understand the risks hidden inside IAM permissions.

The central idea:

> Having permission to perform an action does not necessarily mean that permission should exist.

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

**Built as a hands-on exploration of AWS IAM security, Python development, and cloud threat analysis.**
