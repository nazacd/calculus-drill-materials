# MATH 111 Past Midterm (Fall 2023, Version A): worked solutions

**Sit the paper first, timed (90 minutes, no notes, no calculator), then mark it with this file.**

The format is 9 written-response questions worth 100 points. The front page says "Only fully complete
answers will be eligible to receive full marks", so every solution below is written the way the revision
lectures ask: `lim` on every line until the limit is taken, PROOF for every "show that", hypotheses named
before a theorem is used, and the point checked on the curve.

Each question ends with **Twins**: problems from this year's materials of the same kind.

---

## Question 1 (17 points)

### (a) (5 pts) lim_{x→0} (2x + 5) / arctan(π/x)

**Answer: the limit does not exist.**

As x → 0, π/x runs to +∞ on one side and to −∞ on the other, so go one-sided.

- x → 0⁺: π/x → +∞, so arctan(π/x) → π/2 (the horizontal asymptote of arctan), and 2x + 5 → 5.
  lim_{x→0⁺} (2x + 5)/arctan(π/x) = 5 / (π/2) = **10/π**.
- x → 0⁻: π/x → −∞, so arctan(π/x) → −π/2.
  lim_{x→0⁻} (2x + 5)/arctan(π/x) = 5 / (−π/2) = **−10/π**.

The one-sided limits exist and are different, so lim_{x→0} does not exist.

*Trap:* "substituting" arctan(π/0). *Twins:* Lecture 19 Q61 (option B there is exactly tan⁻¹(1/x)),
Tutorial 7 warm-up 5, Tutorial 2 P6(d).

### (b) (5 pts) lim_{t→0} (1/t − 1/(t² + t))

**Answer: 1.**

Substitution gives "∞ − ∞", which is an instruction to combine the fractions. For t ≠ 0, −1:

1/t − 1/(t(t + 1)) = ((t + 1) − 1) / (t(t + 1)) = t / (t(t + 1)) = 1/(t + 1).

The limit only looks at t ≠ 0, so the cancellation is allowed:

lim_{t→0} (1/t − 1/(t² + t)) = lim_{t→0} 1/(t + 1) = 1.

*Twins:* Tutorial 2 P5(e) (almost the same problem) and P5(d).

### (c) (7 pts) Squeeze: lim_{x→0} x² arctan(π/x)

**Answer: 0.**

For every x ≠ 0: −π/2 < arctan(π/x) < π/2. Multiply by x² > 0:

−(π/2)x² ≤ x² arctan(π/x) ≤ (π/2)x²  for all x ≠ 0.

lim_{x→0} (−(π/2)x²) = 0 and lim_{x→0} (π/2)x² = 0. The two outer limits are equal, so by the
**Squeeze Theorem**, lim_{x→0} x² arctan(π/x) = 0.

*Trap:* writing lim x² · lim arctan(π/x). The second limit does not exist (part (a)), so the product law
cannot be used. Lecture 17's warm-up is exactly this point. *Twins:* Tutorial 2 P8(a), P8(c);
Lecture 17 warm-up; Lecture 3 (x sin(1/x)).

---

## Question 2 (7 points) ε–δ: prove lim_{x→−2} (3 − x/2) = 4

*Scratch work (backwards):* |(3 − x/2) − 4| = |−1 − x/2| = |x + 2|/2, and |x + 2|/2 < ε ⇔ |x + 2| < 2ε.
So δ = 2ε.

**PROOF.** Let ε > 0. Choose δ = 2ε; then δ > 0.
If 0 < |x − (−2)| < δ, that is 0 < |x + 2| < 2ε, then

|(3 − x/2) − 4| = |x + 2| / 2 < 2ε / 2 = ε.

Hence lim_{x→−2} (3 − x/2) = 4. ∎

A proof needs four things (Week 4 revision, Q26): "Let ε > 0" first; a δ that depends only on ε; a chain
that ends in exactly ε; and the concluding sentence.

