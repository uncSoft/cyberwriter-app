---
tags: [design, habitat, engineering, noforn, orcon]
status: approved
author: jt 
---
<div style="background: #ff0000; color: #ffffff; font-family: monospace; font-weight: bold; font-size: 13px; text-align: center; padding: 6px 12px; letter-spacing: 0.15em; border-radius: 4px; margin-bottom: 4px;">
TOP SECRET // SCI // PERIHELION // NOFORN // ORCON
</div>

<div style="background: #1a0000; color: #ff6b6b; font-family: monospace; font-size: 10px; text-align: center; padding: 4px 12px; letter-spacing: 0.1em; border: 1px solid #ff000055; border-radius: 4px; margin-bottom: 16px;">
CLASSIFICATION: TS/SCI &nbsp;|&nbsp; HANDLE VIA PERIHELION CHANNELS ONLY &nbsp;|&nbsp; REL TO FVEY, SOLARNET &nbsp;|&nbsp; DISSEM CTRL: ORCON/PROPIN &nbsp;|&nbsp; NOT RELEASABLE TO FOREIGN NATIONALS &nbsp;|&nbsp; WARNING — UNAUTHORIZED DISCLOSURE SUBJECT TO CRIMINAL SANCTIONS UNDER 18 U.S.C. § 1030 


</div>

# Habitat Design 
## Neo-Kyoto v0.27b ```サイバーシティ]]```

The living quarters for 12 crew members. Every cubic centimeter counts. 

RefDocs: [[Orbital Mechanics]] | [[System Architecture]] | [[Mission Briefing]]

## Concept Render

![[habitat-render.png]]

*^A concept render of Neo-Kyoto Space Habitat^* 

## Status Dashboard

<div style="display: flex; gap: 12px; flex-wrap: wrap; margin: 16px 0;">
  <div style="flex: 1; min-width: 140px; padding: 16px; background: linear-gradient(135deg, #1a3a5c, #0e1117); border: 1px solid rgba(169,199,255,0.2); border-radius: 10px;">
    <div style="font-size: 11px; color: #9a9da6; text-transform: uppercase; letter-spacing: 0.1em;">Module Mass</div>
    <div style="font-size: 28px; font-weight: 700; color: #a9c7ff;">18.4t</div>
    <div style="font-size: 11px; color: #50e764;">&#9650; Within budget</div>
  </div>
  <div style="flex: 1; min-width: 140px; padding: 16px; background: linear-gradient(135deg, #3b0038, #0e1117); border: 1px solid rgba(255,170,247,0.2); border-radius: 10px;">
    <div style="font-size: 11px; color: #9a9da6; text-transform: uppercase; letter-spacing: 0.1em;">Crew Capacity</div>
    <div style="font-size: 28px; font-weight: 700; color: #ffaaf7;">12</div>
    <div style="font-size: 11px; color: #9a9da6;">4 private + 8 shared</div>
  </div>
  <div style="flex: 1; min-width: 140px; padding: 16px; background: linear-gradient(135deg, #1a3a1a, #0e1117); border: 1px solid rgba(125,235,160,0.2); border-radius: 10px;">
    <div style="font-size: 11px; color: #9a9da6; text-transform: uppercase; letter-spacing: 0.1em;">Pressurized Vol.</div>
    <div style="font-size: 28px; font-weight: 700; color: #7deba0;">148m&#xB3;</div>
    <div style="font-size: 11px; color: #9a9da6;">Largest commercial module</div>
  </div>
</div>

## Floor Plan

The habitat uses a **dual-deck layout** with the sleep quarters on the upper deck (quieter, further from machinery) and the common area on the lower deck.

<div style="margin: 16px 0; padding: 20px; background: #141820; border: 1px solid #3a3d45; border-radius: 10px; font-family: monospace; font-size: 12px; color: #9a9da6; line-height: 1.8;">
<span style="color: #a9c7ff; font-weight: bold;">UPPER DECK</span>
<br>&#9484;&#9472&#9472;&#9472;&#9472;&#9472;&#9472;&#9516;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9516;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9516;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9488;
<br>&#9474; <span style="color:#ffaaf7;">SLP1</span> &#9474; <span style="color:#ffaaf7;">SLP2</span> &#9474 <span style="color:#ffaaf7;">SLP3</span> &#9474; <span style="color:#ffaaf7;">SLP4</span> &#9474;
<br>&#9500;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9524;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9524;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9524;&#9472;&#9472;&#9472;&#9472;&#9472;&#9508;
<br>&#9474; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:#7deba0;">CORRIDOR</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &#9474;
<br>&#9500;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9516;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9508;
<br>&#9474; <span style="color:#a9c7ff;">SHARED-A</span> &nbsp;&nbsp; <span style="color:#a9c7ff;">SHARED-B</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9474;
<br>&#9492;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9524;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9496;
<br><br>
<span style="color: #ffd966; font-weight: bold;">LOWER DECK</span>
<br>&#9484;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9516;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9516;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9488;
<br>&#9474; <span style="color:#ffd966;">GALLEY</span>&#9474; <span style="color:#ffd966;">COMMON</span> &#9474; <span style="color:#50e764;">GYM</span> &nbsp;&#9474;
<br>&#9500;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9524;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9524;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9508;
<br>&#9474; <span style="color:#ff9e7a;">MEDICAL</span>&#9474; <span style="color:#ce9aff;">STRG</span> &#9474; <span style="color:#7af4ff;">WASH</span>&nbsp;&nbsp;&#9474;
<br>&#9492;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9524;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9524;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9472;&#9496;
</div>

