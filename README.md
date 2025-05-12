This is the source catalog accompanying Song et al. (2024). Since this catalog is based on the source catalogs provided by the DJA team, please cite Song et al. (2024) and [Valentino et al. (2023）](https://ui.adsabs.harvard.edu/abs/2023ApJ...947...20V/abstract) if you make use of it.


During the data processing conducted by theDJA team, for convenience, the PRIMER-COSMOS field was divided into `EAST` and `WEST` subfields, and the PRIMER-UDS field was divided into `NORTH` and `SOUTH` subfields. As a result, this repository contains seven folders (`CEERS`, `JADES-GDS`, `JADES-GDN`, `PRIMER-COSMOS-E`, `PRIMER-COSMOS-W`, `PRIMER-UDS-S`, and `PRIMER-UDS-N`), each corresponding to a different field, with the associated source catalog included within each. In this study, we utilize the most recent data releases available at the time of analysis: `v7.0` for the `PRIMER-COSMOS` field, `v7.2` for the `CEERS`, `JADES-GDS`, and `PRIMER-UDS` fields, and `v7.3` for the `JADES-GDN` field.


In each field, we include only the **good sample** as defined in Section 2.3 of the paper. The detailed definition of the **good sample** is as follows:
1. A signal-to-noise ratio (S/N) greater than 10 in the detection image ($\rm S/N_{\rm det} > 10$)
2. A reduced chi-squared value satisfying $\chi^2 / N_{\rm filt} \leq 8$ with at least six filters available for photometric redshift estimation ($N_{\rm filt} \geq 6$), where $N_{\rm filt}$ is the number of filters used in the fit.
3. F444W magnitude brighter than 28.5 mag
4. S/N greater than 3 in all six JWST broad bands available across all fields (F115W, F150W, F200W, F277W, F356W, and F444W)


The meaning of each column in the final catalog is as follows:

| **Column**                     | **Description**                                                                                                                |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| id                             | Sequential number identifier, consistent with that in the photometric catalog provided by the DJA team                         |
| ra                             | R.A. expressed in decimal degrees, consistent with that in the photometric catalog provided by the DJA team                    |
| dec                            | decl. expressed in decimal degrees, consistent with that in the photometric catalog provided by the DJA team                   |
| flux\_[band]^1                 | Total flux of the corresponding band from the photometric catalog provided by the DJA team in unit of mJy                      |
| flux\_err\_[band]              | Flux error of the corresponding band from the photometric catalog provided by the DJA team in unit of mJy                      |
| redshift                       | Redshift from the DJA team's redshift catalog. When available, $z_{\rm spec}$ are used; otherwise, $z_{\rm phot}$ are adopted. |
| stellar_mass                   | Stellar mass, which corresponds to $\log(M_{\ast}/M_{\odot})$                                                                  |
| sfr                            | The average star formation rate over the past 100 Myrs, which corresponds to $\log(SFR)[M_\odot yr^{-1}]$                      |
| ssfr                           | The corresponding specific star formation rate                                                                                 |
| Re\_[band]                     | The effective radius measured in the corresponding band, in unit of pixel                                                      |
| n\_[band]                      | The sersic index  measured in the corresponding band.                                                                          |
| q\_[band]                      | The axis ration measured in the corresponding band.                                                                            |
| pa\_[band]                     | The position angle measured in the corresponding band.                                                                         |
| C\_[band]                      | The concentration coefficient measured in the corresponding band.                                                              |
| A\_[band]                      | The Asymmetry coefficient measured in the corresponding band.                                                                  |
| S\_[band]                      | The clumpiness coefficient measured in the corresponding band.                                                                 |
| Gini\_[band]                   | The Gini coefficient measured in the corresponding band.                                                                       |
| M20_[band]                     | The $M_{\rm 20}$ coefficient measured in the corresponding band.                                                               |
| Re\_1um                        | The effective radius measured in rest-frame 1$\mu$m.                                                                           |
| n\_1um                         | The Sersic index measured in rest-frame 1$\mu$m.                                                                               |
| q\_1um                         | The axis ratio measured in rest-frame 1$\mu$m                                                                                  |
| pa\_1um                        | The position angle measured in rest-frame 1$\mu$m                                                                              |
| max\_high\_snr\_radius$^{[2]}$ | max\_high\_snr\_radius defined in Section 4.3                                                                                  |
| annual\_area\_list$^{[3]}$     | A list of the areas of each elliptical annulus in units of $\rm pixel^2$                                                       |
| stellar\_mass\_profile$^{[4]}$ | A list of the stellar mass of each elliptical annulus.                                                                         |
| sfr\_profile$^{[5]}$           | A list of the star formation of each elliptical annulus.                                                                       |
| ssfr\_profile$^{[6]}$          | A list of the specific star formation of each elliptical annulus.                                                              |
Note: 
1. For CEERS field, we use F435W, F606W, F814W, F115W, F150W, F200W, F277W, F356W, and F444W data; for other fields, we also use additional F090W data.
2. The concentric elliptical annuls are created with a radial step of 0.2Re_1um, extending out to 5Re_1um.
3. For annuli that do not meet the S/N criterion, the corresponding value is recorded as NaN.
4. The stellar mass (not in $\log_{\rm 10}$) contained within each annulus (not the stellar mass surface density). The surface density can be obtained by dividing these values by the corresponding annual_area_list
5. similar to stellar mass profile, but to star formation rate
6. similar to stellar mass profile, but for specific star formation rate
