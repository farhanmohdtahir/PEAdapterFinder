# PEAdapterFinder
# Introduction  
PEAdapterFinder is stand for Paired-End Adapter Finder. PEAdapterFinder is capable to  identify two consensus adapter sequences from two paired-end FASTQ file as input. Both FASTQ file can be in multi-line FASTQ file or 4-line FASTQ file.  

- Author  
    - Rayan Gan and Farhan Tahir 
- Date  
    - Jan 2017  
    
# Install PEAdapterFinder (Version 1: If git not installed in system)
1. Download source code from github: https://github.com/farhanmohdtahir/PEAdapterFinder.git (downloaded file will be named as PEAdapterFinder-master.zip)  
2. Open terminal  
3. Go to Downloads directory (or directory which the PEAdapterFinder-master.zip are located)  
   Example:  
    If Downloads directory is located in path: /export/home/farhan/Downloads  
    
        cd /export/home/farhan/Downloads 
            
4. Unzip the PEAdapterFinder-master.zip file by writing the following command:  

        unzip PEAdapterFinder-master.zip  

5. After unzip, go to the PEAdapterFinder-master directory  
   Example:  

        cd /export/home/farhan/Downloads/PEAdapterFinder-master  

6. MAKE the PEAdapterFinder program by writing the following commands (This will create executable PEAdapterFinder program in the directory):  
    
        make  

7. Installation complete. You can run PEAdapterFinder as the following tutorial.  

#Install PEAdapterFinder (Version 2: If git already installed in system)
1. Open Terminal  
2. Cloning the source code from github by writing the following command:  
   
        git clone https://github.com/farhanmohdtahir/PEAdapterFinder.git  

3. Go to PEAdapterFinder directory.  
   Example:

        cd PEAdapterFinder

4. MAKE the PEAdapterFinder program by writing the following commands (This will create executable PEAdapterFinder program in the directory):  
   
        make  

5. Installation complete. You can run PEAdapterFinder as the following tutorial.  

# Run PEAdapterFinder  
1. Open Terminal  
2. Write the command to go to the directory that locate the PEAdapterFinder program  
   Example:  
    If PEAdapterFinder program is located in path: /export/home/farhan/Downloads/PEAdapterFinder-master:  
    
        cd /export/home/farhan/Downloads/PEAdapterFinder-master  

3. Write the command to execute PEAdapterFinder program  
   Example:  
   
        ./PEAdapterFinder -f1 "file1.fastq" -f2 "file2.fastq" [options]  

 -f1 and -f2 are the REQUIRED option for user to insert 2 paired-end FASTQ file  
___Make Sure both input FASTQ file are present in the same directory as PEAdapterFinder Program and paired-end to each other!___  

4. Below is the command of the options that can be use:  

| Option | Description                                                                                                                                                                                                                   | Flag         |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| -f1    | Input File 1. The file must in .fastq OR .fq file format  (multi-line OR 4-line FASTQ file)  Example: __-f1 _sample1.fastq___ OR __-f1 _sample1.fq___                                                                         | __REQUIRED__ |
| -f2    | Input File 2. The file must in .fastq OR .fq file format  (multi-line OR 4-line FASTQ file).  Example: __-f2 _sample2.fastq___ OR __-f2 _sample2.fq___                                                                        | __REQUIRED__ |
| -seql  | Minimum length percentage to get adapter sequence  (default = 70, to change use ‘-seql=’) Example: __-seql=80__                                                                                                               | OPTIONAL     |
| -perc  | Minimum match percentage to get adapter sequence  (default = 85, to change use ‘-perc=’) Example: __-perc=90__                                                                                                                | OPTIONAL     |
| -conf  | Minimum confidence level of nucleotides (default = 1, to change use ‘-conf=’) Example: __-conf=80__                                                                                                                           | OPTIONAL     |
| -debug | Debug level of programme (default = 0, to change use ‘-debug=’ : 0 - only adapter sequences, 1 - nucleotide count and phred score, 2 - dynamic programming matrix and traceback matrix) Example: __-debug=1__ OR __-debug=2__ | OPTIONAL     |
| --help | To view information about option that can be used                                                                                                                                                                             | OPTIONAL     |

5.Wait for the program to complete it's process for the result of adapter sequence found in both file. 
