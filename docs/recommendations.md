# Recommendations for reporting structures determined by 3D electron diffraction

### _Early draft for discussion_

Most of the definitions in the core CIF dictionary can be applied to a description of a 3D ED structure determination experiment. An example of good practice in describing the relevant experimental metadata follows, with some guidance for individual data items.

```
_exptl_crystal_description            'nanocrystal'
_exptl_crystal_colour                 'orange'
_diffrn_ambient_temperature           303(2)
_diffrn_radiation_wavelength          0.0335
_diffrn_radiation_probe               'electron'
_diffrn_radiation_type                'electron'
_diffrn_source                        '120 kV electron microscope'
_diffrn_source_type                   'LaB6 gun'
_diffrn_measurement_device            'transmission electron microscope'
_diffrn_measurement_device_type       'Zeiss Libra 120'
_diffrn_detector                      'single-electron detector MEDIPIX'
_diffrn_detector_type                 'ASI Timepix'
_diffrn_measurement_method
                  'stepwise precession-assisted 3D electron diffraction'
_diffrn_measurement_method_precession  yes
_diffrn_precession_angle               1.0(2)
_diffrn_measurement_integration        stepwise

```

## `_exptl_crystal_description`

For sample materials of a scale suitable for structure determination by electron diffraction, the key word 'nanocrystal' should appear in this free-text field, even where the sample contains amorphous or poorly characterized regions. 

## `_exptl_crystal_colour`

The crystal colour is normally required by checkCIF, but can be difficult or impossible to determine for nanocrystals. In such a case the special CIF character `?` (unquoted) may be used with the meaning 'unknown', or a value of 'undetermined' may be given.

## `_diffrn_measurement.tracking` and `_diffrn_measurement.tracking_method`

`_diffrn_measurement.tracking` is a simple yes/no code to indicate if some tracking method was used to maximize the time that the sample is illuminated by the crystal, if the crystal drifts out of the beam during data collection. Details of the method can be given as free text in the `_diffrn_measurement.tracking_method` field.

## `_diffrn_radiation.illumination_mode`

This data item is used to discriminate between convergent-beam (STEM) and parallel (TEM) illumination of the sample.

## `_diffrn_radiation_probe`

This data item **should always be present with value 'electron'** for 3D ED structure determinations, to inform checkCIF of the nature of the study. The similar data item `_diffrn_radiation_type` is now deprecated and should **not** be used. More detailed description of the energy spectrum of the radiation source may be given in the data item `_diffrn_radiation_wavelength.type` if needed.


## `_diffrn_source` and `_diffrn_source_type`

'Electron microscope' is often used as a value for `_diffrn_source` (defined as _The general class of the source of radiation._), but 'electron gun' is technically more accurate. For `_diffrn_source_type` the usual options in electron diffraction are tungsten, LaB6, Schottky FEG (field-emission gun) or cold-effect FEG.

## `_diffrn_source_size`

This free-text field, already present in the core dictionary, can be used to describe the appropriate measure of the beam size at the sample. For selected-aperture electron diffraction, this should be the beam width corresponding to the aperture setting, and not the total beam width.

## `_diffrn_source_voltage` and `_diffrn_radiation_wavelength`

Both should be supplied for electron diffraction studies. The value of `_diffrn_radiation_wavelength` is expected to include a standard uncertainty to express the expected wavelength spread.

## `_diffrn_detector` and `_diffrn_detector_type`

Defined respectively as _The general class of the radiation detector_ and _The make, model or name of the detector device used._ Typical values for `_diffrn_detector` could be CCD, CMOS, 'Hybrid pixel (HPD)' or 'Direct detection camera (DDC)'.

## `_diffrn_measurement_method_precession`

If beam precession was used, this data item should be present and have the value 'yes' or 'y'. The precession angle should be given as the value of `_diffrn_precession_angle`, including standard uncertainty where possible.

## `_diffrn_measurement_integration`

The method of collecting data from regions of reciprocal space should take one of the values 'beam-tilt', 'rotation' (or its synonym 'continuous') or 'stepwise' according to the technique used. The beam-tilt method is sometimes called 'the rotation method' in 3D electron diffraction.

## `exptl.crystals_number`

The number of crystals used in the measurement of intensities should be specified.

## `_refine.diffraction_theory`

This data item can take the values 'dynamical' and 'kinematical', and should always be specified if refinement is performed using the dynamical theory.

## `refine_diff.density_max`, `_min` and `_RMS`

These quantities were defined in the original core CIF dictionary as indications of the final difference electron density. For electron diffraction, they should report the maximum, minimum and mean difference potential in the final difference Fourier map, and be expressed in units of electrons per ångström.

## `_refine_ls.abs_structure_z_score`

The statistical _z_ score can be determined as a robust measure of the confidence of an absolute structure assignment according to the procedure described in Klar, P. B., Krysiak, Y., Xu, H., Steciuk, G.,Cho, J., Zou, X. & Palatinus, L. (2023). Accurate structure models and absolute configuration determination using dynamical effects in continuous-rotation 3D electron diffraction data. _Nature Chem._ **15**, 848-855. This method is not specific to electron diffraction and may also be used for X-ray diffraction data, but for X-ray work it has largely been superseded by the Flack, Rogers and Parsons parameters.
