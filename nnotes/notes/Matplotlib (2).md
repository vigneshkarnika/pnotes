---
attachments: [Clipboard_2021-03-25-08-01-53.png, Clipboard_2021-03-25-09-17-17.png, Clipboard_2021-03-25-09-22-34.png]
tags: [programming]
title: Matplotlib
created: '2021-03-23T15:24:24.487Z'
modified: '2021-03-28T02:29:16.033Z'
---

# Matplotlib

```py
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
x=np.linspace(1,10,30)
#y=np.linspace(2,3,10)
y=x**2
plt.plot(x,y)
```

### Funtional
```py
plt.plot(x,y)
plt.show() # not required fro jnotebook- in jnotebook outcell will be removed stringg vs print("string")
```

### color and line style

```py

plt.plot(x,y,"r.")
```
![](@attachment/Clipboard_2021-03-25-08-01-53.png)


```py
plt.plot(x,y,"r.")
plt.xlabel("time")
plt.ylabel("speed")
plt.title("rocket")
plt.show()
```

### Subplots
```py
plt.subplot(1,2,1) # rows,cols,and index which should plt
plt.plot(x,y,"r.")
plt.xlabel("time")
plt.ylabel("speed")
plt.title("rocket")
plt.subplot(1,2,2)
plt.plot(x,y,"r.")
plt.xlabel("time")
plt.ylabel("speed")
plt.title("rocket")
plt.show()
```


## Object oriented

```py
fig=plot.figure()
ax1=plot.axes([0,0,1,1])
ax2=plot.axes([0.1,0.7,0.2,0.2])
ax1.set_xlabel("time")
ax1.set_ylabel("speed")
ax1.set_title("rocket")
ax1.plot(x,y)
ax2.plot(y,x)
```


![](@attachment/Clipboard_2021-03-25-09-17-17.png)

```py

fig,axis=plot.subplots(nrows=2,ncols=2)
plot.tight_layout()
```
![](@attachment/Clipboard_2021-03-25-09-22-34.png)

```py
axes[0][1].plot(x,y)
axes[1][0].plot(y,x)

# fig size and dpi

fig=plt.figure(figsize=(3,2))

fig.savefig('mpic',dpi=300)
ax.plot(x,y,color='purple',lw=3,ls='-',marker='o',markersize=20,markerfaceccolor='yellow',markeredgewidth=3,markeredgecolor='green')
```
