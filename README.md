# fqcomp
Quality scores compressor using parallel arithmetic code written by Rust.

Two input Files(input fastq file and parameter json file) are required for program.

The parameter file should contain the following values.
:precision, file_size, thread_num, first_line, last_line


The precision should be set to more than 30 and less than 52.

When compressing, you must enter the value of precision, file_size , and threadnum, and first_line and last_lein can be assigned any value.

When decompressing, you only need to assign a value to the thread_num , and any value to the other parameters.

When random access, you only need to assign a value to the thread_num, first_line, last_line , and any value to the other parameters.
#test

Example of parameter file is in the sample_data folder.


           Usage:  cargo.exe [Cargo OPTIONS] [MAIN OPTIONS] [INPUT FILE |OUTPUT NAME| PARAMETER FILE]

            MAINT OPTIONS: [-c | -d ]  
                    -c : run compressor[default] \n
                    -d : run decompressor\n
                    -r : run random access\n
                    -h : help
                    
                    Example:
                    run compressor in release mode 
                    cargo run --release -- -c input.fastq outputname parameter.json
                    
                    run decompressor in release mode
                    cargo run --release -- -d input'name' outputname parameter.json
                    
                    run randaom access in release mode
                    cargo run --release -- -r input'name' outputname parameter.json
                    
                    when compressing, precision, size of subfile, and number of thread are required for parameter.serde_json.
                    when decompressiong, only number of thread is required.
                    
