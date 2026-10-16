# RayCrypt

An experimental research concept for representing data through geometric ray–surface intersections.

RayCrypt explores a question: **can a data table be represented as a geometric environment, then queried through the path of a ray?** The idea connects data representation, analytical geometry, and classical optics.

**Status:** this repository contains concept notes and an example JSON configuration. It does not yet contain a ray tracer, an implemented cryptosystem, or a compressor. Security, reversibility, compression, and performance have not been validated.

## The proposed model

A table would be mapped into a virtual 2D or 3D scene:

| Data element | Proposed geometric representation |
| --- | --- |
| Cell position | Position of a surface or optical element |
| Cell value | Surface orientation, refractive index, reflectivity, or an associated label |
| Query or input | Ray origin and direction |
| Output | Intersection point, exit direction, or sequence of surface interactions |

The intended experiment is to trace a ray through this scene using reflection or refraction rules and study whether the resulting mapping is useful for data lookup or representation. These rules and the encoding/decoding procedures still need to be specified and implemented.

## Research directions

### Geometric data mapping

The first goal is a small, deterministic example: define a scene, trace an input ray, record its intersections, and show how the result relates to a known data value. This would make the central idea testable before exploring further applications.

### Encryption and hashing concepts

The original proposal considers turning an input into an initial ray and using its final intersection or exit direction as a transformed value. It also suggests exploring scene parameters as a key.

These are research questions, not established cryptographic properties. Sensitivity to input changes does not establish security, and a ray path does not by itself define an invertible encoding or a collision-resistant hash. A complete design would need a threat model, key definition, decoding rules, numerical analysis, and independent cryptographic review. **Do not use RayCrypt to protect sensitive data.**

### Geometric approximation and compression

Another proposed direction is to approximate structured data with curves or surfaces, storing the model and reconstructing values through intersections. Any evaluation would need to count the model, parameters, metadata, and residual data, then measure reconstruction error and compare against a baseline.

No compression algorithm or measured compression ratio is included here. Exact reconstruction and useful storage savings remain open questions.

Possible later experiments include visual steganography and geometry-based identifiers. DRM was also suggested in the original concept; it would require the same unresolved security work as the encryption idea.

## Explore the example configuration

[`schema.json`](schema.json) is a **sample scene configuration**, despite its filename. It is not a formal JSON Schema and does not validate other files.

The example describes:

- A cube centred at `[0, 0, 0]`, with width, height, and depth of `10`.
- A ray starting at `[0, -15, 0]`, with direction `[0.1, 1.0, 0.2]`.
- Proposed settings of eight maximum bounces and `float64` precision.
- Six named faces, each with a normal vector and inside/outside labels.

These fields describe the intended input format; no engine currently interprets them.

With Python 3 installed, clone the repository and enter its directory:

```sh
git clone https://github.com/Z23599848/RayCrypt.git
cd RayCrypt
```

Save the following as `inspect_config.py`, then run `python inspect_config.py`:

```python
import json
from pathlib import Path

config = json.loads(Path("schema.json").read_text(encoding="utf-8"))
print("Geometry:", config["geometry"]["shape"])
print("Faces:", len(config["incident_dictionary"]["faces"]))
print("Max bounces:", config["laser_settings"]["max_bounces"])
```

Expected output:

```text
Geometry: cube
Faces: 6
Max bounces: 8
```

This checks that the example can be parsed and inspected. It does not run a simulation or validate the proposed model.

## Next milestones

- [ ] Specify ray, surface, coordinate, and data-encoding conventions.
- [ ] Implement a minimal analytical ray–surface intersection example.
- [ ] Add reproducible cases for hits, misses, repeated interactions, and numerical edge cases.
- [ ] Define an encoding/decoding pair and measure reconstruction error.
- [ ] Benchmark storage and execution time against simple baselines.
- [ ] Evaluate any proposed security application separately, with a documented threat model and independent review.

Contributions that turn one of these questions into a small, reproducible experiment are welcome. Please include assumptions, a runnable example, and evidence for any claimed result.

## Author and licence

Created by **Ali Ganji**. Licensed under the [Apache License 2.0](LICENSE).

