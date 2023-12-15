# Generating a synthetic population of gamma-ray Pulsar Wind Nebulae
Make predictions about existing gamma-ray PWN populations and their observation, and use existing observational data (taking source confusion into account) to constraint the most adequate synthesis model.

## Notes
[Folder](https://drive.google.com/drive/u/2/folders/1zC_887xpHeDIuXCJKZv-lWm8s63D-Q3j) and [main document](https://docs.google.com/document/d/1I9DiDiJLdtMpVePVEOXQ4yuIY8C1TmiCdTi9AJpLPEM/edit#heading=h.hd6kiblx6ovm) of the project.
## Introduction
This is an organising document for the project “Generating a synthetic population of gamma-ray Pulsar Wind Nebulae” (working title), a collaboration project within the FAPESP/Baylat “High-energy astrophysics in the multimessenger era” Workshop, originally proposed in the first part of the workshop (Erlangen, May 2023) and expected to produce results to be presented during its second part (São Carlos, April 2024).
Population synthesis aims to, from a set of well-defined assumptions, generating statistically significant populations of a variety of astronomical objects, generally in order to either a) make predictions about existing populations and their observation; or b) use existing observational data to constraint the most adequate synthesis model (or combinations thereof). 
COMPAS (Compact Object Mergers: Population Astrophysics and Statistics) is an open-source population synthesis code focused on, as the name implies, binary evolution for synthesising compact object merger populations. It is, however, capable of single stellar evolution, and since 2020 has included a pulsar evolution module. This has turned it into a possible tool also for studying pulsar populations, as has already been done for radio pulsars.
In this project, we are interested in both purposes a) and b) from the first paragraph.

**Summary**
- Create a population of pulsars from stellar evolution model ([COMPAS](https://github.com/TeamCOMPAS/COMPAS)).
- Pulsar birth properties assigned from distributions then evolved.
- PWN evolution according to baseline model of [HESS paper](https://arxiv.org/abs/1702.08280).
- Determine PWN properties for population.
- Normalise distribution based on (e.g.) HAWC observations in the North → use to predict the Southern sky for (e.g.) SWGO.
- Apply observability constraints.

**COMPAS model properties / assumptions**
- Initial mass function 
- Star formation history    
- Metallicity 
- Pulsar birth properties, initial spin-down luminosity & initial spin period

**PWN baseline model variables**
- Initial spin-down luminosity
- Initial spin-down timescale
- Magnetic field 
- Time of reverse shock interaction
- PWN size at 3 kyr
- Set braking index = 3
## Papers
- Modelling double neutron stars: radio and gravitational waves
- Modelling Nuetron Star-Black Hole Binaries: Future Pulsar Surverys and Gravitaional Wave Detectors
- The population of TeV pulsar wind nebulae in the HESS Galactic Planes Survey
## To do
- **Lucas:** load extra columns to PSR output; generate isolated PSR population from the binary populations; investigate references for connecting progenitor-birth PSR properties.
- **Giovanni:** complete pipeline for generating the gamma spectra for a sample:
	- While the relation between Edot and the SED is something that comes from the HESS model, the synthesis brings the correlation between Edot and P, Pdot and B. Thus I could set as a first objective making the plot luminosity-energy for varying P (instead of varying age as in the paper).
- By November 9th, have a step-by-step notebook from loading the PSR table to generating the observed spectra.
	- Use ind_interpolator to add a gamma ray index column to the sample dataframe; this is the index for the 1-10 TeV range of the spectrum.
	- Scatter plots for all possible correlations, looking for something interesting: PxIndex, Pdot x Index, B-field x Index... Anything.
	- Histogram for the index for the FeH=0 (solar metallicity sample);  then look at how it changes for the subsolar (FeH=-200, FeH=-100) and supersolar (FeH=30) samples. Obs.: 1e2FeH=-100 means [Fe/H]=-1.
