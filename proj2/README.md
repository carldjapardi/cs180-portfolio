# Project 2 website

The report is `proj2_index.html`, with one stylesheet (`styles.css`) and local
figures in `assets/`. It uses plain HTML and CSS; no build step, JavaScript,
framework, or external font is needed. The portfolio home page links here.

Preview from `180-portfolio`:

```sh
python3 -m http.server 8002 --bind 127.0.0.1
```

Open `http://127.0.0.1:8002/proj2/proj2_index.html`.

## Coverage

| Requirement | Page anchor and evidence |
| --- | --- |
| 1.1: four-loop and two-loop convolution | `#convolution`: actual code snippets, zero padding, flipped kernels, selfie, box and derivative comparisons, measured timings |
| 1.2: finite differences | `#finite-difference`: original, both derivatives, magnitude, binary edges, threshold justification |
| 1.3: Gaussian and DoG | `#dog`: Gaussian and derivative kernels, both pipelines, comparison with raw derivatives, boundary caveat |
| 1: extra credit | `#dog`: HSV gradient directions computed without built-in angle functions |
| 2.1: unsharp masking | `#sharpening`: derivation, Taj Mahal and building decompositions, four sharpening amounts, blur-then-sharpen experiment |
| 2.2: three hybrid images | `#hybrids`: Derek/Nutmeg, expression, and Ronaldo; two originals and the hybrid at full and 10% size for each |
| 2.2: detailed process | `#hybrids`: original and aligned Ronaldo images, filtered results, five spectra, filter widths, interpretation and limitations |
| 2.2: extra credit | `#hybrids`: grayscale, low-frequency color, high-frequency color, and both-color comparison with a controlled fruit pair |
| 2.3: stacks | `#stacks`: all six Gaussian and Laplacian levels for each fruit; residual and reconstruction explanation |
| 2.3–2.4: Figure 3.42 | `#blending`: twelve labeled panels, masked bands at levels 0/2/4, reconstructed source contributions, and final result |
| 2.4: custom blends | `#blending`: Seattle/ocean, moon/street, and moon/ocean; both moon pairs use curved masks |
| 2.4: process and extra credit | `#blending`: mask stack, expanded moon breakdown, RGB vs. grayscale, discussion of halos |
| Reflection | `#reflection`: the main lesson and limitations |

The page follows the supplied `180-code/proj2/proj_reqs.pdf`, including the stricter
instruction to show two nonlinear-mask pairs in addition to a straight-seam blend.
Grades remain at the course staff's discretion.

## Figure provenance

Existing final outputs are copied from `180-code/proj2/out`; originals come from
`180-code/proj2/input`. Earlier outputs `2_4.png` (an older oraple) and `2_4_crb.png`
(an experiment without a corresponding saved processing path) are not used.
The final reproducible oraple, skyline, and moon outputs are used instead.

`180-code/proj2/report_assets.py` generates the missing comparisons and extra-credit
figures using the existing filters and stack functions. It adds no generated or
stock photography. It also writes `assets/measurements.json` with measured numerical
checks and median timings. Large exported PNGs are encoded as WebP for the website;
original code outputs remain untouched. Source previews are JPEGs capped at 1280 px.

Run the exporter from the parent `180` directory:

```sh
MPLCONFIGDIR=/tmp/proj2-matplotlib python3 180-code/proj2/report_assets.py
```

This refreshes assets, not page copy. If rerunning on another machine, update the
timing table using the new measurements. Hybrid alignments in the original code
are interactive; their selected points were not saved, so the report retains the
provided hybrid outputs rather than silently realigning them.

## Submission

The website files are ready to publish with the existing portfolio. Keep the
processing code and input images in the separate code submission; ensure it includes
`report_assets.py` for the added figures. Publishing, course submission, and the
class-gallery form have not been performed by this website build.
