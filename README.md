# Sudakov Double Logs for a Muon collider

A Mathematica notebook to compute the Sudakov Double Logs for 2->2 processes at a Muon Collider.
These results were used in hep-ph/25xx.xxxxx and hep-ph/25xx.xxxxx (to appear).

## Instructions

The notebook SudakovSMEFT.nb contains all the code for the computation of the cross sections for the many 2->2 processes that can be measured at a high-energy Muon Collider.

The notebook uses FormCalc to compute the Tree-Level amplitudes for diboson processes. The FeynArts model used is included in this repository in the folder FeynArts.
A valid path to Feynarts and FormCalc should be set in the "FeynArts Initialization" section at the beginning of the Notebook.
However, since the computation is quite time-consuming, a "getAmp.mx" file can be loaded that already contains all the results of the Diboson amplitudes.

For Difermion processes, the amplitudes are instead defined by hand. This is because FormCalc does not currently properly support 4-fermion contact operators.

The usage of the notebook is explained in detail inside the notebook itself, specifically in the diboson section.

## Results

The expected number of events are calculated assuming an integrated luminosity of   

$$\hat{\mathcal{L}} = 10\text{ ab}^{-1} \left(\frac{\sqrt{s}}{10\text{ TeV}}\right)^2$$  

where the energy scaling makes the number of SM events the same at every collider energy.

A collection of results is included in the Results folder of this repository. This includes the expected number of events for a 10 TeV Muon Collider for three kind of observables
- Tree Level
- Exclusive
- With Radiation

The meaning of these observables is explained in great detail in hep-ph/2202.10509.
The short version is:
- Exclusive: $\mu\mu\to PP$ with no EW radiation (only virtual effects)
- With Radiation: $\mu\mu\to PP' + X$ must have real soft radiation
The two classes of observables are independent and can be combined separately in fits.

The Tree Level predictions instead are included just for completeness.

Each .mx file in the Results folder contains the definition of several Mathematica Lists, that can be loaded using the Get[...] command.
Each of these objects is a list of ten entries, corresponding to the expected number of events for a given process in 10 equally spaced angular bins between 30 and 150 degrees as a function of all the relevant Wilson Coefficients.
The diquark results are given as a 3x3 matrix in flavor space.

| File | Objects contained | Explanations |
|------|-------------------|-------------------|
|"/Results/Diboson/DibosonTreeLevel.mx"| {nExpZhTreeLevel, nExpWWTreeLevel} | $\mu\mu\to Zh$ and $\mu\mu\to WW$ at Tree Level |
|"/Results/Diboson/DibosonExclusive.mx"| {nExpZhExcl, nExpWWExcl} | $\mu\mu\to Zh$ and $\mu\mu\to WW$ at Exclusive Level |
|"/Results/Diboson/DibosonWithRadiation.mx"| {nExpZhRad, nExpWWRad, nExpWpZSI, nExpZWmSI, nExpWphSI, nExphWmSI} | $\mu\mu\to Zh$, $\mu\mu\to WW$, $\mu\mu\to W^+Z$, $\mu\mu\to Z W^-$, $\mu\mu\to W^+h$ and $\mu\mu\to hW^-$ With Radiation |
|------|-------------------|-------------------|
|"/Results/Difermion/DileptonTreeLevel.mx"| {nExpeeTreeLevel, nExp\\[Mu]\\[Mu]TreeLevel, nExp\\[Tau]\\[Tau]TreeLevel} | $\mu\mu\to ee$, $\mu\mu\to \mu\mu$ and $\mu\mu\to \tau\tau$ at Tree Level |
|"/Results/Difermion/DileptonExclusive.mx"| {nExpeeExcl, nExp\\[Mu]\\[Mu]Excl, nExp\\[Tau]\\[Tau]Excl} | $\mu\mu\to ee$, $\mu\mu\to \mu\mu$ and $\mu\mu\to \tau\tau$ at Exclusive Level |
|"/Results/Difermion/DileptonWithRadiation.mx"| {nExpeeRad, nExp\[Mu]\[Mu]Rad, nExp\[Tau]\[Tau]Rad, nExpem\[Nu]SI, nExp\[Mu]m\[Nu]SI, nExp\[Tau]m\[Nu]SI, nExp\[Nu]epSI, nExp\[Nu]\[Mu]pSI, nExp\[Nu]\[Tau]pSI} | $\mu\mu\to ee$, $\mu\mu\to \mu\mu$ , $\mu\mu\to \tau\tau$, $\mu\mu\to e^-\bar{\nu}$, $\mu\mu\to \nu e^+$, $\mu\mu\to \mu^-\bar{\nu}$, $\mu\mu\to \nu \mu^+$, $\mu\mu\to \tau^-\bar{\nu}$ and $\mu\mu\to \nu \tau^+$ With Radiation |
|------|-------------------|-------------------|
|"/Results/Difermion/DiquarkTreeLevel.mx"| {nExpuuTreeLevel, nExpddTreeLevel} | $\mu\mu\to u^i \bar{u}^j$ and $\mu\mu\to d^i \bar{d}^j$ at Tree Level |
|"/Results/Difermion/DiquarkExclusive.mx"| {nExpuuExcl, nExpddExcl} | $\mu\mu\to u^i \bar{u}^j$ and $\mu\mu\to d^i \bar{d}^j$ at Exclusive Level |
|"/Results/Difermion/DiquarkWithRadiation.mx"| {nExpuuRad, nExpddRad, nExpudSI, nExpduSI} | $\mu\mu\to u^i \bar{u}^j$, $\mu\mu\to d^i \bar{d}^j$, $\mu\mu\to u^i \bar{d}^j$ and $\mu\mu\to d^i \bar{u}^j$ With Radiation |


