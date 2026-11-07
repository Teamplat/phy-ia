# Your IA vs the 13 Clastify essays

IA: *How does the mass of a cylindrical pendulum bob (50–250 g) affect the damping constant γ of a simple pendulum?* (HL, new syllabus)

Files starting with `new - ` are new-syllabus essays. Files without a prefix are old-syllabus.

---

## 1. How each essay measured damping

| # | Essay | Grade | How damping was measured | Points per trial | Fit to theory |
|---|---|---|---|---|---|
| N1 | A/m vs damping rate | SL 7 | ln θ vs t over 15 peaks, Tracker 60 fps | 15 | γ = 0.118(A/m) + 0.001, R² = 0.994. Intercept explained in one sentence ("clamp friction or string losses") |
| N2 | Bob radius vs damping constant | HL 7 | Photogate speed after 49.75 oscillations, put into a derived formula | 1 (plus A₀) | 2000–3000 % off Stokes' law. Hypothesis refuted (quadratic fits better). Causes listed but not proven |
| N3 | Mass added vs amplitude after 10 T | HL 6 | LoggerPro, one amplitude reading after 10 periods | 1 (plus A₀) | ln x vs 1/m curved and **flattened out at high mass**. Put down to nonlinear drag, citing Peters (2003) |
| N4 | Release angle vs damping coefficient | HL 6 | Two-point formula k = −(2/t) ln(A/A₀) | 1 (plus A₀) | "Pearson r = 0.9934". Weak physics, generic evaluation |
| N5 | Al sheet distance vs magnet decay constant | HL 7 | **Half-life**: time for amplitude to fall to A₀/2, γ = ln2 / t½ | 1 threshold | Power law d^−4.8 vs theory d^−6. **No-plate control trial subtracted** to remove air damping |
| N6 | Mass vs drag coefficient (ping-pong) | HL 7 | Tracker, terminal velocity | — | C_d = 32–86, while the literature range is 0.1–2. Discussed honestly |
| N7 | Sugar concentration vs cup decay time | HL 7 | **Two points on the amplitude envelope** | 2 | Expected an exponential trend, got a linear one. Explained qualitatively |
| N8 | SA/m vs final velocity (Tracker) | HL 7 | Tracker velocity | — | Experimental gradient −2.39 vs theory −1.02 |
| O1 | Effect of mass on damping | HL 7 | One amplitude reading after 10 oscillations | 1 | Own model rejected. Python fit, parallax correction |
| O2 | Wire diameter vs damping constant | HL 7 | ln θ vs t over about 41 oscillations, light gate | ~41 | About 2× Mohazzabi & Shankar's values, put down to clamp friction. **Says max/min lines through the end points only are a weakness** |
| O3 | Surface area of the bob vs damping | HL 7 | ln(amplitude) vs t | 5 | Gradient uncertainties of 60–132 % |
| O4 | Mass on a spring vs damping ratio | HL 7 | ζ vs 1/√m | — | Checked whether the intercept range from the max/min lines includes 0 |
| O5 | Swing rope diameter vs damping constant | HL 6 | ln θ vs t | many | Weak trend, little discussion |

Word counts stated in the new-syllabus 7s: 2813 (magnet), 2832 (ping-pong), 2995 (sugar), 3000 (bob radius), 3000 (SA/m). The release-angle 6 states 2875.

---

## 2. Where the feedback is wrong or overstated

**Point 2 ("the 7s fit the whole decay") is mostly wrong.** Only the A/m essay fits many points. The others:
- Magnet (7) uses one fixed-threshold time (the half-life).
- Sugar (7) uses two points on the envelope.
- Bob radius (7) uses one measurement after 49.75 swings.
- Mass-added (6) uses one reading after 10 T.

So your two-point method is normal for a 7, not a weakness in itself.

**The magnet essay has already used the fix for your endpoint problem.** It timed every trial to the *same* amplitude threshold (A₀/2). That is exactly "read A(t) at a fixed threshold for all masses". You can point to it as precedent. This is a cheaper upgrade than a full ln A vs t refit.

**Your χ² and power-law numbers are correct.** Recomputed: χ² for the line with an intercept = 4.2, χ² for the line through the origin = 14.1, n = −0.76 ± 0.05. The real problem is that no working is shown and they cost words. Cutting them is still right, but not because they're wrong.

---

## 3. Feedback numbers I checked (all correct)

Recomputed from your Table 5 means with ordinary least squares:

| Quantity | Value |
|---|---|
| k | (6.27 ± 0.41) × 10⁻⁴ kg⁻¹ s⁻¹ |
| γ₀ | (2.15 ± 0.45) × 10⁻³ s⁻¹ |
| R² | 0.987 (you wrote 0.988; either is fine to 2 s.f.) |
| Residuals (50 → 250 g) | −0.00020, +0.00028, +0.00067, −0.00029, −0.00046. The −, +, +, − pattern suggests slight curvature |
| SD of the 50 g trials | 0.00100 s⁻¹ |
| Ratio test | 6.0 ± 1.7 vs 5.0 expected, so not significant |
| Z for γ₀ | 2.15 / 0.45 ≈ 4.8 |

I also recomputed all 25 per-trial γ values from A₀, A(t) and t. They match your table.

---

## 4. New problems the feedback missed