*Trap:* with a = −2, the term |x − a| is |x + 2|. *Twins:* Week 4 revision Q26, Tutorial 2 P9(b) and P9(d).

---

## Question 3 (12 points)

g(x) = ax − 3 if x ≤ 4,  g(x) = a|2x³ − 8x²| / (x − 4) if x > 4.

### (a) (5 pts) g continuous everywhere: find a

**Answer: a = −3/28.**

For x > 4: 2x³ − 8x² = 2x²(x − 4) > 0, so |2x³ − 8x²| = 2x²(x − 4) and g(x) = 2ax².
Away from 4, each piece is a polynomial, so g is continuous there. At the seam x = 4:

- g(4) = 4a − 3
- lim_{x→4⁻} g(x) = lim_{x→4⁻} (ax − 3) = 4a − 3
- lim_{x→4⁺} g(x) = lim_{x→4⁺} 2ax² = 32a

g is continuous at 4 ⇔ 4a − 3 = 32a ⇔ **a = −3/28**.

*Trap:* the absolute value must be removed using the sign of what is inside. The factor x − 4 cancels
because x > 4. *Twins:* Lecture 17 Q46, Tutorial 3 P4, Tutorial 2 P6(c), Tutorial 3 P3(b).

### (b) (7 pts) a = 1: find g′(x) and its domain

With a = 1: g(x) = x − 3 for x ≤ 4, and g(x) = 2x² for x > 4.

- For x < 4: g′(x) = 1.
- For x > 4: g′(x) = 4x.
- At x = 4: g(4) = 1, but lim_{x→4⁺} g(x) = 32 ≠ 1, so g is **not continuous** at 4. Since
  differentiable ⇒ continuous, g is **not differentiable** at 4. (Directly: the right-hand difference
  quotient (2(4 + h)² − 1)/h → +∞ as h → 0⁺.)

**g′(x) = 1 for x < 4, g′(x) = 4x for x > 4, and the domain of g′ is (−∞, 4) ∪ (4, ∞).**

*Trap:* writing g′(4) = 1 because the formula says "x ≤ 4". At a seam the definition decides (Lecture 18
Q53). *Twins:* Tutorial 5 P5(a), P5(b); Lecture 18 Q53; Week 4 revision "differentiable ⇒ continuous".

---

## Question 4 (7 points) Prove 3x⁵ − 4x² = 3 has a solution in [1, 2]

**PROOF.** Let f(x) = 3x⁵ − 4x² − 3. f is a polynomial, so it is continuous on ℝ, in particular on
[1, 2].
f(1) = 3 − 4 − 3 = −4 < 0 and f(2) = 96 − 16 − 3 = 77 > 0, so N = 0 lies between f(1) and f(2).
By the **Intermediate Value Theorem** there is c in (1, 2) with f(c) = 0, that is 3c⁵ − 4c² = 3. ∎

Write all four parts: name the function, say why it is continuous, give the two values, state the
conclusion. *Twins:* Tutorial 3 P6, Lecture 17 Q47.

---

## Question 5 (8 points) e^{xy} = x + y: tangent line at (0, 1)

**Answer: y = 1** (that is, y = 0·x + 1).

Check the point: e^{0·1} = 1 = 0 + 1. ✓

Differentiate both sides with respect to x. On the left, the outside is e^u and the inside is xy, which is
a product:

e^{xy} (y + x y′) = 1 + y′.

At (0, 1): e⁰ (1 + 0·y′) = 1 + y′, so 1 = 1 + y′ and y′ = 0.

Tangent: y − 1 = 0·(x − 0), so **y = 1**.

*Trap:* differentiating xy as x y′ (Lecture 18 Q58, option B). *Twins:* Tutorial 5 P10, Lecture 18 Q58,
Week 4 revision Q29.

---

## Question 6 (12 points) dy/dx

### (a) (3 pts) f(x) = √(3x² − 5x + 7)

