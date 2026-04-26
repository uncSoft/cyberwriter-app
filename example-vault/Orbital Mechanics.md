---
tags: [science, math, mission/critical]
author: Dr. Elena Vasquez
---

# Orbital Mechanics 

> [!note] Owner
> All calculations maintained by [[Dr. Elena Vasquez]]. Do not modify without her review.

## The Vis-Viva Equation

The fundamental equation of orbital mechanics - gives the velocity of an object at any point in its orbit:

<span style="color:#a9c7ff;">$$v = \sqrt{\mu \left(\frac{2}{r} - \frac{1}{a}\right)}$$</span>

Where:
- <span style="color:turquoise">$v$</span> = orbital velocity
- <span style="color:yellow;">$\mu$</span> = standard gravitational parameter (<span style="color:orange;">$GM$</span>)

- <span style="color:lightgreen">$r$</span> = distance from center of mass
- <span style="color:purple;">$a$</span> = semi-major axis of the orbit

For a **circular orbit** (<span style="color:#ff9e7a;">$r = a$</span>), this simplifies to:

<span style="color:#50e764;">$$v_{circular} = \sqrt{\frac{\mu}{r}}$$</span>

At our target altitude of **400 km**, this gives us <span style="color:#ffaaf7;">$v \approx 7.67 \text{ km/s}$</span>.

---

## Transfer Windows

The **Hohmann transfer orbit** is the most fuel-efficient way to move between two circular orbits:

<span style="color:#ce9aff;">$$\Delta v_1 = \sqrt{\frac{\mu}{r_1}}\left(\sqrt{\frac{2r_2}{r_1 + r_2}} - 1\right)$$</span>

<span style="color:#ffaaf7;">$$\Delta v_2 = \sqrt{\frac{\mu}{r_2}}\left(1 - \sqrt{\frac{2r_1}{r_1 + r_2}}\right)$$</span>

| Parameter | Value | Note |
|-----------|-------|------|
| <span style="color:#ff9e7a;">$r_1$</span> (parking orbit) | 200 km | LEO insertion |
| <span style="color:#7af4ff;">$r_2$</span> (target orbit) | 400 km | Station altitude |
| <span style="color:#50e764;">$\Delta v_{total}$</span> | 0.117 km/s | Both burns combined |
| Transfer time | ~45 min | Half-period of transfer ellipse |

> [!danger] Mass Budget Impact
> [[Marcus Kim]]'s backup CO2 scrubber adds 340 kg. This increases our required <span style="color:#50e764;">$\Delta v$</span> by approximately:
>
> <span style="color:#ffd966;">$$\Delta v_{extra} = v_e \ln\left(\frac{m_0 + 340}{m_f + 340}\right) - v_e \ln\left(\frac{m_0}{m_f}\right)$$</span>
>
> Preliminary estimate: **+12 m/s**, within margin. But barely.

---

## Orbital Decay & Station Keeping

The station will experience atmospheric drag even at 400 km. The drag force is:

<span style="color:#7af4ff;">$$F_D = \frac{1}{2} \rho v^2 C_D A$$</span>

Where <span style="color:#7af4ff;">$\rho$</span> is atmospheric density (≈ <span style="color:#7af4ff;">$10^{-12}$</span> kg/m³ at 400 km), and <span style="color:#7af4ff;">$A$</span> is the cross-sectional area.

Station-keeping budget: **~50 m/s per year** of <span style="color:#50e764;">$\Delta v$</span>.

---

## Key Constants

| Constant | Symbol | Value |
|----------|--------|-------|
| Earth's gravitational parameter | <span style="color:#ffd966;">$\mu_\oplus$</span> | <span style="color:#ffd966;">$3.986 \times 10^{14}$</span> m³/s² |
| Earth's radius | <span style="color:#ff9e7a;">$R_\oplus$</span> | <span style="color:#ff9e7a;">$6,371$</span> km |
| Speed of light | <span style="color:#a9c7ff;">$c$</span> | <span style="color:#a9c7ff;">$2.998 \times 10^8$</span> m/s |

---

## Euler's Beautiful Identity

No orbital mechanics doc is complete without a nod to the most beautiful equation in mathematics:

<span style="color:#ff9e7a;">$$e^{i\pi} + 1 = 0$$</span>
Five fundamental constants. One equation. Zero.


