[![DOI](https://zenodo.org/badge/245466124.svg)](https://zenodo.org/badge/latestdoi/245466124)

# LbL_Hydrogel
Excel sheets implementing LbL Hydrogel fitting

The Excel sheets in this archive accompany the paper "Architecture of Hydrated Multilayer Poly(methacrylic acid) Hydrogels: Effect of solution pH", by Veronika Kozlovskaya, Kelli A. Stockmal, William Higgins, John F. Ankner, Sarah E. Morgan, and  Eugenia Kharlampieva, ACS Applied Polymer Materials 2, 2260 (2020). 

There are two sets of Excel sheets representing two samples: poly(methacrylic acid) (PMAA) hydrogels deposited on silicon (Si) substrates using the hydrogen-bonded (HB) Layer-by-Layer (LbL) technique in: 1) spin-assisted (SA) and 2) dipped variants.

SA sheets:

layers_102384_SA_HB_Dry           #parent HB measured dry from air

layers_114114_SA_Crosslinked_Dry  #crosslinked measured dry from air

layers_103062_SA_Crosslinked_pH4.6  #crosslinked measured from Si against pH 4.6 buffer

layers_114121_SA_Crosslinked_pH4.86  #crosslinked measured from Si against pH 4.86 buffer

layers_114214_SA_Crosslinked_pH6.15  #crosslinked measured from Si against pH 6.15 buffer

layers_114263_SA_Crosslinked_pH6.4  #crosslinked measured from Si against pH 6.4 buffer

layers_114129_SA_Crosslinked_pH7.0  #crosslinked measured from Si against pH 7.0 buffer

Dipped sheets:

layers_102979_Dipped_HB_Dry           #parent HB measured dry from air

layers_114203_Dipped_Crosslinked_Dry  #crosslinked measured dry from air

layers_114271_Dipped_Crosslinked_pH5  #crosslinked measured from Si against pH 5.0 buffer

layers_114278_Dipped_Crosslinked_pH6.4  #crosslinked measured from Si against pH 6.4 buffer

The Excel sheets use macros to calculate reflectivity, evaluate goodness-of-fit, and perform most other operations.  They can therefore be viewed using open-source programs such as Gnumeric or LibreOffice, but they are only really functional when run in Excel with Macros enabled.  Each sheet is independent of the others and contains all of the machinery needed to modify and optimize model fits.  The sheets consist of a number of tabs, including:

Reflectivity tab:

This is the master sheet and contains the model parameters (columns B-H), data (columns I-K), model fit (column L), and fitted model scattering-length density (SLD) profile (columns M-S).  Sheets not employing incoherent smearing contain neutron reflectivity (NR) data, model, and model profile in SI units (columns X-AC); sheets with incoherent smearing contain the smeared reflectivities (columns U-Y) and displace the quantities in SI units to columns AA-AF.  Data can be loaded from 3-column text files (the '#' symbol identifies commented lines not to be loaded) by typing two-fingered ctrl-l; reflectivity is evaluated by ctrl-r; and plotted data and fit display toggled between R and RQ^4 by ctrl-q.  The sheets allowing incoherent smearing (for the SA sample in against buffer solutions) allow in addition calculation of smeared reflectivity using ctrl-s.

SLDs, absorptions, thicknesses and full-width-at-half-maximum (fwhm) interfacial widths are entered or calculated into the labeled columns starting at row 3.  Layers are added to the model and evaluated until the first blank row.  We have primarily used column H for parameters used to calculate and populate the reflectivity columns, but these calculations can be done anywhere on the sheet.  The calculations are described in detail in the Supplementary Information of the manuscript.  The sheets are, however, not limited in function and the models can be modified or the sheets repurposed entirely to fit different data.  Goodness-of-fit is given by chi-squared in cell A10 (or in cell Y2 for incoherent smearing).

Uncertainties tab:

The values and statistical uncertainties of model parameters discussed in the manuscript are calculated and displayed here.

Fitted parameters tabs:

Each fitted parameter in the model has its own tab (e.g. density in layers_102384_SA_HB_Dry).  Parameters are identified by which cell they occupy in the Reflectivity tab (cell A2 in the parameter tab) and can be varied through a range of values (Start, Stop, and Nsteps) in cells (B-D)2.  Pressing ctrl-p evaluates the model over the desired range and fits a parabola to the chi-squared profile.  Parameter minimum chi-squared and uncertainty are written in cells C4 and D4, respectively.  For the sheets using incoherent smearing, ctrl-i carries out the parameter variation.  New parameters can be added by copying, relabeling, and editing an existing parameter tab using standard Excel commands.

ScaledCombined tab:

A copy of the text file used to load in the data using the ctrl-l command in the Reflectivity tab.  Data can also be cut and pasted into the relevant columns in the Reflectivity tab.  Information on the ScaledCombined tab is purely documentary and does not affect the operation of the other features.

ScatteringParameters tab:

A neutron SLD calculator (using ActiveX so it won't work on Macs).  Press the Compound Calculator button, enter values in the popup, and press Enter in the popup to add a line to the table.  Cut and paste from columns D-F to appropriate columns C-E in the Reflectivity tab.

AtomicParameters tab:

The isotopic parameters used for the calculations in the ScatteringParameters tab (compiled by Varley Sears several decades ago).

This brief description is not in any way comprehensive, but feel free to contact the authors if questions or problems arise.
