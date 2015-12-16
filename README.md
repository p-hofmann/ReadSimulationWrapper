# ReadSimulationWrapper
Wrapper for the simulation of reads

## Usage
	python "readsimulationwrapper.py" 10000 \
	-i abundance.tsv \
	-l genome_locations.tsv \
	-o dir_output/ \
	-art art_illumina \
	-epd dir_profile/ \
	-ep "hi150" \
	-sd 27 \
	-m 270

## Formats

### abundance.tsv
Tab separated.  
Abundance reflects genome abundance, not data abundance!

* column 1: genome id
* column 2: relative abundance  


### genome_locations.tsv
Tab separated.  

* column 1: genome id
* column 2: file path to fasta file  

## Adding new ART error profiles

Search in "readsimulationwrapper.py" for the class definition of "ReadSimulationArt" and find the lines:

	_art_error_profiles = {
		"mi": "EmpMiSeq250R",
		"hi": "EmpHiSeq2kR",
		"hi150": "HiSeq2500L150R"}

If someone made new profile files like "HiSeq_5000_L250R_1.txt" and "HiSeq_5000_L250R_2.txt", one only needs to add them like this:

	_art_error_profiles = {
		"mi": "EmpMiSeq250R",
		"hi": "EmpHiSeq2kR",
		"hi150": "HiSeq2500L150R",
		"hi250": "HiSeq_5000_L250R_"}
