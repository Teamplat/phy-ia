# Physics IA: voice rewrite (prose only)

Tables, equations, method steps, figure captions and references are unchanged.


## 1.1 Introduction

During a lesson on simple harmonic motion I noticed that a pendulum with a light bob slowed down within minutes, while one with a heavier bob kept swinging much longer. I wanted to know whether the damping constant of a pendulum really depends on the mass of its bob, and why.

A real pendulum loses energy to air drag on the bob, air drag on the string and friction at the pivot, and each of these depends on mass in a different way (§1.3). If I can tell which one dominates, that also tells me whether a heavier bob or a better suspension does more to reduce the energy loss.

I measure γ for five bob masses (50 to 250 g) with string length and release angle fixed, and test whether the data follow the simple γ ∝ 1/m prediction or the extended model γ = γ₀ + bₛ/(2m), which includes damping that does not depend on mass.


## 1.3 Theory: SHM (after T = 0.803 s)

The sin 15° correction is −0.76%, shifting the effective restoring constant by less than 1%, so the SHM model holds at this release angle.


## 1.3 Damped Motion

If the aerodynamic drag on the bob is proportional to its velocity (the linear drag regime), the drag force is F = −bẋ, with b the linear drag coefficient (kg s⁻¹). Putting this into Newton's second law gives the equation of motion:


## 1.3 Drag Regime (after Re ≈ 533)

Re ≈ 533 lies in the mixed-drag regime, between the Stokes regime (Re ≪ 1; Stokes, 1851) and fully turbulent flow (Re ≫ 1000), and drag there has both a viscous and an inertial part. At Re ≈ 533 the linear model is only an approximation. What the two-point method gives for γ is really an effective average over the amplitude range of each trial, and I come back to this as a source of systematic uncertainty in §4.


## 1.3 Mass Dependence and Extended Model

Energy is lost through three mechanisms, and they do not depend on mass in the same way:

(i) Aerodynamic drag on the bob. The 50 g discs all have the same diameter (25 ± 0.5 mm) and the bob swings sideways, so the area facing the air is S = d × h, where h is the height of the disc stack. Every disc adds the same thickness and the same mass, and S and m grow together in proportion to the number of discs, giving S/m ≈ constant across all masses. The bob-drag contribution, γ_bob ≈ (ρC_d Sv)/(4m), then stays roughly the same as mass increases and shows up as the intercept γ₀ of the γ vs 1/m graph.

(ii) Aerodynamic drag on the string. The drag force on the string depends on string geometry and air speed but not on bob mass. The deceleration it causes is therefore inversely proportional to mass, a = F_string/m, and the string's contribution to γ scales as 1/m, producing the gradient term bₛ/(2m) in the extended model.

(iii) Pivot friction. Friction at the clamp is proportional to mg. That gives a constant deceleration and linear rather than exponential decay, and its main effect is scatter in γ.


## 1.3 (after the extended model equation)

Plotting γ against 1/m should then give a straight line with gradient k = bₛ/2 (kg⁻¹ s⁻¹) and intercept γ₀ (s⁻¹). The simple γ ∝ 1/m model is just the special case γ₀ = 0.


## 1.4 Hypothesis

From the extended model I predict that γ vs 1/m will be linear with a positive gradient k = bₛ/2, plus a positive intercept γ₀ > 0 from bob air drag. The gradient term should dominate at small masses. If tested statistically, γ₀ should come out significantly above zero.


## 2.1 Raw Data

The initial amplitude is A₀ = 4.1 cm ± 0.05 cm for all trials, with the uncertainty coming from the ±0.5 mm ruler resolution and ±0.5 mm placement precision. Figure 2 shows the decay curve for each mass together with the 25 trial endpoints.


## 2.2 Sample Calculation (last line)

Most of the uncertainty comes from the final amplitude: 6.25% for A(t), against 1.2% for A₀ and 0.015% for t.


## 2.3 Processed Data

