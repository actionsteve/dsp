[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> d_wgt:  -0.088672927072602  
>> First babies are lighter than others.  
>> The effect size is  very small.  

>> d_prglngth:  0.028879044654449883. 
>> First babies take longer than others.  
>> The effect size is  very small.  

>> The effect size of weight is stronger than pregnancy length.  

```python
import nsfg
import math

df = nsfg.ReadFemPreg()

live = df[df.outcome == 1]
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

firsts_wgt = firsts.totalwgt_lb
others_wgt = others.totalwgt_lb

firsts_prglngth = firsts.prglngth
others_prglngth = others.prglngth

def cohen_effect_size(group1, group2):
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d

def desc_effect(d):
    """From <https://en.wikipedia.org/wiki/Effect_size#Cohen.27s_d>, we have
    the following descriptions of Cohen's Effect Size:
        
    Very small    0.01
    Small         0.20	
    Medium	     0.50
    Large	     0.80
    Very large    1.20	
    Huge	         2.0
    """
    if abs(d) < 0.2:
        return 'very small.'
    if abs(d) < 0.5:
        return 'small.'
    if abs(d) < 0.8:
        return 'medium.'
    if abs(d) < 1.2:
        return 'large.'
    if abs(d) < 2.0:
        return 'very large.'
    return 'huge.'

def main():
    d_wgt = cohen_effect_size(firsts_wgt, others_wgt)
    d_prglngth = cohen_effect_size(firsts_prglngth, others_prglngth)
    
    print('\nd_wgt: ', str(d_wgt))
    if d_wgt > 0:
        print('First babies are heavier than others.')
    elif d_wgt < 0:
        print('First babies are lighter than others.')
    else:
        print('First babies weight the same as others.')
    print('The effect size is ', desc_effect(d_wgt))

    print('\nd_prglngth: ', str(d_prglngth))
    if d_prglngth > 0:
        print('First babies take longer than others.')
    elif d_prglngth < 0:
        print('First babies take shorter than others.')
    else:
        print('First babies take the same time as others.')
    print('The effect size is ', desc_effect(d_prglngth))

    if abs(d_wgt) > abs(d_prglngth):
        print('\nThe effect size of weight is stronger than pregnancy length.')
    elif abs(d_wgt) < abs(d_prglngth):
        print('\nThe effect size of pregnancy length is stronger than weight.')
    else:
        print('\nThe effect sizes of weight and pregnancy length are equally strong.')

if __name__ == '__main__':
    main()
```
