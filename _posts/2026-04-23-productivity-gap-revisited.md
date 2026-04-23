---
layout: post
title: "Closing the Productivity Gap, 11 Years Later: Revisiting the 2015 Methodology"
date: '2026-04-23'
permalink: /blog/productivitygap-revisited/
share-img: "/assets/img/blog/productivitygap/productspace.png"
published: true
tags:
  - English
  - Productivity Gap
  - Research and Development
  - I+D+i
  - Colombia
  - Tax Benefits
  - OECD
  - Bioeconomy
  - Industry 4.0
  - AI
---

> #### Camilo Eduardo Cabrera Garrido – cecabrera55@gmail.com
##### _Companion note to the 2015 paper ["Methodology to Massively Structure Investment Projects in R&D to Close the Productivity Gap"]({{ site.url }}/blog/productivitygap/)._
###### April 23rd 2026. USD/COP ≈ 4,000.

ABSTRACT: In March 2015 I published a master's-thesis-length argument proposing that Colombia could close its productivity gap by massively structuring R&D investment projects at the firm level, using young professionals and a dedicated institutional architecture. Eleven years later, some of the diagnosis still holds almost word for word, other parts have aged poorly, and a whole new set of levers — OECD membership, AI, bioeconomy, the royalties-for-science reform, the 2022 tax reform — did not exist (or were marginal) when the paper was written. This companion post revisits the original methodology with 2025–2026 data and proposes an updated blueprint.

# Table of content

