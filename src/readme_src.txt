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
While this project focuses on collecting broadband absorbance spectra, their has been a tremendous volume of work in building out this technique for applications such as ultra-low Limit of Detection (LoD) gas sensing or other solid samples. More modern techniques often eschew broadband entriely and rely on single or dual-laser techniques for their greater optical power.

Implimentation:
LOG-20231106
Currently we are testing if this concept is feasable for us to impliment using cheap, off the shelf kit by building a prototype that detects the absorbance of a laser on a piece of sharpied cardboard. We chose this as it could give us the greatest signal to noise given the parts we had avalable to test the idea, and due to the fact that we already had all the parts to test it....

Images and short videos of the current setup can be seen in the src folder.

The set-up currently consists of an ESP-WROOM-32 microcontroller running the provided code to send a Hi-Lo signal to an N-channel MOSFET. This MOSFET is use to chop the inout power to a Creality 1.6W, 450 nm laser aimed at the cardboard sample. This sample is loaded inside a transparent-ish 2-3 mL polypropylene centrifuge vial with an electrit microphone stuck into the cap of the vial. This signal recorded from the microphone, as well as the driving signal sent to the mosfet can been seen on the oscilloscope.

In working_chop_1w, the ocilliscope signals of channels 1 and 2 correspond to the signal recorded by the microphone inside the cell and the driver signal sent to the gate of the MOSFET respectively. This demonstrates that we can observe and record the PA effect given our current equimpent.

Current Bill of Materials(20231106):
Oscilloscope: https://www.amazon.com/YEAPOOK-ADS1013D-oscilloscope-Oscilloscope-Bandwidth/dp/B08L3FRKYF/ref=sr_1_3?crid=18EJ7MYP3QZTI&keywords=oscope&qid=1699328242&sprefix=oscope%2Caps%2C214&sr=8-3&ufe=app_do%3Aamzn1.fos.f5122f16-c3e8-4386-bf32-63e904010ad0

Laser: https://www.amazon.com/Creality-Engraver-Engraving-Attachment-Blue-Violet/dp/B08SHCJ7V4/ref=sr_1_6?crid=KTLKHIGKSU14&keywords=creality+1.6w+laser+module&qid=1699328633&sprefix=creality+1.6W+%2Caps%2C259&sr=8-6

Electret Microphone and Amplifier: https://www.amazon.com/gp/product/B08N4FNFTR/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1

ESP 32: https://www.amazon.com/ESP-WROOM-32-Development-Microcontroller-Integrated-Compatible/dp/B08D5ZD528/ref=sr_1_1?crid=B0WO8SD2VFZ9&keywords=ESP32&qid=1699328266&sprefix=esp32%2Caps%2C243&sr=8-1&th=1

Centrifuge Tubes: https://www.amazon.com/Polypropylene-Micro-centrifuge-Tube-Snap-Natural/dp/B07WRMML5D/ref=sr_1_2?crid=155Y48VL3FV96&keywords=3+ml+centrifuge+tube&qid=1699328306&sprefix=3+ml+cnetr%2Caps%2C147&sr=8-2
