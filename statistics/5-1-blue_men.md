[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)
```
from scipy.stats import norm
u = 178
std = 7.7

minimum = (5 * 12 + 10) * 2.54
maximum = (6 * 12 + 1) * 2.54

print(norm.cdf(maximum, loc=u, scale=std) - norm.cdf(minimum, loc=u, scale=std))
```
Approximately 34.27% of the Us male population is within the range of 5'10'' and 6'1''.