f′(x) = (6x − 5) / (2√(3x² − 5x + 7)).

### (b) (3 pts) f(x) = 3x² sech(x³)

This needs the product rule, plus the chain rule with (sech u)′ = −sech u tanh u · u′:

f′(x) = 6x sech(x³) + 3x² · (−sech(x³) tanh(x³)) · 3x²
     = 6x sech(x³) − 9x⁴ sech(x³) tanh(x³)
     = 3x sech(x³) (2 − 3x³ tanh(x³)).

### (c) (6 pts) f(x) = x^{tan x}

Both the base and the exponent vary, so use **logarithmic differentiation** (x > 0):

ln y = tan x · ln x
y′/y = sec²x · ln x + tan x · (1/x)
**y′ = x^{tan x} (sec²x ln x + (tan x)/x)**

*Traps:* the power rule (tan x · x^{tan x − 1}) and the exponential rule are both wrong here. Don't forget
to multiply by y at the end (Lecture 18 Q55). *Twins:* Tutorial 5 P7(b); Tutorial 7 P4 (P4(e) proves the
sech formula); Tutorial 6 P9; Lecture 18 Q55.

---

## Question 7 (13 points)

### (a) (8 pts) Absolute max and min of f(x) = x^{2/3}(10 − x) on [−1, 10]

**Answer: the absolute maximum is 12∛2 (= 6∛16 ≈ 15.1), at x = 4. The absolute minimum is 0, at x = 0
and at x = 10.**

f is continuous on the closed interval [−1, 10], so the Closed Interval Method applies.

f(x) = 10x^{2/3} − x^{5/3}. For x ≠ 0:
f′(x) = (20/3) x^{−1/3} − (5/3) x^{2/3} = 5(4 − x) / (3∛x).

Critical points in (−1, 10):
- f′(x) = 0 at x = 4.
- f′ does not exist at x = 0, and 0 is in the domain (a cusp).

| x    | −1                    | 0 | 4                 | 10 |
|------|-----------------------|---|-------------------|----|
| f(x) | (−1)^{2/3}·11 = **11** | 0 | 4^{2/3}·6 = 12∛2 | 0  |

12∛2 > 12 > 11 because ∛2 > 1, so no calculator is needed.

*Traps:* missing x = 0 (f′ does not exist there); (−1)^{2/3} = 1, not −1; forgetting the endpoints.
*Twins:* Lecture 19 Q63 (same shape) and Q64; Tutorial 7 P6(b) and P7(d).

### (b) (5 pts) MVT for f(x) = (2x + 3)/(x + 2) on [−1, 2]

**Answer: c = 0.**

*Hypotheses:* f is a rational function, continuous and differentiable wherever x ≠ −2. Since −2 is not in
[−1, 2], f is **continuous on [−1, 2]** and **differentiable on (−1, 2)**, with

f′(x) = (2(x + 2) − (2x + 3)) / (x + 2)² = 1/(x + 2)².

*Conclusion:* f(−1) = 1 and f(2) = 7/4, so (f(2) − f(−1)) / (2 − (−1)) = (3/4)/3 = 1/4.
1/(c + 2)² = 1/4 ⇔ (c + 2)² = 4 ⇔ c = 0 or c = −4. Only **c = 0** lies in (−1, 2).

*Trap:* keeping c = −4. *Twins:* Tutorial 7 P8(b) and P8(c), Lecture 16.

---

## Question 8 (17 points)

f(x) = (2x² + 3)/(3x² − 12), f′(x) = −22x / (3(x² − 4)²), f″(x) = 22(3x² + 4) / (3(x² − 4)³).
(The given f′ and f″ are correct.) The domain is x ≠ ±2.

### (a) (5 pts) Asymptotes

