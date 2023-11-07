File: Readme_src.txt

This is the readme for the source folder for the OpenPhotoacousticSpectrometer (OPS) project. 
Introduction:
The OPS came out of a desire I had to gain more quantitiative information about the optical properties of some of the flame spray and friction surfaced deposits I was helping to produce in the OpenPyrojet and Rotoforge projects, links below. Getting some hard data about the the materials being deposited, such as absorbance/reflectance, and estimating properties like the band gap and oxide/carbide content can useful when coming to conclusion about the quality of deposits for at home power-electronics and semiconductor fabrication.


Actually collecting those spectra can be difficult in a home lab or shop setting due to the cost of aquiring adequate analytical tools, especially in in-vivo conditions. 
To make things worse, most of these samples or their substrates were not flat, poorly reflecting, and we didn't have what we felt were adequate optical detectors that could help us resolve the case. 

We stumbed across Photoacoustic Spectroscopy (PAS) as a possible solution to these problems and have been investigating possible implimentations of it in the form of a cheap, open-source, and practically useful tool to provide both ourselves and other DIY/Hacker/Maker/Researcher types a way in which to indirectly probe the optical properties of samples we make in our home labs and shops.

Brief Theory:
Photoacoustic spectroscopy is a technique in which a sample in a closed cell is stimulated by chopped or pulsed monochromatic or narrow frequency range light, typically in the visible or near-IR wavelengths. Some of the incident light will be absorbed, resulting in a small amount of local heating and stimulating radiative decay modes. The resulting small thermal expansion of the sample induces a pressure wave in the closed cell which can be picked up by a microphone. 
Given enough knowns about the samples thermal response, the timing of the stimulus pulses, and the dynamic range of the microphone and the wavelength of the incident light, a spectra of wavelength vs absorbtion can be derived relative to a standard "perfect" absorber. (usually carbon black or some other well studied, highly absorbing material.)
For more details on theory, I reccommend you check the docs page as well as the wikipedia on PAS. 
https://en.wikipedia.org/wiki/Photoacoustic_spectroscopy
While this project focuses on collecting broadband absorbance spectra, their has been a tremendous volume of work in building out this technique for applications such as ultra-low Limit of Detection (LoD) gas sensing or other solid samples. More modern techniques often esche broadband entriely and rely on singel or dual-laser techniques for their greater optical power.

Implimentation:
Currently we are testing if this concept is feasable for us to impliment using cheap, off the shelf kit by building a prototype that detects the absorbace of a 1.6 W laser at 450 nm, on a piece of sharpied cardboard. We chose this as it could give us the greatest signal to noise given the parts we had avalable to test the idea.

Images and short videos of the current setup can be seen in the src folder.
