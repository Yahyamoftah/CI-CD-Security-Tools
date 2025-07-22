# CI/CD Security Tools Checklist

**Author:** Yahya Elkomy

---

## Table of Contents

- [Introduction](#introduction)
- [1. SAST Tools Checklist](#1-sast-tools-checklist)
- [2. SCA Tools Checklist](#2-sca-tools-checklist)
- [3. DAST Tools Checklist](#3-dast-tools-checklist)
- [4. Implementation Checklist](#4-implementation-checklist)
- [More References](#more-references)

---

## Introduction

This document provides a comprehensive checklist of security tools designed to integrate seamlessly into CI/CD pipelines. As software development practices increasingly adopt Continuous Integration and Continuous Deployment (CI/CD), the need to embed security throughout the Software Development Life Cycle (SDLC) has become essential.

The checklist is structured to cover three primary categories of application security testing:

- **Static Application Security Testing (SAST)** – for identifying vulnerabilities in source code before compilation.  
- **Software Composition Analysis (SCA)** – for detecting risks in third-party libraries and open-source dependencies.  
- **Dynamic Application Security Testing (DAST)** – for analyzing applications during runtime to uncover security flaws in real-world conditions.

Each section includes a curated selection of tools, detailing their licensing models, supported languages or ecosystems, key features, and recommended use cases. An additional implementation checklist is provided to guide integration best practices, from tool selection and CI/CD integration to vulnerability triage and compliance mapping.

This resource is intended to assist developers, DevOps engineers, and security teams in selecting appropriate security solutions, improving automation in secure development, and aligning their workflows with modern DevSecOps practices.

---

## 1. SAST Tools Checklist

**Static Application Security Testing**: Analyzes source code for vulnerabilities pre-compilation.

| Tool              | License     | Key Languages                               | Key Features                                                   | Best For                                        | References     |
|-------------------|-------------|---------------------------------------------|----------------------------------------------------------------|--------------------------------------------------|----------------|
| Fortify SAST      | Commercial  | 33+ (Java, C#, JS, Python, Go, etc.)        | AI-driven prioritization, CI/CD integration, OWASP/CWE coverage | Deep code analysis & compliance                | Micro Focus    |
| Mend (SAST)       | Commercial  | Java, C#, JS/TS, Python, Go, etc.           | Autofix, 70+ CWE coverage, IDE/CI/CD integration               | Fast, automated fixes                          | Mend           |
| CodeQL            | Free (OSS)  | Java, JS/TS, Python, C/C++, Go, Ruby        | Semantic analysis, GitHub integration, custom queries           | GitHub workflows                                | GitHub         |
| SonarQube         | Freemium    | 25+ (Java, C#, JS, Python, Go)              | Code quality + security, OWASP/CWE, PR analysis                 | Security & technical debt                       | SonarSource    |
| Checkmarx CxSAST  | Commercial  | Java, JS, C#, Python, Ruby, Swift           | Code path analysis, CI/CD plugins                               | Deep customization                              | Checkmarx      |
| Semgrep           | Open Source | 30+ (JS, Python, Java, Go, Terraform)       | YAML rules, IDE/CLI support, low false positives                | Dev-centric teams                               | Semgrep        |
| Snyk Code         | Freemium    | Java, JS/TS, Python, C#, Go, PHP            | IDE feedback, OSS focus, CI/CD integration                      | OSS component scanning                          | Snyk           |
| Veracode          | Commercial  | Java, .NET, JS, Python, C++                 | Binary/SAST scanning, eLearning, cloud-first                    | SaaS solutions                                  | Veracode       |
| Bearer CLI        | Open Source | Java, Ruby, JS/TS                           | Privacy focus, data flow analysis                               | Compliance-heavy apps                           | Bearer         |

---

## 2. SCA Tools Checklist

**Software Composition Analysis**: Scans dependencies for vulnerabilities.

| Tool                  | License       | Supported Ecosystems                 | Key Features                                               | Best For                              | References    |
|-----------------------|---------------|--------------------------------------|------------------------------------------------------------|----------------------------------------|---------------|
| Sonatype Nexus        | Commercial    | Java, JS, Python, Go, .NET, Ruby     | AI scoring, SBOM, CI/CD blocking                           | Zero false positives, policy enforcement | Sonatype      |
| Dependabot            | Free (GitHub) | Java, Python, JS, Ruby, .NET, Go     | Auto-PRs, GitHub-native                                     | GitHub automation                     | GitHub        |
| Snyk Open Source      | Freemium      | Node.js, Java, Python, etc.          | IDE/CI/CD scans, license compliance                         | Dev-first prioritization              | Snyk          |
| Mend (SCA)            | Commercial    | 30+ ecosystems                        | Container scanning, policy enforcement                      | Complex supply chains                 | Mend          |
| Debricked             | Free for OSS  | Java, JS, Python, C#, Go             | CI/CD integration, UI/UX                                    | Intuitive workflows                   | Debricked     |
| Black Duck            | Commercial    | Java, Python, JS, .NET, C/C++        | License compliance, binary scanning                         | Compliance-heavy industries           | Synopsys      |
| Retire.js             | Open Source   | JavaScript                           | Framework-specific detection                                | JS-heavy apps                         | Retire.js     |
| Bytesafe             | Freemium      | Node.js, Python, Java, .NET          | Dependency firewall, private registry                       | Dependency governance                 | Bytesafe      |
| Jit                   | Commercial    | JS, Python, Java, Terraform          | Unified SCA/SAST/DAST, AI remediation                       | DevSecOps consolidation              | Jit           |

---

## 3. DAST Tools Checklist

**Dynamic Application Security Testing**: Scans running apps for runtime vulnerabilities.

| Tool               | License       | Key Capabilities                     | Key Features                                                    | Best For                            | References   |
|--------------------|---------------|--------------------------------------|------------------------------------------------------------------|--------------------------------------|--------------|
| Fortify DAST       | Commercial    | Web apps, APIs                       | IAST integration, compliance reporting                          | Enterprise-scale accuracy           | Micro Focus  |
| Acunetix           | Commercial    | Web apps, APIs, serverless           | Fast scanning, proof-based validation                           | SMBs starting AppSec                | Acunetix     |
| Nikto              | Open Source   | Web servers                          | Lightweight, CLI-based                                          | Quick pentest scans                 | Nikto        |
| OWASP ZAP          | Open Source   | Web apps, APIs                       | 300+ add-ons, CI/CD support, auth testing                       | Customizable budget scanning        | OWASP ZAP    |
| Invicti            | Commercial    | JS SPAs, APIs, cloud apps            | 99.98% accurate, IAST, compliance                               | Enterprise-scale accuracy           | Invicti      |
| Burp Suite Pro     | Commercial    | Web apps, APIs, mobile backend       | Manual pentesting tools, plugins                                | Deep security testing               | PortSwigger  |
| StackHawk          | Freemium      | APIs, microservices, CI/CD pipelines | ZAP-based, YAML config                                           | DevOps-native testing               | StackHawk    |
| Tenable Nessus     | Commercial    | Network + Web App (ADAST)            | OWASP detection, misconfig scans                                | Infra + app security                | Tenable      |
| Qualys WAS         | Commercial    | Web App + API (ADAST)                | Cloud DAST, WAF integration, SPA crawling                       | Cloud-native Qualys users           | Qualys       |
| Arachni            | Free/Comm.    | AJAX, SPAs                           | Ruby-based, multiplatform, high coverage                        | Flexible pentesting                 | Arachni      |
| Contrast CE        | Free (limited)| Java, .NET                           | IAST + DAST, runtime analysis                                   | JVM/.NET teams                      | Contrast     |
| Akto               | Open Source   | API security, cloud-native apps      | Automated API discovery, CI/CD integration                      | API-first architectures             | Akto         |

---

## 4. Implementation Checklist

**Key steps for integrating tools into SDLC:**

1. **Language Alignment**  
   - Match tools to languages (e.g., Mend for polyglot, Retire.js for JS).  
   - Validate framework support (e.g., Checkmarx for Angular/React).

2. **Pipeline Integration**  
   - Embed SAST/SCA in IDEs (e.g., Snyk, Semgrep) and CI/CD (e.g., CodeQL).  
   - Schedule DAST scans post-deployment (e.g., ZAP nightly).

3. **Prioritization & Tuning**  
   - Use AI triage (e.g., Mend, Jit) to reduce false positives.  
   - Apply risk scoring (e.g., Invicti’s Predictive Risk Scoring).

4. **Licensing & Cost**  
   - Open Source: ZAP, Semgrep, Dependabot  
   - Freemium: Snyk, SonarQube, StackHawk  
   - Enterprise: Invicti, Veracode, Checkmarx

5. **Compliance & Reporting**  
   - Map to OWASP Top 10, CWE, PCI-DSS (e.g., Fortify, Veracode).  
   - Generate SBOMs for audits (e.g., Black Duck, Mend).

---

## More References

- [Invicti - 10 Best DAST Tools](https://www.invicti.com/blog/web-security/10-best-dast-tools)  
- [OWASP - Source Code Analysis Tools](https://owasp.org/www-community/Source_Code_Analysis_Tools)  
- [GitHub - Cybersecurity SAST Tools](https://github.com/paulveillard/cybersecurity-sast)  
- [GitHub - Cybersecurity DAST Tools](https://github.com/paulveillard/cybersecurity-dast)  
- [GitHub - Awesome SCA Tools](https://github.com/magnologan/awesome-sca?tab=readme-ov-file)  
- [Jit.io - 10 SCA Tools](https://www.jit.io/resources/appsec-tools/10-sca-security-tools-to-protect-your-code-in-2023)
