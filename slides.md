<!--
-------------------------------------------------------------------------------
This file defines the contents of each slide.
The reveal.js configuration can be found in index.html
-------------------------------------------------------------------------------
-->


<!-- .slide: class="slide-title" data-background-opacity="0.3" data-background-image="assets/magali-logo.svg" data-background-color="#000000" data-background-size="contain" -->

<!-- Place the content at the bottom of the slide -->
<div class="r-stretch">
</div>

<h1 id="talk-title">
  
  Magali: Modelling and inversion of magnetic microscopy data 🧲🔬

</h1>
<p id="talk-authors">
  <a id="talk-speaker">Yago M Castro</a>
</p>

<!-- Place location and date side-by-side with affiliation logos -->
<div class="row talk-info">
<div class="col-large">

<i class="fa fa-calendar-alt" style="margin: 0 10px 0 0"></i>
15 April 2022
<span style="margin: 0 20px"></span>
Master's Degree Qualification Exam | IAG

<!-- Permission to reuse and CC-BY license logo -->
<i class="fa fa-camera" style="margin: 0 10px 0 0"></i>
Feel free to screenshot/share/reuse this presentation
<span style="margin: 0 20px"></span>
<a href="https://creativecommons.org/licenses/by/4.0/"><i class="fab fa-creative-commons"></i><i class="fab fa-creative-commons-by" style="margin: 0 10px 0 2px"></i>CC-BY 4.0 License</a>

</div>
<div class="col-medium">

<!-- Add logos here. Need these wrappers to align them to the bottom right -->
<div class="talk-logos-container">
<div class="talk-logos">
  <a href="https://www.compgeolab.org"><img src="assets/compgeolab-banner-light.svg" alt="Computer-Oriented Geoscience Lab"></a>
  <!-- <a href="https://www.iag.usp.br/"><img src="assets/iag.png" alt="Instituto de Astronomia, Geofísica e Ciências Atmosféricas"></a>
  <a href="https://www.usp.br/"><img src="assets/usp.png" alt="Universidade de São Paulo"></a> -->
</div>
</div>

</div>
</div>

===============================================================================

# What is Paleomagnetism?

- The study of Earth’s magnetic field as <b>recorded</b> in rocks.

===============================================================================
# How magnetic minerals are formed?
<ul>
  <li><b>Thermoremanent Magnetization (TRM): </b>igneous rocks record Earth’s magnetic field as they cool below the Curie point</li>
  <li><b>Depositional Remanent Magnetization (DRM):</b> magnetic particles in sediments align with Earth’s field during deposition in aquatic environments</li>
</ul>

===============================================================================

# Why is paleomagnetism important?

<ul>
<li class="fragment"><b>Geomagnetic reversals:</b> shows that Earth's magnetic field has flipped many times throughout its history</li>
<li class="fragment"><b>Continental drift and plate tectonics:</b> helped confirm the theory of continental drift and reconstruct past positions of the continents</li>
<li class="fragment"><b>Geological dating:</b> used as a relative dating tool by comparing rock records with the known magnetic reversal timescale (magnetostratigraphy)</li>
<li class="fragment"><b>Paleofield reconstruction:</b> allows us to understand how Earth’s magnetic field has evolved over hundreds of millions of years</li>
</ul>

===============================================================================

<img src="assets/geomag.svg" style="width: 50%" >

===============================================================================

<div class="r-stretch">

  <img src="assets/sample.svg" height=100%>

</div>

===============================================================================

<div class="r-stretch">

  <img src="assets/microscope-sample.svg" height=100%>

</div>

<div class="footnote-center">

Souza-Junior (2024)

</div>

===============================================================================
<div class="r-stretch">

  <img src="assets/microscope.svg" height=100%>

</div>
<div class="footnote-center">

