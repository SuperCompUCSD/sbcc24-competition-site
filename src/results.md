# SBCC24 Final Results

## Overall Leaderboard

| Rank | Team | 
| --- | --- | 
| 1 |Aalborg |
| 2 |Kansas | 
| 3 |Texas | 
| 4 |San Diego | 

## HPL Leaderboard

| Rank | Team | Gflops |
| --- | --- | --- |
| 1 |Aalborg | `6.81E+02` |
| 2 |Kansas | `3.41E+02` |
| 3 |Texas | `3.18E+01` |
| 4 |San Diego |`3.57E+00` |

## HPCG Leaderboard

| Rank | Team | Gflops |
| --- | --- | --- |
| 1 | Kansas | `25.182` |
| 2 |Aalborg | `24.5444` |
| 3 |San Diego |`3.17678` |
| 4 |Texas |`2.41697` |

## Cube20 Leaderboard

| Rank | Team | Raw Score |
| --- | --- | --- |
| 1 | Kansas | `2058724` |
| 1 | San Diego | `2058724` |
| 1 | Aalborg | `2058724` |
| 2 | Texas | `2058720` |

## Mystery Leaderboard

| Rank | Team | Cobblestones |
| --- | --- | --- |
| 1 | Aalborg | `59,271,270,805.56` |
| 2 | Kansas | `1256.195928` | 
| 3 | San Diego | `~2.76` |
| 4 | Texas |  |

## Score Breakdowns

### Totals
*note that the su2 column is not included in the sum*

| Team | HPL | HPCG | Cube20 | BOINC | SU2 | Total | Score % /60pts |
| --- | --- | --- | --- | --- | --- | --- | --- |
| UT | 0.4671414935 | 0.9598006513 | 19.99996114 | 5 | 0 | 26.42690329 | 44.04% |
| KU | 5.006681842 | 10 | 20 | 12 | 10 | 47.00668184 | 78.34% |
| UCSD | 0.05243850503 | 1.261528076 | 20 | 7 | 3.333333333 | 28.31396658 | 47.19% |
| Aalborg(ASK) | 10 | 9.746803272 | 20 | 20 | 12.85714286 | 59.74680327 | 99.58% |

### HPL
| Team | HPL | Input | GFLOPS | Relative Percent | Final Scaled Score |
|  --- |  --- | --- | --- | --- | --- |
| UT | WR11C2R4 | 8000 192 8 10 10.73 | 3.18E+01 | 4.67% | 0.4671414935 |
| KU | WR11C2R4 | 91392 128 5 8 1492.74 | 3.41E+02 | 50.07% | 5.006681842 |
| UCSD | WR11C2R4 | 5000 4 2 8 23.35 | 3.57E+00 | 0.52% | 0.05243850503 |
| Aalborg | WR00L2L4 | 113408 192 4 16 1428.02  | 6.81E+02 | 100.00% | 10 |
|  |  | TOP | 6.81E+02 | 100% | 10 |

### HPCG
| Team | GFLOPS | Relative Percent | Final Scaled Score |
| --- | --- | --- | --- |
| UT | 2.41697 | 0.09598006513 | 0.9598006513 |
| KU | 25.182 | 1 | 10 |
| UCSD | 3.17678 | 0.1261528076 | 1.261528076 |
| Aalborg | 24.5444 | 0.9746803272 | 9.746803272 |
| TOP | 25.182 | 100% | 10 |


### Cube20
| Team | Raw Score | Normalize Score | Final Scaled Score (20pts) |
| --- | --- | --- | --- |
| UT | 2058720 | 0.999998057 | 19.99996114 |
| KU | 2058724 | 1 | 20 |
| UCSD | 2058724 | 1 | 20 |
| Aalborg | 2058724 | 1 | 20 |
| Top Raw: | 2058724 |

### Boinc
*tldr: it was real messy*

| Team |  |  |  | Total Credits | Weighted Points | Normalize Score | Final Scaled Score (20pts) |
| --- |  --- |  --- | --- | --- | --- | --- | --- | 
| UT | They got it setup and started running, but no "fraction done" numbers in the submission? |  |  |  |  | 0 | 5 |
| KU | 1256.195928 |  |  |  | 1256.195928 | 0.00000002119401037 | 12 |
| UCSD | Unfortunately did not complete any tasks, but partial completion of several -- equivalent to approximately 2.76 tasks |  |  |  |  | 0 | 7 |
| AAU | 55502843941 | 109586364.5 | 3658840500 |  | 59,271,270,805.56 | 1 | 20 |


### Su2
*this was also messy*

*scores for this one aren't included in the final score*

| Team | Scaling: InvBump | Scaling: OneRAM6 | Scaling: Wedge | Speed: Turb_ONERAM6 | Rank | Speed: Turb_Flat_Plate | Rank | Raw Score | Final Scaled Score (20pts) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| UT | no | no | no | 0 | 4 | 0 | 4 | 0 | 0 |
| KU | yes | yes | yes | 98.736 | 2 | 648 | 2 | 2 | 10 |
| UCSD | yes(OOM) | yes | yes | 7440 | 3 | 7920 | 3 | 1.2 | 3.333333333 |
| Aalborg | yes | yes | yes | 3 | 1 | 8 | 1 | 2.8 | 12.85714286 |