1. **Reynolds number.** (1.20)(0.32)(0.025)/(1.8 × 10⁻⁵) = **533**, not 514. Change it everywhere (§1.3, §2.7, the evaluation table).
2. **"40 times larger" is wrong.** 1.25 × 10⁻³ / 6.1 × 10⁻⁵ = **20×**. The feedback says to "keep the 40× gap", but the number itself needs fixing in §2.7 and in the conclusion.
3. **γ_bob arithmetic.** ρC_dSv/(4m) = (1.20)(1.0)(4.91 × 10⁻⁴)(0.32)/(0.200) = **9.4 × 10⁻⁴ s⁻¹**, not 4 × 10⁻⁴. With the correct number, the measured γ₀ is only about 2× the estimate, not 5×. Redo this anyway after fixing the frontal area (diameter × stack height). Then also update §4 Weakness 4 ("less than 1/5 of γ₀").
4. **Hook mass contradiction.** The materials list says the hook mass is "recorded and subtracted". Method step 2 says m includes the hook. The tables show exactly 50, 100, … g. Pick one rule, state the hook mass, and use the real measured masses in the 1/m column.
5. **The Δγ "reported" rule isn't followed.** §2.4 says reported = the larger of the half-range and the propagated value. But 50 g reports 0.0014, which is larger than both 0.0013 and 0.0009. 100 g reports 0.0009, which is larger than the 0.0008 half-range. Either apply the rule exactly or change the rule (e.g. add the two in quadrature).
6. **Max/min lines through the end points only.** The old-syllabus wire-diameter 7 lists this as a weakness of its own method. Either draw the max/min lines so they pass through *all* error bars, or add one line saying it's an approximation.
7. **Table 4 justification row.** It says "five evenly spaced 1/m values (4, 6.67, 10, 20)". Only four values are listed, and they aren't evenly spaced. Even mass steps give *uneven* 1/m spacing: three points crowd below 7 kg⁻¹ and one sits at 20. That point has high leverage on the fit. Say so honestly, or justify the choice in another way.
8. **References:**
   - Peters (2003), arXiv:physics/0306081, is titled **"Nonlinear Damping of the 'Linear' Pendulum"**, not "The pendulum in the 21st century – relic or trendsetter". It argues that real pendulum damping needs nonlinear terms. That supports your Re ≈ 530 / quadratic-drag point. It does *not* support "junction losses are dominant" as far as the abstract shows, so drop that claim (the feedback asked for this too).
   - Wang, Schmitt & Payne (2002), EJP 23(2) 155–164, doi:10.1088/0143-0807/23/2/309, is real, but its title is **"Oscillations with three damping effects"**. The title suggests it covers linear, quadratic and constant-friction damping. If so, it is a good source for your §1.3(iii) claim that friction gives *linear* amplitude decay. Read it before citing it for that.
   - **Garg & Singh (2021)**: the DOI returns 404 and a search found no such paper. **Delete it.**
   - Hamper & Mitchell: the second author is **Emma** Mitchell (E.), not M.
   - Mohazzabi & Shankar (2017) and Stokes (1851): fine.

---

## 5. What your IA does better than the closest essays

- **Mass-added (HL 6)** is the closest essay to yours. It saw the same flattening at large mass but only explained it vaguely, citing Peters. Your extended model γ = γ₀ + k/m turns that flattening into a measured, physically meaningful intercept. That is the main reason yours can be a 7 where that one was a 6. Keep the model and the one-paragraph mechanism argument.
- **Magnet (HL 7)** got credit for separating background damping with a control trial. Your γ₀ does the same job by fitting instead of subtracting. Say that in one sentence.
- **Bob radius (HL 7)** shows that a large disagreement with theory is fine. Your "string drag is ~20× too small" result (see §6 below) is the same kind of honest finding. Leave it unexplained instead of inventing junction friction.

---

## 6. Patterns shared by the 7s (and what they get away with)

**Shared:**
- A research question with values and units.
- One main graph with error bars and a fit.
- An honest statement when theory fails.
- An evaluation table with columns for type, impact and improvement.
- Setup photos or a Tracker screenshot (A/m Figures 1–2; bob radius Figures 2–3).
- About 2800–3000 words.

**Tolerated sloppiness:**
- A/m: the method says 3 trials, the results use 5. Every SD is exactly 0.001. It ends with "Cite the textbook".
- Bob radius: "Invalid source specified" appears throughout.
- Ping-pong: C_d is 30× too large.
- Old blob essay: gradient uncertainties over 100 %.

So the moderators reward reasoning and honesty over polish. Spend your time on the physics points above.

---

## 7. Priority list (in order)

1. Swap in the regression uncertainties (§3). Redo Z = 4.8 and b_s = (1.25 ± 0.08) × 10⁻³ kg s⁻¹.
2. Fix Re = 533, γ_bob (after fixing the frontal area), the 20× ratio, the hook-mass rule and the Δγ rule (§4.1–4.5).
3. Replace junction friction with "unexplained; possible causes are clamp losses or the stack not acting as a point mass, and neither was tested".
4. Fix the references (§4.8). Delete Garg & Singh.
5. Cut the power-law and χ² tests and the "three tests" paragraphs in the conclusion and strengths. Rewrite the ratio test as 6.0 ± 1.7 (not significant).
6. Make the intro match §1.3. Fix the frame rate (60 fps is not slow motion), Δt = ±0.017 s everywhere, one string diameter, Table 4 numbering and the Table 4 1/m row.
7. Add a setup photo, a Tracker screenshot and real Figures 2 and 3 with error bars and max/min lines.
8. **Optional upgrade:** re-read every video at a fixed threshold (e.g. A = 1.0 cm), as the magnet essay did. This is cheaper than a full ln A vs t refit and removes the endpoint question. A full ln A vs t fit for one trial as a worked example is still the strongest option if you have time.
9. Cut the prose to 3000 words or fewer.
