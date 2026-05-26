# HOM Multi-Metric Simulator

Jupyter/QuTiP simulator for the manuscript:

**Melissa Coronado-Arrieta and Boris Kiefer,  
"Beyond the HOM Dip: A Multi-Metric Module for Teaching Two-Mode Quantum Optical Interference"**

This notebook supports an upper-division quantum optics module on Hong--Ou--Mandel (HOM) interference beyond the canonical coincidence dip. It compares Fock, superposition, coherent, and squeezed two-mode inputs under three output metrics:

- on/off coincidence probability \(P_c\),
- normalized cross-correlation \(g^{(2)}_{12}\),
- noise-reduction factor (NRF).

## Repository contents

```text
README.md
requirements.txt
sim_HOM.ipynb
LICENSE
```

## Key convention

The simulator uses the beam-splitter convention

\[
t=\cos(\theta/2), \qquad r=e^{i\phi}\sin(\theta/2),
\]

with the balanced point at \(\theta=\pi/2\). The default module setting is \(\phi=\pi/2\).

The coincidence metric \(P_c\) is an **on/off threshold-detector coincidence probability**:

\[
P_c = 1-P_{0,c}-P_{0,d}+P_{0,cd}.
\]

For the \(|1\rangle_a|1\rangle_b\) input, this equals the usual one-photon-in-each-output HOM coincidence event. For coherent and squeezed inputs, it includes multiphoton threshold-detector coincidences and is not only the projection onto \(|1,1\rangle\).

## Installation

```bash
python -m venv hom_env
source hom_env/bin/activate  # Windows: hom_env\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

or with conda:

```bash
conda create -n hom_env python=3.11
conda activate hom_env
pip install -r requirements.txt
jupyter lab
```

## Recommended first run

1. Open the notebook.
2. Select the Fock and coherent input families.
3. Sweep \(\theta\) through \(\theta=\pi/2\).
4. Compare \(P_c(\theta)\), \(g^{(2)}_{12}(\theta)\), and NRF\((\theta)\).
5. Add the superposition and squeezed inputs.
6. Identify where different metrics agree or disagree.

## Default settings

| Quantity | Default |
|---|---|
| Beam-splitter phase | \(\phi=\pi/2\) |
| Sweep | \(\theta\in[0,\pi]\) |
| Coherent input | \(|\alpha|=1\), \(\arg\alpha=0\) |
| Squeezed input | equal SMSV inputs, \(r=6\) dB |
| Squeezing phases | \(0\), \(\pi/2\) |
| Fock cutoff | \(N_{\rm cut}=12\) |
| Sweep grid | 61 points |

## Citation

A formal citation, DOI, arXiv identifier, or journal reference will be added when available.

## Authors

- Melissa Coronado-Arrieta, Department of Physics, New Mexico State University
- Boris Kiefer, Department of Physics, New Mexico State University  
  Email: bkiefer@nmsu.edu

## Acknowledgements

Melissa Coronado-Arrieta and Boris Kiefer acknowledge support from the National Science Foundation through QCAP-Pilot and QCAP-Design, NSF Award Nos. OSI-2410813 and OSI-2531569.

## License

See `LICENSE`.
