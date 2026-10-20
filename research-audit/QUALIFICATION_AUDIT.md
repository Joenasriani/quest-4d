# Quest-4D Academic Qualification – source audit

Audit basis: commit `8d17426ec3c92aa16d6b7f8fdcad3d9d8375cc48`, examined 2026-10-20.

## Findings

| Claim | Source location | Status | Test / boundary |
|---|---|---|---|
| Tesseract vertices | `index.html`, `vertices4D` | VERIFIED | 16 distinct coordinate tuples in {-1,+1}^4 |
| Edge topology | `index.html`, `edges` | VERIFIED | 32 Hamming-distance-one edges, vertex degree 4 |
| Six 4D rotation planes | `index.html`, `rotateXY/XZ/YZ/XW/YW/ZW` | VERIFIED (mathematics) | Orthogonal 2D rotation blocks, sampled norm conservation |
| 4D perspective reduction | `index.html`, `project4Dto3D` | VERIFIED (formula) | 4/(4-w+0.0001) multiplied by x,y,z; general singularity handling not established |
| User sliders | `index.html`, slider handlers | IMPLEMENTED, runtime not independently tested | Six user angle parameters |
| Orbit camera | `index.html`, `OrbitControls` | IMPLEMENTED, runtime not independently tested | Pan/zoom/orbit enabled |
| Ambient animation | `index.html`, `updateTesseract` | VERIFIED (source) | XY,ZW motion increments per frame rather than elapsed time |
| Immersive VR | Browser script and repository tree | UNSUPPORTED | No WebXR session or headset rendering flow in inspected source |
| Improved learning | `README.md`, `research.html` | UNSUPPORTED | No participants, outcomes or comparative tests |
| Slicing / stereographic projection | Explanatory narrative | PROPOSED or illustrative | Not the executed projection implementation |
| Reproducible source | Six-file tree | PARTIALLY VERIFIED | CDN-based Three.js 0.166.1; no lockfile, CI or local dependency vendor |
| Licensing | Complete tracked tree | UNRESOLVED | No LICENSE file |

## Classification and novelty

Recommended paper type: technical artifact / software demonstration. The mathematics is not novel: Hollasch (1991), *Four-Space Visualization of 4D Objects*; Hanson (1994), *Geometry for N-Dimensional Graphics*, DOI 10.1016/B978-0-12-336156-1.50024-0. Prior software 4D Toys (2017) is also relevant. Do not claim immersive VR, pedagogical effectiveness or priority of tesseract rotation.

## Outstanding release gates

1. Execute instrumented browser/mobile tests; static source inspection does not establish UI reliability.
2. Author confirmation of rights, manuscript license, funding and competing interests.
3. Exhaustive current literature verification and cross-check of legacy public-page references.
4. Independent publication approval of exact PDF and Zenodo fields.

A three-page unreviewed manuscript and local mathematics checks were prepared separately for author review. No publishing, DOI reservation or main-branch change was made.
