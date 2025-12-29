## 1. Functions
A **function** is a relation between two sets where each element in the domain (input set) is related to exactly one element in the codomain (output set).

Types of Functions
1. **One-to-One (Injective)** --> Each element in the codomain is mapped by at most one element from the domain. No two different inputs produce the same output
2. **Onto (Surjective)** --> Every element in the codomain is mapped by at least one element from the domain. 
3. **Both (Bijective)** --> Function is both one-to-one and onto
## 2. Rules of Derivatives
1. **Constant Rule**: d/dx(c) = 0
2. **Power Rule**: d/dx(xⁿ) = n·xⁿ⁻¹
3. **Sum/Difference Rule**: d/dx[f(x) ± g(x)] = f'(x) ± g'(x)
4. **Product Rule**: d/dx[f(x)·g(x)] = f'(x)·g(x) + f(x)·g'(x)
5. **Quotient Rule**: d/dx[f(x)/g(x)] = [f'(x)·g(x) - f(x)·g'(x)]/[g(x)]²

## 3. Finding Derivatives

**Example 1**: y = (2 + 5x)² / x³ - 1

- Use quotient rule and chain rule
- Let u = (2 + 5x)², v = x³ - 1
- u' = 2(2 + 5x)·5 = 10(2 + 5x)
- v' = 3x²
- dy/dx = [10(2 + 5x)(x³ - 1) - (2 + 5x)²·3x²] / (x³ - 1)²

**Example 2**: y = (x-1)(x² - 2x)/x⁴

- Simplify first: y = (x³ - 3x² + 2x)/x⁴ = x⁻¹ - 3x⁻² + 2x⁻³
- dy/dx = -x⁻² + 6x⁻³ - 6x⁻⁴

**Example 3**: r = 12/θ - 4/θ³ + 1/θ⁴

- r = 12θ⁻¹ - 4θ⁻³ + θ⁻⁴
- dr/dθ = -12θ⁻² + 12θ⁻⁴ - 4θ⁻⁵

**Example 4**: y = (2x - 5)⁻¹(x² - 5x)⁶

- Use product rule and chain rule
- Let u = (2x - 5)⁻¹, v = (x² - 5x)⁶
- u' = -(2x - 5)⁻² · 2 = -2(2x - 5)⁻²
- v' = 6(x² - 5x)⁵ · (2x - 5)

**Example 5**: y = sin(t/√(t+1))

- Let u = t/√(t+1)
- dy/dt = cos(u) · du/dt
- Find du/dt using quotient rule

## 4. L'Hôpital's Rule
When to Use? For Indeterminate forms: 0/0, ∞/∞, 0·∞, ∞-∞, 1^∞, 0⁰, ∞⁰

If lim[x→a] f(x)/g(x) gives 0/0 or ∞/∞, then: lim[x→a] f(x)/g(x) = lim[x→a] f'(x)/g'(x)

**Example 1**: lim[x→0] (x cot x)

- Rewrite as lim[x→0] x·(cos x/sin x) = lim[x→0] (x cos x)/sin x
- This gives 0/0 form
- Apply L'Hôpital's rule

**Example 2**: lim[x→0] (1 - cos x)/(x + x²)

- This gives 0/0 form
- Apply L'Hôpital's rule: lim[x→0] sin x/(1 + 2x) = 0/1 = 0

## 5. Sandwich Theorem (Squeeze Theorem)
If f(x) ≤ g(x) ≤ h(x) for all x in some interval containing a (except possibly at a), and if: lim[x→a] f(x) = lim[x→a] h(x) = L

Then: lim[x→a] g(x) = L

Given: 1 - x²/4 ≤ u(x) ≤ 1 + x²/2 for all x ≠ 0 Find: lim[x→0] u(x)

- lim[x→0] (1 - x²/4) = 1 - 0 = 1
- lim[x→0] (1 + x²/2) = 1 + 0 = 1
- Therefore: lim[x→0] u(x) = 1