[aRAUJO et a. (2017)](https://doi.org/10.1002/2017gc006946)

</div>

===============================================================================


<!-- .slide: class="slide-title" data-background-opacity="1" data-background-image="assets/microscope-data.svg"  data-background-size="contain" -->

<div class="r-stretch">
</div>
<div class="footnote-left">

[lENNNN et al. (2019)](https://doi.org/10.3390/s19071636)


</div>

===============================================================================

# Needs
<div class="fragment">

- Algorithms for **automatic detection** of magnetic **grains** and its **magnetic moment** determination

</div>
<div class="fragment">

- **Open software** for forward **modelling** and **inversion** techniques specific to magnetic microscopy 

</div>

<div class="fragment text-left">

- **Data conventions**  

</div>

===============================================================================


<!-- .slide: data-background-opacity="1" data-background-image="assets/readme-banner.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================

<!-- .slide: data-background-opacity="0.2" data-background-image="assets/magali-logo.png"  data-background-size="contain" data-background-color="#262626" -->

<div class="huge ">

What is Magali?

<div class="large fragment">

Free and open source 
<br>
<i class="fab fa-github"></i> <i class="fas fa-lock-open"></i>  <i class="fab fa-osi"></i>

</div>

</div>
<div class="large fragment">

Python library <i class="fab fa-python"></i>

</div>

<div class="large fragment">

Modelling and processing magnetic microscopy data 
<br>
<i class="fas fa-magnet"></i> <i class="fas fa-microscope"></i>

</div>



===============================================================================


<!-- .slide: data-background-opacity="0.2" data-background-image="assets/magali-logo.png"  data-background-size="contain" data-background-color="#262626" -->

# Why do we want to make it?

<div class="fragment text-left">

- Provide code that is **easy to use**

</div>

<div class="fragment text-left">

- Determine the **spatial positions** of **multiple** grains

</div>
<div class="fragment text-left">

- Facilitate the creation of **synthetic data**

</div>
<div class="fragment text-left">

- Propose a standard **data format**

</div>

<div class="fragment text-left">

- Serve as a **foundation** for new methods 

</div>
<div class="fragment text-left">

- Leverage the potential of emerging **magnetic microscopy** studies

</div>

===============================================================================

# Needs

- Algorithms for **automatic detection** of magnetic **grains** and its **magnetic moment** determination


===============================================================================

# Display Gelson's papers here

===============================================================================

<!-- .slide: data-background-opacity="1" data-background-image="assets/synthetic.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================

<p class="text-left"> <b>Step 1 - Source Detection</b></p>
<p class="text-left"> <b>Step 2 - Iterative processing (per window)</b></p>
<ul>
  <li>(a) <strong>Isolate data</strong> – Select magnetic data inside window</li>
  <li>(b) <strong>Euler deconvolution</strong> – Estimate source <em>position</em></li>
  <li>(c) <strong>Linear inversion</strong> – Estimate dipole <em>moment</em> using fixed position</li>
  <li>(d) <strong>Non-linear inversion</strong> – Refine position & moment via FIX!!![Nelder-Mead](Gao & Han, 2010; Nelder & Mead, 1965)</li>
  <li>(e) <strong>Signal removal</strong> – Forward model dipole & subtract from full dataset</li>
</ul>
<p class="text-left"> <b>Step 3 - Repeat detection on residual data:</b> Apply steps 1 and 2  to the stripped dataset to identify new sources and compute their parameters

===============================================================================

## Step 1: Source Detection
- **Goal:** isolate each magnetic particle in the image  
- **Methods used:**
<ul>
<li class='fragment'> Upward continuation</li> 
<li class='fragment'> <b>Total Gradient Amplitude (TGA):</b>  
  Enhances signal near the source (high-pass filter)</li>  
<li class='fragment'> <b>Contrast stretching:</b>  
  Uses percentiles (1st and 99th) to enhance weak particles</li>  
<li class='fragment'> <b>LoG (Laplacian of Gaussian) segmentation:</b>
  Detects “blobs” → 1 window = 1 particle </li>
<li class="fragment">Rank by decreasing signal strength</li>
</ul>

===============================================================================

# What is TGA?


Given a magnetic field $f(x, y, z)$:
$$
\left\| \vec{\nabla} f(x, y, z) \right\| = \sqrt{ \left( \partial_x f \right)^2 + \left( \partial_y f \right)^2 + \left( \partial_z f \right)^2 },
$$

===============================================================================

# Computing the Derivatives
<div class="text_left">
<ul>
  <li>Use <strong>second-order central finite differences</strong> for spatial derivatives:</li>
</ul>
</div>
$$\Delta_xf(x, y, z) ≈ \frac{f(x + \Delta_{x,y,z}) - f(x - \Delta_{x,y,z})}{2\Delta_{x}}$$
<div class="text_left">
<ul>
  <li>For ∂z: apply <strong>upward</strong> and <b>downward</b> in the frequency domain.</li>
</ul>
</div>

===============================================================================

# Advantages of TGA
<ul>
  <li class="text-left fragment">Always positive</li>
  <li class="text-left fragment">Peaks directly over magnetic sources</li>
  <li class="text-left fragment">Less sensitive to magnetization direction</li>
  <li class="text-left fragment">Enhances local features, suppresses regional background</li>
  <li class="text-left fragment">Acts as a <b>high-pass filter</b>, removing long-wavelength noise.</li>
</ul>

===============================================================================
<div class="row">
<div class="col"><img src="assets/synthetic.png" style="width: 100%" ></div>
<div class="col"><img src="assets/tga_iso.png" style="width: 80%" ></div>
</div>

===============================================================================

# Contrast Stretching
- **Goal**: Rescale TGA values to highlight weak/strong signals.  
- **Operation**: Per-pixel transformation to normalize data: 

<p>
\[
\text{TGA}_{\text{rescaled}} = 2 \left( \frac{\text{TGA} - v_{\min}}{v_{\max} - v_{\min}} \right) - 1
\]

</p>

<ul>
<li>$ v_{\text{min}} = 1^\text{st} $ percentile  </li>
<li>$ v_{\text{max}} = 99^\text{th} $ percentile  </li>
<li><b>Output:</b> values stretched to range $[-1, 1]$</li>
</ul>

===============================================================================
# Why Percentile Bounds?
- **Robust Scaling**:  
  - Ignores extreme outliers (e.g., sensor noise).  
- **Empirical Validation**:  
  - Works well for real magnetic microscopy datasets.  
- **Dynamic Range**: Ensures both weak and strong signals are visible.


===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/tga_stretched.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
# LoG Blob Detection
- **Algorithm**: Laplacian of Gaussian (LoG) (Kong et al., 2013).  
- **Purpose**: Detect local maxima ("blobs") in rescaled TGA image.  
- **Advantages**:  
  - Ideal for bright blobs on dark backgrounds.  
  - Accurately identifies particle locations/sizes.  
- **Computation**: Fast for typical magnetic microscopy image sizes.  


===============================================================================
# Implementation Notes
- **Border Handling**: Exclude blobs near image edges to avoid truncation artifacts.  
- **One-Time Cost**: LoG runs once per image.  
- **Trade-off**: Higher accuracy at the cost of longer runtime (acceptable for dataset sizes).  


===============================================================================

# Step 2: Iterative processing (per window)
<ul>
  <li>(a) <strong>Isolate data</strong> – Select magnetic data inside window</li>
  <li>(b) <strong>Euler deconvolution</strong> – Estimate source <em>position</em></li>
  <li>(c) <strong>Linear inversion</strong> – Estimate dipole <em>moment</em> using fixed position</li>
  <li>(d) <strong>Non-linear inversion</strong> – Refine position & moment via FIX!!![Nelder-Mead](Gao & Han, 2010; Nelder & Mead, 1965)</li>
  <li>(e) <strong>Signal removal</strong> – Forward model dipole & subtract from full dataset</li>
</ul>

===============================================================================
<!-- .slide: class="slide-transition" -->


# Euler Deconvolution

===============================================================================

# Euler Deconvolution
<p class="fragment text-left"><b>What it is:</b> a method to estimate the location and depth of magnetic sources from total field data</p>
<div class="text-left fragment">
  <b>Characteristics:</b><br>
  <ul class="text-left"> 
    <li class="fragment ">Assumes dipolar source model</li>
    <li class="fragment">Applied to each segmented data region</li>
    <li class="fragment">Yields source position estimate</li>
    <li class="fragment">Based on Euler’s homogeneity equation</li>
  </ul>
</div>


===============================================================================
# Euler's Homogeneity Equation
  
$$
(x - x_c)\partial_x f + (y - y_c)\partial_y f + (z - z_c)\partial_z f = (b - f)\eta
$$ 
<div class="text-left">

- $x,y,z$ : coordinates ofc;adsmlvikdfsbvsdfovkl,jbh the magnetic field source
- $x_c,y_c,z_c$ : coordinates of the magnetic field source
- $f$ : any function (Ex.: bz)
- $b$ : base level (constant shift in the signal)
- $\eta$ : structural index
</div>
<div class="footnote-center">

[Souza-Junior et al 2024](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2023GC011082)
</div>

===============================================================================

### Structural index for magnetic (M) and gravity (G) sources of different source geometries.

| Source                     | Smellie model     | SI (M) | SI (G) |
|----------------------------|-------------------|--------|--------|
| Sphere                 | Dipole            | 3      | 2      |
| Vertical line end (pipe)  | Pole              | 2      | 1      |
| Horizontal line (cylinder) | Line of dipoles  | 2      | 0      |
| Thin bed fault         | Line of dipoles   | 2      | 2      |
| Thin sheet edge            | Line of poles     | 1      | 0      |
| Finite contact/fault   | —                 | 0  | −1     |
| Infinite contact/fault     | —                 | 0      | ∞  |


<div class="footnote-center">

[Reid & Thurston (2014)](https://library.seg.org/doi/10.1190/geo2013-0235.1)
</div>




===============================================================================

# Euler's Homogeneity Equation
  
$$
(x - x_c)\partial_x f + (y - y_c)\partial_y f + (z - z_c)\partial_z f = (b - f)\eta
$$ 
<p class="fragment"> Rearranging into a pseudo‐parametric model with parameters $x_c, y_c, z_c,
b$</p>
<div class="fragment">

$$
x_c \ \partial_x f + y_c \\partial_y f + z_c \ \partial_z f + \eta b = x \ \partial_x f + y \ \partial_y f + z \ \partial_z f + \eta f
$$
</div>
<div class="footnote-center">

[Souza-Junior et al 2024](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2023GC011082)
</div>

===============================================================================

# Euler's Homogeneity Equation
$$
x_c \ \partial_x f + y_c \\partial_y f + z_c \ \partial_z f + \eta b = x \ \partial_x f + y \ \partial_y f + z \ \partial_z f + \eta f
$$

<p class="fragment"> Applying to each data point, a $N \times 4$ linear system of equations can be formed</p>
<p class="fragment">
  \[
  \underbrace{
  \begin{bmatrix}
  \partial_x f_1 & \partial_y f_1 & \partial_z f_1 & \eta \\
  \partial_x f_2 & \partial_y f_2 & \partial_z f_2 & \eta \\
  \vdots & \vdots & \vdots & \vdots \\
  \partial_x f_N & \partial_y f_N & \partial_z f_N & \eta
  \end{bmatrix}
  }_{\text{Jacobian matrix}}
  \underbrace{
  \begin{bmatrix}
  x_c \\ y_c \\ z_c \\ b
  \end{bmatrix}
  }_{\text{Model parameters}}
  =
  \underbrace{
  \begin{bmatrix}
  x_1 \partial_x f_1 + y_1 \partial_y f_1 + z_1 \partial_z f_1 + \eta f_1 \\
  x_2 \partial_x f_2 + y_2 \partial_y f_2 + z_2 \partial_z f_2 + \eta f_2 \\
  \vdots \\
  x_N \partial_x f_N + y_N \partial_y f_N + z_N \partial_z f_N + \eta f_N
  \end{bmatrix}
  }_{\text{Data vector}}
  \]
</p>

<div class="fragment">

$$\bold{Gp=h}$$

</div>
<div class="footnote-center">

[Souza-Junior et al 2024](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2023GC011082)
</div>

===============================================================================
<!-- .slide: class="slide-transition" -->


# Assuming that noise in the spatial derivatives of $f$ are negligible

===============================================================================

#  Leats-squares solution

<p class="text-left">We want to solve:</p>

$$
\mathbf{G} \mathbf{p} = \mathbf{h}
$$

<div  class= " text-left fragment">
<p class="text-left">When the system is <b>overdetermined</b> (more equations than unknowns), we seek a <b>least-squares solution</b>:</p>

$$
\min \Phi (\mathbf{p}) =||\mathbf{h^o} - \mathbf{h}\||^2
$$

<ul>
  <li>$\Phi (\mathbf{p})$ : objective function</li>
  <li>$\mathbf{h^o}$ : observed data</li>
</ul>
</div>


===============================================================================

## Residual Vector

<p class="text-left">Define the <b>residual</b>:</p>

$$
\mathbf{r} = \mathbf{h^o} - \mathbf{h}
$$

<p class="text-left">Objective function to be minimized:</p>

$$
\Phi(\mathbf{p}) = \|\mathbf{r}\|^2
$$

===============================================================================

# To solve it
<ol>
  <li>
    <strong>Expand the expression:</strong><br>
    \[
    \Phi(\mathbf{p}) = (\mathbf{h}^o - \mathbf{G}\mathbf{p})^\top (\mathbf{h}^o - \mathbf{G}\mathbf{p}) = \mathbf{h}^{o\top}\mathbf{h}^o - 2\mathbf{p}^\top \mathbf{G}^\top \mathbf{h}^o + \mathbf{p}^\top \mathbf{G}^\top \mathbf{G} \mathbf{p}
    \]
  </li>
  <li>
    <strong>Take the gradient with respect to \(\mathbf{p}\) and set to zero:</strong><br>
    \[
      \nabla_{\mathbf{p}} \Phi(\mathbf{p}) = -2 \mathbf{G}^\top \mathbf{h}^o + 2 \mathbf{G}^\top \mathbf{G} \mathbf{p}=\mathbf{0}
    \]
    \[
      \boxed{
      \mathbf{G}^\top \mathbf{G} \mathbf{p} = \mathbf{G}^\top \mathbf{h}^o
      }
    \]
  </li>
  <li>
    <strong>Solve the normal equations and estimate $x_c$, $y_c$, $z_c$ and $b$:</strong><br>
    \[
      \boxed{
      \mathbf{p} = (\mathbf{G}^\top \mathbf{G})^{-1} \mathbf{G}^\top \mathbf{h}^o
      }
    \]
  </li>
</ol>

===============================================================================
<!-- .slide: class="slide-transition" -->


# Linear inversion

===============================================================================

<h1>Dipole Field Model</h1>
<p class="text-left">The field $\mathbf{b}$ generated by a dipole $\mathbf{m} = [m_x, m_y, m_z]^T$:</p>
$$
\mathbf{b} = 
\begin{bmatrix}
b_x \\
b_y \\
b_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi}
\begin{bmatrix}
\frac{\partial^2}{\partial x \partial x} \frac{1}{r} & \frac{\partial^2}{\partial x \partial y} \frac{1}{r} & \frac{\partial^2}{\partial x \partial z} \frac{1}{r} \\
\frac{\partial^2}{\partial y \partial x} \frac{1}{r} & \frac{\partial^2}{\partial y \partial y} \frac{1}{r} & \frac{\partial^2}{\partial y \partial z} \frac{1}{r} \\
\frac{\partial^2}{\partial z \partial x} \frac{1}{r} & \frac{\partial^2}{\partial z \partial y} \frac{1}{r} & \frac{\partial^2}{\partial z \partial z} \frac{1}{r}
\end{bmatrix}
\begin{bmatrix}
m_x \\
m_y \\
m_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi} \mathbf{M} \mathbf{m}
$$
<br>
<div class="text-left"><ul>
<li> $r=\sqrt{(x-x_c)^2+(y-y_c)^2+(z-z_c)^2}$ </li>
<li> MUUUUU </li>

</ul></div>


===============================================================================

<h1>System for $b_z$</h1>


$$
\mathbf{b} = 
\begin{bmatrix}
b_x \\
b_y \\
b_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi}
\begin{bmatrix}
\frac{\partial^2}{\partial x \partial x} \frac{1}{r} & \frac{\partial^2}{\partial x \partial y} \frac{1}{r} & \frac{\partial^2}{\partial x \partial z} \frac{1}{r} \\
\frac{\partial^2}{\partial y \partial x} \frac{1}{r} & \frac{\partial^2}{\partial y \partial y} \frac{1}{r} & \frac{\partial^2}{\partial y \partial z} \frac{1}{r} \\
\frac{\partial^2}{\partial z \partial x} \frac{1}{r} & \frac{\partial^2}{\partial z \partial y} \frac{1}{r} & \frac{\partial^2}{\partial z \partial z} \frac{1}{r}
\end{bmatrix}
\begin{bmatrix}
m_x \\
m_y \\
m_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi} \mathbf{M} \mathbf{m}
$$
<br>
$$
\mathbf{b}_z = 
\begin{bmatrix}
b_x \\
b_y \\
b_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi}
\begin{bmatrix}
\frac{\partial^2}{\partial z \partial x} \frac{1}{r} & \frac{\partial^2}{\partial z \partial y} \frac{1}{r} & \frac{\partial^2}{\partial z \partial z} \frac{1}{r}
\end{bmatrix}
\begin{bmatrix}
m_x \\
m_y \\
m_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi} \mathbf{M}_z \mathbf{m}
$$