For each mass I report the half-range of the five trials, rounded up to the nearest 0.0001 s⁻¹, because it shows the real trial-to-trial spread (for 50 g: (0.0158 − 0.0132)/2 = 0.0013 s⁻¹; the standard deviation of the five trials, 0.0010 s⁻¹, is similar). Single-trial propagated uncertainties (§2.2) vary widely because A(t) is small. For 50 g they range from 0.0009 s⁻¹ (Trial 3, A(t) = 0.8 cm) up to about 0.0026 s⁻¹ (Trial 2, A(t) = 0.3 cm).


## 2.4 Gradient Uncertainty

To get an uncertainty in the gradient that does not rely on the regression software, I draw the steepest and shallowest lines that pass through the error bars of the two extreme data points (50 g and 250 g).


## 2.4 (after Δk)

The max/min method gives k = (6.44 ± 1.00) × 10⁻⁴ kg⁻¹ s⁻¹ and the LINEST regression gives k = (6.27 ± 0.41) × 10⁻⁴ kg⁻¹ s⁻¹ and the two agree. I use the LINEST value in all further calculations because it uses all five points. The best-fit, maximum and minimum gradient lines are shown in Figure 3.


## 2.5 Linear Regression

R² = 0.987 means the linear model accounts for 98.7% of the variation in γ. That is not the whole picture though. The residuals run −, +, +, −, −, so the data may curve slightly, and the best-fit line passes outside two error bars: at 250 g it predicts 0.0046 s⁻¹ against a measured 0.0042 ± 0.0003 s⁻¹, and at 150 g it predicts 0.0063 s⁻¹ against 0.0070 ± 0.0006 s⁻¹ (Figure 3). The minimum-gradient line misses the 150 g error bar as well. Within the measured uncertainties the straight-line model does not fully describe the data. The gradient k = bₛ/2 = (6.27 ± 0.41) × 10⁻⁴ kg⁻¹ s⁻¹ gives bₛ = (1.25 ± 0.08) × 10⁻³ kg s⁻¹ (±6%). The intercept γ₀ = (2.15 ± 0.45) × 10⁻³ s⁻¹ is 4.8 standard errors above zero (Z = 2.15/0.45 ≈ 4.8), which rules out the simple γ ∝ 1/m model (γ₀ = 0).


## 2.6 Damping Mechanism

Comparison with theoretical string drag. Mohazzabi and Shankar (2017) model the drag on each short element of string as proportional to the string diameter and to the element's local speed, which goes from zero at the pivot up to the bob's speed at the bottom. Integrating the drag torque along the string, the string acts like a linear drag coefficient at the bob of b_s = kDL/3, where kD is the drag force per unit length per unit speed. Estimating kD from the drag on a cylinder in crossflow at the bob's maximum speed, kD ≈ ½ C_n ρ d_s v_max, gives:

With C_n ≈ 2 for a cylinder in crossflow, ρ = 1.20 kg m⁻³, an estimated string diameter d_s ≈ 0.001 m (not measured), L = 0.160 m and v_max = 0.32 m s⁻¹:

The experimental bₛ = 1.25 × 10⁻³ kg s⁻¹ is approximately 60 times larger than this estimate (1.25 × 10⁻³ / 2.0 × 10⁻⁵ ≈ 60). Using v_max for the whole string already overestimates the string drag, so the real gap is probably larger still. A factor of 60 is far beyond the ±6% experimental uncertainty, and air drag on the string alone cannot explain the observed 1/m term in the data. Even if the twine were twice as thick as estimated, string drag would still be about 30 times too small, and the conclusion does not depend on the exact diameter.

This investigation does not explain where the rest of the gradient comes from. Energy lost where the string bends at the clamp is one possible cause, and the stacked-disc bob not behaving as a point mass is another. I tested neither here. Extension 1 (§4.3) describes how the string contribution could be tested directly.


## 2.6 Comparison with the intercept

Comparison with the intercept. γ₀ is the part of the damping that does not depend on mass, and the theoretical estimate for bob air drag is:

For one disc (50 g): γ_bob ≈ (1.20)(1.0)(0.025 × h₁)(0.32) / (4 × 0.050) = 0.048 × h₁ s⁻¹, where h₁ is the thickness of one disc in metres. I did not measure the disc thickness, so I estimated it from the disc mass and an assumed density of steel (ρ_steel ≈ 7850 kg m⁻³; Engineering ToolBox, n.d.): h₁ ≈ m / (ρ_steel π r²) = 0.050 / (7850 × π × 0.0125²) ≈ 0.013 m (about 12 to 13 mm). That gives γ_bob ≈ 0.048 × 0.013 ≈ 6 × 10⁻⁴ s⁻¹, about 30% of γ₀. With h₁ estimated, this is an order-of-magnitude value only.

