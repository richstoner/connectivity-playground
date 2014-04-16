
### Objective

Extend the analysis of the AIBS Mesoscale connectome paper to single-voxel level of detail.

493,878 voxels

### Deliverable #1 - Single voxel connectivity matrix (or not)

493,878 x 493,878 matrix of projection strengths

Uncompressed, this matrix will take ~227GB per byte of precision. We can save space with sparse matrices and compression but still, not really feasible without significant effort. Even at 1px/value, we're looking at 500k x 500k pixels, or 250,000 megapixels. 

### Deliverable #2 - Helper webservice (more realistic)

More practically, can we write a python module that sits between use and AIBS api to programmatically generates single voxel maps based on anatomic regions?

Extending this idea, it should work as follows: identify regions in ontology, pass ontology ids of inputs & outputs to webserver, get back either a) matrix of single voxel values or b) visualization of expression heatmap

Bonus points: organize by ontology order and generate colored sidebars as seen in Figure 3.

### Deliverable #3 - Visualization

Using webserice from #2, programmatically generate tiles (zoomify) and host. It's near impossible to rasterize everything at once, but if we coordinate tile arrangement to fit seemlessly over expression grid, we can pull this off. We'd need to go to 18 levels in a tiered pyramid at 256x256px (67108864px x 67108864px) to get everything. 

