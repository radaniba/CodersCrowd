# Make your coding errors reproducible

Since CodersCrowd went online, the amount of comments I received to criticize some of its functions and to improve some features were a source of joy for me each time I read my emails. 

At the time I am writing this article, we are more than 1500 users on CodersCrowd, and I wanted first to thank you all to join us for this CrowdCoding experience.

Ok let's get right to the **exciting updates** we have for the last release of CodersCrowd.

The last version of CodersCrowd was released with a very exciting feature : **Running bioinformatics gists live on the browser !!**, ...., Ok let's think about it for a second .. what does it mean ? ..

* Live code debugging
* Being able to reproduce your bugs/results
* Embark your software into a demo mode instead of writing long description pages
* Reimplement algorithms live with coders all over the places
* Code on the move !! You can code from your mobile devices from everywhere
* Create Interactive Tutorials
* Test codes
* and the list is long ... :)


When you open a code to view (review) on your favorite browser, it will be either a problem to be fixed or a valid code shared by a member, you will be able to see that small button below the code :

![](http://coderscrowd.com/blog/images/runnable.png)

That small little button allows users to run the code live and see the exact same message that he would see on a terminal ... it is like you have a terminal in your browser.

In that example in particular, it is a python code that implements Smith Waterman and Needlman Wunsch alignment. I found that code on [Github](https://github.com/alevchuk/pairwise-alignment-in-python/blob/master/alignment.py), tried it and made sure it is working, then I introduced intentionnally some errors inside, in order to see if we can get the correct error message that we would see on a terminal. 

Ok, now ! this is what you will see when you hit the **Run** button :

![](http://coderscrowd.com/blog/images/runerror.png)

Awesome ! A nice Traceback with the exact line where the problem is ! and this is not a Traceback that is simulated, that's the real python's Traceback that you would see when you run the same code on your local machine.

Ok to be honest I introduced 2 errors in the method names (`Neeeedle()` instead of `needle()`, and `waterm()` instead of `water()`), it is a python code, so it stopped at the first bug found and reported the Traceback

Let's push it further, now let's fix the first error and post a solution and see what's the outcome of that :

![](http://coderscrowd.com/blog/images/solution1.png)

Excellent ! It is *partially* working, we can see the diff in the solution posted, and run it directly ! The solution shows another Traceback, that's the second bug, let's fix it and run another solution : And the winner iiiiis ... :)

![](http://coderscrowd.com/blog/images/solution2.png)

Now let's see the entire code review of this example :

![](http://coderscrowd.com/blog/images/coderev.png)

- - - 

###What can we run on CodersCrowd ?

I'd love to answer : pretty much everything you want :) but let's be realistic, but what I am going to list here is already awesome. You can run :

* Perl / Bioperl
* Python / Biopython
* Java / Biojava
* Scipy, Numpy, Matplotlib
* R / Bioconductor
* Shell (awk..)

Yes, I am serious :)

*Only Python and Perl are supported for the test phase though*

***Update : perl, python, shell and R are runnable now***

###Limitations ?

Hmm, yes sure ! Currently codes using arguments are not supported (they run ! but they will output errors), the reason is that I am not yet allowing access to IO on my server. For codes using access to files, I will create demo files covering pretty much the long list of format we use in bioinformatics, under a same location. If you think of a specific format please leave a comment ; 

* Fasta
* Fastq
* Bam/Sam
* Genbank
* alignments formats
* text
* Vcfs
* etc ...

I will make an update with files that you can use as a test for your codes.

###How is that possible ?

The idea of running code on the browser was one of the main important features I wanted to implement at CodersCrowd. First I started with the CrowdCoding aspect of the application, and then I started to look around at how to implement that **BIG CHALLENGE** task of running user's problem online as fast as a microsecond :) something similar to what [JSFIDDLE](http://jsfiddle.net/) is doing for Javascript community. The task was huge, and the challenge was even bigger, until I met [Docker](https://www.docker.io/)

![](http://coderscrowd.com/blog/images/cc_docker.png)

I started to dig deep into their API and succeeded to do what will be (hopefully) of a great help to the community towards code reproducbility and collaborative programming.

I created an initial docker image with basic tools for bioinformatics that I continued to feed with time as some users kept sending code with specific libraries and dependencies (and it is hopefully keep going that way with your help)

> You need to be a member to run codes on CodersCrowd

Runnable code will be accessible only for members since it is still experimental, when we pass the test phase I will update the public access to this feature.

Have fun !!

Rad
