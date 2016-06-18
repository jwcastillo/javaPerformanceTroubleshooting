# Let's Play Performance Golf!  FORE!
```
NEW!  Support for MS-Windows.
Now you can performanceGolf from MS-Win, Mac, or Linux!
```


## Motivations
This is a crowd-sourced approach to easier and better performance troubleshooting.  Performance problems are everywhere, so java technicians need access to easy-to-use diagnostic tools at every step of the SDLC.

## How to play?

1. Start by [installing](https://github.com/eostermueller/performanceGolf/wiki/Install-and-Run) the live demonstrations of Java Performance Problems in this repo.

2. Pick one of the six holes of golf to play.  You can do this by picking one of the six numbered folders in the repo.  For example, ```02_secondHole```.

3. One at a time, run the 'a' load test and the 'b' load test for the hole you selected.  The a & b tests are two different implementations of the same REST/SOA service.  See [instructions](https://github.com/eostermueller/performanceGolf/wiki/Install-and-Run) (same link as above) for how to run the tests.  

4. Compare the performance of the two tests, a & b.  Which has better response time / throughput?  

5. Using the least amount of tooling/instrumentation, identify the performance problem of the slower test.  Hook it up your self and run the tests.  These [TCP Port numbers and other info](https://github.com/eostermueller/performanceGolf/wiki/Environment)  will be helpful when troubleshooting.

6. At ```codegolf.stackexchange.com```, there is one "Stack Exchange Challenge" for each hole of golf.  [Please upvote this stackexchange.com 'meta challenge'](http://meta.codegolf.stackexchange.com/questions/2140/sandbox-for-proposed-challenges/9381#9381) to provide the approval for a full-blown challenge.  Post the following two things for your solution to that challenge:
  * Post a description of the tools/techniques you used to detect the performance problem.  Must be detailed enough so that others can reproduce your work.
  * Tally the number of strokes for your approach, using the "Scorecard" below.  All solutions must specify the # of strokes incurred.

7. Upvote the solutions that best identify the performance problem __and__ have the fewest strokes (see Scorecard, below).  Similar solutions on different platforms (Mac/Linux/MS-Win) deserve roughly the same number of upvotes.


## Scorecard
This scorecard determines the approach with the least amount of tooling/instrumentation.  Lowest score wins!  

* 1 stroke if JVM restart is required to hook up your monitoring tool of choice.
* 1 stroke for any tool with any $$ licensing cost.
* 1 stroke for every separate install process. No strokes for JVM and pre-installed OS tools. 
* 1 stroke for tools/techniques specific to a particular Database vendor.  Ex: Oracle AWR report.  Even ‘EXPLAIN PLAN’ solutions are proprietary.

## Example One -- zero strokes :-D
This example does not use this github repo, but it will give you the general idea.


[This solution](http://www.nurkiewicz.com/2012/08/which-java-thread-consumes-my-cpu.html) to solving a high CPU problem would get lowest=best instrumentatin score:  zero strokes.  Only JVM and OS tools are used (thread dump and top -H).  There are no tool license costs and a JVM restart was not required for the thread dump.

## Example Two -- 4 strokes :-(
This example also does not use this github repo, but it will give you the general idea of what we mean by the best troubleshooting with the least tooling/instrumentation.


A modern, commercial profiler (YourKit, JProfiler, etc...) would easily solve the high CPU problem in example 1.  But look how many strokes (1+1+1+1=4!) are taken off with this approach:
  * 1 stroke because a JVM restart is required to hook up the tool
  * 1 stroke because profilers are generally tools with so much overhead that few operate in a live production environment
  * 1 stroke because there are licensing costs.
  * 1 stroke to install profiling the tool
