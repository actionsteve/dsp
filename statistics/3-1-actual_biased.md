[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> Actual mean 1.02420515504  
>> Biased mean 2.40367910066  
![3.1pmf](img/TS3-1.png)
```python
import nsfg
import thinkstats2
import probability
import thinkplot

df = nsfg.ReadFemResp()

pmf = thinkstats2.Pmf(df.numkdhh, label='actual')
biased_pmf = probability.BiasPmf(pmf, label='biased')

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Config(xlabel='Number of children under 18 in household', ylabel='PMF')

print('Actual mean', pmf.Mean())
print('Biased mean', biased_pmf.Mean())

```
