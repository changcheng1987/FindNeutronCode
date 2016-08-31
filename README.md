# FindNeutronCode
This project is to find neutron coded pairs in MS1 spectra, as an cooperation project with Dr. Chenxi Jia. 

# Change log

## v1.0.1 (2016-8-31)
**Add new input format: FindNeutron.exe test.config**

All the 15 paramters were listed in the config file as follows:

//paramters for peak detection

MAX_CHARGE	5

SN_CUTOFF	1

PEAK_RINT_CUTOFF	1E-3	//minimum peak relative intensity

PEAK_INT_CUTOFF	1E6	//minimum peak absolute intensity

PEAK_TOLERANCE_PPM	10	//isotope peak mass tolerance: 10 ppm

//parameters in a neutron-coded pair

RATIO\_LIMIT\_LH	10	//max ratio limit for light vs heavy intensity

RATIO\_LIMIT\_SUM\_LH	2 //the ratio limit of sumL/sumH in an XIC  2016-8-27

MIN\_MASS\_DIFF\_IN\_PAIR	5 //mDa

MAX\_MASS\_DIFF\_IN\_PAIR	100	//mDa

//paramters between neutron-coded pairs

MIN\_MASS\_DIFF\_BETWEEN\_PAIR	0	//mDa

MAX\_MASS\_DIFF\_BETWEEN_PAIR	3	//mDa

RT\_TOLERANCE	5	//max rt range when merging redundant ions, default +/-5min

ION\_TOLERANCE\_PPM	3 //precursor ion tolerance when merging redundant ions, default +/-3 ppm

MAX\_R\_NUM	3 //R number in a peptide sequence	 2016-7-29

PEAKPAIR\_LIMIT\_mDa	10	//the tolerance of the mass diff in a peak pair and the theoretical mass diff (42.3 mDa*Rum/charge)

//raw files (one file per line)
e:\task\task_NeutronCoding_JCX\data\raw_data\20160809_SILAC.raw
e:\task\task_NeutronCoding_JCX\data\raw_data\20160705_JCX_SLIAC_DDA_100per.raw 

## v1.0.0 (2016-6-21)
It began on 2016-6-21.

# Features
* Feature detection in MS1 spectra: find all the mono-isotopes with accurate charge, XIC and RT
* Find neutron coded peak pairs in MS1 spectra