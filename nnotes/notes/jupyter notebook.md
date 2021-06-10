---
tags: [editor]
title: jupyter notebook
created: '2021-03-21T13:52:37.699Z'
modified: '2021-03-21T15:04:29.405Z'
---

# jupyter notebook


- Go to the folder 
```bash
jupyter notebook
```
- new > python3 creates new notebook
- change file name

notebook has 2 modes
- command mode(esc)
- edit mode (enter and go inside cell and click)


- cmd+enter - run and stay
- option+enter = run and insert and select new line
- shift+ enter = run and go to new line without selecting

run all

- x to delete

- A = insert new cell above
- B = insert new cell below


- Y = celltype= code
- M = celltype= markdown

running inline terminal command
```bash
!ls -la
```

This notebook also comes with bunch of built in commands  that starts with
%(line magics) or %%(entire cell - cell)

```bash
%lsmagic
```

```bash
Available line magics:
%alias  %alias_magic  %autoawait  %autocall  %automagic  %autosave  %bookmark  %cat  %cd  %clear  %colors  %conda  %config  %connect_info  %cp  %debug  %dhist  %dirs  %doctest_mode  %ed  %edit  %env  %gui  %hist  %history  %killbgscripts  %ldir  %less  %lf  %lk  %ll  %load  %load_ext  %loadpy  %logoff  %logon  %logstart  %logstate  %logstop  %ls  %lsmagic  %lx  %macro  %magic  %man  %matplotlib  %mkdir  %more  %mv  %notebook  %page  %pastebin  %pdb  %pdef  %pdoc  %pfile  %pinfo  %pinfo2  %pip  %popd  %pprint  %precision  %prun  %psearch  %psource  %pushd  %pwd  %pycat  %pylab  %qtconsole  %quickref  %recall  %rehashx  %reload_ext  %rep  %rerun  %reset  %reset_selective  %rm  %rmdir  %run  %save  %sc  %set_env  %store  %sx  %system  %tb  %time  %timeit  %unalias  %unload_ext  %who  %who_ls  %whos  %xdel  %xmode

Available cell magics:
%%!  %%HTML  %%SVG  %%bash  %%capture  %%debug  %%file  %%html  %%javascript  %%js  %%latex  %%markdown  %%perl  %%prun  %%pypy  %%python  %%python2  %%python3  %%ruby  %%script  %%sh  %%svg  %%sx  %%system  %%time  %%timeit  %%writefile

```
```bash
%pwd
%matplotlib inline
```

```python
import matplotlib
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
t = np.arange(0.0, 2.0, 0.01)
s = 1 + np.sin(2 * np.pi * t)

fig, ax = plt.subplots()
ax.plot(t, s)

ax.set(xlabel='time (s)', ylabel='voltage (mV)',
       title='About as simple as it gets, folks')
ax.grid()

fig.savefig("test.png")
plt.show()
```
```bash
%%html
%%bash
%%javascript
%%timeit
```
tab for suggestions
shift+tab - suggestions+ description

l - show line numbers


