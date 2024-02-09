# Work Experience
- Optical Coating Designer - Optics Manufacturing - L3Harris Technologies - Toronto ON
- Research Assistant - Department of Physics - Queen's University - Kingston ON
- Research Assistant - Centre for Nanoscience and Naotechnology UNAM - Ensenada Baja California Mexico

# Education
- PhD in Physics Queen's University
  - [Optical Properties of Chiral Thin Films and Microparticles](http://hdl.handle.net/1974/14915)
- B Sc. in Physics Universidad Autónoma de Baja California

# Projects

### Light Scattering from Randomly-Oriented Particles

During my PhD I studied light scattering from randomly oriented particles. Helical shaped particles were of particular interest because their optical properties resemble those of chiral molecules. These kinds of molecules selectively absorb circularly-polarized light according their molecular orbital asymmetry, known as chirality. This chirality assigns a 'handedness' to the molecule, and interpreting whether a molecule is right or left handed is crucial in understanding its properties such as flavour, odour, drug safety, and drug effectiveness. Additionally, the orientation of the molecule will also have an effect on the absorption spectra, so much so, that the optical response of a randomly oriented collection of molecules might look as the opposite of a single oriented molecule, leading to ambiguity in measurement interpretation.

Using numerical simulations we were able to simulate the optical properties of randomly oriented helical particles. In the lab we were able to fabricate nanostructured helical columnar films, and detached the columns to create a suspension of particles in water to try to characterize the optical properties.

### Discrete Dipole Approximation for Light Scattering
The Discrete-Dipole Approximation (DDA) is a numerical method that represents an arbitrarily-shaped particle as electric dipoles on a cubic lattice. This representation yields a system of linear equations for the induced dipole moments (light-matter interaction). If there are N dipoles representing a particle, this results in a system of linear equations with 3N complex-valued unknowns. Typical values of N range between 10,000 and 100,000 so the equations are solved with iterative techniques (i.e. Conjugate Gradient) in high-performance computing clusters. The solutions are used to calculate the theoretical scattering response for any observation direction.

There are many implementations, but the one I used was [OpenDDA](https://github.com/drjmcdonald/OpenDDA). In particular, I made some modifications to use the parallelized version using the Message-Passing Interface (MPI) for distributed memory clusters. You can see all the modifications I did in the [following repository](https://github.com/bcrodrigo/OpenDDA_MPI_modifications) in my Github.

### Generating Dipole Locations for Different Particle Shapes
Using Python I wrote scripts to generate different kinds of particle shapes: sphere, cylinder, helices, in order to generate input targets for OpenDDA. You can see the code in my Github [dipole_locations](https://github.com/bcrodrigo/dipole_locations/tree/main) repository.

<img src="/images/sphere_preview.png" alt="sphere_preview" width="150" height="auto"> <img src="/images/cylinderpreview.jpg" alt="cylinder_preview" width="150" height="auto"> <img src="/images/helixpreviewLH.jpg" alt="helix_preview" width="150" height="auto"> 

### Simulation Analysis
Simulation outputs were post-processed with custom Python scripts and measurable quantities were calculated. A typical simulation would output a csv file with about 1 million rows, as each simulation calculated a 2-by-2 complex-valued matrix (known as Amplitude Scattering Matrix) for 18 incident wavelengths, 20 orientations, and 181 observation directions.

The 2-by-2 complex-valued matrices were mapped to a 4-by-4 real-valued matrix, known as the Mueller Matrix. This last matrix relates the incident and scattered polarization states, and allows you to validate if the simulation outputs are correct by looking at the number of non-zero elements of the MM as well as its symmetries. Additionally, the elements of the Mueller matrix can be measured experimentally.

Below you can see an example of the calculated Mueller matrix elements for a spherical particle

<img src="/images/MM_sphere_r8_parsed_averaged.png" alt="mm_avg" width="500" height="auto">

You can see the code in the [following repository](https://github.com/bcrodrigo/OpenDDA_output_parsing) in my Github.

### Polarization state of light
Lastly, the simulations enabled to learn what was the polarization state from light scattered by randomly-oriented helical scatterers, what was the effect of structural parameters. Of particular interest was circularly polarized light.

Thesis work at QSpace
During my PhD I studied the linear and non-linear optical properties of helical shaped nanostructured thin film coatings and microparticles. This required a combination of computational and experimental techniques. Follow [this link](http://hdl.handle.net/1974/14915) to take a look at the full document.


