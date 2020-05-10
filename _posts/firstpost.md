---
title: "SPARC Research Pt. 1: Intro"
date: 2020-05-09
categories:
- Blog
- Background Info
---

So this is a bit of a complicated post to write. So much of what I did at SPARC Research is covered by arms regulation that I can only go into detail about a limited subset of the things I did there. I'm going to attempt to write just a bit about the kinds of technologies I used and how I used them.

I got the job at SPARC basically by accident. A classmate in my community college physics course came over to my lab table and said, "You're a programmer, right?". I guess he had overheard me talk about the CS professors or something like that and the company he worked for just so happened to need help with writing software. I said yes, and that's basically how I got the job. 

I didn't really know what to expect, but I honestly expected there would be more structure. That's not to say that SPARC was unorganized, but it was a startup. As a result, there were a lot of tasks and things that no one really knew who should do them. And no one really knew all that much about software or writing code outside of MATLAB, which is a horrible awful no good very bad thing.

So in the first few days I realized that the basic job was to write a GUI for a very old piece of Fortran code that simulated missiles. When I realized this, I was incredibly excited. I had played a lot of KSP and honestly this was the time I realized that I'd be doing real-world rocket science. 

We set about trying to get started on this GUI and it was a heck of a job from the start. The Fortran code we were working with had an arcane input format that basically consisted of a text file with different formatting based on which section you were in and what was needed from a particular part of the software. The first thing I did was to build an object oriented model of the input file for the program and write methods to serialize all the different parts of the file and generate a valid input to our simulation program. That took a few days, most of which was spent reading documentation from the 1980s on the file format.

Once we were able to generate input files, we started working on an actual GUI. It had been decided before I got there that we would use Tkinter, which in many ways is a terrible choice for this kind of project. If the target audience were other software engineers, it would've been fine, but we had to package up our GUI in such a way that an aerospace engineer with no knowledge of python or virtual environments or anything like that could manage to install all the required dependencies and run the software with a minimum of hassle.

We ended up using PyInstaller for this, a difficult package to use even if you know a fair bit about the internals of python and its packaging system, but we knew none of that. We ended up with a whole pile of different versions of our dependencies, testing which ones already had all the appropriate hooks and things to make PyInstaller function without too much extra manual work. Eventually we got it all packaged up and our boss was able to work with the software and create his own simulation models for the contracts we worked on while I was there, but it was no short road to get there.

---

Next time I'll continue with some of the automation tools we used and how we went about building the actual GUI portion of the software.