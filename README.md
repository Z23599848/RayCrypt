# OptiCode
The intersection of **Information Theory** and **Classical Optics**.

# 🚀 Project: OptiCode-Cypher

### *Data Encryption & Compression via Ray-Surface Intersections*

## 📖 The Concept

Traditional data processing treats tables as flat, linear arrays. **OptiCode** reimagines a data table as a **3D Physical Environment**.

Instead of standard lookup functions, this project uses **Geometric Ray Tracing** as a mathematical transform. By treating data cells as coordinates with physical properties (Refractive Index, Surface Normal, or Reflectivity), we can "probe" data using light transport math.

---

## 🛠 How it Works

### 1. The Data-to-Geometry Mapping

A data table is mapped into a virtual 2D or 3D space.

* **Cell :** The position of an optical element (Mirror, Lens, or Prism).
* **Cell Value :** The "bending power" (Refractive Index ) or the "tilt" (Normal Vector ) of that element.

### 2. Encryption (The "Ray-Hash")

To encrypt a piece of information (the **Plaintext**):

1. Convert the plaintext into an **Initial Vector** (Origin  and Direction ).
2. Fire the ray into the "Data Table" geometry.
3. The ray bounces () and bends () through the data cells.
4. The final **Incident Point** where the ray exits the system is your **Ciphertext**.

> **Security:** Because of the "Butterfly Effect" in optics, changing one bit in the data table completely changes the final exit point.

### 3. Compression (Geometric Approximation)

Instead of storing a massive table of  raw values, we store a set of **Geometric Primitives** (curves and surfaces) that represent the data's trend.

* To retrieve a value, you "trace" a ray at a specific index.
* The **Intersection Point** reconstructs the original data.
* This achieves compression by storing **formulas** instead of **indices**.

---

## ⚡ Why this is Efficient

Unlike graphical ray tracing (RTX), this is **Pure Math Ray Tracing**. It does not require a GPU because:

* **No Pixels:** We only calculate the path of *one* ray, not millions.
* **Analytical Solutions:** We use simple linear algebra ( and ).
* **Reversibility:** Optical paths are mathematically reversible, allowing for symmetric decryption without heavy overhead.

---

## 🧪 Potential Use Cases

* **Visual Steganography:** Hiding data inside the "noise" of an optical simulation.
* **Geometric Hashing:** A new way to create unique IDs for large datasets.
* **Lightweight DRM:** Using a physical "lens shape" as a decryption key for a file.

---

## 🚀 Getting Started

*(This is where you would put your code snippet or link to your implementation)*

```python
# Conceptual Python snippet for a 1D Data Trace
def trace_data(input_key, data_table):
    ray_angle = input_key
    for cell in data_table:
        # Each cell acts as a refractive interface
        ray_angle = apply_snells_law(ray_angle, cell.value)
    return ray_angle # This is your transformed data point

```
