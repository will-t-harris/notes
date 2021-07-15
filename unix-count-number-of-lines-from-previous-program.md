https://unix.stackexchange.com/questions/72819/count-number-of-lines-of-output-from-previous-program

`program | tee >(wc --lines)`
or
`program | tee >(wc -l)`