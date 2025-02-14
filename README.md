# Sudakov Double Logs for a Muon collider

A Mathematica notebook to compute the Sudakov Double Logs for 2->2 processes at a Muon Collider.

## Instructions

The notebook SudakovSMEFT.nb contains all the code for the computation of the cross sections for the many 2->2 processes that can be measured at a high-energy Muon Collider.

The notebook uses FormCalc to compute the Tree-Level amplitudes for diboson processes. The FeynArts model used is included in this repository in the folder FeynArts.
A valid path to Feynarts and FormCalc should be set in the "FeynArts Initialization" section at the beginning of the Notebook.
However, since the computation is quite time-consuming, a "getAmp.mx" file can be loaded that already contains all the results of the Diboson amplitudes.

For Difermion processes, the amplitudes are instead defined by hand. This is because FormCalc does not currently properly support 4-fermion contact operators.

The usage of the notebook is explained in detail inside the notebook itself, specifically in the diboson section.

## Results

A collection of results is included in the Results folder of this repository. This includes the expected number of events for a 10 TeV Muon Collider for three kind of observables
- Tree Level
- Exclusive
- With Radiation

The meaning of these observables is explained in great detail in hep-ph/2202.10509.

Each .mx file in the Results folder contains the definition of several Mathematica Lists, that can be loaded using the Get[...] command.
Each of these objects is a list of ten entries, corresponding to the expected number of events for a given process in 10 equally spaced angular bins between 30 and 150 degrees as a function of all the relevant Wilson Coefficients.


| File | Objects contained | Explanations |
|------|-------------------|-------------------|
|"/Results/Diboson/DibosonTreeLevel.mx"| {nExpZhTreeLevel, nExpWWTreeLevel} | $\mu\mu\to Zh$ and $\mu\mu\to WW$ at Tree Level |
|"/Results/Diboson/DibosonExclusive.mx"| {nExpZhExcl, nExpWWExcl} | $\mu\mu\to Zh$ and $\mu\mu\to WW$ at Exclusive Level |
|"/Results/Diboson/DibosonWithRadiation.mx"| {nExpZhRad, nExpWWRad, nExpWZSI, nExpWhSI} | $\mu\mu\to Zh$, $\mu\mu\to WW$, $\mu\mu\to WZ$ and $\mu\mu\to Wh$ With Radiation |
|------|-------------------|-------------------|
|"/Results/Difermion/DileptonTreeLevel.mx"| {nExpeeTreeLevel, nExp\[Mu]\[Mu]TreeLevel, nExp\[Tau]\[Tau]TreeLevel} | $\mu\mu\to ee$, $\mu\mu\to \mu\mu$ and $\mu\mu\to \tau\tau$ at Tree Level |
|"/Results/Difermion/DileptonExclusive.mx"| {nExpeeExcl, nExp\[Mu]\[Mu]Excl, nExp\[Tau]\[Tau]Excl} | $\mu\mu\to ee$, $\mu\mu\to \mu\mu$ and $\mu\mu\to \tau\tau$ at Exclusive Level |
|"/Results/Difermion/DileptonWithRadiation.mx"| {nExpeeRad, nExp\[Mu]\[Mu]Rad, nExp\[Tau]\[Tau]Rad, nExpe\[Nu]SI, nExp\[Mu]\[Nu]SI, nExp\[Tau]\[Nu]SI} | $\mu\mu\to ee$, $\mu\mu\to \mu\mu$ , $\mu\mu\to \tau\tau$, $\mu\mu\to \nu e$, $\mu\mu\to \nu\mu$ and $\mu\mu\to \nu\tau$ at Exclusive Level |
|------|-------------------|-------------------|
|"/Results/Difermion/DiquarkTreeLevel.mx"| {nExpjjTreeLevel, nExpccTreeLevel, nExpttTreeLevel, nExpbbTreeLevel} | .. |
|"/Results/Difermion/DiquarkExclusive.mx"| {nExpjjExcl, nExpccExcl, nExpttExcl, nExpbbExcl} | .. |
|"/Results/Difermion/DiquarkWithRadiation.mx"| {nExpjjRad, nExpccRad, nExpttRad, nExpbbRad, nExpcsSI, nExptbSI} | .. |



















