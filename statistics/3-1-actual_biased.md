[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

```
# import data and generate pmf
from probability import BiasPmf
import thinkstats2
import thinkplot
import nsfg

resp = nsfg.ReadFemResp()

actual = thinkstats2.Pmf(resp['numkdhh'], 'Actual')
survey = BiasPmf(actual, 'Survey Bias')

# plot pmf
thinkplot.PrePlot(2)
thinkplot.Pmfs([actual, survey])
thinkplot.Show(xlabel='Kids in Household', ylabel='PMF')

#calculate means
sum=0
for k,v in actual.Items():
	sum+= k*v
	i+=1
print(sum)

survey_sum=0
for k,v in survey.Items():
	survey_sum+=k*v
	i+=1
print(survey_sum)
```