- **Vertical: x = 2 and x = −2.** The denominator 3(x² − 4) is 0 there, while the numerator is 11 ≠ 0.
  lim_{x→2⁻} f = −∞, lim_{x→2⁺} f = +∞, lim_{x→−2⁻} f = +∞, lim_{x→−2⁺} f = −∞.
- **Horizontal: y = 2/3** at both ends. Divide by x²:
  lim_{x→±∞} (2 + 3/x²)/(3 − 12/x²) = 2/3.

### (b) (6 pts) Critical numbers, increasing and decreasing, local extrema

- f′(x) = 0 ⇔ x = 0. f′ does not exist at ±2, but those are **not in the domain**, so they are not
  critical numbers. **The only critical number is 0.**
- The denominator of f′ is > 0 for x ≠ ±2, so the sign of f′ is the sign of −x.
- **Increasing on (−∞, −2) and (−2, 0); decreasing on (0, 2) and (2, ∞).**
- f′ changes from + to − at 0 (First Derivative Test): **local maximum f(0) = −1/4, at the point
  (0, −1/4).** There is no local minimum.

*Trap:* writing "increasing on (−∞, 0)" across the asymptote. The Increasing/Decreasing Test is about an
interval (see Lecture 19's tan x example).

### (c) (6 pts) Concavity and inflection points

The numerator 22(3x² + 4) is always > 0, so the sign of f″ is the sign of (x² − 4).

- **Concave upward on (−∞, −2) and (2, ∞); concave downward on (−2, 2).**
- **No inflection points.** The concavity changes only at x = ±2, where f is not defined.

*Twins:* Tutorial 3 P9; Tutorial 7 P10–P12; Lecture 19 Q66–Q68.

---

## Question 9 (7 points) f(x) + (f(x))³ = 2 sin(3x), f(0) = 1: find f′(0)

**Intended answer: f′(0) = 3/2.**

Differentiate both sides. Each f brings an f′, and sin(3x) is a chain:

f′(x) + 3(f(x))² f′(x) = 6 cos(3x).

At x = 0: f′(0) (1 + 3·1²) = 6 cos 0 = 6, so f′(0) = 6/4 = **3/2**.

**The data are inconsistent.** At x = 0 the equation says f(0) + f(0)³ = 2 sin 0 = 0, but f(0) = 1
makes the left side 2. The professor's habit "check that the point is on the curve" catches this; it was
probably a typo in the 2023 paper. On an exam, compute what is asked and add one line saying the check
fails.

*Traps:* (f³)′ = 3f² without the f′; (sin 3x)′ = cos 3x without the 3 (Week 4 revision Q28).
*Twins:* Lecture 18 Q60, Week 4 revision Q28, Tutorial 5 P9 and P10.

---

## Where the 100 points went

| Topic | Questions | Points |
|---|---|---|
| Limits: one-sided, ∞ − ∞, Squeeze, linear ε–δ | 1, 2 | 24 |
| Continuity: seam with an absolute value; IVT proof | 3(a), 4 | 12 |
| Derivatives: seam/domain, implicit, chain, hyperbolic, logarithmic differentiation | 3(b), 5, 6, 9 | 34 |
| Applications: Closed Interval Method with a cusp, MVT, curve analysis with asymptotes | 7, 8 | 30 |

## In this year's revision lectures but not on the 2023 paper (do not skip)

- The derivative from the definition (Tutorial 4 P1, Tutorial 5 P6)
- (f⁻¹)′(a) without a formula for f⁻¹ (Lecture 18 Q56, Tutorial 6 P2)
- Limits at ±∞ with √(x²) = |x| (Week 4 revision Q25, Lecture 17 Q50, Tutorial 3 P8)
- ε–δ with the min trick (Week 4 revision Q27, Lecture 17 Q49)
- Inverse trig values and derivatives (Tutorial 7 P1, P2)
- Rolle: exactly one root; MVT bounds (Tutorial 7 P9, Lecture 19 Q65)
- Exponential and logarithm limits, and log laws (Tutorial 6 P3, P10, P11)
