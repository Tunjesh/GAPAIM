# GAP-AIM
GAP-AIM (Governance Assessment & Prioritization – Addressability, Impact, Mitigation) is a quantitative AI governance and risk prioritization model inspired by the [Failure Mode and Effects Analysis (FMEA)](https://asq.org/quality-resources/fmea) method. It adapts the structured scoring logic of FMEA to AI governance, focusing on the practical assessment of ethical AI principles such as fairness, transparency, privacy, accountability, and security. 

GAP-AIM calculates a multiplicative score to rank AI risks based on how **addressable** they are by design, their potential **impact**, and the strength of **mitigation** measures in place. The model complements [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework), [UNESCO AI Ethics Recommendation](https://unesdoc.unesco.org/ark:/48223/pf0000381137), [OECD AI Principles](https://oecd.ai/en/ai-principles), and [ISO/IEC 42001](https://www.iso.org/standard/81230.html) by providing organizations with a complementary, visual, and actionable way to prioritize AI risks and communicate risk posture to both technical and non-technical stakeholders through traffic-light-style visuals.

GAP-AIM acts as a governance engine — providing structure to measure, prioritize and communicate ethical AI principles.
It help organizations to:

•	Identify potential risk senerios for each AI governance principle (e.g., accountability, bias, privacy, security, etc).

•	Assess contextual risk senerio(s) via three dimensions - (Addressability, Impact and Mitigation)
  
•	Visualize results using a traffic-light scale (Red/Yellow/Green) to make risk posture instantly clear to both technical and non-technical stakeholders.

## Why GAP-AIM?
While frameworks like NIST AI RMF,OECD, and ISO/IEC 42001, establish key principles and risk frameworks, they do not include a specific scoring system. GAP-AIM bridges this gap by introducing a **lightweight, quantitative model** inspired by **FMEA** and communicated through a **traffic light analogy** for clarity.

### **Relationship to Existing Frameworks**

NIST AI RMF
: Provides categories for trustworthy AI but does not prescribe quantitative scoring. GAP-AIM operationalizes prioritization.

UNESCO RAM
: Emphasizes human rights and global equity; GAP-AIM translates these into addressable and measurable risks.

OECD AI Principles
: Defines values like robustness and accountability; GAP-AIM enables scoring of gaps in implementation.

ISO/IEC 42001
: Establishes an AI management system standard; GAP-AIM complements it with practical scoring and visualization.

## The principles.
OECD, NIST, ISO 42001, EU AI Act all aim to solve the same core risks to people and societal wellbeing (bias, opacity, safety, accountability, privacy) and therefore gravitate to similar principles rooted in human rights and rule‑of‑law traditions.
OECD’s principles set a high-level baseline, while NIST’s AI RMF operationalizes them across the AI lifecycle. ISO 42001 standard translate them into auditable management and risk processes, while the EU AI Act makes these high‑level AI principles operational and enforceable within the E. U.S. executive orders (2025) supports the same principles to build trust and consistency.
For the purpose of this tool, the priciples have been grouped into five:

**Privacy & data protection:** Collect only necessary data, secure it, and use it lawfully. Ensure consent/notice, retention limits, and data subject rights.

**Accountability & oversight:** Name an owner for every AI system and decision and keep humans in the loop for consequential decisions. 

**Safety & security:** Design for predictable, resilient, cyber‑secure operation. Test for failures, adversarial inputs, model drift, and incident response. 

**Transparency & explainability:** Disclose when AI is used, what data matters, and provide understandable reasons for outcomes. 

**Fairness & inclusion:** Detect and mitigate bias across data, models, and outcomes. Define fairness metrics, monitor disparities, and remediate harms. 

## The Three Dimensions

GAP-AIM 

1. **A — Addressability**  

This dimension looks at how feasible it is to prevent or eliminate the risk before it occurs/ or deployed to production. Addressability emphasizes prevention over remediation. It assesses whether a risk can be addressed upstream through design choices, testing, and governance. It ranges from easy to hard. This maps to the occurence dimension of FMEA. 

 - Easy: We can embed the solution upstream. E.g with better training data selection, choice of algorithm, etc.
 - Hard: No reliable way to address the risk in time.

Example: A financial AI system risks discriminatory lending. By addressing it upstream — balancing datasets, applying fairness constraints, and auditing decisions — the organization demonstrates ethical responsibility and preserves trust before deployment.

2. **I — Impact**

This  dimension asks the question - What is the harm if we ignore it?.  How minimal is the harm if we ignore it?. If the consequences are minimal to negligible, then the impact is low. It like measuring the consequence of inaction and  It forces stakeholders to confront the real-world harms that can occur if an AI risk is overlooked.

- Low:  If the risk occurs, and we ignore it, and its consequences are minimal to negligible.
- High:  If the risk occurs and we ignore it, and the effect is severe
Example: An AI diagnostic tool trained on unbalanced data misdiagnoses minority patients. If ignored, the harm includes patient injury, malpractice suits, and public distrust in AI-enabled healthcare..

3. **M — Mitigation**

This is the dimension that looks at how effectively the risk senerio can be monitored, contained, or corrected once the AI is already running. It is our ability to detect, contain, and correct the issue after deployment, before it causes serious harm. It reflects how effectively harm can be detected, contained, and remediated in real time. This maps to the detect function of FMEA.

 - Matured: There is vailability of monitoring tools, audit trails.
 - Immature: There is no or minimal control in place.

Example:
In a well-designed AI, model drift can occur. If this can be detected and mitigated quickly in production, then mitigation is mature.
If no monitoring in place; issues would be detected only after significant harm occurs.


**Scoring and Prioritization**
Score  each dimension.
GAP-AIM uses three multipliers (Addressability, Impact, Mitigation) → simple, scalable, easy to communicate.
Scores  ranging from 1 to 3, is assigned for each dimension,
Addressability → 3 (Easy) to 1 (Hard)
Impact → 3 (Low) to 1 (High)
Mitigation → 3 (Mature) to 1 (Immature)

**Calculate Risk Score**.
The Risk score ( AIM Score is calculated by multipling the assignned scores of each dimension) - Similar to FMEA’s Risk Priority Number (RPN), but using AIM scoring.
This lets you rank risk senerios across all principles, not just security.

**GAP AIM Scoring Methodology**

The GAP AIM scoring model evaluates risks by assigning scores derived from a structured mathematical framework. The foundation of this approach is based on the principle of equivalence classes under multiplicative scoring, where multiple combinations of contributing factors may map to the same overall score.

To illustrate, consider three evaluation dimensions A,B,C, each with possible values {1,2,3}. The Cartesian product of these sets yields 3×3×3=27 possible combinations.
However, many of these combinations produce the same outcome when multiplied. For example:

(3,1,1), (1,3,1), and (1,1,3) all yield a product of 3.

(3,1,2), (2,3,1), and (2,1,3) all yield a product of 6.

By grouping such results, we find only 10 unique outcome scores, (1,2,3 4 ,6,8,9,12,18,27) ranging from 1 through 27.

This deduplication follows the logic of prime factorization and equivalence partitioning: while different inputs may look distinct, if their products are the same, they represent the same “AIM score” in our model. This gives us a condensed, meaningful scoring scale that avoids over-counting redundant combinations.

**Risk Color Banding**

To interpret these numeric scores, we apply color bands to communicate urgency and prioritization. The current bands are:

* 🔴 **Red (High Concern)** (1–4): Represents the most critical risks. Scores in this range reflect conditions with  Significant impact with limited mitigations.. These scenarios require urgent attention.

* 🟡 **Yellow (Moderate Concern)** (5–17): Represents moderate risks. The spread reflects situations where risk factors compound but are still within a controllable threshold. These should be monitored and addressed according to organizational priorities.

* 🟢 **Green (Low Concern)** (18–27): Represents lower risks. Residual risk is understood and managed. Scores here reflect either high resilience or low combined impact from contributing factors.
 
Flexibility and Risk Appetite

It is important to note that these thresholds are not absolute. The chosen bands (1–4, 5–17, 18–27) are based on a balance of clarity and practicality but may be adjusted depending on the risk appetite of the organization. For instance, highly regulated industries may set a tighter boundary around “Red,” while more agile environments may tolerate higher variability in the “Yellow” range.

The flexibility of this scale ensures that the GAP AIM scoring model can be tailored to align with organizational strategy, regulatory requirements, and governance standards.

#**Why GAP-AIM Uses a 1–3 Scoring Scale**

Many established risk assessment tools, such as FMEA, use a 1–10 scale to rate severity, occurrence, and detection. 
While this offers fine-grained precision, it may introduce complexity, inconsistency, and “false accuracy” when used in cross-functional AI governance contexts.

GAP-AIM is designed for executives, regulators, and multidisciplinary teams, where speed, clarity, and consensus are critical.
A 1–3 scale offers three key advantages:
 - Simplicity & Alignment: Maps directly to the traffic-light metaphor (1 = Red/High, 2 = Orange/Medium, 3 = Green/Low) for instant, non-technical communication.
 - Consistency Across Raters: Fewer scoring options reduce subjectivity and debate, improving scoring reliability across diverse teams/assessors/evaluators.
 - Actionable Prioritization: Encourages decision-makers to focus on clear risk bands rather than debating marginal score differences.
By sacrificing some granularity, GAP-AIM gains usability and decision-readiness, enabling AI risk assessments to move beyond theoretical scoring into operational governance actions.
Theoretical underpinnings

| Concept                             | How it supports GAP-AIM grouping                                                                         |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **Ordinal scaling theory**          | Ensures the 1–3 per factor scale preserves ranking without implying equal distance between scores.       |
| **Multiplicative risk scoring**     | Recognized in FMEA RPN, cybersecurity CVSS (Base Score factors multiply), and safety engineering.        |
| **Weakest link principle**          | One poor score can disproportionately lower the total, aligning with real-world risk amplification.      |
| **Human factors / decision theory** | Executives respond faster to 3-band categorizations than to granular numbers.                            |
| **Signal detection theory**         | Color-coded bands increase detection and correct classification of priority levels under cognitive load. |



## Getting Started

1. **Understand the AIM Scoring Model** – Review how Addressability, Impact, and Mitigation interact.
2. **Identify risk senerios** and effect for  each applicable principle
3. **Apply GAP-AIM to a Use Case** – Score risks for an AI system against global principles.
4. **Visualize Results** – Use the traffic light model to communicate priorities across technical and governance teams.

**Steps**
Understand Context per Principle
For each AI governance principle (e.g., Accountability, Bias, Privacy, Security, Fairness), you define:
Risk Senerio → What could go wrong in real deployment?
Associated AIM → The Addressability, Impact, and Mitigation aspects tied to that failure.



# **How GAP-AIM maps to NIST AI RMF**
NIST AI RMF is a framework - conceptual guidance on what to do.
GAP-AIM is a scoring and prioritization model that can be used inside RMF processes to help make certain steps more data-driven and visually actionable.

The NIST AI RMF is organized into 4 core functions and GAP-AIM fits inside them:
NIST AI RMF Function	How GAP-AIM Fits
Govern	Uses RMF’s principles (accountability, fairness, transparency, etc.) as the evaluation scope.
Map	Identifies potential risk senerios and effects based on usecase/system context.
Measure	Quantifies risk using Addressability, Impact, Mitigation scoring.
Manage	Prioritizes remediation based on AIM scores and focuses resources on low score risk senerio.


## Disclaimer

GAP-AIM is an **early-stage research model**. It is not a regulatory framework, certification, or compliance tool. It is designed to **complement existing AI governance frameworks** by making risk more **measurable and actionable**.

## Feedback
Kindly send feedback to info@theffrentials.com .
________________________________________
📜 License & Attribution
This framework is free to use.
________________________________________