## Radiation Shielding

The habitat uses a **water wall** approach - the water supply doubles as radiation shielding for the sleep quarters. [[Dr. Elena Vasquez]] calculated the required thickness:

> For <span style="color:#ff9e7a;">$\leq 20$</span> mSv/year (NASA career limit fraction): minimum **8 cm** polyethylene-equivalent shielding on the sun-facing wall. Limits raised for engineers on performance improvement plans


## Radiation Shielding

The habitat uses a **water wall** approach - the water supply doubles as radiation shielding for the sleep quarters. [[Dr. Elena Vasquez]] calculated the required thickness:

> For <span style="color:#ff9e7a;">$\leq 20$</span> mSv/year (NASA career limit fraction): minimum **8 cm** polyethylene-equivalent shielding on the sun-facing wall. Limits raised for engineers on performance improvement plans

The following script was used to model transmission through the water wall at varying thicknesses:

```python
import math

# Radiation attenuation through water wall shielding
# Using the exponential attenuation model: I = I0 * e^(-mu * x)

SOLAR_FLUX_MSVY = 300.0      # mSv/year baseline GCR flux at Mars surface
MU_WATER = 0.096             # linear attenuation coefficient (cm^-1), GCR approximation
NASA_ANNUAL_LIMIT = 20.0     # mSv/year (Vasquez safety threshold)

def attenuated_dose(thickness_cm: float) -> float:
    """Return annual dose (mSv/year) after shielding of given thickness."""
    return SOLAR_FLUX_MSVY * math.exp(-MU_WATER * thickness_cm)

def find_minimum_thickness(step_cm: float = 0.1) -> float:
    """Scan thicknesses until dose falls within the NASA limit."""
    thickness = 0.0
    while attenuated_dose(thickness) > NASA_ANNUAL_LIMIT:
        thickness += step_cm
    return round(thickness, 2)

if __name__ == "__main__":
    min_thickness = find_minimum_thickness()
    print(f"Minimum shielding required: {min_thickness} cm")
    print(f"Resulting dose: {attenuated_dose(min_thickness):.2f} mSv/year")

    print("\n-- Thickness scan --")
    for t in range(0, 16):
        dose = attenuated_dose(t)
        flag = " ✓ SAFE" if dose <= NASA_ANNUAL_LIMIT else " ✗"
        print(f"  {t:>2} cm → {dose:>7.2f} mSv/year{flag}")
```

> **Note:** Attenuation coefficient is a coarse GCR approximation. High-energy particles and secondary neutron production are not modelled — see the full Monte Carlo results in the radiation analysis appendix.


## Structural & Thermal Analysis

### 1. Pressure Vessel Hoop Stress

The cylindrical pressure shell must sustain internal overpressure. The circumferential (hoop) stress in the Al-Li 2195 shell is given by:

$$\sigma_{\theta} = \frac{p \, r}{t}$$

where <span style="color:#a9c7ff;">$p = 101.3\ \text{kPa}$</span> is the internal gauge pressure, <span style="color:#ffaaf7;">$r = 2.15\ \text{m}$</span> is the shell mid-radius, and <span style="color:#7deba0;">$t = 4.8\ \text{mm}$</span> is wall thickness. With a safety factor $\eta = 2.0$ applied against the Al-Li yield strength $\sigma_y = 503\ \text{MPa}$:

