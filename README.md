This repository contains a Jupyter notebook that reproduces the main catalog search result of Yang+2026

`SESN_GW_coincidence.ipynb` uses only public data (the ZTF Bright Transient Survey and GraceDB):

- **Steps 1–7** reproduce the catalogue search of Yang+26: the stripped-envelope supernova sample, the gravitational-wave sample, sky and time matching, close pairs of gravitational-wave candidates, and the chance-coincidence statistics.
- **Step 8** evaluates the odds of association, O/ξ = I_t p̄_V / R_class (Lasky+), from the public sky maps for each proposed gravitational-wave–supernova association: SN 2019rsq (S190910d, S190910h), SN 2019qwo (S190910h, S190901ap), SN 2025tt (S241230ev, S250101k), AT 2025ulz (S250818k; Kasliwal+25) and SN 2025adtq (S251112cm; Hall+26).

## Running

Dependencies: `numpy scipy astropy pandas matplotlib requests ligo-gracedb`, and a LaTeX installation for the figure labels. No `healpy` or `ligo.skymap` is needed.

Downloads are cached in `data_cache/`, which is not tracked. From an empty cache, the notebook downloads the BTS catalogue and about 1 GB from GraceDB; this took about 6 minutes on a laptop, and the cache grows to about 6 GB, mostly the resampled NSIDE-256 maps. With a full cache, the notebook runs in under a minute.

## Data

- `data/sn2019qwo_explosion_epoch.csv`: 3,510 posterior samples of the explosion epoch of SN 2019qwo (MJD), from a redback Arnett-model fit to its ZTF photometry (Lasky+). Step 8 uses them for the timing overlap.