<p class="text-left">$$ b_z = \frac{\mu_0}{4\pi} \mathbf{M}_z \mathbf{m} $$</p>
<p class="text-left">For $N$ observations:</p>
$$
A \mathbf{m} = \mathbf{d}
$$
<p class="text-left">$\mathbf{A}$: Jacobian</p>

===============================================================================

# Computing the Derivatives
<ul>
  <li>Use <strong>second-order central finite differences</strong> for spatial derivatives:</li>
</ul>
$$
\frac{\partial^2}{\partial z \partial x} \frac{1}{r} = \frac{3(z - z_c)(x - x_c)}{r^5}
$$
$$
\frac{\partial^2}{\partial z \partial y} \frac{1}{r} = \frac{3(z - z_c)(y - y_c)}{r^5}
$$
$$
\frac{\partial^2}{\partial z \partial z} \frac{1}{r} = \frac{3(z - z_c)^2}{r^5} - \frac{1}{r^3}
$$

===============================================================================


<h1>Problem Formulation</h1>
<p class="text-left">Given $N$ observations of $b_{z}$ in a window containing a single source an $N\times 3$ linear system is formed:</p>
\[
\underbrace{  
\begin{bmatrix}
\frac{\mu_0}{4\pi} \frac{3(z_1 - z_c)(x_1 - x_c)}{r_1^5} & \frac{\mu_0}{4\pi} \frac{3(z_1 - z_c)(y_1 - y_c)}{r_1^5} & \frac{\mu_0}{4\pi} \left( \frac{3(z_1 - z_c)^2}{r_1^5} - \frac{1}{r_1^3} \right) \\
\frac{\mu_0}{4\pi} \frac{3(z_2 - z_c)(x_2 - x_c)}{r_2^5} & \frac{\mu_0}{4\pi} \frac{3(z_2 - z_c)(y_2 - y_c)}{r_2^5} & \frac{\mu_0}{4\pi} \left( \frac{3(z_2 - z_c)^2}{r_2^5} - \frac{1}{r_2^3} \right) \\
\vdots & \vdots & \vdots \\
\frac{\mu_0}{4\pi} \frac{3(z_N - z_c)(x_N - x_c)}{r_N^5} & \frac{\mu_0}{4\pi} \frac{3(z_N - z_c)(y_N - y_c)}{r_N^5} & \frac{\mu_0}{4\pi} \left( \frac{3(z_N - z_c)^2}{r_N^5} - \frac{1}{r_N^3} \right)
\end{bmatrix}}_{\text{Jacobian matrix}}
\underbrace{
\begin{bmatrix}
m_x \\
m_y \\
m_z
\end{bmatrix}}_{\text{Parameter vector}}
=
\underbrace{
\begin{bmatrix}
b_{z_1} \\
b_{z_2} \\
\vdots \\
b_{z_N}
\end{bmatrix}}_{\text{Observation vector}}
\]
<p class="fragment">$$\mathbf{Am=b}$$</p>

