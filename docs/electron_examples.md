# Current practical use of CIF by 3DED authors

This is a survey of papers recently published or in production across our journals, to show how authors are currently interpreting and using core data names. It may be useful in constructing a model example CIF to add to the Notes for Authors pages.

Also included is LOHZER, an unpublished structure from Simon Coles' facility. This includes some author responses to checkCIF ALERTS.

je5035 looks like the example that Mauro supplied. je 5052 uses the `_exptl_crystal_colour_lustre`, `_exptl_crystal_colour_modifier` and `_exptl_crystal_colour_primary` triad of enumerated colour characteristics.

There are a few CIF errors: je5050 uses 'electrons' as the value of `_diffrn_radiation_probe`, but this is a reserved word and **electron** should be used. lo5099 gives the units of `_diffrn_source_voltage`, but the value should just be 300 as the units are specified in the dictionary. The same paper appears to misinterpret the purpose of `_diffrn_source`. There are a few typing errors, reproduced verbatim in the table.

Several of the papers report a crystal size (not shown in the table), _e.g._

```
_exptl_crystal_size_max          0.00002
_exptl_crystal_size_mid          0.000015
_exptl_crystal_size_min          0.00001
```

or

```
_exptl_crystal_size_rad          0.000015
```

I note that these do not have a s.u. (but neither does the _SHELX_ example CIF that we distribute for _Acta C_).

|  journal | b | b | b | b | b | b | b | c  | CSD |
|  --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  cnor | je5035 | je5043 | je5050 | je5052 | je5053 | je5054 | lo5099 | nh3001  | LOHZER |
|  authors | I. Andrusenko, J. Potticary, S. R. Hall and M. Gemmi | T. E. Gorelik, S. Habermehl, A. A. Shubin, T. Gruene, K. Yoshida, P. Oleynikov, U. Kaiser and M. U. Schmidt | T. E. Gorelik, S. L. Beko, J. Teteruk, W. Heyse and M. U. Schmidt | D. Marchetti, A. Pedrini, C. Massera, M. F. Faye Diouf, C. Jandl, G. Steinfeld and M. Gemmi | Golle-Leidreiter, P., Bhat, S., Wiehl, L., Wen, Q., Kroll, P., Ishikawa, R., Etter, M., Farla, R., Ikuhara, Y., Riedel, R. and Kolb, U. | S. Plana-Ruiz, E. Gotz, T. Neumann, P. Schwesig and U. Kolb | O. P. Missen, S. J. Mills, S. Canossa, J. Hadermann, G. Nenert, M. Weil, E. Libowitzky, R. M. Housley, W. Artner, A. R. Kampf, M. S. Rumsey, J. Spratt, K. Momma and M. A. Dunstan | K. Gurung, P. Simek, A. Jegorov Jr and L. Palatinus  | D.N. Rainer |
|  software | SHELXL-2018/3' | SHELXL-2018/3 | ? | Jana2020 1.3.40' | 'Jana2020 1.3.49' | 'Jana2020 1.3.52' | 'Jana2020 Version : 11/03/2021' | 'Jana2020 1.3.43'  | 'Olex2 1.5-ac6-018' |
|  _exptl_crystal_description | 'nanocrystal' | 'square platelets' | irregular |  | ? | 'Nanocrystals of up to 500 nm in size' | irregular | "'long, flat rods'"  | VRF reponse: These data originate from 3DED data and are obtained from a crystal with dimensions smaller than 1 um. |
|  _exptl_crystal_colour | ? | blue | orange | clear/light/white | ? |  | green | 'white'  | |
|  _diffrn_radiation_probe |  | electron | electrons | electron | electron | electron | electron | 'electrons 200 keV'  | electron |
|  _diffrn_radiation_type | 'electron' |  |  | electron | electron | electron | electron | electron  | electron |
|  _diffrn_radiation_source |  |  |  | 'LaB6' | ? |  |  | 'Lab6 cathode'  | |
|  _diffrn_source | '120 kV electron microscope' | 'tansmission electron microscope' |  | 'LaB6' |  |  | 'Cu3TeO6 nanocrystal' |   | 'electron diffractometer' |
|  _diffrn_source_voltage |  | 200 |  | ? | ? |  | 300kV |   |  |
|  _diffrn_source_type | 'LaB6 gun' |  |  |  |  |  |  |   |  'JEOL JSM-2300ED, LaB6' |
|  _diffrn_measurement_device | 'transmission electron microscope' |  |  | ? | 'transmission electron microscope' | FEI Tecnai F30' | 'FEI Titan cubed' | 'TEM FEI Tecnai G2 20'  | 'electron diffractometer' |
|  _diffrn_measurement_device_type | 'Zeiss Libra 120' | 'transmission electron microscope' | 4k | 'Eldico ED-1' | 'Tecnai F30 ST' | 'TEM' | 'transmission electron microscope' |   | 'XtaLAB Synergy-ED, HyPix-ED, electron source at 200keV' |
|  _diffrn_detector | 'single-electron detector MEDIPIX' | 'CCD area detector' |  | ? | 'gatan ultrascan 4000' | 'Gatan UltraScan4000' | 'US1000 CCD detector' | 'ASI Cheetah'  | 'Hybrid Pixel Array Detector' |
|  _diffrn_detector_type | 'ASI Timepix' | 'Gatan MSC 2k' |  |  |  |  |  |   | HyPix-ED |
|  _diffrn_measurement_method | 'stepwise precession-assisted 3D electron diffration' | ? |  | '3D - cRED' | 'ADT with precession' |  | 'stepwise toration' | 'continuous rotation 3D ED'  | 'continuous rotation electron diffraction' |
