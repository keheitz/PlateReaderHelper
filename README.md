# PlateReaderHelper
## Script to reformat data from a 96-well Plate Fluorescence Spectrophotometer (Plate Reader) to facilitate analysis.

###Synopsis
This ipython notebook takes output data from a 96-well Plate Fluorescence Spectrophotometer, and reorganizes and summarizes the data so that chemists can more easily analyze for patterns. 

The original output data from a Plate Reader is a text file that approximates the layout of the well-plate. This notebook script transforms the data to output two new files.

Users can specify different numbers for well_groupings which map to compounds in the output data, and relabel compounds and row concentrations to more accurately identify the values.

###Example
####Original output data from the plate reader:

	37.00	4.4886	0.74	0.7452	0.7466	0.74	0.746	0.7412	0.744	0.7438	0.7462	0.7474	0.7432		

		3689.802	3409.322	3778.041	3079.057	2818.387	2788.283	2845.285	3284.842	3649.555	3456.887	3660.852	3742.566		
    
The first value (37.00) is a temperature reading. The subsequent values in the first row are time readings. The second row contains corresponding fluorescence readings for each time. This is repeated for each row in the plate, with a break in between.

####readings_filename:
	PlateRead	Concentration	Compound	Time	Fluorescence
0	1	Control	Compound A	0.7386	3689.802
1	1	Control	Compound A	0.74	3409.322
2	1	Control	Compound A	0.7452	3778.041
3	1	Control	Compound A	0.7466	3079.057
4	1	Control	Compound B	0.74	2818.387
5	1	Control	Compound B	0.746	2788.283
6	1	Control	Compound B	0.7412	2845.285
7	1	Control	Compound B	0.744	3284.842
8	1	Control	Compound C	0.7438	3649.555
9	1	Control	Compound C	0.7462	3456.887
10	1	Control	Compound C	0.7474	3660.852
11	1	Control	Compound C	0.7432	3742.566

(same data as above, formatted to show each well-reading individually)

####stats_filename:
	Plate Read	Concentration	Compound	Avg Fluorescence	Standard Deviation	Avg Time
21	1	Control	Compound A	3489.0555	315.3135886	0.7426
22	1	Control	Compound B	2934.19925	234.9185045	0.7428
23	1	Control	Compound C	3627.465	121.0340918	0.74515

(further groups data by plate, row, and compound, and provides average stats)
###Motivation
To make it easier to analyze the output data for active compounds, and create charts for research.

###Installation
Python 2.7
Required packages: csv, pandas, numpy, decimal
