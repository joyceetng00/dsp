[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)
```
import thinkstats2
import thinkplot
import nsfg
import math

preg=nsfg.ReadFemPreg()
first=preg[preg.birthord==1]
other=preg[preg.birthord!=1]

fh=thinkstats2.Hist(first['totalwgt_lb'].apply(lambda x:round(x,0)),label='First Child')
oh = thinkstats2.Hist(first['totalwgt_lb'].apply(lambda x: round(x,0)), label='Other Children')

wd = 0.45
thinkplot.PrePlot(2)
thinkplot.Hist(fh, align='right', width = wd)
thinkplot.Hist(oh, align='left', width = wd)
thinkplot.Show(xlabel='Birth Weight (lb)', ylabel='Frequency')


# calculate Cohen's D
fm = first.totalwgt_lb.mean()
om = other.totalwgt_lb.mean()
wgtco = thinkstats2.CohenEffectSize(first.totalwgt_lb, other.totalwgt_lb)
lgtco = thinkstats2.CohenEffectSize(first.prglngth, other.prglngth)
effectmag = math.fabs(wgtco / lgtco)

print('First Child Mean Weight (lb): ', fm)
print('Other Children Mean Weight (lb): ', om)
print('Cohen Effect Size: ', wgtco)
print('The effect size on weight is %.3f times that of on pregnancy length.' % effectmag)
```
The calculated Cohen effect size is 0.089. The effect size on weight of first-borns is 0.081 times that of non-first born children. The mean weight of first-borns is 7.2lbs, compared to the weight of other children at 7.32lbs. 
