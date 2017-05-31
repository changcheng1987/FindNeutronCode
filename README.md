# FindNeutronCode
This project is to find neutron coded pairs in MS1 spectra, as an cooperation project with Dr. Chenxi Jia. 

# Change log
##v1.1.3 (2017-5-31 Major improvement!)
* Add a new function to find the unlabeled peak for neutron code pair. The mono-isotope and the second isotope of the unlabeled precursor are required. 
* Modify the project name as *NeutronCodeFinder*

##v1.1.2 (2016-12-24) Merry Christmas:-)
Add a new parameter "NeuCode_Mass" to the config file
For our method, the NeuCode_Mass is 42.3 mDa, for Coon's method it is 36.6 mDa

##v1.1.1 (2016-11-17)
Cancel off the "isused" feature for every isotopic peak.
Allow multiple neutron-coded peak pairs share the same peak.

##v1.1.0 (2016-11-15 Major improvement!)
The original algorithm only considered the simplest situation--the peak pair indicated the i-*th* and the i+1 *th* peaks. The new algorithm includes all the possible situations, meaning the i-*th* and i+n *th* peaks within the mass tolerance (n>1) will be considered.

default range: charge=[2,5]; Rnumber=[1,5] 

##v1.0.4 (2016-11-11)
allow the output of multiple R number for one PSM
 
##v1.0.3 (2016-10-31)
(1) fix a bug when peak picking

(2) add de-noise function before peak picking (need refinement)

(3) change some default parameters in config file
##v1.0.2 (2016-9-6)
(1) output R number in the pep and pepion result files

(2) output the mean mass of the neutron-coded mono-isotope peak pair (set as m) and calculate the mass of the non-coded peak pair (calculated as m-6.016254*Rnum/charge)


## v1.0.1 (2016-8-31)

**(1) Output the m/z when the peak intensity is the max in each XIC in pep file**

**(2) Add new input format: FindNeutron.exe test.config**

All the 15 paramters were listed in the config file as follows:

//paramters for peak detection

MAX_CHARGE	5

SN_CUTOFF	1

PEAK_RINT_CUTOFF	0	//minimum peak relative intensity,default 0.

PEAK_INT_CUTOFF	1E5	//minimum peak absolute intensity

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