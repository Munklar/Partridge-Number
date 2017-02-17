Analysis of N=8 solutions:

All of my findings are based on results generated by the various routines in "postproc.py". It's pretty shabby code written with the assumption that it only needs to run once. (Sorry.)

One thing I wanted to figure out was if tiles of a particular size tended to fall in particular locations. The (not very interesting) answer can be found in a text file called "tile-dist.txt" that shows the average tile value for each position in the board. The range of tile values is pretty small across all tile locations: it's 7.27722984563 at maximum and 6.0541380789 at minimum. 

Another question I had was whether there were any disallowed locations for the 1x1 tile (aside from the two rows and columns next to the edges (obviously)). A text file called "1freq-zero.txt" shows the total number of times the 1x1 tile was located at each position of the board in all 18,656 solutions. The range was surprisingly large: a low of 1 and a high of 416. There's another file called "1freq-white.txt" that's the same only it doesn't use any zeroes so it's easier to read for humans (and slightly more difficult to parse for a computer program).

It might be interesing to do a similar analysis on all the solutions for larger values of N but generating all the solutions for N=9 alone would probably take a couple of days.

Lastly, I wanted to find the most fragmented and the least fragmented solutions. A fragmented solution is one where few tiles of the same size are adjacent. To do this, I wrote routines that scored each solution based on how many regions it held. A "region" is an area on the board composed of adjoining tiles all of the same size. The text file "regions.txt" shows the number of regions in each solution. The minimum was 13 and the maximum was 24 which was a pretty small spread considering there are 18,656 solutions all in all. So I tried another way of getting at a measure of fragmentation. I wrote a routine that scans each row and column in a solution and counts how many times it detects a transition from one sized tile to a different sized tile. See "transitions.txt" for the results. The minimum was 243 and the maximum was 341, a pretty decent spread.

There are only 16 solutions with 243 transitions so when you take rotations and reflections into account, there are only 2 solutions with minimal fragmentation and the first is Solution #1021. Similarly, there are only 32 solutions with 341 transitions so when you take rotations and reflections into account, there are only 4 solutions with maximal fragmentation and the first is Solution #240.  
