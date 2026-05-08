# From Drug Substance to Patient

**Backlinks:** [downstream/overview.md](overview.md) | [_index.md](../../../_index.md)  
**Related:** [downstream/uf_df.md](uf_df.md) | [manufacturing/overview.md](../../../manufacturing/overview.md) | [regulatory/ich_guidelines.md](../../../regulatory/ich_guidelines.md)

---

## The Last Mile of Biopharmaceutical Manufacturing

The drug substance (DS) that exits UF/DF is a bulk protein solution — the active ingredient in its final buffer, at its final concentration, meeting all drug substance specifications. It is not yet a product that a patient can receive. The remaining steps — bulk drug substance handling, drug product manufacturing (fill-finish), packaging, quality release, storage, and distribution — constitute the journey from DS to patient.

MSAT's direct responsibility typically ends at or before drug substance release. However, understanding the full supply chain is important because:
- Drug substance stability during frozen storage and shipping affects what arrives at fill-finish
- Drug product manufacturing decisions (formulation adjustments, fill conditions) can affect CQAs
- Supply chain disruptions affect scheduling decisions MSAT supports

---

## Bulk Drug Substance (BDS)

### Sterile Filtration

Before bulk filling, the drug substance is filtered through a 0.2 µm sterilizing-grade filter (e.g., Millipore Millipak, Sartorius Sartopore) in a cleanroom environment. This is the **bioburden reduction / sterile filtration** step that brings the DS into sterile condition.

Sterile filtration adds the final aggregate filter step — the 0.2 µm membrane also removes subvisible particles above that size. However, this is not its primary purpose (particles must already be low from earlier steps; a heavily particulate solution would clog this filter rapidly).

The sterile filtration step requires:
- Filter integrity test before use (forward flow test, diffusion test) to confirm no defects
- Post-use filter integrity test to confirm the filter was not damaged during use
- Environmental monitoring in the filling suite (viable and non-viable particle counts)

### Bulk Filling

The sterile-filtered DS is filled into bulk containers:
- **Stainless steel tanks (biocontainers):** Traditional; reusable; require CIP/SIP (clean-in-place/steam-in-place)
- **Single-use bioprocess bags:** Disposable; eliminate CIP/SIP; reduce cross-contamination risk; increasingly standard for BDS storage

Containers are filled under aseptic conditions in a Grade A (ISO 5) environment within a Grade B (ISO 7) background.

Fill volume must account for overfill (to ensure the labeled quantity after any volume loss) and must be within the validated fill volume specification for the container.

### BDS Storage and Stability

Bulk drug substance is typically frozen and stored at **−80°C** (ultra-low temperature). Some products with higher stability can be stored at −20°C or even 2–8°C (refrigerated).

Frozen storage provides:
- Long-term stability (typically 24–36 months or longer)
- Flexibility to decouple drug substance manufacturing from drug product fill-finish

**Freeze-thaw considerations:**
- Rapid freezing can cause ice crystal formation that damages protein structure (though slow, controlled freezing avoids this by controlled nucleation)
- Freeze concentration: as ice forms, solutes concentrate in the remaining liquid phase. If the formulation lacks adequate cryoprotectant (sucrose, trehalose), this can drive aggregation.
- Freeze-thaw cycling: BDS is typically freeze-thawed only once; validated studies confirm acceptable quality after the maximum number of freeze-thaw cycles.

**Shipping:** Frozen BDS is shipped from the drug substance manufacturing site to the fill-finish site in dry ice or LN2 vapor shippers with temperature logging. Shipping validation confirms the drug substance remains frozen and within specification throughout the shipping journey.

---

## Drug Product Manufacturing (Fill-Finish)

### Compounding (Formulation)

If the bulk drug substance arrives at the fill-finish site in a concentrated form, it may be diluted with formulation buffer to the target drug product concentration. Excipients (surfactant, additional stabilizers) may be added at this stage.

The final drug product formulation is defined in the regulatory filing and is not typically changed post-approval without a regulatory submission.

### Sterile Fill-Finish

The compounded drug product is sterile-filtered and filled into the final primary container (vial, pre-filled syringe, cartridge):