===============================================================================
<h1>Least Squares Estimation</h1>
<p class="text-left">We minimize the misfit function:</p>
$$\Gamma(\mathbf{m}) = \|\mathbf{d}^{o}-\mathbf{A}\mathbf{m}\|^2$$
<p class="text-left">Leading to the normal equations:</p>
$$\mathbf{A}^T\mathbf{A}\mathbf{m} = \mathbf{A}^T\mathbf{d}^{\prime}$$
<p class="fragment">Solution gives estimated dipole moment $\mathbf{\hat{m}}$</p>

===============================================================================
<h1>Converting to Interpretable Parameters</h1>
<p>The dipole moment vector can be expressed as:</p>
$$\begin{aligned}
I &= -\tan^{-1}\frac{m_z}{\sqrt{m_x^2+m_y^2}} \\
D &= \tan^{-1}\frac{m_y}{m_x} \\
m &= \sqrt{m_x^2 + m_y^2 + m_z^2}
\end{aligned}$$

[Tauxe!!!!!!!!!!!!!!!!!!!!!!!!!]

===============================================================================
<!-- .slide: class="slide-transition" -->


# Non-Linear inversion

===============================================================================

<h1>Problem with Linear Inversion</h1>
<p class="fragment text-left">We now have estimatives for position and magnetic moment of the sources</p>
<p class="fragment text-left">However <strong>interfering sources</strong> distort these estimates</p>
<h2 class="fragment"><strong>Solution:</strong> Joint non-linear optimization</h2>

