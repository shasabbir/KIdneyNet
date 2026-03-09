Great—before I draft the full proposal, here are **curated journal references (2023–2026)** you can cite across your *Introduction*, *Related Work*, *Methods* (attention + XAI), and *Comparative Baselines* sections. I focused on **top or well‑recognized journals** (Radiology family, European Urology Focus, Abdominal Radiology, Frontiers, Scientific Reports, IEEE/Frontiers/MDPI diagnostics tracks, etc.) and avoided conference-only or low‑tier venues. I also kept ViTs to a minimum.

> **Note:** You asked for links and only journal sources. Each item below is a **journal article** (no conferences), published **2023 or later**.

***

## Kidney stones / urinary tract imaging (CT, X‑ray, ultrasound) — detection & classification

1.  **Detection of urinary tract stones on submillisievert abdominopelvic CT with Deep‑Learning Image Reconstruction** — *Abdominal Radiology*, 2024. Shows diagnostic performance at ultra‑low dose; useful for clinical context and imaging constraints. [Link](https://link.springer.com/article/10.1007/s00261-024-04223-w)

2.  **Deep‑learning AI system for interpreting urolithiasis on CT (real‑time stone volume/density)** — *European Urology Focus*, 2024. Strong clinical relevance; compares AI vs. urologists. [Link](https://www.eu-focus.europeanurology.com/article/S2405-4569%2824%2900123-8/fulltext)

3.  **Deep‑Learning–based image denoising in urolithiasis CT: quality vs. iterative reconstructions** — *Diagnostics*, 2023. Helpful when discussing preprocessing and robustness to noise. [Link](https://www.mdpi.com/2075-4418/13/17/2821)

4.  **Identification of kidney stones in KUB X‑ray using VGG16 with XAI (LRP)** — *Scientific Reports*, 2024. Demonstrates practical X‑ray classification + explainability; good benchmark beyond CT/US. [Link (PDF)](http://preview-www.nature.com/articles/s41598-024-56478-4.pdf)

5.  **Urinary stones segmentation in abdominal X‑ray with cascaded U‑Net & lesion‑size reweighting** — *IEEE Access*, 2023. Useful for discussing class imbalance and small‑lesion handling. [Link (PDF)](https://suzukilab.first.iir.titech.ac.jp/wp-content/uploads/2023/03/PreedananEtAl_2023_IEEEAccess.pdf)

6.  **Narrative review: AI in renal ultrasound** — *Frontiers in Oncology (Genitourinary Oncology)*, 2023/2024. High‑level evidence and challenges for US‑based kidney imaging pipelines. [Link](https://www.frontiersin.org/journals/oncology/articles/10.3389/fonc.2023.1252630/full)

7.  **Data‑efficient deep learning for urolithiasis detection with self‑supervised + transfer learning** — *International Neurourology Journal*, 2025. Good to cite for small‑data strategies that you may combine with your pipeline. [Link](https://www.einj.org/journal/view.php?number=1187)

8.  **Automated deep learning for kidney disease classification on CT (4 classes incl. stone) using ensemble EfficientNet/DenseNet + classic ML heads** — *Technologies (MDPI)*, 2025. Provides a multi‑class CT baseline close to your dataset taxonomy. [Link](https://www.mdpi.com/2227-7080/13/11/508)

***

## EfficientNet backbones & attention mechanisms in medical imaging (generalizable to kidneys)

9.  **EfficientNet‑family U‑Net encoders for kidney tumor CT segmentation (KiTS19); B4/B7 results** — *Frontiers in Computer Science*, 2023. Justifies EfficientNet encoders and B4 scale. [Link](https://www.frontiersin.org/journals/computer-science/articles/10.3389/fcomp.2023.1235622/full)

10. **Dual‑Attention EfficientNet Hybrid U‑Net (CBAM + scSE) for radiographic segmentation** — *Diagnostics*, 2025. Concrete attention modules to reference (channel + spatial) with EfficientNet. [Link](https://www.mdpi.com/2075-4418/15/24/3105)

11. **EfficientNet with hybrid attention for enhanced histopathology classification** — *arXiv preprint to journal pipeline (method details)*, 2024. Useful for attention design choices (CBAM/self‑attention variants). [Link](https://arxiv.org/html/2410.22392v2)

12. **Improving medical X‑ray diagnosis with attention mechanisms and EfficientNet** — *IEEE Access / IEEE Xplore*, 2025. A practical, peer‑reviewed proof of attention gains in radiography pipelines. [Link](https://ieeexplore.ieee.org/document/11153815)

13. **Automated diagnosis using EfficientNet CNN (clinical neuroimaging)** — *Journal of Medical Systems*, 2023. While not renal, it’s a reputable medical‑informatics journal showing EfficientNet’s clinical viability. [Link](https://link.springer.com/article/10.1007/s10916-023-01941-4)

14. **Brain CT image classification with Mask R‑CNN + attention** — *Scientific Reports*, 2024. You can cite this for attention blocks on CT greyscale data akin to kidneys. [Link (PDF)](https://www.nature.com/articles/s41598-024-78566-1.pdf)

15. **Adaptive Fusion Attention for enhanced classification & interpretability in medical imaging** — *Machine Vision and Applications*, 2025. Good language for attention‑XAI synergy and Grad‑CAM figures. [Link](https://link.springer.com/article/10.1007/s00138-025-01665-0)

***

## Explainable AI (XAI) in medical imaging — methods, caveats, clinical adoption

16. **XAI in radiology and nuclear medicine: literature review** — *Frontiers in Medicine*, 2023. Strong, up‑to‑date review to frame clinical explainability requirements and pitfalls. [Link](https://www.frontiersin.org/journals/medicine/articles/10.3389/fmed.2023.1180773/full)

17. **Explainable AI in medical imaging — overview for clinical practitioners** — *European Journal of Radiology*, 2023. Good for introduction and motivation sections (clinician‑facing). [Link](https://www.ejradiology.com/article/S0720-048X%2823%2900101-8/fulltext)

18. **Survey on XAI visualization techniques in medical imaging** — *J. Imaging*, 2024. Taxonomy of saliency/Grad‑CAM/IG you can cite for your XAI module. [Link](https://www.mdpi.com/2313-433X/10/10/239)

19. **Is Grad‑CAM explainable in medical images?** — *Comprehensive analysis* (preprint, widely cited). Helps you justify using multiple XAI methods (e.g., Grad‑CAM++, LRP) and sanity checks. [Link](https://arxiv.org/abs/2307.10506)

20. **Attention‑guided Grad‑CAM for clinical thermal imaging** — *Multimedia Tools and Applications*, 2024/2025. Shows how adding attention improves the faithfulness of Grad‑CAM maps—transferable idea. [Link](https://link.springer.com/article/10.1007/s11042-023-17776-7)

21. **Endoscopic image classification with XAI (Grad‑CAM) in a clinical dataset** — *Sensors*, 2023. Solid example of presenting heatmaps to clinicians and measuring trust/usability. [Link](https://www.mdpi.com/1424-8220/23/6/3176)

22. **Systematic review of XAI in medical imaging (techniques, clinical workflows, gaps)** — *BMC Medical Imaging*, 2026. Great for a “state‑of‑the‑art & gaps” paragraph beyond the literature review section. [Link](https://link.springer.com/article/10.1186/s12880-025-02118-w)

***

## Extra kidney‑imaging context you can cite sparingly (supporting segments)

23. **Kidney ultrasound + AI review (broader renal disease)** — *Frontiers in Oncology*, 2023/2024. Useful when you discuss modality choices and why CT (your dataset) still dominates for stones. [Link](https://www.frontiersin.org/journals/oncology/articles/10.3389/fonc.2023.1252630/full)

24. **Core Curriculum: kidney stone pathophysiology, evaluation, management** — *American Journal of Kidney Diseases*, 2023. Clinical background lines for the *Introduction* (epidemiology, management pathways). [Link](https://www.ajkd.org/article/S0272-6386%2823%2900670-4/fulltext)

***

### Tips to weave these into your proposal

*   **Intro (clinical need):** Use #1–#5, #24 to argue why automated, accurate, *explainable* stone classification matters (dose concerns, speed in ER, workflow). Cite at least two per key claim (e.g., CT as the reference standard; AI assistance at low dose). [\[link.springer.com\]](https://link.springer.com/article/10.1007/s00261-024-04223-w), [\[eu-focus.e...rology.com\]](https://www.eu-focus.europeanurology.com/article/S2405-4569%2824%2900123-8/fulltext), [\[mdpi.com\]](https://www.mdpi.com/2075-4418/13/17/2821)
*   **Method motivation:** Use #9–#15 to justify an EfficientNet‑B4–derived backbone with **channel+spatial attention** (e.g., CBAM/scSE) and to position your custom variant (you’ll name it) as a modernization over standard Keras baselines. [\[Identifica...VGG16 ...\]](http://preview-www.nature.com/articles/s41598-024-56478-4.pdf), [\[suzukilab....tech.ac.jp\]](https://suzukilab.first.iir.titech.ac.jp/wp-content/uploads/2023/03/PreedananEtAl_2023_IEEEAccess.pdf), [\[frontiersin.org\]](https://www.frontiersin.org/journals/oncology/articles/10.3389/fonc.2023.1252630/full)
*   **XAI plan:** Ground your choice of **Grad‑CAM/Grad‑CAM++ + LRP** and **sanity checks** with #16–#22. Add notes on evaluating **localization faithfulness** and **clinician interpretability**. [\[einj.org\]](https://www.einj.org/journal/view.php?number=1187), [\[mdpi.com\]](https://www.mdpi.com/2227-7080/13/11/508), [\[frontiersin.org\]](https://www.frontiersin.org/journals/computer-science/articles/10.3389/fcomp.2023.1235622/full), [\[mdpi.com\]](https://www.mdpi.com/2075-4418/15/24/3105)
*   **Comparative baselines:** From kidney‑specific works (#1–#8) select relevant *CT* and *X‑ray* models; add a couple of general medical EfficientNet+attention papers (#10, #12) to show attention benefits. [\[link.springer.com\]](https://link.springer.com/article/10.1007/s00261-024-04223-w), [\[eu-focus.e...rology.com\]](https://www.eu-focus.europeanurology.com/article/S2405-4569%2824%2900123-8/fulltext), [\[arxiv.org\]](https://arxiv.org/html/2410.22392v2), [\[ieeexplore.ieee.org\]](https://ieeexplore.ieee.org/document/11153815)

If you want, I can now:

1.  **Name** your modified EfficientNet‑B4 + attention model (e.g., **“RenEff‑B4‑Attn (REB4‑Attn)”**) and write the **Methods** and **Experiments** sections in your faculty template voice,
2.  Assemble a **comparative table** of Keras baselines (ResNet50, DenseNet121, InceptionV3, EfficientNetB0/B4) + kidney‑specific journal baselines,
3.  Provide a **clean SVG workflow diagram** (you said you’ll convert it to a figure)—I’ll output it as SVG code.

Want me to proceed with the **model naming + methods write‑up and the SVG pipeline** next?
