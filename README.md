# Biomedical Data Science Workshop & Careers Panel

This repository contains the slides, recordings, and tutorials for the July 18, 2022 Biomedical Data Science Workshop & Careers Panel (a satellite event of the [Lange Symposium](https://compmed.ucla.edu/annual-lange-symposium-biomathematics)).

This event is sponsored by  

- UCLA Department of Computational Medicine  
- National Human Genome Research Institute (NHGRI)  
- National Science Foundation  
- American Statistical Association - Statistical Computing Section

## Syllabus

### Module 1: Data Science in Action, 1pm-3pm
[Video Recording](https://youtu.be/gBHijDki6aQ)
| Time | Topic | Presenter |  
|:-----------|:------------|:------------|  
| 1:00-1:15 | Introduction \[[html](https://langesymposium.github.io/2022-July-Workshop/module1-01-intro/module1-01-intro.html)\] | Dr. Hua Zhou |  
| 1:15-1:45 | R \[[html](https://langesymposium.github.io/2022-July-Workshop/module1-02-R/module1-02-R/module1-02-R.html)\] | Dr. Xiaoqian Liu |  
| 1:45-2:15 | Python \[[html](https://langesymposium.github.io/2022-July-Workshop/module1-03-Python/module1-03-Python.html)\] | Dr. Seyoon Ko |  
| 2:15-2:45 | Julia \[[html](https://langesymposium.github.io/2022-July-Workshop/module1-04-Julia/module1-04-Julia/module1-04-Julia.html)\] | Dr. Hua Zhou |  
| 2:45-3:00 | Q&A, exercises | Participants |  

### Module 2: Data Exploration Tools Using Julia, 3:30pm-5:30pm
[Video Recording](https://youtu.be/hdxiVKI4r60)
| Time | Topic | Presenter |  
|:-----------|:------------|:------------|  
| 3:30-3:45 | Introduction | Dr. Hua Zhou |  
| 3:45-4:15 | Easy manipulation of genetic variant data \[[html](https://langesymposium.github.io/2022-July-Workshop/module2-01-GeneticVariantData/module2-01-GeneticVariantData.html)\]| Dr. Seyoon Ko |  
| 4:15-4:45 | High-performance genomic data visualization using [GeneticsMakie.jl](https://github.com/mmkim1210/GeneticsMakie.jl) \[[html](https://langesymposium.github.io/2022-July-Workshop/module2-02-GeneticsMakie/module2-02-GeneticsMakie.html)\] | Dr. Minsoo Kim |  
| 4:45-5:15 | Practicing Reproducible Data Science in Julia \[[html](https://langesymposium.github.io/2022-July-Workshop/module2-03-DataDeps/module2-03-DataDeps.html)\] ([DataDeps.jl](https://openresearchsoftware.metajnl.com/article/10.5334/jors.244/))| Dr. Alfonso Landeros |  
| 5:15-5:30 | Q&A, exercises | Participants |

### Module 3: Career Panel with Data Scientists, 5:30pm-6:30pm

Moderator: Dr. Eric Sobel. 

Panelists:   

  - [Kevin Keys](https://www.lathisms.org/calendar-2021s/kevin-l-keys), PhD - Scientist II, Ambys Medicines.
  
  - [Roch Nianogo](https://ph.ucla.edu/faculty/nianogo), PhD - Professor, UCLA.

  - [Christina Ramirez](https://ph.ucla.edu/faculty/ramirez), PhD - Professor, UCLA.

  - [Emma Zohner](https://engine1.com/team/emma-zohner), PhD - Principal Data Scientist, Engine No. 1.

## How to run the optional tutorials using Jupyter Notebooks

During the workshop you may run the optional tutorials on our server. We do **not** recommend running the tutorials on your own laptop during the workshop, because your software environment (OS, software versions, package versions, etc.) may be quite different from ours. If you want to run Jupyter Notebooks on your own machine after the workshop, simply *git clone* [https://github.com/LangeSymposium/2022-July-Workshop.git](https://github.com/LangeSymposium/2022-July-Workshop.git) to sync the most recent course materials to your computer and install all needed software. At the workshop you will receive the connection details. The tutorials use the [MIMIC](https://mimic.mit.edu/) data set. If you wish to use this data for practice, or to use in your own research, you may request access by following the instructions at:
https://mimic.mit.edu/docs/gettingstarted/

### Tips

1. Anytime during the workshop, feel free to ask for help. 

    Course assistants: 
    - Brendon Chau  
    - Dr. Ben Chu  
    - Dr. Sarah Ji  
    - Dr. Seyoon Ko  
    - Dr. Alfonso Landeros  
    - Dr. Xiaoqian Liu  
    - Do Hyun Kim     
    - Tomoki Okuno  
    - Dr. Jeanette Papp  
    - Dr. Eric Sobel  
    - Dr. Hua Zhou  
    - Dr. Jin Zhou  
    - Xinkai Zhou  
    
2. In JupyterLab, avoid running many kernels at the same time. Promptly shut down the kernels you don't use. 

3. If your kernel dies, most likely you have used more resource than allocated (1 CPU core and 3.6 GB memory). Make sure that you shut down the kernels not in use and try again. Remember that running the tutorials is optional. You can always read the static slides if the server is not responding. We plan to make the workshop materials available to you after the workshop, so you can try again later.