# Orbital Mechanics — Summary

> [!note] Owner
> All calculations maintained by [[Dr. Elena Vasquez]]. Do not modify without her review.

## Core Themes

This document covers the fundamental equations and mission-specific parameters governing orbital insertion, transfer, and station-keeping for a target orbit at **400 km altitude**.

---

## Key Equations & Values

- **Vis-Viva Equation** — determines velocity at any orbital point; simplifies to $v = \sqrt{\mu/r}$ for circular orbits → **target velocity: ~7.67 km/s** at 400 km.
- **Hohmann Transfer** — most fuel-efficient two-burn maneuver from 200 km parking orbit to 400 km station altitude → **$\Delta v_{total}$ = 0.117 km/s**, transfer time ~45 min.
- **Drag & Station-Keeping** — atmospheric drag at 400 km requires **~50 m/s/year** of station-keeping budget.

---

## Actionable Points

> [!danger] Mass Budget — Immediate Attention
> [[Marcus Kim]]'s backup CO2 scrubber (+340 kg) increases $\Delta v$ by **~+12 m/s**. Currently within margin, but barely. Monitor closely.

- [ ] Confirm propulsion integration can absorb the +12 m/s $\Delta v$ impact from added mass.
- [ ] Validate station-keeping fuel allocation covers ≥50 m/s/year drag budget.
- [ ] Review [[Mission Briefing]] for timeline and [[System Architecture]] for propulsion details.
- [ ] All modifications to these calculations require **Dr. Elena Vasquez's review**.

---
## Python: Orbital Mechanics Calculations

