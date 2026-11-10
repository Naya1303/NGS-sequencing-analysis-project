NGS Sequencing DNA Analysis Project

*Background and purpose of project*:
This Python program analyses DNA sequencing reads by validating, summarising and identifying mismatches against a reference sequence. It investigates whether treatment is associated with increased mutation frequency and whether particular nucleotide positions show significant differences between treatment and control samples.

*Instructions on how to run*:
Open the Notebook in Google Colab. Upload reads.csv and reference.txt, then run the notebook cells sequentially from the beginning to execute the analysis and display the results.

*Inputs and Outputs*:
This program requires a CSV file containing read identifiers, sample labels, group data and DNA sequences, alongside a reference DNA sequence stored in a text file. It returns validated reads, mutation locations and nucleotide substitutions, followed by sample-level summaries. It also identified the three most frequent mismatch positions across both groups and compares their frequencies using Welch's two-sided t-test.

*Method*:
The analysis is divided into separate functions each with their own purpose, making testing easier and code simpler to maintain.
1. validate_read() checks sequence length and valid nucleotide characters individually, recording both errors where applicable. It also converts lowercase sequences to uppercase for comparisons.
2. find_mutations() identifies mutations by comparison against the reference DNA sequence.
3. analyse_reads() returns dictionaries containing information about reads combining validity with finding mutations.
4. summarise_samples() produces a summary table of results, including top three positions with mismatches and percentage of valid reads containing one or more mismatches.
5. compare_positions() calculates mismatch percentages using valid reads only and selects the three most frequent positions. Separating statistical calculations into calculate_statistics() avoids repeating Welch's t-test and allows comparisons to be performed consistently.

*Testing*:
Three categories of tests were performed. First, validate_read() was tested using lowercase sequences, incorrect lengths and invalid nucleotide characters. Second, find_mutations() was tested with identical sequences and sequences containing one or multiple substitutions. Third, analyse_reads() and the summary functions were tested using mixed valid and invalid reads, empty inputs and assertions checking expected results. These tests demonstrated that the functions handle normal, edge-case and invalid inputs.
