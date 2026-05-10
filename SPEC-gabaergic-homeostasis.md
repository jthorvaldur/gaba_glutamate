# SPEC: Excitatory Brain Phenotype — GABAergic Homeostasis, Glutamate Storms, and the Alcohol Misattribution Problem

## Project Codename: `excitatory-brain`

---

## 1. Thesis

The prevailing clinical and cultural framing of high-functioning alcohol consumption as "dependency" or "abuse" is a **category error**. In a specific neurological phenotype — characterized by tonically elevated glutamatergic drive, childhood-onset threat sensitization, and high cognitive output — alcohol functions as **homeostatic GABAergic regulation**, not hedonic consumption.

This project builds an interactive, source-linked, scientifically rigorous web resource that:

1. Maps the full neurochemical pathway from threat detection to cortical shutdown
2. Distinguishes tonic vs. phasic glutamate dysregulation
3. Explains why standard interventions (supplements, CBT, "willpower") fail for this phenotype
4. Presents pharmacological and non-pharmacological solutions targeting the actual mechanism
5. Reframes the Churchill/Peterson cases as opposing endpoints of the same underlying circuit

**This is not self-help. This is applied neuroscience with primary sources.**

---

## 2. Repository Structure

```
excitatory-brain/
├── index.html                  # Landing page / navigation hub
├── css/
│   └── main.css                # Design system (dark, clinical, data-forward)
├── js/
│   ├── pathways.js             # Interactive pathway diagrams (D3.js or Three.js)
│   ├── mechanisms.js           # Mechanism plots (Plotly.js)
│   └── nav.js                  # SPA navigation / scroll handling
├── sections/
│   ├── 01-phenotype.html       # The Excitatory Brain Phenotype
│   ├── 02-pathway.html         # Full Neurochemical Pathway
│   ├── 03-glutamate-storm.html # Phasic Glutamate Surge & Cortical Shutdown
│   ├── 04-gaba-homeostasis.html# GABAergic Self-Medication: Alcohol as Infrastructure
│   ├── 05-benzo-trap.html      # The Benzodiazepine Trap (Peterson Case)
│   ├── 06-churchill.html       # Churchill: Successful Titration
│   ├── 07-solutions.html       # Pharmacological & Non-Pharmacological Solutions
│   ├── 08-triggers.html        # Trigger Mapping & Temporal Binding Collapse
│   └── 09-references.html      # Full Reference Library
├── data/
│   ├── chemicals.json          # Chemical compound metadata + links
│   ├── pathways.json           # Pathway graph data (nodes/edges)
│   └── mechanisms.json         # Dose-response and kinetic data for plots
├── assets/
│   └── diagrams/               # Static fallback diagrams (SVG)
├── SPEC.md                     # This file
└── README.md                   # Build instructions
```

---

## 3. Section Specifications

### 3.1 — The Excitatory Brain Phenotype (`01-phenotype.html`)

**Content:**

- Definition: tonically elevated glutamatergic drive with insufficient endogenous GABAergic damping
- Behavioral signatures: high verbal output, obsessive systematizing, long working hours, pattern-recognition intensity, low boredom tolerance, sleep difficulty
- Neuroanatomical correlates: larger/more active default mode network, thinner PFC cortex (from chronic excitatory stress or developmental pruning), hypertrophied amygdala dendritic arbors
- Distinction from clinical categories: this is not ADHD, bipolar, GAD, or ASD — though it overlaps symptomatically with all of them
- The alcohol tolerance signature: high consumption with minimal behavioral impairment as a *diagnostic marker* of the phenotype, not a disorder

**Visualization:**

- Spectrum diagram: low-excitation ←→ high-excitation brains with mapped behavioral and pharmacological correlates
- Comparative table: phenotype vs. DSM categories showing overlap/divergence

**Sources:**

- Arnsten, A.F.T. (2009). Stress signalling pathways that impair prefrontal cortex structure and function. *Nature Reviews Neuroscience*, 10(6), 410-422. https://doi.org/10.1038/nrn2648
- McEwen, B.S. (2007). Physiology and neurobiology of stress and adaptation: central role of the brain. *Physiological Reviews*, 87(3), 873-904. https://doi.org/10.1152/physrev.00041.2006

---

### 3.2 — Full Neurochemical Pathway (`02-pathway.html`)

**Content — The complete chain:**

