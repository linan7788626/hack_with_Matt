#Galaxy-galaxy Strong Lensing in PhoSim

### Introduction
In the Twinkles simulation, multiply lensed quasars and supernovas are presented well using the lensing system from OM10 and PhoSim. But the images of lenses and the lensed images of host galaxies of quasars or supernovas are needed. We developed an approach to produce images of lenses and lensed host galaxies, and combine them together using PhoSim according to a given lens from OM10.

### Images of Lenses.  
- Randomly pick one lensing system from OM10 (see Table 1).
- Find the closest velocity dispersion from a galaxy catalog (Table 1 in [paper 1](http://arxiv.org/abs/1501.04977v2)) to obtain Effective radius and Apparent magnitude.
- Assume that the Orientation, Axis ratio, and Redshift of the images are the same with the lens.
- Compose a python script to create an instance catalog based on these parameters.
- Produce the image of the lens in 6 bands by feeding the catalog into PhoSim.

     |OM10                      |  Parameters of the image
:-------:|:-------------------------:|:-------------------------:
ID    | 630751| Same
Orientation  (degree) | 156.5082 | Same
Axis Ratio (a/b) |1.117 | Same
Velocity Dispersion | 287.7398 (km/s) |Same
Redshift of the Lens| 0.228| Same
Effective radius|         -          |1.526 "
Apparent magnitude|     -        | 17.654
Index of Sersic|          -          | 4  



### Lensed Images
- Use the same lensing system picked from OM10.
- Randomly generate an instance catalog of a source galaxy.
- Run a ray-tracing simulation to produce lensed arc (fits file).
- Calculate the total magnitude of lensed images according to the input catalog.
- Input the fits file, apparent magnitude, and a reasonable SED into PhoSim.


### Galaxy-galaxy Strong lensing in PhoSim

![new_lens](https://cloud.githubusercontent.com/assets/14111037/17041473/e3b3de00-4f6b-11e6-97e8-b7f344d1a892.jpg)

![new_gal_gri](https://cloud.githubusercontent.com/assets/14111037/17041496/0448bc94-4f6c-11e6-90d1-eee6a23f3e66.jpg)



### Future work
- Try Fundamental planes with larger samples of observed galaxies, and more realistic index of Sersic profile.  
- Create the instance catalog of source galaxies (host galaxies) according to the lensed quasars or supernovas.
- Combine lens galaxies, lensed galaxies, and lensed quasars (supernovas) together for Twinkles.
- Think about integrating ray-tracing routines into PhoSim to parameterize the strongly lensed arcs.

### References 
- http://arxiv.org/abs/1501.04977v2
- https://github.com/drphilmarshall/OM10
