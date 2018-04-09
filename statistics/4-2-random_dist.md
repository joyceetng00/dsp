[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```
import thinkstats2
import thinkplot
import random

rand = []

for i in range(1000):
    rand.append(random.random())
    
rp = thinkstats2.Pmf(rand, label='random.random pmf')
rc = thinkstats2.Cdf(rand, label='random.random cdf')

thinkplot.Pmf(rp)
thinkplot.Show(xlabel='Value', ylabel='Probability')
```

The PMF shows that the numbers generated in the range of random.random() have a uniform selection. The CDF shows that the  probability of the value increases linearly with the range. 

