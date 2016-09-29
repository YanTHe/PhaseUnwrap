Phase unwrapping with multiple ambiguities and experimental noise.

The problem:

Data is phase of a travelling wave collected using a laser interferometer at discreet points along a membrane. The magnitude of the  raw data is between 0 and -360 degrees and needs to be unwrapped to calculate with overall phase lag (to be used to calculate the velocity of the travelling wave). There is also a random 180 degree phase ambiguity that needs to be corrected and experimental noise.

In isolation both the 360 and 180 phase steps are simple to correct: 
Jumps greater than |180| between adjacent points should be corrected by |360| in the opposite direction. 
Jumps greater than |90| between adjacent points should be correct by |180| in the opposite direction

However, the interaction between these ambiguities, the experimental noise and an expected change in phase magnitude, means applying the correct correction becomes harder than a simple sum of its parts. While experimental noise can be assumed to be normal for each measurement point, overall uncertainly of total lag (the final value) is cumulative and restricted by the fixed ambiguities and therefore is not normal. The expected phase change with distance is within a measurable range (i.e., it’s not more than ~90 degrees per point), and is roughly linear. 

The functions here are designed to automate the process of unwrapping clean data (with more control than Matlab’s unwrap function) and to automatically estimate the most-likely correct phase trajectory in the presence of noise.

stochasticUnwrap3.mlx – Matlab live script demonstrating problem and use of unwrap3 and attempts to simulate and then find correct trajectory.

Unwrap3.m – does fairly standard phase unwrapping, but allows adjustment of thresholds and correction magnitudes.

