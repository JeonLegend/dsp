[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

import nsfg

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

# Comparing mean weights of first babies and other babies
firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean() 

Result: (7.201094430437772, 7.325855614973262) # First babies are lighter than others

# function for Cohen's d
def Cohens(group1, group2):
  diff = group1.mean() - group2.mean()
  
  var1 = group1.var()
  var2 = group2.var()
  
  n1, n2 = len(group1), len(group2)
  
  pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
  d = diff / (pooled_var ** (1/2))
  
  return d
 
Cohens(firsts.totalwgt_lb, others.totalwgt_lb)

Result: -0.088672927072602
