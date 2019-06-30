[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```
sample = np.random.random(size=1000)
pmf = thinkstats2.Pmf(sample)
thinkplot.Pmf(pmf)
```

```
cdf = thinkstats2.Cdf(sample)
thinkplot.Cdf(cdf)
```
CDF distribution is __uniform__
