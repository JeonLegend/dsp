[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

```
pmf = thinkstats2.Pmf(resp.numkdhh, label='actual)

def biasedPmf(pmf, label):
    new_pmf = pmf.Copy(label = label)
    for x, p in pmr.Items():
        new_pmf.Mult(x,x)
    new_pmf.Normalize()
    return new_pmf
    
biased_pmf = biasedPmf(pmf, label = 'observed')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, new_pmf])
thinkplot.Show(xlabel='numkdhh', ylabel='PMF')

print('Actual mean', pmf.Mean(), '\nBiased mean', new_pmf.Mean())
```
__Actual mean__ 1.024205155043831
__Biased mean__ 2.403679100664282
