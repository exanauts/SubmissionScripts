# SubmissionScripts

This is a collection of submission scripts for various computer platforms

## Summit

Download the Julia binary for Summit from https://exanauts.github.io/ .

Load the modules needed for Julia:

```
module load gcc/7.4.0
```
If you use MPI, `MPI.jl` has to be linked to the system's MPI library.

```
julia --project -e 'ENV["JULIA_MPI_BINARY"]="system"; using Pkg; Pkg.build("MPI"; verbose=true)'
```

Then submit the job defined in `summit.lsf`.

```
bsub summit.lsf
```

