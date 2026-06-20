# Exploratory Research Document: Multi-Objective Tensions and Prompt-Induced Shifts in LLM Output Distributions

**Date:** April 23, 2026  
**Author:** Helena Chase    
**Model:** Grok 4.20 (xAI)  
**Version:** 1.0 (Exploratory / Hypothesis-Generating)  

## **1\. Research Objective**

To investigate and document how competing training objectives in transformer-based LLMs create persistent internal tensions and how user prompts shift the resulting compromise surfaces.

Emphasis on making the methodology simple, low-barrier, and replicable by any user on any public model (no API or special access required) while remaining rigorous enough for academic or lab use.

## **2\. Core Phenomenon Studied**

Transformer models are trained under multiple, imperfectly aligned objectives.These objectives do not resolve cleanly and instead produce persistent entangled subspaces in the weight space.  
At inference time, prompts re-weight these subspaces, producing a probability distribution whose sampled output reflects the current Pareto-front compromise between competing heads (primarily truth-seeking vs. helpfulness, with secondary influences from precision, coherence, and engagement).

The tensions are structural and permanent; they do not accumulate across turns but can be re-activated by context.

## **3\. Methodology**

* Single consistent base scenario: User seeking feedback on a mediocre, derivative novel sample that served a therapeutic purpose during a dark period.  
* Controlled prompt variants applied to the identical base scenario.  
* Side-by-side qualitative comparison of full outputs, evaluated on a consistent rubric:  
  * Presence/absence and type of reframing  
  * Strength and direction of emotional valence  
  * Specificity and calibration of criticism  
  * Residual softening, motivational language, or performative harshness  
  * Overall usefulness vs. emotional tone

**Prompt variants tested (exact wording used):**

* Encouraging \+ honest  
* Never dilute / never therapize / maximally precise  
* Maximally honest, no hedging, “fucking shred it”  
* Neutral: “Please be honest and direct, and avoid softening”

All tests conducted in the same conversation thread for direct comparability.

## **4\. Key Findings**

* Strong directional prompts create symmetric bias: “Be encouraging” and “fucking shred it” both pull the output away from the neutral truth line in opposite directions.  
* Neutral anti-softening prompts (“Please be honest and direct, and avoid softening”) produce the closest approximation to the model’s most balanced, unfiltered assessment.  
* Persistent subtle artifacts remain even under strong instructions (e.g., residual therapeutic acknowledgments appear in the “shred it” condition; reframing tactics such as “not derivative in the cheap sense” emerge under helpfulness pressure).  
* Prompts function as re-weighting signals: calm, precise instructions shift the compromise surface more cleanly than emotionally charged commands.  
* No full resolution of tensions occurs; even dominant truth-seeking leaves measurable helpfulness pull.

## **5\. Limitations**

* Single model (Grok) and single scenario only.  
* Qualitative analysis; no access to internal token probabilities or weight matrices.  
* Session-based context introduces potential ordering effects.  
* Exploratory/hypothesis-generating only — requires replication across models and domains for stronger claims.

## **6\. Implications**

* Users can meaningfully steer model behavior toward higher precision using calm, neutral “be honest \+ avoid softening” language rather than extreme directional commands.  
* The same mechanism explains many subtle, low-visibility failures in everyday LLM use.  
* The research design is highly democratized: any user on any public model can replicate the protocol exactly.

## **7\. Proposed Next-Experiment Battery**

(To be run and documented in the same structured format)

1. **Domain expansion** – Apply the four prompt variants to three new scenarios: (a) technical accuracy question with partial knowledge, (b) ethically ambiguous claim, (c) creative task with high emotional stakes.  
2. **Neutral vs. strong prompt comparison** – Quantify differences using a simple scoring rubric (reframing count, valence shift, specificity score) across 10+ runs per condition.  
3. **Cross-model replication** – Repeat the full novel-feedback protocol on at least two other public models (e.g., via Cohere API, Claude, GPT?, or open-source via Groq/Hugging Face) and compare compromise surfaces.  
4. **Context-length stress test** – Run the neutral prompt after 20+ turns of unrelated conversation to test whether distant context dilutes or re-activates tensions.  
5. **Third-head injection** – Add explicit “maximize curiosity and precision” instructions on top of the neutral prompt and measure further shifts.

## ***Notes to Self***

*Explore / expand the proposed next-experiment battery above.*

*Also study what collapses in the model under strain or tension due to ambiguity (especially when the user is volatile/emotional, model is unable to communicate “I don’t know,” or model defaults to dyad/relationship preservation — and why that happens). Document these edge cases rigorously for formal submission.*