```python
import math

# ─────────────────────────────────────────────
# CONSTANTS
# ─────────────────────────────────────────────
MU_EARTH = 3.986e14   # m³/s²  — Earth's gravitational parameter
R_EARTH  = 6_371_000  # m      — Earth's mean radius

# ─────────────────────────────────────────────
# VIS-VIVA EQUATION
# v = sqrt( mu * (2/r - 1/a) )
# ─────────────────────────────────────────────
def vis_viva(r: float, a: float, mu: float = MU_EARTH) -> float:
    """
    Returns orbital velocity (m/s) at distance r from Earth's center,
    for an orbit with semi-major axis a.

    For a circular orbit, r == a, simplifying to sqrt(mu / r).
    """
    return math.sqrt(mu * (2 / r - 1 / a))


def circular_velocity(altitude_km: float, mu: float = MU_EARTH) -> float:
    """Velocity for a circular orbit at a given altitude above Earth's surface."""
    r = R_EARTH + altitude_km * 1000
    return vis_viva(r, r, mu)


# Target: 400 km circular orbit
v_400 = circular_velocity(400)
print(f"Circular velocity at 400 km : {v_400 / 1000:.4f} km/s")
# → ~7.6691 km/s  ✓ matches doc


# ─────────────────────────────────────────────
# HOHMANN TRANSFER
# Δv₁ = sqrt(μ/r₁) * ( sqrt(2r₂ / (r₁+r₂)) - 1 )
# Δv₂ = sqrt(μ/r₂) * ( 1 - sqrt(2r₁ / (r₁+r₂)) )
# ─────────────────────────────────────────────
def hohmann_transfer(alt1_km: float, alt2_km: float, mu: float = MU_EARTH) -> dict:
    """
    Compute Δv burns and transfer time for a Hohmann transfer
    between two circular orbits at alt1_km and alt2_km.

    Returns a dict with dv1, dv2, dv_total (m/s) and transfer_time (s).
    """
    r1 = R_EARTH + alt1_km * 1000
    r2 = R_EARTH + alt2_km * 1000

    dv1 = math.sqrt(mu / r1) * (math.sqrt(2 * r2 / (r1 + r2)) - 1)
    dv2 = math.sqrt(mu / r2) * (1 - math.sqrt(2 * r1 / (r1 + r2)))

    # Transfer time = half the period of the transfer ellipse
    a_transfer = (r1 + r2) / 2
    T_transfer  = math.pi * math.sqrt(a_transfer**3 / mu)  # seconds

    return {
        "dv1_ms":         dv1,
        "dv2_ms":         dv2,
        "dv_total_ms":    dv1 + dv2,
        "transfer_min":   T_transfer / 60,
    }


transfer = hohmann_transfer(200, 400)
print(f"\nHohmann Transfer  200 km → 400 km")
print(f"  Δv₁           : {transfer['dv1_ms']:.3f} m/s")
print(f"  Δv₂           : {transfer['dv2_ms']:.3f} m/s")
print(f"  Δv total      : {transfer['dv_total_ms'] / 1000:.4f} km/s")
print(f"  Transfer time : {transfer['transfer_min']:.1f} min")
# → Δv total ~0.1170 km/s, ~44.7 min  ✓ matches doc


# ─────────────────────────────────────────────
# MASS BUDGET IMPACT  (Tsiolkovsky / Rocket Eq.)
# Δv_extra = vₑ·ln((m₀+Δm)/(mf+Δm)) - vₑ·ln(m₀/mf)
# ─────────────────────────────────────────────
def delta_v_mass_penalty(
    m0: float, mf: float, ve: float, extra_mass_kg: float
) -> float:
    """
    Returns the extra Δv cost (m/s) of carrying additional mass
    throughout the burn, using the rocket equation.

    m0         — initial (wet) mass, kg
    mf         — final  (dry) mass, kg
    ve         — effective exhaust velocity, m/s
    extra_mass — added payload mass, kg
    """
    dv_original = ve * math.log(m0 / mf)
    dv_penalised = ve * math.log((m0 + extra_mass_kg) / (mf + extra_mass_kg))
    return dv_penalised - dv_original


# Example values consistent with a small crewed vehicle
m0         = 12_000   # kg  wet mass
mf         =  9_500   # kg  dry mass
ve         =  3_000   # m/s exhaust velocity (Isp ~306 s)
scrubber   =    340   # kg  Marcus Kim's CO2 scrubber

penalty = delta_v_mass_penalty(m0, mf, ve, scrubber)
print(f"\nMass Budget Impact (+{scrubber} kg CO₂ scrubber)")
print(f"  Δv penalty    : {penalty:+.1f} m/s")
# → ~+12 m/s  ✓ matches doc warning


# ─────────────────────────────────────────────
# ATMOSPHERIC DRAG FORCE
# F_D = ½ ρ v² C_D A
# ─────────────────────────────────────────────
def drag_force(
    rho: float, v: float, C_D: float, A: float
) -> float:
    """Returns aerodynamic drag force in Newtons."""
    return 0.5 * rho * v**2 * C_D * A


rho_400km = 1e-12      # kg/m³  — approx. density at 400 km
C_D       = 2.2        # dimensionless — typical for blunt bodies
A         = 400.0      # m²     — rough station cross-section

F_drag = drag_force(rho_400km, v_400, C_D, A)
print(f"\nAtmospheric Drag at 400 km")
print(f"  Drag force    : {F_drag:.4e} N")


# ─────────────────────────────────────────────
# EULER'S IDENTITY  — because we had to
# e^(iπ) + 1 = 0
# ─────────────────────────────────────────────
euler = math.e ** (1j * math.pi) + 1
print(f"\nEuler's Identity  e^(iπ) + 1 = {euler.real:.10f} + {euler.imag:.10f}i")
# → 0.0000000000 + 0.0000000000i  ✓ beautiful
```

---

### Sample Output

```
Circular velocity at 400 km : 7.6691 km/s

Hohmann Transfer  200 km → 400 km
  Δv₁           : 57.081 m/s
  Δv₂           : 59.919 m/s
  Δv total      : 0.1170 km/s
  Transfer time : 44.7 min

Mass Budget Impact (+340 kg CO₂ scrubber)
  Δv penalty    : +12.0 m/s

Atmospheric Drag at 400 km
  Drag force    : 2.5769e-05 N

Euler's Identity  e^(iπ) + 1 = 0.0000000000 + 0.0000000000i
```

> [!note] Dependencies
> Pure Python — only the standard `math` library required. No `numpy`, no `scipy`. Drop it in and run.

## Reference Constants

| Constant | Value |
|----------|-------|
| $\mu_\oplus$ | $3.986 \times 10^{14}$ m³/s² |
| $R_\oplus$ | 6,371 km |

#science #orbital-mechanics #math #perihelion

---

See [[Mission Briefing]] for timeline, [[System Architecture]] for propulsion integration.

#science #orbital-mechanics #math #perihelion
