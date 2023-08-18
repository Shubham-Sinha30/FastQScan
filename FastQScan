import argparse
from Bio import SeqIO
import fastqc

def generate_perbase_quality_graph(input_fastq, output_directory):
    sequences = SeqIO.parse(input_fastq, "fastq")

    fastqc_data = fastqc.FastQC()
    fastqc_data.add_sequences(sequences)

    fastqc_data.run(output_directory)
    print("Per-base quality graph generated in", output_directory)

if __name__ == "__main__":
    parser = argparse.ArgumentParser(description="Generate per-base sequence quality graph using FastQC")
    parser.add_argument("input_fastq", help="Input FASTQ file")
    parser.add_argument("output_directory", help="Output directory for FastQC results")
    args = parser.parse_args()

    generate_perbase_quality_graph(args.input_fastq, args.output_directory)
