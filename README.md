# Project-Algorithms
Computational thinking with algorithms module, this is the final project where I time, plot and comment five sorting algorithms.

## Getting started
### Installing
Since I have used libraries like *NumPy* and *matplotlib* I recommend you to install *Anaconda* to make sure that you will be able of running the code without any kind of issues. If you needed it, you can download it [here](https://www.anaconda.com/download/)


## Content
Through a python app via Jupyter Notebook I have choosen a simple comparison-based sort, Insertion sort; an efficient comparison-based one, Merge sort; a non-comparison one: Counting sort: Cycle sort, another comparison-based sort which is efficient for any other in-place sorting technique. Lastly, Gnome sort completes the list of algorithms to be analyzed and compared in this README.md file.

## Python app
In order to generate the problem arrays I used a numpy random function and within a for loop
they were automatically generated for every input size as a dictionary, being the keys the input size
and their value the numpy arrays themselves.
Then the algorithms taken from different sources were entered in the Jupyter Notebook as well as a
loop which calls one of them to prepare the CPU before timing them.
Again, I turned to a loop to time the executions by iterating through the dictionary which contains
the problem arrays. Every loop calls all five algorithms per one input size. Every execution time (s)
was appended to an array, one array per algorithm.
When calculating the average of the 10 execution times per algorithm and input size I created a new
dictionary (avgTimes{}) with the intention of having the data generated more separate and tidier.
This way every key represents the average execution time from one of the algorithms per input size.
And in order to display the output with a nice format I used a pandas data frame. All
figures are shown in seconds and formatted to display just 3 floating points.

Finally I plotted the figures with matplotlib converting seconds into milliseconds as per Professor's request and setting specific features to achieve a more visual output.

During the implementation of this app I learnt things like a varialbe which stores an array needs to be referenced with copy.deepcopy() in case we need to keep its original value (like the order of its elements after passing it through an algorithm a number of times). I also learnt what dictionaries are, I wanted to automate the generation of variables and this abstract data type played a role in the app.

Timing the algorithms returned some 0.0 marks for the smallest input sizes reason why I tried to
get nanosecond precision by using time_ns() but that didn’t execute properly despite it is included
within python.

On the other hand, considering the results it is no surprise the shape of the plot lines in relation to
the algorithm they represent. Two of them are quite flat, Counting sort and Merge sort, and the
other three get much steeper, especially for the biggest input sizes the increment of execution time
is outstanding. And that is similar to what a quadratic time should look like, which is a feature of
these three algorithms, at least in the worst and average cases, the most common scenarios in
practice.

Although, on a closer look I became more aware of the execution time difference between Merge
sort and Counting sort. And also the difference between these two and the other three was even
more obvious.

Finally Counting sort and Merge sort show they are much less affected by the input size. With n + k
and n log n times respectively, Merge sort plot is above Counting sort one, which is the expected
outcome.

Looking at these facts makes an obvious difference when it comes to identifying certain properties
and applications of these algorithms.

And as an extension in the visualization area of this project, I think it is worth looking at the
consistency of the execution time between algorithms. The last plots show every single
execution time before getting the averages, represented with a dot. The right half of the plot makes obvious the increase of execution time per input size increment.

Each group of 10 dots represents the execution time of every input size for the slowest algorithms
(or at least the ones affected by input size in a greatest way): Insertion, Cycle and Gnome sort.
Then, considering each n group is represented by nearly horizontal lines of dots I could set out that
the execution is fairly consistent. Just one or two dots per n group seem to be slightly off the line.
And one particular thing that catches my eye, for n group 12 (n = 8750) Gnome sort and Cycle sort
dots seem to be mirrored. Note the small arrow that points at them.

Just as I took a closer look at the main plot, so too I checked the fastest algorithms closer. And this
shows a bigger variability between the execution times of Merge sort if we compare them with
Counting sort ones, especially for the greatest input sizes. It may not be something really significant
but rather something to note.

## References

Source | Link
-------|-----
Insertion Sort| https://interactivepython.org/courselib/static/pythonds/SortSearch/TheInsertionSort.html 
Merge Sort | https://www.geeksforgeeks.org/merge-sort/ 
Counting Sort |  https://www.sanfoundry.com/python-program-implement-counting-sort/  
Cycle Sort | https://www.geeksforgeeks.org/cycle-sort/
*Scatter plot adaptation | https://pythonspot.com/matplotlib-scatterplot/ 
Gnome Sort | https://www.geeksforgeeks.org/gnome-sort-a-stupid-one/ 

### Other sources:

- P. Mannion (2019). Sorting Algorithms Lectures 8 - 10. Galway-Mayo Institute of Technology.
- G. Heineman, G. Pollice, S. Selkow. (2015) Algorithms in a nutshell. O’Reilly Media, Inc.
- M. Goodrich, R. Tamassia, M. Goldwasser. (2013) Data Structures & algorithms in Python.
Chapters 3 & 4. John Wiley & Sons, Inc.
- D. Harel, Y. Feldman. (2004) Algorithmics, the spirit of computing. 3rd Edition, Chapter 5. Pearson
Education Limited.

- Websites:
http://scanftree.com 
https://stackoverflow.com 
https://www.khanacademy.org 
https://softwareengineering.stackexchange.com
https://www.hackerearth.com 