- [1. Why a companion note?](#why)
- [2. What the 2015 paper got right](#right)
- [3. What the 2015 paper got wrong (or what reality changed)](#wrong)
- [4. The 2026 diagnosis: same gap, new texture](#diagnosis)
  - [4.1. Labor productivity: stuck at 22–25% of the US](#labor-productivity)
  - [4.2. Competitiveness and innovation rankings](#rankings)
  - [4.3. TFP, misallocation, and the "missing middle"](#tfp)
  - [4.4. Management quality: the under-discussed gap](#management)
  - [4.5. Informality and the workweek shock](#informality)
- [5. The new institutional and fiscal architecture](#institutions)
  - [5.1. From Colciencias to MinCiencias](#minciencias)
  - [5.2. From PTP to Colombia Productiva to iNNpulsa](#innpulsa)
  - [5.3. The royalties-for-science reform (Ley 2056 de 2020)](#sgr)
  - [5.4. Tax benefits after the 2022 reform (Ley 2277)](#tax)
- [6. What's genuinely new since 2015](#new)
  - [6.1. OECD accession (2020) and the "Going for Growth" lens](#oecd)
  - [6.2. AI, Industry 4.0, and digital productivity](#ai)
  - [6.3. Bioeconomy, green productivity, and the just transition](#bioeconomy)
  - [6.4. Open-source system dynamics (PySD, SDEverywhere)](#opensource)
- [7. An updated methodology proposal](#methodology)
- [8. Closing: what the 23-year-old author would tell the 35-year-old one](#closing)
- [Appendix A. Legal addendum: mapping the 2015 citations to 2026](#legal-addendum)
- [References](#refs)

## 1. Why a companion note? <a name="why"></a>

The original 2015 paper was written for a Cambridge, Massachusetts conference, as a synthesis of my Industrial Engineering thesis at Universidad de los Andes. Its core claim was simple: Colombia does not lack *ideas* for productive transformation — it lacks **a pipeline of well-structured, fundable R&D projects at the firm level**, and it lacks the **qualified young human capital** to structure them. The proposed methodology was a three-phase engine — *structuring*, *funding*, *execution* — that would systematically convert policy intent into bankable I+D+i projects.

Eleven years on, most of the structural framing still applies. But three things force a revision:

1. **Data has moved.** Many of the rankings, macro figures, and institutional acronyms in the 2015 paper are now obsolete or frankly misleading.
2. **The policy toolkit has changed.** The royalties system was reformed (2019–2020), Colombia joined the OECD (2020), the tax code was overhauled (2016, 2019, 2022), and Colciencias became a ministry (2019).
3. **The technology frontier moved under our feet.** In 2015, "Industry 4.0" was a slogan. In 2026, productivity gains are being captured — or missed — through generative AI, cloud-based simulation, and open-source digital twins. Systems dynamics software that cost thousands of dollars in iThink/Vensim PLE licenses now runs on free Python libraries.

This note updates the diagnosis, the instrument set, and the methodology. It is not a rewrite: the 2015 paper stands as the reference document and is [still available here]({{ site.url }}/blog/productivitygap/).

## 2. What the 2015 paper got right <a name="right"></a>

Reading the paper today, several claims have aged remarkably well:

- **"Productivity is the residual that explains long-run income differences."** The 2024 IMF *Colombia: Selected Issues* paper uses exactly this framing: Colombia's aggregate Total Factor Productivity (TFP) "has fallen and stagnated over the past three decades," and the decomposition shows that much of the decline is *within-firm* rather than compositional (IMF, 2024).
- **"The private sector under-invests in R&D; public expenditure alone cannot close the gap."** In 2016 OECD data, Colombian business expenditure on R&D was 0.11% of GDP — *15 times less* than the OECD average (OECD, 2019). That ratio has barely moved.
- **"Institutional dis-coordination between Colciencias, MinCIT, PTP and Bancóldex wastes public effort."** This was the paper's most repeated complaint. It is still the OECD's most repeated recommendation in every *Going for Growth* cycle.
- **"Colombia is trapped in the low-complexity periphery of the Product Space."** The Harvard Growth Lab's updated *Atlas of Economic Complexity 10.0* (2024) still ranks Colombia around the **56th** position in Economic Complexity — mid-table and largely stagnant.
- **"The methodology must be operational, not a policy document."** Every serious productivity program launched in Colombia since 2015 (*Fábricas de Productividad*, *Misiones de Sabios 2019*, *Misiones de Ciencia, Tecnología e Innovación* under the PND 2022–2026) has converged on some version of the "young-professional-plus-firm-plus-consulting-group" triangle the paper proposed.

## 3. What the 2015 paper got wrong (or what reality changed) <a name="wrong"></a>

With the benefit of hindsight, several things in the 2015 paper need correction:

| 2015 claim | 2026 reality |
|---|---|
| R&D/GDP target of **0.9%** for the PND 2014–2018 | The target was never met; actual investment stayed around **0.24–0.29% of GDP**. The PND 2022–2026 *lowered the ambition* to **0.5% by 2026** (DNP, 2023). |
| **Colciencias** as the axis of the innovation system | Colciencias was transformed into **MinCiencias** (Ministry of Science, Technology and Innovation) via Ley 1951 de 2019. |
| **Productive Transformation Program (PTP)** as the delivery arm | PTP became *Colombia Productiva* (2018), and in 2024 was merged into **iNNpulsa Colombia** under MinCIT. |
| **175% deduction** on R&D investment (Art. 158-1 ET) as the flagship tax benefit | Art. 158-1 was **repealed** by Ley 2277 de 2022. The current instrument is a **30% tax discount** on qualifying investment (new Art. 256 ET) plus a fiscal credit for MiPymes — no longer a deduction, but a direct credit against income tax. |
| **iThink, Vensim PLE, AnyLogic** as the modelling stack | All still exist, but **PySD** and **SDEverywhere** let you build and run the exact same stock-and-flow models in open-source Python/Julia, fully reproducible and version-controllable. |
| The **mining boom** (≈60% of exports) as the productivity-trap context | Mining/hydrocarbons fell to **~40–45% of exports** by 2024, partly by design (PND 2022–2026 *descarboniza las exportaciones*) but also because of price cycles and declining production. |
| USD/COP = **2,612** | USD/COP ≈ **4,000** (a ~53% nominal depreciation in 11 years, which matters enormously for any argument about cost competitiveness or capital goods imports). |

The paper also under-weighted three things that we now know matter enormously:

- **Management quality** (the Bloom–Van Reenen agenda).
- **Firm-size distribution** (the "missing middle" between microenterprises and large firms).
- **Digital adoption** (cloud, data, AI), which in 2015 was still largely framed as "IT" rather than as a productivity lever on par with R&D.

## 4. The 2026 diagnosis: same gap, new texture <a name="diagnosis"></a>

### 4.1. Labor productivity: stuck at 22–25% of the US <a name="labor-productivity"></a>

The 2015 paper cited McKinsey's finding that a Colombian worker produced about 23% of what a U.S. worker produced. Eleven years later, the number is essentially unchanged. The OECD's *Production Transformation Policy Review of Colombia* and successive *Going for Growth* chapters repeat, verbatim, that "since the 2000s, Colombia's labour productivity has been 25% of that of the United States." Over the same period, **China's productivity gap with the U.S. narrowed by 400%.**

Colombia is now the **lowest-productivity OECD member on a per-hour basis**, and the country's own Consejo Privado de Competitividad estimates that closing even half the gap with the OECD median would add roughly two percentage points of sustained annual GDP growth.

### 4.2. Competitiveness and innovation rankings <a name="rankings"></a>

The headline rankings tell a sobering story of stagnation and, recently, regression:

- **IMD World Competitiveness Ranking:** Colombia was 51/59 in 2014 (the snapshot used in the 2015 paper). In the 2025 edition it sits at **56/69** — essentially unchanged in relative terms.
- **WEF Global Competitiveness Index:** Discontinued in its old form after 2019; Colombia's last classical position was 57/141.
- **WIPO Global Innovation Index (GII):** 2014 = 68/143. 2024 = **61/133** (best-ever). 2025 = **71/139** — a ten-position drop in a single year, driven by weaker innovation inputs (institutions, infrastructure, business sophistication).
- **Harvard Economic Complexity Index (ECI):** around **56th** globally in the Atlas 10.0 dataset (2024). Colombia's export basket remains dominated by commodities and simple manufactures.

The 2015 paper's argument that Colombia is a "middle-of-the-pack" country that fails to *converge* is, if anything, truer today than when it was written.

### 4.3. TFP, misallocation, and the "missing middle" <a name="tfp"></a>

The most important analytical advance since 2015 is the widespread use of **firm-level data** to decompose productivity. The IMF's 2024 Selected Issues paper applies the Melitz–Polanec dynamic Olley–Pakes decomposition to Colombia's micro-data (IMF, 2024) and reaches two striking conclusions:

1. **Aggregate TFP decline is broad-based, but its composition differs by sector.** Mining's fall is "within-firm" (declining ore grades, higher capex); manufacturing and agriculture actually benefit from **positive reallocation** (productive firms gaining share), which partially offsets the within-firm decline.
2. **The missing channel is *entry*.** New firms in Colombia are, on average, *less* productive than incumbents. This is the opposite of what happens in dynamic economies, and it is the single biggest mechanical drag on aggregate TFP.

This maps directly onto what Colombian economists now call the **"missing middle"**: a firm-size distribution dominated by sub-scale microenterprises (where ~84% of workers are informal) and a small number of large firms, with a thin layer of medium-sized, formal, productive companies in between. The 2015 paper identified symptoms of this without naming it; in 2026, it is the central empirical fact of the productivity debate.

### 4.4. Management quality: the under-discussed gap <a name="management"></a>

The **World Management Survey (WMS)** — which did not exist in Colombia when the 2015 paper was drafted — has since measured management practices in thousands of Colombian manufacturing plants (Bermúdez and Harker, 2016; Scur et al., 2021). The results are blunt: Colombia ranks **24th out of 35 countries** in average management score, below Brazil, Argentina, Chile and Mexico, and *roughly half the score of U.S. firms*.

The gap is not primarily about talent. It is about **systematic practices** — target setting, performance monitoring, meritocratic promotion, lean operations — that can be taught, audited, and improved. This is exactly the kind of "operational thinking" that the 2015 paper tried to anchor as the intellectual core of its methodology, but today we have a *measurable, benchmarkable* version of it. Any serious productivity methodology in 2026 has to include a management-diagnostic module — something the 2015 version did not.

### 4.5. Informality and the workweek shock <a name="informality"></a>

Two labor-market facts reframe the productivity conversation in ways the 2015 paper could not anticipate:

- **Informality is stuck.** After falling from ~68% in 2010 to ~57% by 2019, Colombia's informality rate has hovered at **55–56%** for three years. In rural areas it remains at **~85%**. Half of the occupied labor force is effectively outside the formal productive system.
- **The workweek is contracting fast.** Ley 2101 de 2021 reduces the legal workweek from 48 to **42 hours** in four annual steps ending **15 July 2026**, *without salary reduction*. Mechanically, labor productivity *per hour* rises by construction; but *per worker* output will only rise if firms invest in capital, automation and process redesign to offset the ~12.5% reduction in available hours. For SMEs that have never invested in digital tools, this is a shock. For firms that do invest, it is a once-in-a-generation forcing function — precisely the kind of window the 2015 methodology was designed to exploit.

## 5. The new institutional and fiscal architecture <a name="institutions"></a>

The 2015 paper described an institutional map that, in 2026, no longer exists. Any reader coming back to the methodology needs the new map to make sense of the instruments.

### 5.1. From Colciencias to MinCiencias <a name="minciencias"></a>

Ley 1951 de 2019 elevated **Colciencias** (a department) to the **Ministry of Science, Technology and Innovation (MinCiencias)**. It is now cabinet-level, has a dedicated budget line, and chairs the *Consejo Nacional de Beneficios Tributarios en CTeI (CNBT)* — the body that qualifies R&D projects for tax benefits. The PND 2022–2026 also announced the creation of an **Agencia Nacional de Ciencia, Tecnología e Innovación** as the executing arm for calls and programs; as of 2026, its rollout is still partial.

### 5.2. From PTP to Colombia Productiva to iNNpulsa <a name="innpulsa"></a>

The Productive Transformation Program (PTP) became **Colombia Productiva** in 2018, and in 2024 was absorbed into **iNNpulsa Colombia** — now the single delivery arm for productivity and entrepreneurship programs under MinCIT. Its flagship program is **Fábricas de Productividad y Sostenibilidad**, a public extension service that pairs certified consultants ("extensionistas") with SMEs across nine lines of intervention (operations, quality, logistics, digital, commercial, labor, sustainability, energy, product development). After six cycles, the program reports:

- **4,000+** firm-level interventions.
- **Average productivity improvement of ~31–48%** (measured on the firm-defined KPI per intervention).
- Top-performing lines: **Quality Management (+115%)**, **Digital Transformation (+64%)**, **Product Sophistication (+54%)**.

In effect, Colombia already has an operational version of what the 2015 paper proposed. It is smaller in scope, less R&D-oriented, and less connected to the university system — but it exists, it works, and it is the natural anchor for any updated methodology.

### 5.3. The royalties-for-science reform (Ley 2056 de 2020) <a name="sgr"></a>

The single most consequential CTeI reform since the 2015 paper is the overhaul of the **Sistema General de Regalías (SGR)**. Acto Legislativo 05 de 2019, reglamentado por Ley 2056 de 2020, earmarks **10% of total royalties** (≈ 1.2 billion pesos per biennium in recent years) for the **Asignación para Ciencia, Tecnología e Innovación**, of which a minimum of **2 percentage points** must go to environmental CTeI.

Critically, projects are now allocated through **convocatorias públicas, abiertas y competitivas** operated by MinCiencias and approved by a dedicated **OCAD CTeI**, instead of the politically-captured, ad-hoc approvals that dominated the old SGR. The reform is imperfect (the Contraloría has reported irregularities worth tens of billions of pesos in flagship scholarship projects), but it is structurally the most significant CTeI funding vehicle Colombia has ever had. It was not on the radar of the 2015 paper.

### 5.4. Tax benefits after the 2022 reform (Ley 2277) <a name="tax"></a>

The tax architecture the 2015 paper relied on has been completely rewritten:

- **Article 158-1 ET (175% deduction on qualifying R&D)** — the instrument most heavily promoted in the 2015 paper — was **repealed** by Ley 2277 de 2022.
- **Article 256 ET** now grants a **30% tax discount** (up from 25%) on qualifying CTeI investment, also extending to:
  - Donations to scholarship programs for estratos 1–3.
  - Donations to the Fondo Francisco José de Caldas.
  - Salary paid to PhD-level personnel working on I+D+i.
- **Article 256-1 ET** creates a **50% fiscal credit** on CTeI investment specifically for MiPymes that cannot use the discount (because they have no or low tax liability), issuable as a negotiable TIDIS by the DIAN. This is structurally closer to the UK's R&D tax credit and is arguably the most SME-friendly R&D instrument Colombia has ever had.
- The **annual cap** is set by CONFIS based on CNBT requests, and a reserved share must go to MiPymes.

In short: the incentive is smaller in headline percentage but **far better targeted** and, for the first time, genuinely usable by small innovative firms. Any updated methodology has to route through Article 256 / 256-1 rather than the defunct 158-1.

## 6. What's genuinely new since 2015 <a name="new"></a>

### 6.1. OECD accession (2020) and the "Going for Growth" lens <a name="oecd"></a>

Colombia formally joined the OECD on **28 April 2020**, becoming its 37th member. This is not just a diplomatic badge; it imports an entire evaluative framework:

- Biannual **Economic Surveys** with enforceable peer review.
- Country-specific priorities in **Going for Growth**: Colombia's list consistently headlines *reducing informality, easing firm entry/exit, boosting R&D, closing the digital divide, and strengthening competition policy.*
- Integration into the **OECD productivity databases** (MultiProd, DynEmp), which is how the firm-level decomposition in IMF (2024) became possible in the first place.

For a methodology like the one proposed in 2015, OECD membership is free air cover: the *diagnostic* work — identifying where productivity is lost, in which sectors, by which firms — is now partially subsidized by the OECD itself.

### 6.2. AI, Industry 4.0, and digital productivity <a name="ai"></a>

The most important category the 2015 paper could not have written about is **digital productivity**. Three things changed:

1. **Cloud + SaaS made modern management tools SME-affordable.** ERPs, CRMs, MES systems, BI tools, and lately vertical AI copilots are now within reach of a ~50-employee Colombian firm. The binding constraint is not price; it is adoption capability.
2. **Generative AI is a productivity multiplier in the exact activities Colombian white-collar work does.** Drafting, summarization, translation, basic analysis, code scaffolding. Early evidence (BCG, MIT, Anthropic internal studies) suggests 20–40% productivity gains on targeted tasks — larger than any single intervention in *Fábricas de Productividad*'s track record.
3. **Digital twins and simulation left the lab.** The 2015 paper's systems-dynamics module required commercial iThink/Vensim/AnyLogic licenses. Today, **PySD** (Python) and **SDEverywhere** (Julia/WebAssembly) let you encode, simulate, and *share* stock-and-flow models in a Git repository, with the same fidelity.

A 2026 productivity methodology without a "digital and AI adoption" line of intervention is not a productivity methodology. It is a historical exercise.

### 6.3. Bioeconomy, green productivity, and the just transition <a name="bioeconomy"></a>

The PND 2022–2026 places **bioeconomy, energy transition and decarbonization of exports** at the center of the productive transformation agenda (Articles 225, 226, 258 of Ley 2294 de 2023). This is not merely rhetoric:

- Colombia's biodiversity is genuinely a unique productive asset (2nd most biodiverse country on Earth; ~10% of global species).
- The mining-export dependency is being actively wound down, creating space — and pressure — for knowledge-intensive export lines.
- The **Asignación Ambiental de Regalías CTeI** creates a concrete funding line for green R&D projects.

The 2015 paper framed the choice as "mining rents versus industrial transformation." The 2026 framing is subtler: **how to use declining extractive rents to fund the transition to a knowledge-and-nature-based economy**, before both the rents and the time window close.

### 6.4. Open-source system dynamics (PySD, SDEverywhere) <a name="opensource"></a>

A small but real methodological upgrade: the modelling work described in Chapter 5 of the 2015 paper — stock-and-flow diagrams, delta-based Cobb-Douglas productivity simulations, baseline and optimistic scenarios — can today be done in a Jupyter notebook with **PySD** (which parses Vensim/XMILE models), **SDEverywhere** (which compiles them to JavaScript or Julia), and **Streamlit** for the interactive dashboard. This matters for three reasons: reproducibility, version control, and the ability to open the model to public scrutiny — something no Colombian productivity study, including my own 2015 one, has ever really done.

## 7. An updated methodology proposal <a name="methodology"></a>

Keeping the original three-phase structure — **Structuring → Funding → Execution** — here is how I would rewrite each phase today:

**Structuring phase.**
- *Replace "Master's Degree in Productive Transformation"* with a 12-month **specialization blending industrial engineering, management practices (WMS-style), and applied data/AI**. Host it inside a consortium of Uniandes, EAFIT, Universidad del Valle and UIS, not a single university.
- *Local immersion* becomes an **extended co-location with a host SME**, using *Fábricas de Productividad*'s extensionista protocol as scaffolding but pushing further into R&D and IP generation.
- *International immersion* becomes a **rotation in an OECD peer country's extension service** (e.g., Germany's Fraunhofer-SME program, Korea's KITECH, Portugal's IAPMEI) rather than only academic visits.
- Add a new module: **digital and AI adoption readiness**, including a concrete inventory of cloud/AI tooling, data maturity, and cybersecurity posture.

**Funding phase.**
- *Replace* the old 175% deduction logic with the **Art. 256 (30% discount) + Art. 256-1 (50% fiscal credit for MiPymes)** pairing. The fiscal credit is the unlock for small firms.
- Route co-funding through **SGR convocatorias CTeI** (departmental) and **iNNpulsa calls** (national) rather than bespoke negotiations with Colciencias.
- Build explicit **blended finance**: Bancóldex debt, angel/VC equity (now a real market — Colombia has three unicorns in 2024: Rappi, Habi, Addi), and philanthropic/ESG capital for bioeconomy projects.

**Execution phase.**
- Keep the *Monitoring Board* idea, but run it on a **modern data stack** — every project ships a dashboard, a PySD/SDEverywhere model, and a public KPI log.
- Add a formal **management-practices uplift track** (WMS-benchmarked), not just a technology-transfer track.
- Add an **AI copilot track** that treats generative AI as a standard productivity tool across operations, sales, and back office, the way spreadsheets were treated in the 1990s.
- The *Reinvestment* loop should flow not only back into structuring but also into **open-source public goods** — shared datasets, published models, reusable templates — so that each cohort lowers the cost of the next.

## 8. Closing: what the 23-year-old author would tell the 35-year-old one <a name="closing"></a>

Re-reading the 2015 paper in 2026 is a disorienting experience. The diagnosis is almost embarrassingly durable: 11 years later, the gap is still the gap, the institutional sprawl is still sprawling, R&D spending is still a fifth of what the country keeps promising, and young talent is still insufficiently connected to the productive fabric. In the most depressing reading, very little has changed.

But the operational environment is unrecognizable. A 2026 version of the same methodology would be cheaper to build (open-source tooling), better targeted (firm-level data, WMS, OECD diagnostics), better funded (SGR CTeI, Art. 256-1 fiscal credit, VC market), and — if done right — far more measurable.

If the 2015 paper was a thesis proposing that Colombia *could* close the productivity gap by industrializing its project pipeline, this 2026 companion is more modest: it says that the tools, data and institutions finally exist to *try it seriously*, and that the only remaining bottleneck is the one the original paper always suspected — the **structuring** of good projects, and the **people** capable of structuring them. That part hasn't gotten any easier. But it has finally stopped being the excuse for not starting.

The full original paper remains available [here]({{ site.url }}/blog/productivitygap/). Think of this post as its 2026 errata, appendix and update.

## Appendix A. Legal addendum: mapping the 2015 citations to 2026 <a name="legal-addendum"></a>

This appendix exists because almost every specific statute cited in the 2015 paper has been amended, consolidated, or outright repealed. Anyone trying to *operationalize* the methodology in 2026 needs the current legal footing. Use this as a citation-replacement table rather than a commentary.

### A.1. Tax-benefit architecture for I+D+i

| 2015 citation | Status | 2026 equivalent / replacement |
|---|---|---|
| **Art. 158-1 ET** — 175% deduction on qualifying R&D investment, with a 40% net-income cap | ❌ **Repealed** by **Ley 2277 de 2022 (Art. 96)**. Previously, Ley 1819 de 2016 had already converted it into a *descuento tributario* and Ley 2010 de 2019 kept that structure. | Use **Art. 256 ET** (30% tax discount on CNBT-qualified I+D+i investment) and/or **Art. 256-1 ET** (50% fiscal credit for MiPymes, issued as TIDIS by the DIAN). Both are now the operative articles. |
| **Ley 1450 de 2011, Art. 36** — raised the R&D deduction from 125% to 175% and expanded the net-income cap | ❌ **Repealed** in its tax content via the 2016 → 2019 → 2022 chain of reforms. | Cite instead **Ley 1819 de 2016** (moved the benefit to Art. 256 ET at 25%), **Ley 2010 de 2019** (maintained the structure), and **Ley 2277 de 2022, Arts. 21–22** (raised the discount to 30% and introduced Art. 256-1). |
| **Ley 1739 de 2014** — added "Innovation" to the qualifying categories, making it explicitly I+D+i | ⚠️ **Superseded** but its logic survives: I+D+i is still the qualifying category under Art. 256 ET. | No need to cite Ley 1739 de 2014 anymore; the I+D+i scope is now built directly into Art. 256 ET as amended by Ley 2277 de 2022. |
| **CNBT Acuerdo 08 de 2014** — capped the deductible base at COP 500 billion for that fiscal year | ⚠️ **Superseded.** The CNBT still exists and still issues annual agreements, but the *overall cap* is now set by **CONFIS**, with a reserved share for MiPymes. | Consult the **most recent CNBT agreement** published on `minciencias.gov.co` → *Beneficios Tributarios*, and the annual **CONFIS** resolution setting the cap. |
| **"175% deduction" narrative** | ❌ **Dead letter.** Do not cite. | Rewrite as "30% tax discount (Art. 256 ET) plus 50% fiscal credit for MiPymes (Art. 256-1 ET)." |

### A.2. Institutional architecture

| 2015 citation | Status | 2026 equivalent |
|---|---|---|
| **Colciencias** (*Departamento Administrativo de Ciencia, Tecnología e Innovación*) | ❌ **Dissolved and upgraded** by **Ley 1951 de 2019**. | **Ministerio de Ciencia, Tecnología e Innovación (MinCiencias)**. |
| **Programa de Transformación Productiva (PTP)** — MinCIT's flagship productive-transformation arm | ❌ **Rebranded → merged.** Became *Colombia Productiva* in 2018; absorbed into **iNNpulsa Colombia** under MinCIT in 2024. | **iNNpulsa Colombia** — single delivery arm for productivity, innovation and entrepreneurship programs (including *Fábricas de Productividad y Sostenibilidad*). |
| **Jóvenes Investigadores e Innovadores** (Colciencias scholarship, cited as COP 15.3 bn annual budget) | ❌ **Wound down** in its 2015 form around 2018–2019. | Functionally replaced by **Jóvenes en Investigación** calls funded through **SGR CTeI** (Ley 2056 de 2020) and by specific MinCiencias scholarship programs. There is no single equivalent line-item; calls are episodic and run by MinCiencias + departmental OCADs. |
| **Bancóldex** as project-finance and productive-transformation vehicle | ✅ **Still in force**, expanded role. | Still Bancóldex, now explicitly co-financing iNNpulsa programs and with a dedicated VC/PE fund-of-funds (**Bancóldex Capital**). |

### A.3. Planning framework and royalties

| 2015 citation | Status | 2026 equivalent |
|---|---|---|
| **Plan Nacional de Desarrollo 2010–2014** (Ley 1450 de 2011) — used as the general policy umbrella | ❌ **Expired.** Replaced three times since. | **PND 2014–2018** (Ley 1753 de 2015) → **PND 2018–2022** (Ley 1955 de 2019) → **PND 2022–2026 "Colombia, potencia mundial de la vida"** (**Ley 2294 de 2023**), currently in force. |
| **Plan Nacional de Desarrollo 2014–2018** (referenced as "Bases del PND 2014–2018" from DNP) | ❌ **Expired.** | Same chain — current statute is **Ley 2294 de 2023**. |
| **"10% of royalties to Science, Technology and Innovation"** (Ministerio de Educación, 2012; from the original SGR created by Acto Legislativo 05 de 2011 and Ley 1530 de 2012) | ✅ **Preserved and strengthened.** The 10% CTeI earmark was kept and the governance fully rebuilt. | **Acto Legislativo 05 de 2019** + **Ley 2056 de 2020** — current SGR statute. Adds a **minimum 2 percentage points for environmental CTeI**, creates the **OCAD CTeI** chaired by MinCiencias, and mandates **convocatorias públicas, abiertas y competitivas** for all project approvals. Decreto 1821 de 2020 reglaments operational details. |

### A.4. New legislation with no 2015 counterpart

These are instruments that **did not exist** (or existed only in nascent form) in 2015 and which any updated methodology must incorporate:

- **Ley 1951 de 2019** — creates **MinCiencias**, with cabinet-level rank and a dedicated budget line.
- **Acto Legislativo 05 de 2019** + **Ley 2056 de 2020** — overhauls the SGR and formalizes the OCAD CTeI route with competitive calls.
- **Ley 2101 de 2021** — progressive reduction of the workweek from 48 to **42 hours** by 15 July 2026, without salary reduction. Relevant because it mechanically reshapes labor productivity measurement and creates a forcing function for automation/digitalization investment.
- **Ley 2277 de 2022** — the most consequential tax reform for CTeI since the 2015 paper: repeals Art. 158-1, raises the Art. 256 discount to 30%, and introduces **Art. 256-1 (fiscal credit for MiPymes)**.
- **Ley 2294 de 2023** (PND 2022–2026) — Arts. **225** (MinCiencias institutional strengthening / Agencia Nacional CTeI), **226** (mission-oriented innovation policy), **258** (0.5% R&D/GDP target for national-government entities), **170–171** (IP from publicly-funded research; Open Science policy).

### A.5. Practical citation rules for anyone reusing the 2015 methodology

If you are quoting or building on the original paper today, apply these substitutions *mechanically*:

1. Every "175% deduction" → "30% tax discount (Art. 256 ET) / 50% fiscal credit for MiPymes (Art. 256-1 ET), as amended by Ley 2277 de 2022."
2. Every "Colciencias" → "MinCiencias (since Ley 1951 de 2019)."
3. Every "PTP" or "Programa de Transformación Productiva" → "iNNpulsa Colombia (since the 2024 merger with Colombia Productiva)."
4. Every "PND 2010–2014" or "PND 2014–2018" → "PND 2022–2026 (Ley 2294 de 2023)" unless you are explicitly doing historical analysis.
5. Every reference to the old SGR (Ley 1530 de 2012) → "SGR reformed by Acto Legislativo 05 de 2019 and Ley 2056 de 2020, with the CTeI allocation approved by the OCAD CTeI via competitive calls."
6. Add a standing reference to **CONFIS** as the cap-setting authority for R&D tax benefits (it was not the binding actor in 2015).

With those six substitutions, the 2015 methodology is legally re-grounded for 2026 without rewriting its conceptual core.

## References <a name="refs"></a>

- Bermúdez, N., and Harker, A. (2016). *Factors associated with the quality of school management practices in Colombia*. Universidad de los Andes / World Management Survey.
- Cabrera, C. E. (2015). *Methodology to Massively Structure Investment Projects in R&D to Close the Productivity Gap*. [Paper]({{ site.url }}/files/blog/productivitygap/Tesis ENG.pdf).
- Congreso de la República de Colombia. (2011). *Ley 1450 de 2011 — Plan Nacional de Desarrollo 2010–2014* (original basis of the 175% deduction under Art. 158-1 ET; repealed in this respect by Ley 2277 de 2022).
- Congreso de la República de Colombia. (2014). *Ley 1739 de 2014 — reforma tributaria* (added "Innovación" to the qualifying categories; superseded).
- Congreso de la República de Colombia. (2016). *Ley 1819 de 2016 — reforma tributaria estructural* (converted the R&D deduction into a 25% descuento tributario under Art. 256 ET).
- Congreso de la República de Colombia. (2019). *Acto Legislativo 05 de 2019 — que modifica el artículo 361 de la Constitución Política (Sistema General de Regalías)*.
- Congreso de la República de Colombia. (2019). *Ley 1951 de 2019 — por la cual se crea el Ministerio de Ciencia, Tecnología e Innovación*.
- Congreso de la República de Colombia. (2019). *Ley 2010 de 2019 — Ley de Crecimiento* (mantuvo la estructura del descuento por I+D+i).
- Congreso de la República de Colombia. (2020). *Ley 2056 de 2020 — por la cual se regula la organización y funcionamiento del Sistema General de Regalías*.
- Congreso de la República de Colombia. (2021). *Ley 2101 de 2021 — reducción gradual de la jornada laboral*.
- Congreso de la República de Colombia. (2022). *Ley 2277 de 2022 — reforma tributaria para la igualdad y la justicia social* (Arts. 21–22 y 96: modifica Art. 256 ET, introduce Art. 256-1 ET, deroga Art. 158-1 ET).
- Congreso de la República de Colombia. (2023). *Ley 2294 de 2023 — Plan Nacional de Desarrollo 2022–2026 "Colombia, potencia mundial de la vida"*.
- Presidencia de la República. (2020). *Decreto 1821 de 2020 — reglamentario del SGR (ciclo de proyectos CTeI)*.
- DANE. (2025). *Medición de empleo informal — trimestre móvil*.
- Growth Lab, Harvard Kennedy School. (2024). *Atlas of Economic Complexity 10.0*. [atlas.hks.harvard.edu](https://atlas.hks.harvard.edu/rankings).
- iNNpulsa Colombia / Colombia Productiva. (2024). *Resultados acumulados del programa Fábricas de Productividad y Sostenibilidad*.
- International Monetary Fund. (2024). *Colombia: Selected Issues — Unpacking Low Productivity*. IMF Country Report 2024/083.
- OECD. (2019). *Production Transformation Policy Review of Colombia*. OECD Development Pathways.
- OECD. (2021, 2023). *Economic Policy Reforms: Going for Growth — Colombia chapters*.
- OECD. (2024). *OECD Reviews of Labour Market and Social Policies: Colombia 2024*.
- Scur, D., Sadun, R., Van Reenen, J., Lemos, R., and Bloom, N. (2021). *The World Management Survey at 18: Lessons and the Way Forward*. NBER Working Paper No. 28524.
- WIPO. (2024, 2025). *Global Innovation Index — Colombia country profiles*.
