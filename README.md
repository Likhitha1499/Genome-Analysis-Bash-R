# Genome-Analysis-Bash-R
Scripts for genomic data analysis using Bash and R
#Download the FASTA file
 wget https://ftp.ncbi.nlm.nih.gov/genomes/archive/old_refseq/Bacteria/Escherichia_coli_K_12_substr__MG1655_uid57779/NC_000913.faa -O NC_000913.faa

#Calculate total no.of aminoacids
 total_amino_acids=$(grep -v "^>" NC_000913.faa | tr -d "\n" | wc -m)

#Calculate total no.of proteins
total_proteins=$(grep "^>" NC_000913.faa | wc -l)

#Calculate average length of the protein
average_length=$(echo "scale=2; $total_amino_acids / $total_proteins" | bc)
echo "The average protein length is: $average_length"
The average protein length is: 316.85
