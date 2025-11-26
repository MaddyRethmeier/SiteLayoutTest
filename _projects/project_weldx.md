---
layout: page
title: WelDX
description: The welding data exchange format
img: assets/img/WelDX.png
importance: 1
category: Projects
related_publications: false
---

Scientific welding data covers a wide range of physical domains and
timescales and are measured using various different sensors. Complex and
highly specialized experimental setups at different welding institutes
complicate the exchange of welding research data further.

The WelDX research project aims to foster the exchange of scientific
data inside the welding community by developing and establishing a new
open source file format suitable for the documentation of experimental
welding data and upholding associated quality standards. In addition to
fostering scientific collaboration inside the national and international
welding community an associated advisory committee will be established
to oversee the future development of the file format. The proposed file
format will be developed with regard to current needs of the community
regarding interoperability, data quality and performance and will be
published under an appropriate open source license. By using the file
format objectivity, comparability and reproducibility across different
experimental setups can be improved.

The project is under active development by the [Welding Technology](https://www.bam.de/Navigation/EN/About-us/Organisation/Organisation-Chart/President/Department-9/Division-93/division93.html)
division at Bundesanstalt für Materialforschung und -prüfung (BAM).

## Features

WelDX provides several Python API to perform standard tasks like
experiment design, data analysis, and experimental data archiving.

### Planning

- Define measurement chains with all involved devices, error sources,
  and metadata annotations.
- Handle complex coordinate transformations needed to describe the
  movement of welding robots, workpieces, and sensors.
- Planing of welding experiments.
- convenient creation of [ISO 9692-1](https://www.iso.org/standard/62520.html) welding groove types.

### Data analysis

- Plotting routines to inspect measurement chains, workpieces (planned
  and welded).
- Analysis functions for standard measurements like track energy,
  welding speed to fill an ISO groove, and more to come.

### Data archiving

The ultimate goal of this project is to store all information about the
experiment in a single file. We choose the popular [ASDF](https://en.wikipedia.org/wiki/Advanced_Scientific_Data_Format)
format for this task. This enables us to store arbitrary binary data,
while maintaining a human readable text based header. All information is
stored in a tree like structure, which makes it convenient to structure
the data in arbitrary complex ways.

The ASDF format and the provided extensions for WelDX types like

- workpiece information (used alloys, geometries)
- welding process parameters (GMAW parameters)
- measurement data
- coordinate systems (robot movement, sensors)

enables us to store the whole experimental pipeline performed in a
modern laboratory.

## Design goals

We seek to provide a user-friendly, well documented programming
interface. All functions and classes in WelDX have attached
documentation about the involved parameters (types and explanation), see
[API docs](https://weldx.readthedocs.io/en/stable/api.html). Further
we provide rich [Jupyter notebook tutorials](https://weldx.readthedocs.io/en/stable/tutorials.html) about the
handling of the basic workflows.

All involved physical quantities used in `weldx` (lengths, angles,
voltages, currents, etc.) should be attached with a unit to ensure
automatic conversion and correct mathematical handling. Units are being
used in all standard features of WelDX and are also archived in the ASDF
files. This is implemented by the popular Python library [Pint](https://pint.readthedocs.io/en/stable/), which flawlessly handles
the creation and conversion of units and dimensions.
