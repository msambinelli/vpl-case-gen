# VPL-CASES-GEN

This script generates *.cases files for the Moodle VPL plugin.  

## Usage



```bash
usage: vpl-cases-gen [-h] [--interpreter INTERPRETER] [-o filepath] program filepath [filepath ...]

Generator of test cases files for the Moodle VPL plugin.

positional arguments:
  program               The program that are going to process the input cases to generate the outputs.
  filepath              Files with the input cases.

optional arguments:
  -h, --help            show this help message and exit
  --interpreter INTERPRETER
                        If necessary, you can use this option to specify an interpreter to run program.
  -o filepath, --output filepath
                        Specify an output file to write the generate cases (default: write to the stdout).

```



## Usage examples



### Basic usage



```bash
./vpl-cases-gen program input01.in input02.in input03.in
```



where:

- `program` is the program that will be fed by the test cases contained in the input files to generate the reference output that will be used for grading the students' solutions.
- `inputXX.in` is a file containing one or more test cases for `program`. If `inputXX.in` has more than one test case, then a line containing the mark `<<<>>>` should be put between two test cases to represent that one test case is ending and another is starting. 



### Writing the output to a file

You can write the output to a file with the option `-o` or `--output`.

```bash
./vpl-cases-gen -o output.cases program input01.in input02.in input03.in
```



### Setting an interpreter 

If the program require an interpreter to run properly (maybe because the program has no execution permission or because the OS does not understand shebang), you can specify one with the option `--interpreter`.



```bash
./vpl-cases-gen --interpreter julia program.jl input01.in input02.in
```