===============================================================================

<h1>Non-Linear Misfit Function</h1>
<div class="math-block">
    \[
    \xi(\mathbf{x}, \mathbf{m}) = \| (\mathbf{d}^o - b) - \mathbf{d}(\mathbf{x}, \mathbf{m}) \|_2^2
    \]
</div>
<p >Jointly optimizes position \(\mathbf{x}\) and dipole moment \(\mathbf{m}\)</p>
<ul>
    <li>\(\mathbf{d}^o \): observed data</li>
    <li>\(\mathbf{d}(\mathbf{x}, \mathbf{m})\): forward model prediction</li>
</ul>


===============================================================================

<h2>Why Nelder-Mead?</h2>
<ul>
    <li class="fragment">No need for gradient calculations</li>
    <li class="fragment">Works with irregular/noisy functions</li>
    <li class="fragment">Simple to implement</li>
    <li class="fragment">Effective for low-dimensional problems (like our 6-parameter dipole problem)</li>
</ul>

===============================================================================

<p class="text-left"> <b>Step 1 - Source Detection</b></p>
<p class="text-left"> <b>Step 2 - Iterative processing (per window)</b></p>
<ul>
  <li>(a) <strong>Isolate data</strong> – Select magnetic data inside window</li>
  <li>(b) <strong>Euler deconvolution</strong> – Estimate source <em>position</em></li>
  <li>(c) <strong>Linear inversion</strong> – Estimate dipole <em>moment</em> using fixed position</li>
  <li>(d) <strong>Non-linear inversion</strong> – Refine position & moment via FIX!!![Nelder-Mead](Gao & Han, 2010; Nelder & Mead, 1965)</li>
  <li>(e) <strong>Signal removal</strong> – Forward model dipole & subtract from full dataset</li>
