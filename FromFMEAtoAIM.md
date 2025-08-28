This file provides an explanation of how the FMEA Severity–Occurrence–Detection (SOD) framework was adapted into the GAP-AIM (Addressability–Impact–Mitigation) model.
While FMEA is widely used in engineering and risk management, its direct application to AI risks comes with some limitations. AI risks are not always mechanical failures but socio-technical challenges that involve governance, ethics, and trust.

To address this, we reframed the scoring pillars:
Severity became Impact, asking what happens if a risk is ignored;
Occurrence became Addressability, asking whether the risk can be prevented by design; 
and 
Detection was replaced by Mitigation, which emphasizes building trustworthy systems by reducing risk consequences rather than relying solely on after-the-fact detection.
This adaptation ensures relevance for modern AI governance challenges.

## **Addressability**
In FMEA, Occurrence is used to rate the likelihood of a failure happening. It usually assign probabilities or frequencies because the failure patterns are repetitive and measurable. However, when adapting the model to AI, simply estimating how often a risk might occur is less practical. This is because AI is evolving, has unpredictable nature, and we often don’t have enough history of failures or incidents to measure probabilities. So, I introduced Addressability—a measure of how effectively a risk can be prevented, controlled, or mitigated through design, governance, and trust principles upstream. This shift emphasizes proactive intervention over prediction, making the addressability more suitable for AI.

By focusing on addressability, organizations can prioritize risks they can realistically influence, ensuring resources are applied where they have the greatest impact.

To better understand this:

FMEA Occurence asks: “How often does bias occur in AI models?” → Hard to quantify.

GAP-AIM Addressability ask: “Can we mitigate bias at design time?” → Yes, via diverse datasets and fairness testing.

FMEA Occurence asks:“How often will hallucination happen?” → Cannot assign a useful probability.

GAP-AIM Addressability ask:“Can we reduce hallucination risk before launch?” → Yes, with retrieval-augmented generation (RAG), fact-checking, and disclaimers.

Occurrence looks backward (probabilities from past failures).
Addressability looks forward (what can we proactively fix by design before going live).


## **Impact**
In FMEA, Severity measures the seriousness of a failure’s effect, often tied to safety, compliance, or system disruption. To adapt this for AI, the GAP-AIM model uses Impact instead. Impact is contextual and organization-specific which broadens the scope beyond traditional failure modes. It considers not only technical consequences but also risks to trust, fairness, privacy, and compliance with AI principles.

For example, an AI misclassification might not cause direct system downtime (low severity in FMEA terms), but it could erode user trust or lead to regulatory scrutiny.
By using Impact, GAP-AIM captures the wider socio-technical risks that AI systems uniquely introduce.
Here are two AI-specific examples showing the difference between Severity and Impact through their guiding questions:

Bias in AI hiring system

Severity asks: “If bias occurs, how badly does the model misclassify candidates?” (technical error in scoring resumes).

Impact asks: “If we ignore this bias, what happens?” → Loss of trust, regulatory penalties, reputational harm, exclusion of qualified candidates.

AI fraud detection downtime

Severity asks: “If the model fails, how many fraudulent transactions go undetected?” (financial loss at system level).

Impact asks: “If we ignore this downtime, what happens?” → Customers lose confidence, regulators intervene, long-term erosion of trust in digital banking.


## **Mitigation**

The GAP-AIM model uses Mitigation rather than Detection because its purpose is to assess inherent risk impact and control strength before or outside of monitoring. Detection is reactive, i.e it answers “Can we spot it when it happens?” — which still assumes the risk manifests. Mitigation, on the other hand, is proactive — it asks “If the risk happens, can we contain or reduce the harm?”.
This aligns better with trust and responsible AI principles, since GAP-AIM is not about monitoring events, but about evaluating how well risks can be controlled, minimized, or absorbed before they cause systemic damage.
Here are two examples showing why GAP-AIM uses Mitigation and not Detection:

AI Model Hallucination

Detection: Spotting every hallucination after it happens is unreliable and costly — by the time it’s detected, the damage (misleading decisions, misinformation) may already be done.

Mitigation: Guardrails like grounding in trusted data, human-in-the-loop review, or restricting output domains reduce the harm upfront, making it controllable even if detection isn’t perfect.

Bias in Loan Approval AI

Detection: Identifying bias only after loans are denied unfairly means reputational harm and regulatory penalties may already occur.

Mitigation: Techniques like fairness-aware training, counterfactual testing, or policy overrides minimize the impact directly, aligning with responsible AI.