- **Vials:** Most common for biologics. Glass vials (Type I borosilicate glass), rubber stoppers (chlorobutyl or bromobutyl), aluminum crimp seals.
- **Pre-filled syringes:** Increasingly preferred for patient convenience (self-administration). Glass or polymer barrels; rubber plunger; needle or luer lock.
- **Autoinjectors / pens:** Secondary device around a pre-filled syringe; for subcutaneous self-administration.

Fill-finish operations occur in a highly controlled cleanroom environment:
- **Grade A / ISO 5:** The filling zone directly above the open vial/syringe. Unidirectional (laminar) airflow to prevent particle contamination.
- **Grade B / ISO 7:** The background environment around the Grade A zone.
- **Grade C / ISO 8:** Preparation areas.

### Lyophilization (Freeze-Drying)

Some biologics are lyophilized (freeze-dried) to improve stability for products that are unstable in liquid form. The filled vials are loaded into a lyophilizer, frozen, then subjected to primary drying (water removed by sublimation under vacuum) and secondary drying (bound water removed).

The resulting lyophilized cake is reconstituted by the healthcare provider or patient before administration.

Lyophilization is a complex, time-consuming step that is not required for all products. mAbs are often stable enough in liquid formulation at 2–8°C. However, some products (particularly those requiring room-temperature storage or long shelf life) may require lyophilization.

### Inspection and Release

After fill-finish, each container is inspected:
- **Visual inspection** (automated or manual): Check for visible particles, cracks, stopper position, fill volume.
- **100% inspection** of primary containers for visible particles, cosmetic defects.

The drug product batch is then tested against all release specifications:
- Potency
- Purity (SEC, CE-SDS, icIEF)
- Identity (intact mass or peptide map identity test)
- Safety (sterility, endotoxin, subvisible particles USP <788>)
- Quantity (fill volume, protein concentration)
- Appearance (color, clarity, opalescence)

The QA department reviews all manufacturing and testing records (batch record review). Upon successful review and passing all specifications, the lot is released for distribution.

---

## Regulatory Submissions and the Supply Chain

### Certificate of Analysis (CoA)

Each released lot is accompanied by a Certificate of Analysis listing all release test results with acceptance criteria. The CoA follows the lot through distribution.

### Cold Chain

Most biologic drug products are distributed at 2–8°C (refrigerated cold chain). Maintaining the cold chain from manufacturing through distribution to the clinic or patient is a supply chain and logistics requirement. Temperature excursions are investigated and may require stability data to support continued use.

### Patient Administration

The route of administration for most mAbs:
- **Intravenous (IV) infusion:** Diluted in 0.9% NaCl or 5% dextrose and infused over 30 min to 2 h. Requires clinic or hospital.
- **Subcutaneous (SC) injection:** Concentrated formulation (often 100–200 mg/mL) injected with a small-volume pre-filled syringe or autoinjector. Patient self-administration is possible. Growing preferred route for chronic conditions.

The formulation (concentration, excipients, volume) and the primary container (vial vs. pre-filled syringe) are chosen with the intended administration route in mind. These choices are made during product development and constrain upstream and downstream manufacturing decisions (e.g., a subcutaneous product requires higher concentration → more demanding UF/DF → more aggregation risk → formulation must be more robust).

---

## MSAT's Connection to This Stage

Although MSAT typically does not own fill-finish or distribution operations, it is involved in:

- **Drug substance specification setting:** MSAT defines the DS specifications that determine whether the DS is suitable for fill-finish
- **Stability program support:** MSAT generates data for the DS stability dossier (ICH Q5C) that defines the DS shelf life
- **Comparability across the supply chain:** If a DS manufacturing change is made, comparability to prior DS (and to drug product made from that DS) must be demonstrated — an MSAT-led activity
- **Deviation investigation:** If a fill-finish deviation is traced to a DS quality issue, MSAT leads the technical investigation
- **Tech transfer to fill-finish sites:** When DS manufacturing moves to a new site, the DS must be shipped to a qualified fill-finish site — a tech transfer exercise with MSAT involvement
