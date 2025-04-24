
# Week 1: Inclined Plane and Classical Dynamics

This module introduces Newton’s Second Law applied to inclined planes, basic dynamics, and connections to calculus-based motion analysis.

![Incline Diagram](free_body_diagram_block_on_incline.svg)

---

## 📘 Topics Covered
- Free-body diagrams for objects on inclines
- Decomposition of forces: gravitational, normal, and frictional (optional)
- Vector visualization using Python
- Root-finding and problem modeling from Burden & Faires
- Probability intersections from Asimow & Maxwell
- Calculus-based derivations of kinematic equations

---

## 📐 Calculus Derivations (Kinematics)

Given constant acceleration \( a \):

1. Velocity as the derivative of position:
   \[
   v(t) = \frac{dx}{dt}
   \]

2. Acceleration as the derivative of velocity:
   \[
   a(t) = \frac{dv}{dt}
   \]

3. Position from velocity:
   \[
   x(t) = x_0 + \int v(t) dt = x_0 + v_0t + \frac{1}{2}at^2
   \]

4. Alternate derivation (eliminating \( t \)):
   \[
   v^2 = v_0^2 + 2a(x - x_0)
   \]

---

## 🧮 GRE-Style Problem Set (Conceptual + Quantitative)

**Q1:** A 2.0 kg block slides down a frictionless incline of 30°. What is the acceleration?  
→ Use: \( a = g \sin\theta \)

**Q2:** A projectile is launched at angle \( \theta \). Derive time of flight and maximum height using integrals.

**Q3:** Use Newton-Raphson to numerically find the time \( t \) at which \( x(t) = 5 \) for:
   \[
   x(t) = x_0 + v_0t + \frac{1}{2}at^2
   \]

**Q4:** A force \( F(t) = 5t \) N acts on a 1 kg mass. Find velocity as a function of time.

**Q5:** Find the normal and tangential components of acceleration for a particle on a curved path \( y = \sin(x) \).

---

## 📂 Files Included

- `incline_diagram.py`: Python sketch of inclined plane forces
- `incline_diagram.ipynb`: Interactive notebook
- `free_body_diagram_block_on_incline.svg`: Vector diagram for incline
- `bisection_method.py`: Numerical root solver (Burden & Faires style)
- `combinatorics_simulation.py`: Monte Carlo + set operations for P(A ∪ B)
- `newton_raphson_question3.py`: Visual and numerical solution of root for \( x(t) = 5 \)

---

## ⚙️ Computational Physics (Python Algorithms)

These exercises emphasize algorithmic thinking applied to classical systems.

**1. Inclined Plane Simulation with Time Evolution**
```python
# Euler method: simulate sliding block
dt = 0.01
t_max = 2
g = 9.8
theta = np.radians(30)
a = g * np.sin(theta)
v = 0
x = 0
positions = []
times = []

for i in range(int(t_max / dt)):
    v += a * dt
    x += v * dt
    positions.append(x)
    times.append(i * dt)

plt.plot(times, positions)
plt.title("Block Position vs Time (Euler Simulation)")
plt.xlabel("Time (s)")
plt.ylabel("Position (m)")
plt.grid(True)
plt.show()
```

**2. Vector Field Plot of Forces**
```python
# Visualize gravity vector field
X, Y = np.meshgrid(np.linspace(-2, 2, 10), np.linspace(-2, 2, 10))
U = 0 * X
V = -9.8 * np.ones_like(Y)

plt.quiver(X, Y, U, V)
plt.title("Gravitational Field Vectors")
plt.axis("equal")
plt.grid(True)
plt.show()
```

These simulations support deeper understanding of forces, motion, and numerical integration—foundational for computational mechanics and robotics.

---

## 📄 PDF Version

[📥 Download Week 1 Curriculum (PDF)](week1-computational-physics.pdf)

## 🧠 GRE-Style Solutions PDF

Detailed solutions with calculus-based derivations and formula analysis:

[📥 Download GRE-Style Problem Set Solutions (PDF)](week1-gre-answers.pdf)