Since S/m is constant, γ_bob is the same for every mass and sits inside γ₀. On this estimate bob air drag explains roughly 30% of γ₀, and the origin of the other 70% is not explained by this investigation.


## 3. Conclusion

Direct answer to the research question: The damping constant γ decreases as bob mass increases and follows the extended model γ = γ₀ + k/m, where k = (6.27 ± 0.41) × 10⁻⁴ kg⁻¹ s⁻¹ and γ₀ = (2.15 ± 0.45) × 10⁻³ s⁻¹ (R² = 0.987).

Going from 50 g to 250 g, γ drops from 0.0145 s⁻¹ to 0.0042 s⁻¹, a factor of 3.5 reduction. Doubling the mass from 100 to 200 g takes γ from 0.0087 to 0.0050 s⁻¹, a factor of 1.74, close to but not exactly 2, consistent with a non-zero intercept γ₀.

The hypothesis was partially correct. γ vs 1/m was broadly linear (R² = 0.987), although the best-fit line misses the 150 g and 250 g error bars, so the data are not fully linear within their uncertainties. γ₀ > 0 was confirmed (Z = 4.8). The gradient term does dominate at small mass as predicted: at 50 g, k/m = 6.27 × 10⁻⁴ × 20 = 0.0125 s⁻¹, about 5.8× γ₀. Where the hypothesis went wrong is the source of the gradient. I assumed it came from air drag on the string, but the measured bₛ is about 60 times larger than the theoretical string drag, and what causes the gradient remains unexplained.

For the intercept, bob air drag accounts for roughly 30% of γ₀ (γ_bob ≈ 6 × 10⁻⁴ s⁻¹), using a disc thickness estimated from the disc mass and an assumed steel density. The rest of γ₀ is not explained.


## 4.1 Strengths

R² = 0.987 shows a strong overall trend between γ and 1/m, even though the line does not pass through every error bar (§2.5). Five independent repeat trials per mass let me compute both a mean and a half-range uncertainty for each γ, so the error bars reflect real trial-to-trial variation and not only instrument resolution. The mass range of 50 to 250 g (a factor of 5) gave a wide spread in 1/m (4 to 20 kg⁻¹), which makes the gradient well determined, although the 50 g point at 20 kg⁻¹ has a large pull on it (Table 4).


## 4.2 (below Table 7)

Two inputs to the mechanism analysis in §2.6 were estimated rather than measured: the string diameter (≈ 1 mm) and the disc thickness (≈ 13 mm, from the disc mass and an assumed density). The string-drag and bob-drag comparisons are therefore order-of-magnitude estimates. Improvement: measure both with calipers.

Effective pendulum length. The 0.160 m was the string length between the knot at the clamp and the knot at the hook, not the distance to the bob's centre of mass, and I did not re-tie the string as discs were added. Each disc adds roughly 13 mm to the stack, so from 50 g to 250 g the distance to the centre of mass grew by roughly 26 mm. For the heaviest bob that makes the period roughly 7% longer, and the fixed 41 mm release mark gives a slightly smaller release angle, so mass was not the only variable that changed. Improvement: shorten the string after each disc is added so the distance from the clamp to the centre of the stack stays at 0.160 m.


## 4.3 Extensions

Extension 1: Testing whether the string causes the gradient. Repeat the experiment with two strings of different diameter, the twine used here (≈ 1 mm, estimated) and a string about twice as thick (similar C_d). String drag scales with diameter. If the gradient k increases in proportion to string diameter, string drag is responsible for the 1/m term, and if k does not change, the gradient comes from something else, such as losses at the clamp.

Extension 2: Multi-point fit. Track the bob automatically in Tracker and fit ln A against t over 10 or more peaks per trial. Each γ then gets its own fit uncertainty, and you can see directly whether the decay is truly exponential.