</ul>
<p class="fragment text-left"> <b>Step 3 - Repeat detection on residual data:</b> Apply steps 1 and 2  to the stripped dataset to identify new sources and compute their parameters
<p class="fragment text-left">This step ensures weaker or previously masked sources are detected after removing stronger signals.</p>

===============================================================================

<!-- .slide: data-background-opacity="1" data-background-image="assets/re-detection-methodology.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================

<!-- .slide: data-background-opacity="1" data-background-image="assets/readme-banner.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/github.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/pull_requests.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/pull_request_details.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/checks.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================

<!-- .slide: data-background-opacity="1" data-background-image="assets/tests.png"  data-background-size="contain" data-background-color="#262626" -->


===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/documentation.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================

<!-- .slide: data-background-opacity="1" data-background-image="assets/api.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/doc_function.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/fatiando-data.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/morroco.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="0.2" data-background-image="assets/magali-logo.png"  data-background-size="contain" data-background-color="#262626" -->

<div class="r-stretch centered">
<div>

<i class="fas fa-comments"></i>
<br>
Contact:
<a>yagomcastro1@gmail.com</a>

<i class="fab fa-github"></i>
<br>
Source code for this presentation:
<br>
[github.com/YagoMCastro/science-day-2024-magali](https://github.com/leouieda/talk-template)

<i class="fab fa-creative-commons"></i><i class="fab fa-creative-commons-by"></i>
<br>
Unless otherwise noted,
the contents of this presentation are
licensed under the
<br>
[Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

</div>
</div>