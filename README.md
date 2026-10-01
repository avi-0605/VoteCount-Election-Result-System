# VoteCount — Election Result Dissemination System

**Software Development — Case Study No. 50**

VoteCount is a secure election-result dissemination system designed for a State Election Commission. It collects vote-count data from **4,100 counting tables across 70 constituencies**, verifies the results through supervisors and Returning Officers, and publishes only verified results to the public portal.

## 📌 Project Overview

The system is designed to handle heavy counting-day traffic while maintaining the **accuracy, integrity, security, and traceability** of published election results.

### Key Scale

* **4,100** counting tables
* **70** constituencies
* **240,000** concurrent public viewers
* **18,000 requests/second** expected peak load
* Results published every **20 minutes**
* Stress testing target: **360,000 concurrent viewers**
* Stress testing target: **27,000 requests/second**

## 🔐 Core Verification Rule

An unverified result must never be published.

```text
Counting Table
      ↓
Result Entry
      ↓
Input Validation
      ↓
Supervisor Check
      ↓
Returning Officer Verification
      ↓
Digital Signature Validation
      ↓
Central Verification
      ↓
Publication Gate
      ↓
Static Result Generation
      ↓
CDN / Cache
      ↓
Public Portal
```

A result is published only when:

```text
Result Status = VERIFIED
AND
Digital Signature = VALID
AND
Validation Rules = PASSED
```

Otherwise, the result is rejected or held for correction.

## 🏗️ System Features

* Table-wise result data entry
* Input and arithmetic validation
* Supervisor verification
* Returning Officer verification
* PKI-based digital signatures
* Publication eligibility gate
* Static JSON/HTML result generation
* CDN-based result delivery
* Audit logging with timestamps and SHA-256 hashes
* Correction and re-verification workflow
* Role-based access control
* Multi-factor authentication
* Result history
* Offline buffering during network outages

## 📊 Project Estimation

The project is estimated using the **Basic COCOMO Model — Semi-detached mode**.

| Parameter            |                Value |
| -------------------- | -------------------: |
| Project Size         |              27 KLOC |
| Estimated Effort     | 120.30 Person-Months |
| Estimated Duration   |         13.37 Months |
| Average Team Size    |            9 Persons |
| Available Window     |             7 Months |
| Budget at Completion |          ₹1.05 Crore |

The COCOMO estimate exceeds the available 7-month window, so the project requires **parallel development, early testing, resource concentration, and strict scope management**.

## 📈 Earned Value Status

At Month 4:

| Metric            |     Result |
| ----------------- | ---------: |
| Schedule Variance |  -₹0.09 Cr |
| Cost Variance     |  -₹0.15 Cr |
| SPI               |       0.85 |
| CPI               |      0.773 |
| EAC               |  ₹1.359 Cr |
| VAC               | -₹0.309 Cr |
| TCPI              |      1.385 |

The project is currently behind schedule and over budget according to the EVM analysis.

## 🧪 Testing Strategy

The system includes:

* Functional testing
* Verification-chain testing
* Digital-signature validation
* Invalid/tampered result testing
* Load testing
* Stress testing
* Spike testing
* Soak testing
* Recovery testing
* Full dress rehearsal

### Load Testing

The system is tested at **1.5× the expected peak load**:

* Expected: 240,000 concurrent viewers
* Stress: 360,000 concurrent viewers
* Expected: 18,000 requests/sec
* Stress: 27,000 requests/sec

## ⚠️ Risk Management

Major risks include:

| Risk                            | Probability | Impact | Exposure |
| ------------------------------- | ----------: | -----: | -------: |
| Portal collapse under load      |         0.5 |      9 |      4.5 |
| Counting table data-entry error |         0.6 |      7 |      4.2 |
| Network outage                  |         0.4 |      6 |      2.4 |
| Unverified figure publication   |         0.2 |     10 |      2.0 |

Risk mitigation includes load testing, validation controls, verification gates, redundancy, offline buffering, monitoring, and a **manual fallback process**.

## 🗂️ Project Management

The project plan includes:

* Work Breakdown Structure (WBS)
* 7-month Gantt schedule
* Resource allocation
* Resource histogram
* Risk management
* Testing and rehearsal
* Scope reduction strategy

If schedule pressure occurs, optional features such as advanced dashboards, analytics, and additional visualizations can be simplified or deferred.

Core features such as **verification, digital signatures, security, auditability, traceability, and result publication cannot be removed**.

## 📁 Project Structure

```text
VoteCount-Election-Result-System/
│
├── VoteCount_SEPM_CaseStudy_Report.pdf
│
├── figures/
│   ├── activity_diagram.png
│   ├── deployment_diagram.png
│   ├── evm_chart.png
│   ├── gantt_chart.png
│   ├── load_testing_levels.png
│   ├── resource_allocation.png
│   ├── resource_histogram.png
│   ├── result_verification_flow.png
│   ├── risk_matrix.png
│   ├── scope_pyramid.png
│   ├── state_diagram.png
│   ├── system_architecture.png
│   └── verification_chain.png
│
└── README.md
```

## 🎓 Academic Information

**Student:** Aavani Perumbessi
**Roll No.:** 150096724059
**Programme:** B.Tech CSE
**Semester:** III
**Subject:** Software Development
**Case Study:** 50 — VoteCount

## 📄 Documentation

The complete case study report contains:

1. Project Estimation and Status
2. Software Requirements Specification
3. System Design
4. Testing and Rehearsal Plan
5. Risk Management
6. Project Management Plan
7. Conclusion and References

---

**VoteCount — Secure. Verified. Traceable.**