## 7. Anti-derivatives (Integration)

- ∫ xⁿ dx = xⁿ⁺¹/(n+1) + C (n ≠ -1)
- ∫ 1/x dx = ln|x| + C
- ∫ eˣ dx = eˣ + C
- ∫ sin x dx = -cos x + C
- ∫ cos x dx = sin x + C
- ∫ sec²x dx = tan x + C
- ∫ sec x tan x dx = sec x + C

**Example 1**: ∫ sec x(sec x + tan x) dx

- = ∫ (sec²x + sec x tan x) dx
- = tan x + sec x + C

**Example 2**: ∫ (x² - 2x + 5) dx

- = x³/3 - x² + 5x + C

**Example 3**: ∫ sin²x dx

- Use identity: sin²x = (1 - cos 2x)/2
- = ∫ (1 - cos 2x)/2 dx = x/2 - sin 2x/4 + C

## 8. Gradient, Divergence and Curl

> **Gradient** --> Take partial derivatives of the given scalar function then combine the result into a vector.
$$
\text{Gradient} \quad \nabla f = \left\langle \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right\rangle
$$
> **Divergence** --> Take partial derivatives of the given vector then add the result to get a scalar.
$$
\text{Divergence} \quad \nabla \cdot \vec{F} = \frac{\partial F_1}{\partial x} + \frac{\partial F_2}{\partial y} + \frac{\partial F_3}{\partial z}
$$
> **Curl** --> Put values into the determinant to get a resulting vector.
$$
\text{Curl} \quad \nabla \times \vec{F} = \left|\begin{matrix}
\hat{i} & \hat{j} & \hat{k} \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
F_1 & F_2 & F_3
\end{matrix}\right|
$$

Example 1. Find the gradient of $f(x, y, z) = x^2y + yz^3$.
**Solution:**
$$
\frac{\partial f}{\partial x} = 2xy, \quad \frac{\partial f}{\partial y} = x^2 + z^3, \quad \frac{\partial f}{\partial z} = 3yz^2
$$
$$
\nabla f = \langle 2xy, x^2 + z^3, 3yz^2 \rangle
$$

Example 2. Find the divergence of $\vec{F} = \langle x^2, y^2, z^2 \rangle$.
**Solution:**
$$
\frac{\partial F_1}{\partial x} = 2x, \quad \frac{\partial F_2}{\partial y} = 2y, \quad \frac{\partial F_3}{\partial z} = 2z
$$
$$
\nabla \cdot \vec{F} = 2x + 2y + 2z
$$

Example 3. Find the curl of $\vec{F} = \langle yz, xz, xy \rangle$.
**Solution:**
$$
\nabla \times \vec{F} = \begin{vmatrix}
\hat{i} & \hat{j} & \hat{k} \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
yz & xz & xy
\end{vmatrix}
$$
$$
= \hat{i} \left( \frac{\partial (xy)}{\partial y} - \frac{\partial (xz)}{\partial z} \right)
- \hat{j} \left( \frac{\partial (xy)}{\partial x} - \frac{\partial (yz)}{\partial z} \right)
+ \hat{k} \left( \frac{\partial (xz)}{\partial x} - \frac{\partial (yz)}{\partial y} \right)
$$
$$
= \hat{i}(x - x) - \hat{j}(y - y) + \hat{k}(z - z) = \langle 0, 0, 0 \rangle
$$
$$
\text{Curl is zero ⇒ conservative field.}
$$


## 9. Euler's Theorem
If f(x,y) is a homogeneous function of degree n, then: x(∂f/∂x) + y(∂f/∂y) = nf

**Example 1**: f(x,y) = x sin y + y sin x + xy

- Check if homogeneous and verify Euler's theorem

**Example 2**: f(x,y) = x² + y(sin x - x²)

- Find partial derivatives and verify the theorem
