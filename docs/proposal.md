# Updates of the cif dictionary and checkcif procedure to accommodate 3D ED data

## 1.	Introduction

One of the aims of the NanED project is proposing and introducing standards for recording, reporting and validation of the crystal structures determined by the 3D ED techniques. To that end, the Standardization committee of the NanED consortium (NanED SC) was established with the task of coordinating the effort. 

After discussions on the topic, the NanED SC proposes the roadmap to the necessary changes to the CIF dictionary and changes to the CheckCIF procedure. This document summarizes the proposal and serves as the starting point for the broader discussion within the electron diffraction community.

## 2.	Changes to the CIF dictionary

*	Adding a keyword specifying if precession electron diffraction was used.
Possible keyword: `_diffrn_precession_angle XX` (numerical value in degrees)

*	Adding a keyword specifying if the refinement was kinematical or dynamical.
Possible keyword: `_refine_diffraction_theory 'value'`, with permitted values ‘kinematical’, ‘dynamical’, ‘two-beam’

*	Adding an additional option to `_chemical_absolute_configuration`. In addition to the existing options, an option ‘dyn’ could be used to specify determination by dynamical refinement

*	Adding an option to specify values in the difference Fourier map. Currently, only `_refine_diff_density_max`, `_refine_diff_density_min` and `_refine_diff_density_rms` are available for the purpose, implying a difference density. The CIF dictionary also specifies that the units are e/Å^3. Possible solution: add three keywords `_refine_diff_potential_max`, `_refine_diff_potential_min` and `_refine_diff_potential_rms` to specify difference potential. The problem are the units. The numbers coming out of _Olex2_, _SHELXL_ or _Jana2020_ are derived from the units for the scattering factors, which are Å. Their Fourier transform thus has units of Å^-2. This, however, is not a very common unit for reporting electrostatic potential. A better unit would be either volts or e/Å. We need to discuss, which of the three options should be adopted in the CIF standard.
_(This proposal was subsequently modified to use the existing `_refine_diff.density_*` items, but change the units for electron diffraction with a DDLm method.)_

*	Adding tools for specifying the orientation of individual frames. Possible specification:

```
loop_
_diffrn_frame_id
_diffrn_frame_u
_diffrn_frame_v
_diffrn_frame_w
_diffrn_frame_omega
_diffrn_frame_phi
_diffrn_frame_chi
1  0.15802  0.20648 -1.00000 1.000 -53.011 -0.349    22.438     0.910
2  0.15272  0.19983 -1.00000 1.000 -52.556 -0.285    22.429     0.984
. . .
```
 
## 3.	Changes to the CheckCIF procedure

* Recognize kinematical and dynamical refinement
* For kinematical refinement, relax limits for Alerts A/B for some quantities. The proposed quantities are:
    * Rint – alert A above 25%, alert B above 15%
    * Robs – Alert A above 25%, alert B above 18%
    * wRall2 – what would be suitable limits?
Affected alerts: **PLAT082, PLAT084, RINTA01**
*	Relax the limit for the alert on Low Bond Precision on C-C Bonds. What would be a suitable value ? Affected alert: **PLAT340**

*	For dynamical refinement remove alerts A and B for missing Rint. Affected alert: **PLAT881**

*	Adjust the limits for the alert on too long Long O-H bond, because in electron diffraction it is normal to obtain longer bonds than the neutron values. Affected alert : **PLAT355**

