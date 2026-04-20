# Data Release README

This is an introduction to the data we have released. For more detailed information, please refer to [Song et al. 2026](https://arxiv.org/abs/2512.01684v2).

During the data processing conducted by theDJA team, for convenience, the PRIMER-COSMOS field was divided into `EAST` and `WEST` subfields, and the PRIMER-UDS field was divided into `NORTH` and `SOUTH` subfields. As a result, this repository contains seven folders (`CEERS`, `JADES-GDS`, `JADES-GDN`, `PRIMER-COSMOS-E`, `PRIMER-COSMOS-W`, `PRIMER-UDS-S`, and `PRIMER-UDS-N`), each corresponding to a different field, with the associated source catalog included within each. In this study, we utilize the most recent data releases available at the time of analysis: `v7.0` for the `PRIMER-COSMOS` field, `v7.2` for the `CEERS`, `JADES-GDS`, and `PRIMER-UDS` fields, and `v7.3` for the `JADES-GDN` field.

The IDs in our catalogue correspond to the IDs on the DJA website.

Each folder contains data for the corresponding field, with the following file formats:

---

## `[Field]-parent-sample.fits`

Contains information for all **good samples** described in [Song et al. 2026](https://arxiv.org/abs/2512.01684v2)

1. A signal-to-noise ratio (S/N) greater than 10 in the detection image ($\rm S/N_{\rm det} > 10$)
2. A reduced chi-squared value satisfying $\chi^2 / N_{\rm filt} \leq 8$ with at least six filters available for photometric redshift estimation ($N_{\rm filt} \geq 6$), where $N_{\rm filt}$ is the number of filters used in the fit.
3. F444W magnitude brighter than 28.5 mag
4. S/N greater than 3 in all six JWST broad bands available across all fields (F115W, F150W, F200W, F277W, F356W, and F444W)

### Column Descriptions

| Column | Description |
|--------|-------------|
| `id` | ID in the DJA catalogue |
| `ra` | RA in the DJA catalogue |
| `dec` | Dec in the DJA catalogue |
| `z_spec` | z_spec in the DJA catalogue |
| `z_phot` | z_phot in the DJA catalogue |
| `FLUX_[band]` | Total flux in [band] from the DJA catalogue |
| `FLUX_ERR_[band]` | Total flux error in [band] from the DJA catalogue |
| `MAG_[band]` | Best-fit magnitude in [band] from GALFIT output |
| `MAG_ERR_[band]` | Best-fit magnitude error in [band] from GALFIT output |
| `XC_[band]` | Best-fit XC in [band] from GALFIT output |
| `YC_[band]` | Best-fit YC in [band] from GALFIT output |
| `RE_[band]` $^1$ | Best-fit effective radius in [band] from GALFIT output |
| `RE_ERR_[band]` | Best-fit effective radius error in [band] from GALFIT output |
| `N_[band]` | Best-fit Sérsic index in [band] from GALFIT output |
| `N_ERR_[band]` | Best-fit Sérsic index error in [band] from GALFIT output |
| `PA_[band]` | Best-fit position angle in [band] from GALFIT output |
| `PA_ERR_[band]` | Best-fit position angle error in [band] from GALFIT output |
| `AR_[band]` | Best-fit axis ratio in [band] from GALFIT output |
| `AR_ERR_[band]` | Best-fit axis ratio error in [band] from GALFIT output |
| `FLAG_[band]` | GALFIT flag in [band] |
| `C_[band]` | Concentration in [band] |
| `A_[band]` | Asymmetry in [band] |
| `S_[band]` | Smoothness in [band] |
| `G_[band]` | Gini coefficient in [band] |
| `M20_[band]` | M20 in [band] |
| `RE_1MICRO`  | Effective radius in rest-frame 1 μm |
| `RE_ERR_1MICRO` | Effective radius error in rest-frame 1 μm |
| `N_1MICRO` | Sérsic index in rest-frame 1 μm |
| `N_ERR_1MICRO` | Sérsic index error in rest-frame 1 μm |
| `PA_1MICRO` | Position angle in rest-frame 1 μm |
| `PA_ERR_1MICRO` | Position angle error in rest-frame 1 μm |
| `AR_1MICRO` | Axis ratio in rest-frame 1 μm |
| `AR_ERR_1MICRO` | Axis ratio error in rest-frame 1 μm |
| `FLAG_1MICRO` | Flag in rest-frame 1 μm |
| `C_1MICRO` | Concentration in rest-frame 1 μm |
| `A_1MICRO` | Asymmetry in rest-frame 1 μm |
| `S_1MICRO` | Smoothness in rest-frame 1 μm |
| `G_1MICRO` | Gini coefficient in rest-frame 1 μm |
| `M20_1MICRO` | M20 in rest-frame 1 μm |
| `z_best` | Best redshift used for SED fitting; z_spec if available, otherwise z_phot |
| `STELLAR_MASS` | Total stellar mass derived from CIGALE |
| `STELLAR_MASS_ERR` | Total stellar mass error derived from CIGALE |
| `SFR` | Star formation rate |
| `SFR_ERR` | Star formation rate error |
| `SFR_10Myr` | SFR averaged over 10 Myr |
| `SFR_10Myr_ERR` | SFR error averaged over 10 Myr |
| `SFR_100Myr` | SFR averaged over 100 Myr |
| `SFR_100Myr_ERR` | SFR error averaged over 100 Myr |

---

## `[Field]-profile-summary.fits`

Contains profile information for galaxies at 0 < z < 4 and $log(M_∗/M_☉) > 8$ with well-measured morphologies, as described in [Song et al. 2026](https://arxiv.org/abs/2512.01684v2)

### Column Descriptions

| Column | Description |
|--------|-------------|
| `id` | ID in the DJA catalogue |
| `ra` | RA in the DJA catalogue |
| `dec` | Dec in the DJA catalogue |
| `z_spec` | Spectroscopic redshift |
| `z_phot` | Photometric redshift |
| `max_high_snr_radius_convolved` $^3$ | ID of the outermost annulus where S/N > 3 in all 6 JWST bands (convolved) |
| `distance_from_center_convolved` $^3$ | Distance of each annulus from the galaxy center, in units of re_1micro |
| `annulus_area_convolved` $^3$| Area of each annulus in pixel² ; (1 × 25) array |
| `mass_profile_convolved` $^3$| Total stellar mass in each annulus; (1 × 25) array |
| `sfr_profile_convolved` $^3$| Total SFR in each annulus; (1 × 25) array |
| `max_high_snr_radius_deconvolved` $^4$| ID of the outermost annulus where S/N > 3 in all 6 JWST bands (deconvolved) |
| `distance_from_center_deconvolved` $^4$| Distance of each annulus from the galaxy center, in units of pixels |
| `annulus_area_deconvolved` $^4$| Area of each annulus in pixel²; (1 × 25) array |
| `mass_profile_deconvolved` $^4$| Total stellar mass in each annulus; (1 × 25) array |
| `sfr_profile_deconvolved` $^4$| Total SFR in each annulus; (1 × 25) array |

**Note:**
`1`, `2`:  RE is measured in pixels.
`3`: These results are without deconvolution. We used an annual step of $0.2 RE$; feel free to rebin the data according to your requirements.
`4`: These are the results after deconvolution. We adopted an annual step of 2 pixels; you may rebin them as needed.
