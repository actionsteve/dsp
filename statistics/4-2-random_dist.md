[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> The PMF makes sense. Each randomly selecte value is unlikely to be a duplicate and therefore has an equal probability (prob=0.0010) of being selected.  
>> The CDF is approximately a straight line with a slope of 1, so about x% of the data we randomly generated will be below the x^th percential (for any x we choose). This, the distribution is uniform.  
```python
import numpy as np
import thinkstats2
import thinkplot

rands = np.random.random(1000)

pmf = thinkstats2.Pmf(rands)
cdf = thinkstats2.Cdf(rands)

thinkplot.PrePlot(1, cols=2)
thinkplot.Pmf(pmf, linewidth=0.1)
thinkplot.Config(xlabel='Random variate', ylabel='PMF')

thinkplot.PrePlot(1)
thinkplot.SubPlot(2)
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel='Random variate', ylabel='CDF')

# PMF makes sense; each randomly selected value is unlikely to be a duplicate
# and therefore has an equal probability (p=0.0010) of being selected.
#
# CDF is approximately a straight line with a slope of 1, so about x% of
# the data we randomly generated will be below the x^th percentile, for any x.
# Thus, the distribution is uniform. The following snippet confirms this slope
# is usually not far from 1 for values in [0.01, .99]:
#
# print([(cdf.Prob(x)/x) for x in [x/100 for x in range(1, 100)]])
```
>> The following snippet confirms this slope is not usually far from 1 (y=x) for values in the range [0.01, .99]:  
```python
print([(cdf.Prob(x)/x) for x in [x/100 for x in range(1, 100)]])
```
