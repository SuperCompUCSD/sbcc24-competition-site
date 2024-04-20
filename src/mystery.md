# Mystery Application <a id="top"></a>
Surprise, there is not only 1 mystery application, there are 2! 

Our first one being [boinc](https://boinc.berkeley.edu/). (which apparently stands for “Berkeley Open Infrastructure for Network Computing”, but I’m not gonna remember that acronym; its pronounced /bɔɪŋk/ – rhymes with "oink"). 

BOINe is a volunteer scientific computing project that allows users to perform computation for a variety of scientific computing projects – projects range from genome sequencing to numerical relativity to prime number calcululations. Take a look [here](https://boinc.berkeley.edu/projects.php) for a list of all of the projects. 

So actually, BOINC is not just one application, but a framework that lets you run any number of them – you get to pick the ones that seem most interesting to you! 

Our Second Mystery App is [Su2](https://su2code.github.io/). While BOINC keeps some portion of your cluster occupied see if you can squeeze in a few SU2 runs. At many supercomputing centers to get access to the really big queues researchers have to demonstrate that their code will scale up too many many nodes. We make them produce a scaling test.

## TOC
 * [Boinc](#boinc)
 * [Su2](#su2)

# Boinc <a id="boinc"></a>

You should look through the [BOINC user manual](https://boinc.berkeley.edu/wiki/User_manual) for details, but I’ll give you some rough ideas of what to do. The goal is to get BOINC projects running on your cluster – the more computation you perform, the more you’ll be rewarded. 

First, install BOINC. There are versions in the repositories of most major distros, but you might not want to use that version! Look at the user manual. This will give you the programs `boinc_client` (which is the main “driver” program, that should be running in the background, also aliased to `boinc` on some distros apparently), `boinccmd`, and command-line interface to perform BOINC tasks, and `boincmgr`, a GUI that does the same (if you do use this, you probably want to switch it to “View -> Advanced Mode”.  

Then, to set up a BOINC project, the general approach is to go to the website of the project and make an account ([boincstats.com](boincstats.com) can help manage multiple accounts for you). Then, in the `boincmgr` GUI, you go to “Add Project”, put in your login credentials, and the project will start giving you tasks (assuming it has some to give), and start crunching! Keep an eye on the `boinc_client` output – it is where any messages are logged. 

Note that it is possible to use `boincmgr` remotely, by following the instructions [here](https://boinc.berkeley.edu/wiki/Controlling_BOINC_remotely). Alternatively, it [is possible](https://boinc.berkeley.edu/wiki/Boinccmd_tool) to use `boinccmd` to run projects from the command line, and configure *many* other things. 

You probably want to run the BOINC projects across several nodes in your cluster. This simply involves running the BOINC client on each of the nodes. It’s up to you how to arrange this – it’s possible to use the GUI `boincmgr`, or use `boinccmd` on each of the machines, or [many more complicated options](https://boinc.berkeley.edu/trac/wiki/GridIntegration) designed for clusters. How you do it is up to you!

Although it is possible to set up BOINC “teams” (i.e. groups of accounts whose credits get reported together), we suggest creating just one account for your team, and sharing the password (since you are all in the same place anyway). That’ll make keeping track of credits easier. 

## Things to think about
- Not all applications will run on all architectures – you should do some research on this (hint: the Science United page lists all of the ones that work on ARM). 
- Run some benchmarks! These might give you some ideas of which applications
    - `boinccmd --host localhost --passwd <password> --run_benchmarks`
    - This will print some information to the `boinc_client` log. These are the results I get on my laptop, but your single board computers will probably be much slower:
```
18-Apr-2024 16:42:46 [---] Benchmark results:
18-Apr-2024 16:42:46 [---]	Number of CPUs: 16
18-Apr-2024 16:42:46 [---]	6135 floating point MIPS (Whetstone) per CPU
18-Apr-2024 16:42:46 [---]	70384 integer MIPS (Dhrystone) per CPU
```
- Note that the floating point MIPS (millions of instructions per second) and integer MIPS are *not the same* – think about your cluster’s architecture, and which projects might be better suited for it. 
- Many applications will take a *looong* time to run. On my laptop, Einstein@HOME apps took ~6 hours, and World Community Grid’s Mapping Cancer apps took ~3 hours. You may want to do some research, or try several different applications before finding one that will be practical – make sure to manage your time and plan ahead! 
- Incidentally, there’s cute OpenGL graphics (the “Show graphics” button in `boincmgr`) 😀

## How it’ll be scored: 
The BOINC project conveniently gives us a measure of credits, which they call [“cobblestones”](https://boinc.berkeley.edu/wiki/Computation_credit).

We will score you on the number of credits earned – the top scoring team will get the full 20 points, every team below that will get proportionately that many points. We’ll also give some (fixed) extra points just for getting BOINC running and starting to work on a project, even if you don’t successfully manage to finish a full “work unit”. 

## What to submit!
Ideally, you’d just tell us your team username for a site like [BoincStats](https://www.boincstats.com/) or [ScienceUnited](https://scienceunited.org/su_home.php) (both of which are “login managers” for all of the BOINC projects, and let you see a given user’s overall stats), and we could just see the total number of credits accrued. To make our lives even easier, you could upload a screenshot showing your total number of credits. 

*Unfortunately*, I am aware that linking your accounts to these various websites is rather finicky (it took me an embarrassing amount of time), and I don’t need you wasting time on that kind of thing, so we are willing to accept the full output of `boinccmd --get_project_status` (and we’ll just add up the relevant values ourselves). 

## Conclusion
And lastly, have fun!! You have the freedom to learn about projects in *almost any area of science or mathematics you might be interested in!* So go forth, learn about them, and come back and tell us all the cool stuff you found out!
<br><sub>For more questions please ask Ritoban Roy-Chowdhury accessible in person or at rroychowdhury@ucsd.edu pertaining to Boinc</sub>

[Back to Top](#top)

# Su2 <a id="su2"></a>

While BOINC keeps some portion of your cluster occupied see if you can squeeze in a few SU2 runs. At many supercomputing centers to get access to the really big queues researchers have to demonstrate that their code will scale up too many many nodes. We make them produce a scaling test.

We would like you to run a number of the tutorial examples in [SU2](https://su2code.github.io/). The tutorials repository can be found here: [https://github.com/su2code/Tutorials.git](https://github.com/su2code/Tutorials.git)

We would like you to produce scaling tests for the following core-counts: `1,2,4,8,12,16,32,64,128` (stop when your cluster runs out of cores). If you have time fill in some of the gaps to keep populating the graph. If your cluster has GPUs you can do increments of whole GPUs (instead of individual cores).

The following scaling tests are required:
```
Inviscid_Bump
Inviscid_ONERAM6
Inviscid_Wedge
```

The application appears to have some methods for tracking time internally but your amazing (speaking for myself: not-so-amazing) committee couldn't make it work - welcome to computing - there's always some part that doesn't work just quite right. Extra credit awarded to anyone who gets the `SCREEN_OUTPUT=  WALL_TIME` working. For everyone else there is the Linux `time` command or write a wrapper script around your launch command that snapshots the date command before and at the end of your runs.

The requirement is to produce a spreadsheet with the following columns:

`total cores (-n) | nodes (-N) | runtime | command executed`

(if a machines-file applies, upload and link)

Please provide a single upload of `history.csv`, `restart_flow.dat` and any `*.vtu` files - they should all match for each run.

Following this you are required to run (one short, one long) and using a wrapper script that saves the output of the "data" command before the run and after the run completes.
```
Turbulent_ONERAM6
Turbulent_Flat_Plate
With the following modifications to the config file:

      turb_SA_flatplate.cfg
      % Epsilon to control the series convergence
      CONV_CAUCHY_EPS= 1E-6
      Change the above to read:
      CONV_CAUCHY_EPS= 1E-5

      turb_ONERAM6.cgf
      % Epsilon to control the series convergence
      CONV_CAUCHY_EPS= 1E-8
      Change the above to read:
      CONV_CAUCHY_EPS= 1E-12
```

upload of `history.csv`, `restart_flow.dat` and any `*.vtu` files and provide your timing via whatever method you use to capture it (if its using "`time`" do not forget to actually add before you start a serious run - don't ask us how we know).

None of the scaling-test runs `(Inviscid_[Bump|Wedge|ONERAM6])` should take longer than 30mins so if your solutions are not ever converging consider an error and rather cancel a job than end up with jobs that never converge. Half the points are awarded for fully populating the curve no matter how fast your jobs run. Extra points can be scored for noting any of the artifacts that we expect to find and a brief comment on why you think that they occur.

Finally, the turbulence flows will award points for fastest time to convergence (while using the specified convergence values above). If you are forced to cancel either of the turbulence runs early for any reason - saving out the last line, specifically the iteration number along with your time

e.g:
```
|        1095|  7.7166e-01|   -8.955272|  -10.731343|    0.251469|    0.015833|
       ^this^
```
would get you partial credit (higher number is better) if no team completes these runs.
<br><sub>For more questions please ask Nick Thorne accessible in person or at nthorne@tacc.utexas.edu pertaining to Su2</sub>

[Back to Top](#top)