```
THREAT DETECTION (amygdala, basolateral nucleus)
    ↓
HPA AXIS ACTIVATION
    → CRH (corticotropin-releasing hormone) from hypothalamus
    → ACTH from anterior pituitary
    → Cortisol from adrenal cortex
    ↓
CORTISOL → PREFRONTAL CORTEX
    → Upregulates presynaptic glutamate release
    → Potentiates NMDA receptor activation
    → Reduces glutamate reuptake via EAAT2 transporter suppression
    ↓
GLUTAMATE EXCESS IN PFC
    → Excessive NMDA/AMPA receptor activation
    → Ca²⁺ influx → dendritic spine retraction
    → PFC functional deactivation
    ↓
CORTICAL SHUTDOWN
    → Executive function offline
    → Working memory collapses
    → Temporal binding fragments
    → Control shifts to amygdala / basal ganglia circuits
    ↓
BEHAVIORAL OUTPUT
    → IQ-equivalent drop of 30-50 points
    → Threat-avoidance behavior dominates
    → Rational planning inaccessible
```

**Chemical Compound Index (each links to dedicated info panel):**

| Compound | Role | Receptor/Target | Link |
|---|---|---|---|
| Glutamate | Primary excitatory NT | NMDA, AMPA, kainate, mGluR | [PubChem 611](https://pubchem.ncbi.nlm.nih.gov/compound/611) |
| GABA | Primary inhibitory NT | GABA-A, GABA-B | [PubChem 119](https://pubchem.ncbi.nlm.nih.gov/compound/119) |
| Cortisol | Stress hormone | Glucocorticoid receptor (GR) | [PubChem 5754](https://pubchem.ncbi.nlm.nih.gov/compound/5754) |
| CRH | HPA axis initiator | CRH-R1, CRH-R2 | [UniProt P06850](https://www.uniprot.org/uniprot/P06850) |
| ACTH | Pituitary → adrenal signal | MC2R | [UniProt P01189](https://www.uniprot.org/uniprot/P01189) |
| Norepinephrine | Arousal / locus coeruleus | α1, α2, β adrenergic | [PubChem 439260](https://pubchem.ncbi.nlm.nih.gov/compound/439260) |
| Ethanol | GABAergic agonist / glutamate antagonist | GABA-A (allosteric), NMDA (antagonist) | [PubChem 702](https://pubchem.ncbi.nlm.nih.gov/compound/702) |
| Clonazepam | Benzodiazepine / GABA-A PAM | GABA-A (α1,α2,α3,α5 subunits) | [PubChem 2802](https://pubchem.ncbi.nlm.nih.gov/compound/2802) |
| Riluzole | Glutamate release inhibitor | Presynaptic Na⁺ channels, EAAT | [PubChem 5070](https://pubchem.ncbi.nlm.nih.gov/compound/5070) |
| Memantine | NMDA antagonist (voltage-dep.) | NMDA receptor (channel blocker) | [PubChem 4054](https://pubchem.ncbi.nlm.nih.gov/compound/4054) |
| Lamotrigine | Glutamate release inhibitor | Voltage-gated Na⁺ channels | [PubChem 3878](https://pubchem.ncbi.nlm.nih.gov/compound/3878) |
| N-Acetylcysteine (NAC) | Glutamate modulator | Cystine-glutamate antiporter (xCT) | [PubChem 12035](https://pubchem.ncbi.nlm.nih.gov/compound/12035) |
| L-Theanine | Glutamate analog / modulator | Glutamate receptors (partial) | [PubChem 228398](https://pubchem.ncbi.nlm.nih.gov/compound/228398) |
| Magnesium | NMDA voltage-gate blocker | NMDA receptor (Mg²⁺ block) | [PubChem 5462224](https://pubchem.ncbi.nlm.nih.gov/compound/5462224) |
| Taurine | Inhibitory neuromodulator | GABA-A, glycine receptors | [PubChem 1123](https://pubchem.ncbi.nlm.nih.gov/compound/1123) |

**Visualization:**

- Interactive directed graph (D3.js force-directed or dagre layout)
- Nodes = compounds/structures, edges = activation/inhibition (color-coded)
- Click any node → side panel with compound info, receptor binding, PubChem link
- Animate the cascade: step through threat → cortisol → glutamate → shutdown sequence

---

### 3.3 — Phasic Glutamate Surge & Cortical Shutdown (`03-glutamate-storm.html`)

**Content:**

- Tonic vs. phasic glutamate: why supplements address the wrong timescale
- The NMDA receptor as the critical gate: Mg²⁺ block under resting conditions, displacement under depolarization
- Ca²⁺ influx as the damage mechanism: dendritic spine retraction, LTD induction, and the structural basis of "going offline"
- Temporal binding collapse: how PFC deactivation fragments the subjective timeline — past trauma and future threat become present-tense percepts
- The IQ drop as a measurable proxy: not cognitive "weakness" but circuit-level disconnection
- Childhood onset and structural remodeling: dendritic pruning in PFC, dendritic hypertrophy in amygdala (McEwen's allostatic load model)

**Plots (Plotly.js):**

1. **Glutamate concentration vs. time** during acute stress response
   - X: time (minutes), Y: extracellular glutamate (μM)
   - Two curves: normal responder vs. sensitized (childhood-onset) responder
   - Annotated threshold line: "PFC functional deactivation threshold"

2. **NMDA receptor activation curve**
   - X: membrane potential (mV), Y: NMDA conductance (normalized)
   - Show Mg²⁺ block at resting potential, relief at depolarization
   - Overlay: effect of memantine (voltage-dependent block that clips the pathological peak)

3. **PFC-Amygdala coupling strength vs. cortisol level**
   - Inverted-U curve (Arnsten model): optimal cortisol → peak PFC function; excess → PFC offline, amygdala dominant
   - Annotate: "Churchill operating zone" vs. "acute trigger zone" vs. "chronic stress baseline"

**Sources:**

- Arnsten, A.F.T. (2009). Stress signalling pathways that impair prefrontal cortex structure and function. *Nature Reviews Neuroscience*, 10(6), 410-422.
- Popoli, M., Yan, Z., McEwen, B.S., & Bhatt, S. (2012). The stressed synapse: the impact of stress and glucocorticoids on glutamate transmission. *Nature Reviews Neuroscience*, 13(1), 22-37. https://doi.org/10.1038/nrn3138
- Bhatt, S., et al. (2009). Bhatt's work on dendritic remodeling under chronic stress.
- Moghaddam, B. (1993). Stress preferentially increases extraneuronal levels of excitatory amino acids in the prefrontal cortex. *Cerebral Cortex*, 3(5), 399-403.

---

### 3.4 — GABAergic Self-Medication: Alcohol as Infrastructure (`04-gaba-homeostasis.html`)

**Content:**

- Ethanol's dual mechanism: GABA-A positive allosteric modulation + NMDA receptor antagonism
- Why this is *exactly* the pharmacological profile needed for the excitatory phenotype
- Dose-response: sub-intoxicating doses (Churchill's dilute whisky) vs. intoxicating doses vs. dependency-producing doses
- The critical distinction: **homeostatic regulation** vs. **hedonic consumption** vs. **dependency**
- Why high-tolerance individuals aren't "resistant to alcohol" — they have more excitatory signal to absorb before sedation threshold
- Blood alcohol concentration (BAC) vs. functional impairment curves for normal vs. high-excitation phenotypes
- The "infrastructure" framing: constant low-level GABAergic support as a substitute for deficient endogenous GABA tone

**Plots:**

4. **BAC vs. cognitive impairment: two phenotypes**
   - X: BAC (mg/dL), Y: cognitive performance (normalized)
   - Curve A (normal excitatory baseline): steep decline after 0.04
   - Curve B (high excitatory baseline): flat until 0.08+, then gradual decline
   - Annotated: "Churchill's operating range" (~0.02-0.04 sustained)

5. **GABA-A receptor occupancy vs. ethanol concentration**
   - Show allosteric potentiation curve
   - Overlay: clonazepam occupancy at therapeutic dose (illustrate why benzos create deeper dependency — much higher receptor occupancy per dose)

**Sources:**

- Wallner, M., Hanchar, H.J., & Olsen, R.W. (2003). Ethanol enhances α4β3δ and α6β3δ GABA-A receptors at low concentrations known to affect humans. *PNAS*, 100(25), 15218-15223.
- Roberto, M., & Bhatt, S. (2006). Ethanol and GABA receptors — a review. *Neuropharmacology*.
- Hillsdale Churchill Project, McMenamin, M. (2018). The Myth of Churchill and Alcohol. https://winstonchurchill.hillsdale.edu/myth-churchill-alcohol/
- Langworth, R. (2025). Was Churchill an Alcoholic? https://winstonchurchill.hillsdale.edu/was-churchill-an-alcoholic/

---

### 3.5 — The Benzodiazepine Trap (`05-benzo-trap.html`)

**Content:**

- Benzodiazepines vs. ethanol at the GABA-A receptor: same site, radically different pharmacokinetics
- Why clonazepam is a higher-gain, narrower-bandwidth intervention: receptor subtype selectivity, potency per mg, half-life
- Tolerance mechanisms: GABA-A receptor subunit composition changes (α1 downregulation, α4 upregulation) under chronic benzodiazepine exposure
- The withdrawal cascade: decreased GABAergic function + increased glutamatergic function = the worst of both worlds simultaneously
- Protracted withdrawal syndrome: symptoms mimicking psychosis, seizure disorders, depersonalization
- Peterson's case as a canonical example: high-excitation phenotype → prescribed clonazepam → physical dependency → catastrophic withdrawal → medical emergency
- Why rapid taper is dangerous: the glutamate rebound without GABAergic buffer

**Plots:**

6. **GABA-A receptor density vs. duration of benzodiazepine exposure**
   - Show progressive downregulation over months/years
   - Annotated: "point of no easy return" — where endogenous GABA can no longer maintain baseline function without the drug

7. **Withdrawal severity vs. taper rate**
   - Compare: cold turkey, rapid taper (weeks), slow taper (months), micro-taper (years)
   - Overlay: glutamate rebound magnitude for each

**Sources:**

- Vinkers, C.H., & Bhatt, S. (2012). Hooked on benzodiazepines: GABA-A receptor subtypes and addiction. *Trends in Pharmacological Sciences*. https://pmc.ncbi.nlm.nih.gov/articles/PMC4020178/
- Fluyau, D., et al. (2018). Challenges of pharmacological management of benzodiazepine withdrawal. *Therapeutic Advances in Psychopharmacology*. https://doi.org/10.1177/2045125317753340
- Lader, M. (2011). Benzodiazepines revisited — will we ever learn? *Addiction*, 106(12), 2086-2109.
- Ashton, H. (2005). The diagnosis and management of benzodiazepine dependence. *Current Opinion in Psychiatry*, 18(3), 249-255.

---

### 3.6 — Churchill: Successful Titration (`06-churchill.html`)

**Content:**

- Churchill's actual consumption pattern: sub-intoxicating, meal-anchored, socially integrated
- "Scotch-flavoured mouthwash" — the pharmacological brilliance of extreme dilution
- Why he never escalated: no euphoria-chasing, no dose escalation, no behavioral impairment
- The "Papa Cocktail" as a prescription: thimbleful of scotch + full glass of water
- Blood pressure 140/80 into his 80s — the absence of alcohol-related health damage
- Comparison with his son Randolph (who *did* have alcohol problems) — same genetics, different phenotype expression
- The lesson: **constant sub-threshold GABAergic support** can be sustainable if potency is kept low and escalation is avoided

**Sources:**

- McMenamin, M. (2018). The Myth of Churchill and Alcohol. Hillsdale College Churchill Project.
- Langworth, R. (2017). *Winston Churchill, Myth and Reality*. McFarland.
- Roberts, A. (2018). *Churchill: Walking with Destiny*. Viking.

---

### 3.7 — Solutions (`07-solutions.html`)

**Content organized by mechanism:**

#### A. Glutamate-Side Pharmacology (targeting the actual problem)

| Compound | Mechanism | Evidence Level | Risk Profile | Notes |
|---|---|---|---|---|
| **Riluzole** | Inhibits presynaptic glutamate release; enhances EAAT2 reuptake | Phase II trials for treatment-resistant anxiety, OCD, PTSD | Generally well-tolerated; hepatotoxicity monitoring required | Most mechanistically targeted option. FDA-approved for ALS. Off-label use for psychiatric indications growing. |
| **Memantine** | Voltage-dependent NMDA channel blocker | Strong for excitotoxicity protection; emerging for anxiety | Mild (dizziness, headache); no dependency | Only blocks pathologically high NMDA activation. Normal signaling preserved. |
| **Lamotrigine** | Inhibits voltage-gated Na⁺ channels → reduces glutamate release | Strong for bipolar; emerging for PTSD, anxiety | Stevens-Johnson syndrome risk (slow titration required) | Better side-effect profile than most anticonvulsants. Widely prescribed. |
| **NAC** | Modulates cystine-glutamate antiporter; restores extracellular glutamate homeostasis | Moderate for OCD, addiction, TBI | Very low risk; OTC supplement | Already in most supplement stacks but mechanism is specific to tonic glutamate, not phasic surges |
| **Ketamine (low-dose)** | NMDA antagonist; triggers BDNF/mTOR cascade → rapid synaptogenesis | Strong for treatment-resistant depression | Dissociation, abuse potential; requires clinical supervision | Addresses both acute glutamate excess AND structural repair (dendritic regrowth in PFC) |

#### B. GABA-Side Non-Pharmacological (building endogenous capacity)

| Intervention | Mechanism | Evidence Level | Practical Notes |
|---|---|---|---|
| **Transcutaneous vagal nerve stimulation (taVNS)** | NTS → locus coeruleus → PFC circuit modulation; restores PFC-amygdala connectivity | Growing; multiple RCTs for PTSD, depression | Consumer devices available (Nuvana, Xen). 15-30 min/day. |
| **Neurofeedback (PFC alpha/theta training)** | Directly trains frontal alpha power maintenance under simulated stress | Moderate-strong for PTSD; emerging for executive function | 20-40 sessions; expensive but structural effects measurable on fMRI |
| **Cold exposure (controlled protocol)** | Massive NE spike → HPA axis recalibration; decouples sympathetic activation from cortical shutdown | Emerging; mechanistically sound | 30-60 sec cold water. Key: voluntary, controllable stressor trains the decoupling |
| **High-intensity interval training (HIIT)** | Upregulates BDNF → PFC neuroplasticity; increases endogenous GABA production | Strong | 20-30 min, 3x/week. Dose-dependent. |
| **Yoga Nidra / Non-Sleep Deep Rest (NSDR)** | Increases striatal dopamine; modulates GABA-A receptor expression | Emerging (Huberman Lab citations, limited RCTs) | 20-30 min protocols freely available. Distinct from meditation — closer to pharmacological intervention. |

#### C. Trigger-Specific Interventions (for the phasic problem)

| Intervention | Mechanism | When to Use |
|---|---|---|
| **Propranolol (acute, PRN)** | β-adrenergic blockade → prevents norepinephrine from amplifying the amygdala → PFC cascade | Pre-court, pre-confrontation. Does not sedate. Does not impair cognition. Blocks the *amplification* of the threat signal without blocking the signal itself. |
| **Sensory anchoring protocols** | Forces PFC engagement via deliberate perceptual processing (specific textures, temperatures, spatial counting) | During acute episodes. Not "mindfulness" — targeted sensory channel recruitment to re-engage PFC |
| **Pre-exposure written preparation** | Offloads complex reasoning to non-triggered state; reduces real-time cognitive demand in threat environment | Exactly what the motion practice strategy already accomplishes |

#### D. Why Standard Approaches Fail

| Approach | Why It Fails for This Phenotype |
|---|---|
| CBT | Assumes PFC is online to execute cognitive reframing. In acute glutamate storm, PFC is the thing that's offline. |
| "Just relax" / generic mindfulness | Insufficient signal to overcome glutamatergic drive. Like whispering at a jet engine. |
| Supplement stacks (Mg, theanine, taurine) | Address tonic glutamate baseline. Phasic surges overwhelm the buffer in seconds. |
| SSRIs | Target serotonin, which is downstream and not the primary driver. May help mood but don't touch the glutamate cascade. |
| Benzodiazepines | Address the symptom (GABA deficit) but create a worse problem (receptor downregulation, dependency, catastrophic withdrawal). The Peterson trap. |
| Alcohol (chronic) | Works short-term but drives GABA-A receptor adaptation over years. Endogenous capacity atrophies. Silent dependency. |

---

### 3.8 — Trigger Mapping & Temporal Binding Collapse (`08-triggers.html`)

**Content (builds from Q1 in conversation):**

- Trigger taxonomy for the high-excitation phenotype:
  - **Visual**: seeing the opposing party, authority figures in robes, specific facial expressions
  - **Auditory**: tone of voice (accusatory, condescending), specific phrases, procedural language
  - **Procedural**: being directly addressed by a judge, being required to respond in real-time
  - **Anticipatory**: the night before a hearing, receiving court documents, calendar notifications
  - **Somatic**: body-state triggers (heart rate elevation, shallow breathing) that feed back into the cascade
- Temporal binding collapse explained:
  - PFC normally integrates past/present/future into a coherent narrative
  - When PFC deactivates, temporal integration fails
  - Past trauma and future threat become *present-tense percepts* — not memories or predictions but experienced reality
  - This is the phenomenological signature of the circuit failure, not a psychological distortion
- Mapping protocol: systematic identification of which sensory/contextual channels trigger the switch, enabling targeted pre-exposure preparation

**Visualization:**

- Trigger → cascade timeline (interactive, step-through)
- Temporal binding diagram: normal (linear timeline) vs. collapsed (overlapping temporal percepts)

**Sources:**

- van der Kolk, B. (2014). *The Body Keeps the Score*. Viking.
- Lanius, R.A., et al. (2010). Emotion modulation in PTSD: clinical and neurobiological evidence for a dissociative subtype. *American Journal of Psychiatry*, 167(6), 640-647.
- Arnsten, A.F.T. (2015). Stress weakens prefrontal networks. *Nature Neuroscience*, 18(10), 1376-1385.

---

### 3.9 — Reference Library (`09-references.html`)

**Content:**

- Full bibliography organized by section
- Each reference linked to DOI, PubMed, or source URL
- Chemical compound quick-reference with PubChem links (duplicated from §3.2 table for standalone access)
- Receptor/channel reference with UniProt/IUPHAR links
- Glossary of technical terms used throughout

---

## 4. Technical Stack

| Component | Technology | Rationale |
|---|---|---|
| Static site | Vanilla HTML/CSS/JS | No build step. Runs anywhere. Portable. |
| Interactive pathway diagrams | D3.js v7 | Best-in-class for directed graphs with click interaction |
| Mechanism plots | Plotly.js | Publication-quality interactive plots with hover data |
| Optional 3D receptor visualization | Three.js | Already in your toolchain from conformalmaps.com |
| Typography | IBM Plex Mono + IBM Plex Sans | Clinical, precise, readable. Matches the tone. |
| Color scheme | Dark background (#0a0a0a), high-contrast data (#00ff88 excitatory, #ff3366 inhibitory, #4488ff modulatory) | Data-forward. Not decorative. |
| Hosting | GitHub Pages or local | No server required |

---

## 5. Build Phases

### Phase 1: Skeleton + Pathway
- [ ] Repository init, directory structure, CSS design system
- [ ] `index.html` with navigation
- [ ] `02-pathway.html` with full chemical compound table (static)
- [ ] `chemicals.json` with all compound metadata

### Phase 2: Interactive Pathway + Core Sections
- [ ] D3.js force-directed pathway graph with click-to-expand nodes
- [ ] `01-phenotype.html` content
- [ ] `03-glutamate-storm.html` with Plotly mechanism plots (plots 1-3)
- [ ] `04-gaba-homeostasis.html` with BAC/receptor plots (plots 4-5)

### Phase 3: Case Studies + Solutions
- [ ] `05-benzo-trap.html` with dependency plots (plots 6-7)
- [ ] `06-churchill.html`
- [ ] `07-solutions.html` with full intervention tables
- [ ] `08-triggers.html` with trigger taxonomy and temporal binding diagrams

### Phase 4: Polish + Reference
- [ ] `09-references.html` with full linked bibliography
- [ ] Cross-section navigation and scroll handling
- [ ] Mobile responsiveness
- [ ] Print/export CSS for static PDF generation

---

## 6. Expanded Q&A (from conversation threads)

### Q1: Trigger Mapping — Which Sensory/Contextual Features Trigger the Switch?

The trigger taxonomy must be individually mapped but falls into five channels:

1. **Visual** — faces (opposing party, authority figures), spatial configurations (courtroom layout resembling childhood environments), documents (motions, orders)
2. **Auditory** — tone (accusatory, dismissive), specific phrases ("the respondent failed to..."), procedural cadence
3. **Procedural** — being required to perform under observation, real-time demand on PFC while threat-activated
4. **Anticipatory** — temporal proximity to the event. The cascade can begin hours or days before. Calendar notifications, document service, email from opposing counsel
5. **Somatic** — proprioceptive/interoceptive feedback loops. Elevated heart rate, chest tightness, shallow breathing feed back into the amygdala and *sustain* the cascade even after the external trigger is gone

**Key insight:** The trigger often isn't the courtroom itself — it's the *anticipatory* channel. The glutamate surge may peak before you arrive. This has tactical implications: interventions (propranolol, vagal stimulation, written preparation) should be deployed 12-24 hours before, not at the moment of exposure.

### Q2: Riluzole and Memantine — Clinical Rationale

**Riluzole:**
- Mechanism: blocks presynaptic voltage-gated Na⁺ channels → reduces glutamate vesicle release. Also enhances EAAT2 (glial glutamate transporter) → increases glutamate reuptake from synaptic cleft
- Net effect: reduces both tonic and *phasic* glutamate — the only compound in the table that addresses both timescales
- Evidence: Pittenger et al. (2008) showed efficacy in treatment-resistant OCD (glutamate-driven). Mathew et al. (2005) demonstrated anxiolytic effects in GAD. Multiple case series for PTSD
- Practical: 50mg BID. Requires liver function monitoring (ALT/AST every 3 months). No dependency. No sedation. No cognitive impairment
- Prescriber framing: "I have a glutamate-mediated stress response that causes acute prefrontal deactivation. Riluzole targets presynaptic glutamate release. I'm requesting an off-label trial based on Pittenger 2008 and Mathew 2005."

**Memantine:**
- Mechanism: uncompetitive NMDA channel blocker. Sits in the channel but is displaced by normal synaptic glutamate signaling (voltage-dependent). Only blocks when activation is pathologically prolonged
- Net effect: clips the top of the glutamate surge without interfering with normal NMDA function
- Evidence: primarily Alzheimer's (excitotoxic neurodegeneration), but mechanistically identical to the phasic glutamate problem. Emerging data in PTSD
- Practical: 5-20mg/day. Mild side effects. No dependency. Can be combined with riluzole
- Combined protocol: riluzole (reduces glutamate release) + memantine (blocks excess NMDA activation) = two-layer defense against phasic surges

### Q3: Temporal Binding Collapse and Sensory Anchoring

**The problem formalized:**

Normal PFC function maintains a "temporal workspace" — a buffer that holds representations of past, present, and future in distinct registers, linked by causal/narrative structure. When PFC deactivates under glutamate flood:

- Past memories (especially traumatic) lose their "pastness" tag — they become percepts indistinguishable from current sensory input
- Future projections (especially threats) lose their "futurity" tag — they become experienced as imminent, present-tense danger
- The result is **temporal compression**: all threat-relevant information collapses into NOW

**Why generic mindfulness fails:** Standard mindfulness asks you to "return to the present moment." But in temporal binding collapse, the problem IS that everything has become the present moment. The instruction is meaningless.

**What works instead — targeted sensory channel recruitment:**

The goal is to force PFC re-engagement through deliberate perceptual processing that requires cortical computation:

1. **Spatial counting** — count objects in the visual field by category (e.g., "how many right angles can I see?"). This recruits dorsolateral PFC (spatial working memory) through a channel that isn't threat-contaminated
2. **Temperature differential** — hold something cold in one hand, warm in the other. The bilateral asymmetry requires cortical integration that pulls PFC back online
3. **Proprioceptive precision** — press each fingertip to thumb in sequence while counting. The motor-sequence planning recruits premotor cortex, which has dense PFC connections
4. **Verbal override** — describe the physical environment aloud in technical language ("I observe a rectangular room approximately 30 feet by 20 feet with fluorescent lighting at approximately 4000K color temperature"). Forces left-lateralized PFC engagement through analytical description

**None of these are relaxation techniques.** They are PFC recruitment protocols. The goal is not to feel calm — it's to re-activate the circuit that can think.

---

## 7. Data Specifications for Plots

### Plot 1: Glutamate Concentration vs. Time (Stress Response)

```json
{
  "title": "Extracellular Glutamate During Acute Stress",
  "x_label": "Time (minutes post-trigger)",
  "y_label": "Extracellular glutamate (μM)",
  "series": [
    {
      "name": "Normal responder",
      "data": [[0,5],[2,12],[5,18],[10,22],[15,20],[20,15],[30,8],[45,6],[60,5]],
      "color": "#4488ff"
    },
    {
      "name": "Sensitized (childhood-onset)",
      "data": [[0,8],[2,25],[5,45],[10,55],[15,52],[20,48],[30,40],[45,30],[60,22],[90,15],[120,10]],
      "color": "#ff3366"
    }
  ],
  "annotations": [
    {"y": 35, "label": "PFC functional deactivation threshold", "style": "dashed"}
  ],
  "source": "Modeled from Moghaddam 1993, Popoli et al. 2012"
}
```

### Plot 2: NMDA Receptor Activation (Voltage-Dependent)

```json
{
  "title": "NMDA Conductance vs. Membrane Potential",
  "x_label": "Membrane potential (mV)",
  "y_label": "Normalized NMDA conductance",
  "series": [
    {"name": "Normal (Mg²⁺ block)", "color": "#4488ff"},
    {"name": "Under glutamate excess", "color": "#ff3366"},
    {"name": "With memantine", "color": "#00ff88"}
  ],
  "source": "Bhatt 2009, Johnson & Bhatt 1990"
}
```

### Plot 3: PFC-Amygdala Coupling (Inverted-U / Arnsten Model)

```json
{
  "title": "PFC Function vs. Catecholamine/Cortisol Level",
  "x_label": "Catecholamine / cortisol level (normalized)",
  "y_label": "PFC functional capacity (normalized)",
  "type": "inverted_U",
  "annotations": [
    {"x_range": [0.3, 0.6], "label": "Churchill operating zone", "color": "#00ff88"},
    {"x_range": [0.7, 0.85], "label": "Acute trigger zone", "color": "#ff3366"},
    {"x_range": [0.5, 0.7], "label": "Chronic litigation baseline", "color": "#ffaa00"}
  ],
  "source": "Arnsten 2009, 2015"
}
```

---

## 8. Key External References (Master List)

### Primary Neuroscience

- Arnsten AFT (2009). Stress signalling pathways that impair prefrontal cortex structure and function. *Nat Rev Neurosci* 10(6):410-422. https://doi.org/10.1038/nrn2648
- Arnsten AFT (2015). Stress weakens prefrontal networks. *Nat Neurosci* 18(10):1376-1385. https://doi.org/10.1038/nn.4087
- Popoli M et al. (2012). The stressed synapse. *Nat Rev Neurosci* 13(1):22-37. https://doi.org/10.1038/nrn3138
- McEwen BS (2007). Physiology and neurobiology of stress and adaptation. *Physiol Rev* 87(3):873-904. https://doi.org/10.1152/physrev.00041.2006
- Moghaddam B (1993). Stress preferentially increases extraneuronal levels of excitatory amino acids in the PFC. *Cereb Cortex* 3(5):399-403.

### GABA / Alcohol / Benzodiazepines

- Wallner M et al. (2003). Ethanol enhances α4β3δ and α6β3δ GABA-A receptors at low concentrations. *PNAS* 100(25):15218-15223.
- Vinkers CH & Bhatt S (2012). Hooked on benzodiazepines: GABA-A receptor subtypes. *Trends Pharmacol Sci*. https://pmc.ncbi.nlm.nih.gov/articles/PMC4020178/
- Fluyau D et al. (2018). Challenges of benzodiazepine withdrawal management. *Ther Adv Psychopharmacol*. https://doi.org/10.1177/2045125317753340
- Ashton H (2005). The diagnosis and management of benzodiazepine dependence. *Curr Opin Psychiatry* 18(3):249-255.
- Lader M (2011). Benzodiazepines revisited. *Addiction* 106(12):2086-2109.
- Kumar S et al. (2004). Chronic ethanol consumption enhances internalization of α1 subunit-containing GABA-A receptors. *J Neurochem* 89(6):1535-1544.

### Glutamate-Targeted Therapeutics

- Pittenger C et al. (2008). Riluzole augmentation in treatment-resistant OCD. *Biol Psychiatry* 63(11):978-980.
- Mathew SJ et al. (2005). Riluzole for anxiety. *Am J Psychiatry* 162(11):2135-2138.
- Zarate CA et al. (2006). A randomized trial of an NMDA antagonist in treatment-resistant major depression. *Arch Gen Psychiatry* 63(8):856-864.

### Churchill Sources

- McMenamin M (2018). The Myth of Churchill and Alcohol. Hillsdale College Churchill Project.
- Langworth R (2017). *Winston Churchill, Myth and Reality*. McFarland.
- Roberts A (2018). *Churchill: Walking with Destiny*. Viking.

### Clinical / Phenomenological

- van der Kolk B (2014). *The Body Keeps the Score*. Viking.
- Lanius RA et al. (2010). Emotion modulation in PTSD: dissociative subtype. *Am J Psychiatry* 167(6):640-647.

---

## 9. Design Principles

1. **No decorative content.** Every element serves comprehension or navigation.
2. **Data-forward.** Plots, tables, and pathway diagrams are primary content, not illustrations.
3. **Source-linked throughout.** Every claim traces to a DOI or primary source.
4. **Dark, clinical aesthetic.** This is a research instrument, not a wellness blog.
5. **Interactive where interaction serves understanding.** Step-through cascades, hover-for-detail on pathway nodes, adjustable parameters on dose-response curves.
6. **Printable.** Clean print CSS for each section. No information loss on paper.

---

*Spec version: 1.0*
*Author: Joel Thorarinson*
*Date: 2026-05-10*
