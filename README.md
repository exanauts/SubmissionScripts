# SubmissionScripts

This is a collection of submission scripts for various computer platforms

## Summit

The PowerPC binaries required for Summit are now available through the JuliaLang webpage: https://julialang.org/downloads/ .

Load the modules needed, like for example CUDA when using `CUDA.jl`:

```
module load cuda
```

`CUDA.jl` at version `v2.6` is confirmed to work:

```
] add CUDA@2.6
```

If you use MPI, `MPI.jl` has to be linked to the system's MPI library.

```
julia --project -e 'ENV["JULIA_MPI_BINARY"]="system"; using Pkg; Pkg.build("MPI"; verbose=true)'
```

Then submit the job defined in `summit.lsf`.

```
bsub summit.lsf
```

