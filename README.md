# Make Watershed BEM

[![Run on Brainlife.io](https://img.shields.io/badge/Brainlife-bl.app.807-blue.svg)](https://doi.org/10.25663/brainlife.app.807)

## Description

This app computes a watershed Boundary Element Model (BEM) surface from a FreeSurfer subject
reconstruction, using [MNE-Python's `mne.bem.make_watershed_bem`](https://mne.tools/stable/generated/mne.bem.make_watershed_bem.html#mne-bem-make-watershed-bem)
function (which wraps FreeSurfer's watershed algorithm). The FreeSurfer subject directory is
copied into `out_dir`, the watershed BEM surfaces are generated there, and a QC report
visualizing the BEM surfaces over the MRI is produced.

The app generates:
- The FreeSurfer subject reconstruction, copied into `out_dir`, with the generated `.surf` BEM
  surface files added to it
- An HTML QC report with MRI/BEM surface visualization

## Inputs

- **`output`** (`neuro/freesurfer`): FreeSurfer subject reconstruction directory (`recon-all`
  output) to compute the watershed BEM surfaces from (required)

## Outputs

- `out_dir/`: copy of the input FreeSurfer subject directory, including the generated watershed
  BEM `.surf` files
- `out_report/report.html`: QC report with MRI/BEM surface visualization
- `product.json`: metadata about the BEM computation

## Configuration Parameters

| key | type | default | description |
|-----|------|---------|-------------|
| `output` | string (path) | `in_dir/freesurfer` | Path to the FreeSurfer subject reconstruction directory (`SUBJECTS_DIR`) |

## Usage

### Running on Brainlife.io

1. Go to the [Make watershed BEM](https://doi.org/10.25663/brainlife.app.807) app page on
   brainlife.io.
2. Select a FreeSurfer reconstruction (`neuro/freesurfer`) as input.
3. Submit the process and retrieve `out_dir` (the FreeSurfer subject directory with its new BEM
   surfaces) and `out_report/report.html` once it completes.

### Local Testing

```bash
# Create a config.json pointing to a FreeSurfer subject reconstruction directory
python3 main.py
```

## Authors
- [Kami Salibayeva] (ksalibay@iu.edu)

### Contributors
- [Kami Salibayeva] (ksalibay@iu.edu)
- [Maximilien Chaumon] (maximilien.chaumon@icm-institute.org)
- [Guiomar Niso]

## Citations

1. Hayashi, S., Caron, B.A., Heinsfeld, A.S. et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. Nat Methods 21, 809–813 (2024). https://doi.org/10.1038/s41592-024-02237-2
2. Gramfort, A. et al. MEG and EEG data analysis with MNE-Python. Front. Neurosci. 7, 267 (2013). https://doi.org/10.3389/fnins.2013.00267

## Funding Acknowledgement

brainlife.io is publicly funded and for the sustainability of the project it is helpful to Acknowledge the use of the platform. We kindly ask that you acknowledge the funding below in your code and publications. Copy and paste the following lines into your repository when using this code.

[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-1636893](https://img.shields.io/badge/NSF_BCS-1636893-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-ACI-1916518](https://img.shields.io/badge/NSF_ACI-1916518-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1916518)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://grantome.com/grant/NIH/R01-EB029272-01)
[![NIH-NIBIB-R01EB030896](https://img.shields.io/badge/NIH_NIBIB-R01EB030896-green.svg)](https://grantome.com/grant/NIH/R01-EB030896-01)

## License

Copyright (c) 2026 MEEG Brainlife team. Licensed under AGPL-3.0, see [license.txt](license.txt).
