# SimpleSoilSampleSim
simulating soil sample methods

# User expirence

1. Define the chemicals and their distribution in the soil
want: 

```Python
soil = Soil(chemicals, comp_function)
```

The soil object is created with a list of chemicals and a function that defines the distribution of the chemicals in the soil. The function should return an array of shape(batch_size, n_chemicals) with values between 0 and 1 for any point (x, y, z) in the soil. The soil object can be used to sample the soil at any point or a batch of points.

2. Define the cross section of the soil sample
```Python
volume = UnifVolume(min_x, max_x, min_y, max_y, min_z, max_z)
selection_dist = unif_dist(min_x, max_x, min_y, max_y, min_z, max_z)
readings = soil.sample_volume(volume, selection_dist, v_parts, n_pts)
```

The volume object is created with the dimensions of the soil sample. The soil object is used to sample the soil at random points inside the volume. The soil object returns the chemical readings at the points. The selection_dist parameter defines the distribution of the points inside the volume. The v_parts parameter defines the number of vertical parts the volume is divided into. The n_pts parameter defines the number of points to sample.
The selection_dist object is created with the dimensions of the volume. The object can be used to sample points inside the bounding box of the volume.