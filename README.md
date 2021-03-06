# Steps for initial MEA analysis

The code used here was created by Timothy Sit, and was edited to work on computers with 8GB of RAM or possibly less. These scripts will run electrode-by-electrode rather than going over all electrodes at the same time. For the original scripts, go to [Tim's GitHub](https://github.com/Timothysit).

### Procedure for Spike Detection
1. Use MC_DataTool to initially convert `.mcd` files into `.raw` format.
2. Run `MEA_batchConvert.m` in the folder containing the `.raw` file to create `.mat` files for each electrode (make sure the script calls `MEA_load_bin_original_preallocate.m` so that it converts electrode-by-electrode).
3. Run `electrodeByElectrodeDetect.m` to create `spikeMatrix.mat` - a sparse binary matrix in which a '1' refers to a spike. You can change the spike detection method within the script (refer to `detectSpikes.m` for different methods). May need to copy and paste the contents of the function rather than running the function as a whole.

### Getting inital visualizations
4. Run `mecp2_main.m` to get filtered traces / grid traces, raster plots, multiple single trace plots, and spike sum heat maps (script runs spike detection, so you may not need to do step 3).
5. For correlational visualizations/network plots, use `organoidCorrelation.m`.
