# NeuroFusion-SZ — Research Intelligence Pages

Interactive web pages for the **NeuroFusion-SZ** project, which studies schizophrenia using structural MRI, deep learning and genetics.

This repository hosts the public, browser-based side of the project. The model code, training reports and results live in the main repository: [NeuroFusion-SZ/NeuroFusion-Schizophrenia](https://github.com/NeuroFusion-SZ/NeuroFusion-Schizophrenia).

> **Research only.** These pages summarise published research for education and communication. They are not diagnostic tools and must not be used to assess any individual.

---

## Live pages

| Page | What it is | Link |
| --- | --- | --- |
| **Literature Constellation** | An interactive map of the papers behind the project and the research gaps they leave open | [neurofusion-sz.github.io/neurofusion-sz](https://neurofusion-sz.github.io/neurofusion-sz/) |
| **3D Brain Atlas** | Control vs schizophrenia brains in 3D, with the pathways that connect the brain to the body | [neurofusion-sz.github.io/neurofusion-sz/brain-atlas.html](https://neurofusion-sz.github.io/neurofusion-sz/brain-atlas.html) |

---

## 1. Literature Constellation · `index.html`

A force-directed map of the systematic review behind NeuroFusion-SZ.

- **19 papers** on structural MRI, deep learning, multimodal fusion, genetics and polygenic risk scores (PRS) in schizophrenia, grouped into **7 research domains**.
- **9 research gaps**, sized by severity, each linked to the papers that expose it.
- Click a paper to see its dataset, sample size, model, validation approach, performance, limitations and DOI.
- Filter by domain, highlight gaps, switch to *Gap focus* mode, or search titles, models and journals.

**The key gap (G9):** no published study combines structural MRI, deep learning and polygenic risk scores in one end-to-end model. This is the niche NeuroFusion-SZ is working towards.

## 2. 3D Brain Atlas · `brain-atlas.html`

Two brains side by side, a control and a schizophrenia brain, which rotate together.

**Brain structure**
- The schizophrenia brain is scaled from published group-average effect sizes (Cohen's d) from the ENIGMA consortium. For example, the hippocampus is smaller (d = −0.46), the lateral ventricles are larger (d = +0.37) and the cortex is thinner (d = −0.53).
- An *Exaggerate differences* slider runs from ×1 to ×10. At ×1 the brains look almost identical, which is accurate: the two groups overlap heavily.
- The cortex can be shown as glass, solid or hidden. Click any structure to see its role, the difference reported in schizophrenia, and the source.

**Pathways**

| Pathway | Proposed change in schizophrenia | Evidence |
| --- | --- | --- |
| Associative striatum dopamine | ↑ increased | Strong (PET) |
| Mesolimbic dopamine | ↑ increased | Moderate |
| Mesocortical dopamine | ↓ reduced | Weaker, mostly indirect |
| Glutamate cortex–thalamus loop | ↓ reduced (NMDA hypothesis) | Moderate |
| Nigrostriatal dopamine → movement | Normal; antipsychotic side effects | Pharmacology |
| Tuberoinfundibular dopamine → prolactin | Normal; antipsychotic side effects | Pharmacology |
| HPA stress axis | ↑ increased | Moderate |
| Vagus nerve → heart | ↓ reduced (lower heart rate variability) | Strong (meta-analysis) |

**Brain + body view.** This view follows the pathways out of the skull: the vagus nerve to the heart, motor signals down the spinal cord, and the stress hormones (ACTH and cortisol) and prolactin carried in the blood. Solid lines are nerve pathways and dashed lines are hormonal routes. Moving dots show relative activity.

Schizophrenia is a brain disorder. The body links shown are the established ones (autonomic, hormonal and motor); the peripheral nerves are not a site of the illness.

---

## Sources

| Topic | Reference |
| --- | --- |
| Subcortical volumes | van Erp et al. 2016, *Molecular Psychiatry* — [doi:10.1038/mp.2015.63](https://doi.org/10.1038/mp.2015.63) |
| Cortical thickness and surface area | van Erp et al. 2018, *Biological Psychiatry* — [doi:10.1016/j.biopsych.2018.04.023](https://doi.org/10.1016/j.biopsych.2018.04.023) |
| Dopamine hypothesis | Howes & Kapur 2009, *Schizophrenia Bulletin* — [PMC2669582](https://pmc.ncbi.nlm.nih.gov/articles/PMC2669582/) |
| Aberrant salience | Howes & Nour 2016, *World Psychiatry* — [doi:10.1002/wps.20276](https://doi.org/10.1002/wps.20276) |
| Glutamate hypothesis | Moghaddam & Javitt 2012, *Neuropsychopharmacology* — [PMC3238069](https://pmc.ncbi.nlm.nih.gov/articles/PMC3238069/) |
| Stress (HPA) model | Walker & Diforio 1997, *Psychological Review* — [doi:10.1037/0033-295x.104.4.667](https://doi.org/10.1037/0033-295x.104.4.667) |
| Heart rate variability | Clamor et al. 2016, *British Journal of Psychiatry* — [doi:10.1192/bjp.bp.114.160762](https://doi.org/10.1192/bjp.bp.114.160762) |

Each paper in the Literature Constellation links to its own DOI from inside the page.

---

## Limitations

- The schizophrenia brain shows **average group differences** from large studies. It does not show any real person's brain.
- Anatomy is simplified and not to scale. Structures are drawn procedurally, not taken from a brain template.
- Pathway activity shows the *direction* each hypothesis proposes. The strength of evidence differs between pathways and is stated for each one.
- The OpenNeuro ds000030 dataset used by the NeuroFusion-SZ model is not an African cohort. No claim of validation in African populations is made.

---

## Running locally

Both pages are single HTML files with no build step.

```bash
git clone https://github.com/NeuroFusion-SZ/neurofusion-sz.git
cd neurofusion-sz
python -m http.server 8000
# open http://localhost:8000 and http://localhost:8000/brain-atlas.html
```

They need an internet connection for their libraries (D3 for the constellation, three.js for the atlas) and fonts. The atlas needs a browser with WebGL.

## Deployment

The site is deployed with **GitHub Pages** from the `main` branch, root folder. Any commit to `main` republishes it within a couple of minutes.

## Related

- **Model, training reports and results:** [NeuroFusion-SZ/NeuroFusion-Schizophrenia](https://github.com/NeuroFusion-SZ/NeuroFusion-Schizophrenia)
- **Data:** [OpenNeuro ds000030](https://openneuro.org/datasets/ds000030) — UCLA Consortium for Neuropsychiatric Phenomics
