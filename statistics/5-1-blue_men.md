[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> Approximately 34% of U.S. males fit this range.  
```python
import scipy.stats

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

def in_to_cm(x):
    return x/0.393701

low = in_to_cm(5*12+10)
high = in_to_cm(6*12+1)

print(dist.cdf(high)-dist.cdf(low))
```
