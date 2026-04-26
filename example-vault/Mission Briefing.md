---
tags: [mission, planning, priority/critical]
created: 2026-03-25
status: active
---

# Mission Briefing: Project Perihelion

**Objective:** Design, build, and deploy a 12-person commercial research station in Low Earth Orbit by Q4 2027. 

**Mission Lead:** [[Zara Okafor]]
**Science Lead:** [[Dr. Elena Vasquez]]
**Systems Lead:** [[Marcus Kim]] 

## Timeline


```mermaid
---
config:
  theme: 'dark'
  themeVariables: 
    taskBkgColor: '#1a1a2e'
    taskBorderColor: '#e94560'
    taskTextColor: 'white'
    taskTextDarkColor: 'white'
    taskTextLightColor: '#ffffff'
    taskTextOutsideColor: '#cccccc'
    taskTextClickableColor: '#00e9e2'
    activeTaskBkgColor: '#0f3460'
    activeTaskBorderColor: '#00d4ff'
    doneTaskBkgColor: '#16213e'
    doneTaskBorderColor: '#4a4a6a'
    critBkgColor: '#7b0000'
    critBorderColor: '#ff4444'
    todayLineColor: '#e2e1e6'
    gridColor: '#2a2a4a'
    sectionBkgColor: '#0d0d1a'
    sectionBkgColor2: '#111128'
    altSectionBkgColor: '#13132a'
    titleColor: 'Turquoise'
    textColor: '#e2e1e6'
---
gantt
    title Project Perihelion Timeline
    dateFormat  MM-DD
    axisFormat  %b
    section Design
        Station Architecture:done, d1, 2026-01-15, 110d
        Hab Module Des.     :done, d2, 2026-02-01, 90d
        Life Sup Specs      :active, d3, 2026-03-01, 75d
    section Engineering
        Struct Prototyping  :active, e1, 2026-04-01, 100d
        Power Systems       :e2, after e1, 80d
        Comms               :e3, after e2, 45d
    section Testing
        Vacuums             :t1, 2026-09-01, 55d
        Full                :t2, after t1, 60d
        Final               :l1, 2027-01-15, 90d
        Launch              :milestone, l2, 2027-02-01, 10d
```  

## Budget Overview

```mermaid
---
config:
  theme: 'base'
---
pie title Budget Allocation ($ Millions)
    "Hardware & Materials" : 42
    "Personnel" : 28
    "Testing & Certification" : 15
    "Launch Services" : 35
    "Contingency" : 11
```

## Key Risks 

> [!danger] Launch Window 
> The February 2027 window is non-negotiable. Miss it and we wait 8 months for the next orbital alignment. See [[Orbital Mechanics#Transfer Windows]] for the math.

> [!warning] Life Support Redundancy
> Current design has single-point-of-failure in CO2 scrubbing. [[Marcus Kim]] is leading the redesign. Tracked in [[Sprint Review 2026-03-25]].

> [!success] Habitat Module
> Structural design passed all simulation loads. [[Habitat Design]] is approved for prototyping.

## Related

- [[System Architecture]] - full technical diagram
- [[Orbital Mechanics]] - trajectory and orbit calculations
- [[Sprint Review 2026-03-25]] - latest progress

#mission #perihelion #planning