<!--

Furthermore, the results for the charged final states with radiation are also simulated at fixed order using MadGraph. These results are included in the following files

| File | Objects contained | Explanations |
|------|-------------------|-------------------|
|"/Results/Diboson/DibosonTreeLevelRadiation.mx"| {nExpwhTreeLevel, nExpwzTreeLevel} | $\mu\mu\to Wh$ and $\mu\mu\to WZ$ with Ratiation at fixed order |
|"/Results/Difermion/DileptonTreeLevelRadiation.mx"| {nExpe\[Nu]TreeLevel,nExp\[Mu]\[Nu]TreeLevel, nExp\[Tau]\[Nu]TreeLevel} | $\mu\mu\to e\nu$, $\mu\mu\to \mu\nu$ and $\mu\mu\to \tau\nu$ with Ratiation at fixed order |
|"/Results/Difermion/DiquarkTreeLevelRadiation.mx"| {nExpudTreeLevel, nExpcsTreeLevel, nExptbTreeLevel} | $\mu\mu\to ud$, $\mu\mu\to cs$ , $\mu\mu\to tb$ and $\mu\mu\to bb$ with Ratiation at fixed order |

--->

NOTE: these expected numbers of events are computed WITHOUT including any experimental tagging efficiencies and mistag errors. These parameters are reported here as and should be included for sensitivity projections.

For each lepton, we assume the following reconstruction efficiencies:  
- $$\epsilon_{e,\mu}=100\\%$$  
- $$\epsilon_{\tau}=50\\%$$  

For each top quark, we assume the following reconstruction efficiency:  
- $$\epsilon_{t}=80\\%$$  

For each other quarks we assume the following mistag probabilities $\epsilon_{\text{true},\text{tagged}}$:  
- $$\epsilon_{bb} = 80\\%,\quad \epsilon_{bc} = 10\\%,\quad\epsilon_{bj} = 10\\%$$   
- $$\epsilon_{cb} = 10\\%,\quad \epsilon_{cc} = 50\\%,\quad\epsilon_{cj} = 40\\%$$  
- $$\epsilon_{jb} = 1\\%,\quad \epsilon_{jc} = 2\\%,\quad\epsilon_{jj} = 97\\%$$   

For diboson processes we assume the following overall efficiencies, combining branching ratios and reconstruction:   
- $$\epsilon_{Zh}=26\\%$$  
- $$\epsilon_{WW}=44\\%$$   
- $$\epsilon_{WZ}=23\\%$$    
- $$\epsilon_{Wh}=19\\%$$    















