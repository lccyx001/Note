# How to use make

## What is make

Make is a tool which used to make files, but make itself doesn't know how to do this.By using a config file called Makefile or using parameter -f , you can let make know how to finish this job.That means you should write down rules in Makefile.

## Makefile's structure

```make
<target> : <prerequisites> 
[tab]  <commands>
```
