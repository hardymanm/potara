[![Build Status](https://travis-ci.org/sildar/potara.svg?branch=master)](https://travis-ci.org/sildar/potara)
[![Coverage Status](https://coveralls.io/repos/sildar/potara/badge.png?branch=master)](https://coveralls.io/r/sildar/potara?branch=master)

# Basics

Potara is a multi-document summarization system that relies on Integer
Linear Programming (ILP) and sentence fusion.

Its goal is to summarize a set of related documents.
It proceeds by fusing similar sentences in order to create sentence
that are either shorter or more informative than those found in the
documents.
It then uses ILP in order to choose the best set of sentences, fused
or not, that will compose the resulting summary.

It relies on state-of-the-art approaches introduced by Gillick and
Favre for the ILP strategy, and Filippova for the sentence fusion.

# How To

Basically, you can use the following

```
s = Summarizer()
print("Adding docs")
s.setDocuments([document.Document('pathtofilenumber' + n)
       for i in range(1,11)])
print("summarizing")
s.summarize()
print(s.summary())
```

There's some preprocessing involved and a sentence fusion step, but I
made it easily tunable.

#WINDOWS requirements (Modified on 1/4/16)
Tested on Windows 7 64 bit Python 2.7.9

1.Install GLPK for windows
2.Edit the file pulp.cfg.win and point your glpk solver under the GLPK section.
3.Set JAVAHOME in your windows environment to point to your java.exe
4.install all the potara's requirements using requirements_win.txt
5.install potara using python setup.py install
