homework 1: SNaQ data
=====================

### background (may be skipped)

SNaQ is a method to estimate the phylogenetic (~ genealogical) network
that generated a set of molecular alignments.
Given input data, SNaQ seeks the network that minimizes a **score**
(negative log pseudo-likelihood).
This score has a rough surface (often with local minima)
and the space of networks is a complex space to explore.
Therefore, each SNaQ analysis does **multiple runs**,
then returns the best network across all the runs.

Several SNaQ analyses were performed, always on the same input data,
with varying values of tuning parameters. These parameters control
how the search is done and when it is stopped. The goal of this study
was to find a combination of tuning parameters that makes the analyses
faster but as accurate, compared to the default parameters.

## data files

For each analysis, 2 files were created:
`xxx.out` in the directory `out` (for the main output: best network)
and `xxx.log` in the directory `log` (to record the parameter values and
details on the individual runs of a single analysis).
Here, `xxx` is an arbitrary name chosen by the analyst.

## preparation for submission through github

You need to download the data for the course in a git repository
that is **kept separate** from your own directories when you do the work.
Git repositories **must not** be nested within one another.
(if you hear about submodules, forget about them for now).

1. Get the data for the course:
  - navigate to where you want the data to go.
    This should **not** be inside a current git repository.
  - run `git clone git@github.com:UWMadison-computingtools/coursedata.git`.
    You should see a new directory `coursedata`. Do `ls` to check and
    `ls coursedata` to see what's in there.
2. Create a directory where you want to do all of your work for the course:
  for this homework, other homeworks and projects, **outside** the
  course data repository.  I will call this directory `stat679work`.
3. Inside `stat679work`, create a directory for this first homework.
  I will call it `hw1`.
4. Copy the data for this homework inside `hw1`.

Later, you will turn "stat679work" into a git repository, in order to broadcast
it to github and to submit your work there (instructions to follow).

## exercises

1. Create a shell script to change all file names `timetesty_snaq.log`
   to `timetest0y_snaq.log`, where "y" is a digit between 1 and 9,
   and to change `timetesty_snaq.out` `timetest0y_snaq.out`.

2. Create a shell script `summarizeSNaQres.sh` to start a summary of the results
   from all these analyses. The script should produce a table in `csv` format,
   with 1 row per analysis and 3 columns:

   - "analysis": the file name root ("xxx")
   - "h": the maximum number of hybridizations allowed during the analysis: `hmax`
   - "CPUtime": total CPU time, or "Elapsed time".

   Hint: start with a single command to extract one piece only (like h) for
   a single analysis. Then wrap it in a loop to apply this command to all
   analyses.

3. Create a script to summarize the results with more information.
   The script should produce a table in `csv` format with 1 row per analysis,
   the same columns as before and additional columns for:

   - Nruns: number of runs
   - Nfail: tuning parameter, "max number of failed proposals"
   - fabs: tuning parameter called "ftolAbs" in the log file (tolerated
     difference in the absolute value of the score function, to stop the search)
   - frel: "ftolRel"
   - xabs: "xtolAbs"
   - xrel: "xtolRel"
   - seed: main seed, i.e. seed for the first runs
   - under3460: number of runs that returned a network with a score better than
     (below) 3460
   - under3450: number of runs with a network score under 3450
   - under3440: number of runs with a network score under 3440
   <!-- - aveCPUtime: average CPU time per run: CPUtime / Nruns -->