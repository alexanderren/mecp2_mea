# Steps for initial MEA analysis

### Procedure for Spike Detection
1. Use MC_DataTool to initially convert `.mcd` files into `.raw` format.
2. Run `MEA_batchConvert.m` in the folder containing the `.raw` file to create `.mat` files for each electrode (make sure the script calls `MEA_load_bin_original_preallocate.m` so that it converts electrode-by-electrode).
3. Run `electrodeByElectrodeDetect.m` to create `spikeMatrix.mat` - a sparse binary matrix in which a '1' refers to a spike. You can change the spike detection method within the script (refer to `detectSpikes.m` for different methods).

### Getting inital visualizations
4. Run `mecp2_main.m` to get filtered traces / grid traces, raster plots, multiple single trace plots, and spike sum heat maps (script runs spike detection, so you may not need to do step 3).
5. For correlational visualizations/network plots, use `organoidCorrelation.m`.
