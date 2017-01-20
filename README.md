# PEAdapterFinder
# Introduction  
PEAdapterFinder is stand for Paired-End Adapter Finder. PEAdapterFinder is capable to  identify two consensus adapter sequences from two paired-end FASTQ file as input. Both FASTQ file can be in multi-line FASTQ file or 4-line FASTQ file.  

- Developer  
    - Rayan Gan and Farhan Tahir 
- Date  
    - Jan 2017  
    
# Install PEAdapterFinder (Version 1: If git is not installed in system)
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

6. Compile the source code by writing the following commands (This will create executable PEAdapterFinder program in the directory):  
    
        make  

7. Installation complete. You can run PEAdapterFinder as the following tutorial.  

# Install PEAdapterFinder (Version 2: If git is installed in system)
1. Open Terminal  
2. Cloning the source code from github by writing the following command:  
   
        git clone https://github.com/farhanmohdtahir/PEAdapterFinder.git  

3. Go to PEAdapterFinder directory.  
   Example:

        cd PEAdapterFinder

4. Compile the source code by writing the following commands (This will create executable PEAdapterFinder program in the directory):  
   
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
| -f1    | Input File 1. The file must in .fastq OR .fq file format  (multi-line OR 4-line FASTQ file)<br/>  Example: __-f1 _sample1.fastq___ OR __-f1 _sample1.fq___                                                                         | __REQUIRED__ |
| -f2    | Input File 2. The file must in .fastq OR .fq file format  (multi-line OR 4-line FASTQ file).<br/>  Example: __-f2 _sample2.fastq___ OR __-f2 _sample2.fq___                                                                        | __REQUIRED__ |
| -l  | Minimum length percentage to get adapter sequence <br/> _This parameter will set the percentage's limit of length of sequence alignment for both read to determine whether both read contain Adapter Sequence or not._<br/>  (default = 70)<br/> Example: __-l 80__                                                                                                               | OPTIONAL     |
| -m  | Minimum match percentage to get adapter sequence <br/>_This parameter will set the percentage's limit of match bases between sequence alignment in read 1 and read 2 to determine whether both read contain Adapter Sequence or not._<br/> (default = 85)<br/> Example: __-m 90__                                                                                                                | OPTIONAL     |
| -c  | Minimum confidence level of nucleotides<br/>_This parameter will set the limit of biggest phred score for each bases in the adapter sequence that allowed in order to determine the confidence level of Adapter Sequence_<br/> (default = 10)<br/> Example: __-c 20__                                                                                                                           | OPTIONAL     |
| -d | Debug level of programme (default = 0 : 0 - only adapter sequences, 1 - nucleotide count and phred score, 2 - dynamic programming matrix and traceback matrix)<br/> Example: __-d 1__ OR __-d 2__ | OPTIONAL     |
| --help | To view information about option that can be used                                                                                                                                                                             | OPTIONAL     |

5.Wait for the program to complete it's process for the result of adapter sequence found in both file. 

# Set the PEAdapterFinder program in your linux environment [OPTIONAL]
Rather than you need to go to path of PEAdapterFinder program for each time you want to run the program, You may export it into your linux environment. So that, you can run the PEAdapterFinder program in any directory instead of go to the program's directory first. To do so, you can write the command: 

      export PATH=$PATH:<PEAdapterFinder program's directory>

## OR

You can copy the PEAdapterFinder Program from the directory and paste it into the path that already set into your linux environment. To view paths that already set in your linux environment, you can write the command: 

      echo "$PATH"
      
This command will display all path that had been set in your linux environment. Example output: 

      /usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games
      
So you can paste it in _/usr/local/bin_ OR _/usr/bin_ OR _/usr/local/games_ OR _/usr/games_

# Run PEAdapterFinder After Set the Path in Linux Environment

If you had set the path of PEAdapterFinder program into your linux environment, you can run it in any directory you wish(you may run it in your sample file's directory). But, in order to run the program, you doesn't need to write "./" command. See the example command below:

      PEAdapterFinder -f1 sample1.fastq -f2 sample2.fastq
      