$$\eta \cdot \sigma_{\theta} = \frac{2.0 \times 101.3 \times 10^3 \times 2.15}{4.8 \times 10^{-3}} \approx \color{#ffd966}{90.7\ \text{MPa}} \ll \sigma_y$$

Shell design is <span style="color:#50e764;">**margin-positive**</span> under nominal atmospheric loading.

---

### 2. Radiation Attenuation — Water Wall

The exponential attenuation model used in Dr. Vasquez's script formalised:

$$\Phi(x) = \Phi_0 \, e^{-\mu x}$$

Solving for the minimum compliant thickness $x^*$ at the <span style="color:#ff9e7a;">NASA annual limit</span> $\Phi_{\lim} = 20\ \text{mSv/yr}$:

$$x^* = \frac{1}{\mu} \ln\!\left(\frac{\Phi_0}{\Phi_{\lim}}\right) = \frac{1}{0.096} \ln\!\left(\frac{300}{20}\right) \approx \color{#ff9e7a}{28.6\ \text{cm}}$$

> The 8 cm design figure assumes supplemental polyethylene-equivalent offset from structure and MMOD blankets. Full Monte Carlo results revise $\mu_{\text{eff}}$ upward — see secondary neutron correction term below.

The secondary neutron flux correction applied by [[Dr. Elena Vasquez]] introduces a build-up factor $B(x)$:

$$\Phi_{\text{total}}(x) = \Phi_0 \, B(\mu x)\, e^{-\mu x}, \qquad B(\mu x) = 1 + \color{#ce9aff}{A\,(\mu x)\,e^{\,b\,\mu x}}$$

where empirical fit coefficients for GCR in water are $A = 0.427$, $b = 0.116$.

---

### 3. Thermal Control — Radiator Sizing

Waste heat $\dot{Q}$ radiated from the habitat's external panel array follows the Stefan–Boltzmann law:

$$\dot{Q} = \varepsilon \, \sigma_{\text{SB}} \, A_{\text{rad}} \left( T_{\text{rad}}^4 - T_{\text{sink}}^4 \right)$$

For the Neo-Kyoto module with emissivity <span style="color:#7deba0;">$\varepsilon = 0.88$</span>, radiator temperature <span style="color:#a9c7ff;">$T_{\text{rad}} = 318\ \text{K}$</span>, and deep-space sink <span style="color:#9a9da6;">$T_{\text{sink}} = 4\ \text{K}$</span>, required area for $\dot{Q} = 14.2\ \text{kW}$ continuous dissipation:

$$A_{\text{rad}} = \frac{\dot{Q}}{\varepsilon \, \sigma_{\text{SB}} \, T_{\text{rad}}^4} = \frac{14200}{0.88 \times 5.67\times10^{-8} \times 318^4} \approx \color{#ffd966}{8.7\ \text{m}^2}$$

---

### 4. Crew Volume Allocation

Pressurized volume $V_p = 148\ \text{m}^3$ is partitioned across $n = 12$ crew. The <span style="color:#ffaaf7;">habitable volume index</span> $\mathcal{H}$ (NASA-STD-3001 metric) accounts for equipment packing fraction $\phi = 0.38$:

$$\mathcal{H} = \frac{V_p\,(1 - \phi)}{n} = \frac{148 \times 0.62}{12} \approx \color{#7deba0}{7.65\ \text{m}^3/\text{person}}$$

This exceeds the <span style="color:#50e764;">long-duration mission threshold</span> of $5.66\ \text{m}^3/\text{person}$ by a margin of:

$$\Delta\mathcal{H} = \mathcal{H} - \mathcal{H}_{\min} = 7.65 - 5.66 = \color{#a9c7ff}{+1.99\ \text{m}^3/\text{person}}$$

---

### 5. Orbital Decay — Atmospheric Drag Estimate

At the design orbital altitude $h = 420\ \text{km}$, the drag-induced semi-major axis decay rate for the module:

```math
\left\langle \frac{da}{dt} \right\rangle = -\frac{C_D \, A_{\text{ref}} \, \rho(h)}{m} \sqrt{\mu_\oplus \, a}
```

With <span style="color:#ce9aff;">$C_D = 2.2$</span>, frontal area $A_{\text{ref}} = 31.4\ \text{m}^2$, module mass $m = 18{,}400\ \text{kg}$, and NRLMSISE-00 density $\rho(420\ \text{km}) = 3.1 \times 10^{-12}\ \text{kg/m}^3$:

$$\left\langle \frac{da}{dt} \right\rangle \approx \color{#ff9e7a}{-47\ \text{m/day}}$$

Reboost cadence requirement: $\Delta v_{\text{annual}} \approx 17.2\ \text{m/s/yr}$ — within the allocated propellant budget per [[Orbital Mechanics]].

## Embedded Image Demo

Here's the station concept alongside the test image from the vault:

![[nexus-patch.png]]

## Materials

| Component | Material | Mass (kg) |
|-----------|----------|-----------|
| Pressure shell | Al-Li 2195 | 4,200 |
| MMOD shielding | Nextel/Kevlar | 1,800 |
| Interior structure | Carbon fiber | 2,100 |
| Windows (x6) | Fused silica | 340 |
| Hatch mechanisms | Ti-6Al-4V | 280 |

## Related

- [[System Architecture]] - power and life support integration
- [[Marcus Kim]] - structural engineering lead
- [[Dr. Elena Vasquez]] - radiation analysis
- [[Mission Briefing]] - schedule and budget

#design #habitat #engineering #approved


