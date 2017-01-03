# Partridge-Number
Solution, Visualization, and General Exploration of the "Partridge Number" 

Suppose you have a bunch of square tiles: you have N of the tiles that are N units on a side, N-1 of the tiles that are (N-1) x (N-1) in size, and so forth, down to 1 of the 1x1 tiles. Well, it's easy enough to compute the area of all those tiles taken together and it would be:
    Total Area = N^3 + (N-1)^3 + (N-2)^3 + ... + 1^3

And it turns out that that sum equals [ N x (N+1) / 2 ]^2

That's pretty interesting: the sum is expressed as a term (i.e., "N X (N+1)/2") that is *squared* and that raises the possibility that all those tiles could be arranged to fit inside a square that is N x (N+1)/2 units on each side. OK, but a quick look reveals that for small values of N (e.g., 2 or 3) you can't actually make the tiling work. So what is the smallest value of N where it *does* work? That minimum value is called the "Partridge Number" and here are the only links I've been able to find that discuss it:

http://www2.stetson.edu/~efriedma/papers/partridge.pdf

http://www2.stetson.edu/~efriedma/mathmagic/0802.html

http://www.mathpuzzle.com/partridge.html

Although the articles discuss Partridge Numbers for a variety of shapes (e.g., equilateral triangles, trapezoids, rectangles), I'm only concerned with squares (at least for now). The "literature" (i.e., the three articles above) all refer to work done by Bill Cutler and Patrick Hamlyn who apparently were able to determine that the Partridge Number for square tiles is 8 and that there are 2332 solutions. The articles don't say if there are 2332 *unique* solutions that exclude rotations and reflections and I couldn't find a comprehensive list of all possible solutions so I thought I would write a program and generate them myself.

I came up with an exhaustive search algorithm and implemented it in Python. It has a triple nested loop, each O(N^2), that recurses so that makes it what, an O(N^12) beast? I ran the Python version for over a week and it was checking about 5200 configurations per second. That was going much too slowly so I ported it to Java which clocked in at about 1.3 million configurations per second. It checked all 60+ billion configurations in less than a day.

The Solutions.txt file contains all 18,656 solutions, including rotations and reflections. Since there are 7 rotations and reflections for every solution, the total number of unique solutions is 2332, which agrees with Bill Cutler's and Patrick Hamlyn's result.

Next steps:

1. Eliminate duplicates. By duplicates I mean the three rotations and four reflections that each configuration has.


