# Custom scripts to interact with the Logan database.

## Requirements: 
Prior to using this script, ensure you have installed the following:
- Aws CLI
- rcgrep
- zstd

### To install aws CLI, please follow the instractions via :
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

### To install rcgrep please execute the command line 
`pip install rcgrep`
  
### Tutorial :
Execute the command line : 
- ` git clone https://github.com/Fadwa7/Scripts_Logan.git `
- ` cd Scripts_Logan ` 

To test the script, you'll need two files: id_accessions.txt and query_test.txt.
- id_accessions.txt: contains SRR Identifiers for your samples, with each ID on a separate line.
- query_test.txt: contains queries to search each query on a separate line.
  
### Downloading files using id_accessions.txt:

Execute the following command:

` ./download.sh $PATH/TO/ID_ACCESSIONS_FILE . `

- $ACCESSIONS_LIST : id_accessions.txt
- $PATH_TO_OUTPUT_DIRECTORY : The absolute path to the output directory, e.g : . (current directory)
  
Output :
```
SRR10030979.unitigs.fa.zst
SRR10030980.unitigs.fa.zst
SRR10030981.unitigs.fa.zst
SRR10030982.unitigs.fa.zst
SRR10030983.unitigs.fa.zst
```

### Search for queries:

Use the script: search_v2.sh.
Execute the following command:

` ./search.sh  . $PATH/TO/QUERY_LIST_FILE `

In the example: 
- DATA_FOLDER : . (for current directory)
- QUERY_LIST_FILE: query_test.txt

In the terminal you should have this output

```
List of queries:
TGTATCGTCAAGGCACTCTTGCCTACGCCATCAGCTCCAACTACCACAAGTTTATATTCAG 
TGTATCGTCAAGGCACTCTTGCCTACGCCAACAGCTCCAACTACCACAAGTTTATATTCAG 
GTATCGTCAAGGCACTCTTGCCTACGCCACAAGCTCCAACTACCACAAGTTTATATTCAGT 
GTATCGTCAAGGCACTCTTGCCTACGCCACGAGCTCCAACTACCACAAGTTTATATTCAGT 
AGCTGTATCGTCAAGGCACTCTTGCCTACGTCACCAGCTCCAACTACCACAAGTTTATATT 
TGTATCGTCAAGGCACTCTTGCCTACGCCAGCAGCTCCAACTACCACAAGTTTATATTCAG
Searching for queries...

~~~~~~ Query result for SRR10030979 ~~~~~~~



~~~~~~ Query result for SRR10030980 ~~~~~~~


>SRR10030980_4087562 ka:f:5.0   L:-:559931:+  L:+:4024443:- 
CTGAATATAAACTTGTGGTAGTTGGAGCTGATGGCGTAGGCAAGAGTGCCTTGACGATACA

~~~~~~ Query result for SRR10030981 ~~~~~~~



~~~~~~ Query result for SRR10030982 ~~~~~~~



~~~~~~ Query result for SRR10030983 ~~~~~~~



Process completed successfully.

```




