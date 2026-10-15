# Quantum Electron Simulator

This is a project I built to visualize how electrons fill up orbitals in an atom. I wanted to make something that actually follows the rules of quantum chemistry instead of just drawing random circles.

## ⚛️ Scientific Principles Used

To make the simulator accurate, I programmed the logic based on three main rules:

1.  **The Aufbau Principle:** This is the "building up" principle. My code ensures that electrons always fill the lowest energy orbitals first (1s, then 2s, then 2p, and so on).
2.  **The Pauli Exclusion Principle:** I set a hard limit of 2 electrons per single orbital. If there are two, the code assigns them opposite spins ($\uparrow$ and $\downarrow$).
3.  **Hund's Rule:** For orbitals that have the same energy (like the three boxes in the $2p$ subshell), the code fills each box with one electron first before it starts pairing them up.

## 💻 How I Built the Visuals

### The Bohr Model (Dots)
For the regular model, I used basic trigonometry ($\sin$ and $\cos$) to place electrons on concentric circles. I gave each shell a different orbit speed so they don't all move together, which makes it look more natural.

### The Quantum Cloud (Probability Shading)
The "Quantum Cloud" mode is my favorite part. Since electrons aren't actually little dots in a circle, I wanted to simulate **Probability Density**.

**How I did the shading:**
Instead of drawing a dot, I rendered the electron as a large, semi-transparent circle with a heavy **Gaussian Blur** filter.
*   **Opacity:** I set the opacity very low (around 8%).
*   **Overlapping:** When multiple electrons are in the same shell or subshell, their blurred circles overlap. In CSS, these transparent colors add up.
*   **The Effect:** Where the clouds overlap, the color becomes darker and more intense. This mimics a probability map—the "darker" the area, the higher the probability that an electron is located there.

## 🔢 The Math behind the Quantum Numbers

I created a logic engine that tracks every single electron added. For each one, the code calculates:
*   **n (Principal):** Based on the shell number in my data array.
*   **l (Azimuthal):** Mapped as $s=0, p=1, d=2$.
*   **ml (Magnetic):** Based on which specific "box" the electron landed in.
*   **ms (Spin):** Based on whether it was the first or second electron to enter that box.

## 🚀 How to Run
1. Download the `index.html` file.
2. Open it in any modern web browser (Chrome, Firefox, or Safari).
3. Use the $+$ and $-$ buttons to add electrons and watch the element and quantum numbers update in real-time!
