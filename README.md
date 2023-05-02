Download Link: https://assignmentchef.com/product/solved-comp-2007-assignment-2
<br>
5/5 - (1 vote)

Assume we are about to go for dinner, and there are several restaurants to consider. To decide which restaurants to go to we might take the attributes of the restaurants into consideration. For example, the estimated price and the quality of the food. Of course, if every attribute of restaurant A is better than the attributes of restaurant B then restaurant A is always a better option than B. In this case we say that restaurant A is superior to restaurant B, and that B is inferior to A.



Figure 1 shows an example where we have ve possible restaurants p1; : : : ; p5 and we only consider two attributes: price and quality. It is easy to see that there are restaurants that are not inferior to any other restaurant. The highlighted restaurants, p1 and p5, are not inferior to any other restaurants, however, restaurant p1 is superior to p2; p3 and p4 while p5 is not superior to any other restaurant. We will use this observation to measure the importance of a restaurant. If a restaurant pi is superior to k other restaurants then we say that its importance is k. Your task in this assignment is to compute the importance of every restaurant.

pricep1p2p4p3p5quality

figure 1: The two restaurants p1 and p5 are not inferior to any other restaurant but the importance of p1 is 3 while the importance of p5 is 0.

We now state the problem more formally. Let P = fp1; : : : ; png be a set of n points in d-dimensional space, where each point pi is a d-tuple pi = (pi(x1); pi(x2); : : : ; pi(xd)) representing its x`-coordinates, 1 ` d.

A point pi is said to be superior to a point pj if and only if pi(x`) pj (x`) for all `, 1 ` d. In this case pj is said to be inferior to pi. If neither point is superior/inferior to the other then the points are incomparable. If a point pi is superior to exactly k points in P n fpig then we say that its importance is k, denoted imp(pi) = k.Your task is to design algorithms in 1D and 2D that compute the importance of every point in P .

Note that the input test les follow the following name convention: The test cases for each of the three questions (1d, 2a(iv) and 2b(iv)) are ns <a href="http://ix.in/" target="_blank" rel="nofollow noopener">ix.in</a> for the input les and ns ix.out for theoutput les, where s is the number of points [10; 100; 200; 500; 1000] and i is an index in [0; 1; 2]. E.g. n10 <a href="http://0.in/" target="_blank" rel="nofollow noopener">0.in</a> is the rst input le on 10 points, n10 <a href="http://1.in/" target="_blank" rel="nofollow noopener">1.in</a> is the second input le on 10 points and, n10 <a href="http://2.in/" target="_blank" rel="nofollow noopener">2.in</a> is the third input le on 10 points. In total there are 15 test cases for each question.1.  [20 points] We will start with the simpler 1-dimensional case, that is, let P = fp1; : : : ; png be a set of n points in 1-dimensional space (multiple points may have the same value). Your

task is to design an O(n log n) time algorithm that computes the importance of each point in P .

a)Description of how your algorithm works (in plain English”).[5 points](b)Argue why your algorithm is correct.[4 points](c)Prove an upper bound on the time complexity of your algorithm.[3 points]

(d)   Implement your algorithm (in Ed) and test it on the the given input instances. Each instance is given in a text le using the following format (where n is the number of points):



p1(x1) p2(x1)…

pn(x1)

You may assume that all the coordinates are given as non-negative integers. The output data le must use the following format:

imp(pi1 ) imp(pi2 )..

imp(pin )where pi1 ; pi2 ; : : : ; pin are ordered according to increasing x1-coordinates. Important: The points must be sorted otherwise the automatic tests will fail your submission. [8 points]

2.  [80 points] Consider the same problem in 2D, that is, let P = fp1; : : : ; png be a set of n points in 2-dimensional space, where each point pi is a 2-tuple pi = (pi(x1); pi(x2)). The task is to solve this problem using a divide-and-conquer approach. A divide and conquer algorithm works by recursively breaking down a problem into two (or more) sub-problems of the same or related type, until these become simple enough to be solved directly. The solutions to the sub-problems are then merged to give a solution to the original problem. For full marks on this question the algorithm is required to run in O(n log n) time.

We will start with the merge step.

(a)   [40 points] Let P1 = fp1; : : : ; pn1 g and P2 = fq1; : : : ; qn2 g be two point sets in the plane that are separated by a vertical line (every point in P1 lies to the left of all points in P2). Also, the sets in P1 and P2 are ordered from bottom to top (in case of a tie the points are ordered with respect to increasing x1-coordinates). Assume that the problem has been solved for P1 and P2, respectively. That is, the importance of each points in P1 has been computed with respect to P1 and the importance of each points in P2 has been computed with respect to P2. Your task is to combine the two solutions into one solution for P = P1 [ P2. An example is shown in Fig. 2.

i. Description of how your algorithm works (in plain English”).       [13 points]

ii. Argue why your algorithm is correct. [12 points]

iii. Prove an upper bound on the time complexity of your algorithm. [5 points]

iv.   Implement your algorithm (in Ed) and test it on the input instances. Each instance is given in a text le using the following format (where n is the total number of points, l is the number of points in P1 and r is the number of points in P2):

n

p1(x1) p1(x2) imp(p1) p2(x1) p2(x2) imp(p2)

: : :

pl(x1) pl(x2) imp(pl) r

q1(x1) q1(x2) imp(q1) q2(x1) q2(x2) imp(q2)

: : :

qr(x1) qr(x2) imp(qr)

The output format should be in the following form for each of the output      les:imp(pi1 ) imp(pi2 )

: : :

imp(pin )where pi1 ; pi2 ; : : : ; pin are ordered according to increasing x2-coordinates (in case of ties, order with respect to increasing x1-coordinates). Important: The points must be sorted otherwise the automatic tests will fail your submission. Note that this sorting step does not have to be described or analyzed. [10 points]

00

0

P3

1merge

4

1

1

10⇒12

0

0

0

P1                       P2

Figure 2: The two points set P1 and P2 are separated by a horizontal line. The merge step merges the input data into the importance of all the points in P = P1 [ P2.(b)   [40 points] The nal task is to use the merge step algorithm from (a) to construct a divide-and-conquer algorithm for the problem.

i. Description of how your algorithm works (in plain English”).       [8 points]

ii. Argue why your algorithm is correct. [10 points]

iii. Prove an upper bound on the time complexity of your (entire) algorithm [10 points]iv.   Implement your algorithm (in Ed) and test it on the input instances. Each instance is given in a text le using the following format (where n is the number of points):

p1(x1) p1(x2) p2(x1) p2(x2)

pn(x1) pn(x2)

The output format should be in the following form for each output      le:

imp(pi1 ) imp(pi2 )

: : :

imp(pin )

where pi1 ; pi2 ; : : : ; pin are ordered according to increasing x1-coordinates (in case of ties, order with respect to increasing x2-coordinates). Important: The points must be sorted otherwise the automatic tests will fail your submission. Note that this sorting step does not have to be described or analyzed. [12 points]