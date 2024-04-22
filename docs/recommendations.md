# Recommendations for reporting structures determined by 3D electron diffraction

Most of the definitions in the core CIF dictionary can be applied to a description of a 3DED structure determination experiment. An example of good practice in describing the relevant experimental metadata follows, with some guidance for individual data items.

```
_exptl_crystal_description       'nanocrystal'
_exptl_crystal_colour            'orange'
_diffrn_ambient_temperature      303(2)
_diffrn_radiation_wavelength     0.0335
_diffrn_radiation_probe          'electron'
_diffrn_radiation_type           'electron'
_diffrn_source                   '120 kV electron microscope'
_diffrn_source_type              'LaB6 gun'
_diffrn_measurement_device       'transmission electron microscope'
_diffrn_measurement_device_type  'Zeiss Libra 120'
_diffrn_detector                 'single-electron detector MEDIPIX'
_diffrn_detector_type            'ASI Timepix'
_diffrn_measurement_method
             'stepwise precession-assisted 3D electron diffraction'

```

## `_exptl_crystal_description`

For sample materials of a scale suitable for structure determination by electron diffraction, the key word 'nanocrystal' should appear in this free-text field, even where the sample contains amorphous or poorly characterized regions. 


