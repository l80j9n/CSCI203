java c
CSCI203 – Data Structures and Algorithm, 2024 S3 
Assignment 2 (15% of total marks) 
Due date: 12 August 2024,   Monday Scope: 
The tasks of   this assignment cover the data structure and algorithm.   The assignment   covers the topics discussed   in topics   4,   and   5.The assignment is divided into two parts - Part   One   covers the theoretical   aspect   of the   materials discussed during classes, and Part   Two covers the practicality of the concepts.   The total   marks for   Part One   is   70, and   Part Two   is   30.
Assessment criteria: 
Marks will   be awarded   for:
•            Correct,
•            Comprehensive, and
•            Appropriate
application of the   materials covered in this   subject.
Marks: 
Total   mark:   100
Weightage:   15% of total subject   mark
Assignment Specification: 
Part A:   (70   marks)
Question 1 (15.0 marks) a.   The   INORDER   traversal   output   of   a   binary   tree   is   H,Y,P,H,E,N,A,T,I,O,N   and   the   POSTORDER   traversal   output   of   the   same   tree   is Y,H,E,A,N,H,O,I,T,P,N.   Construct   the tree and determine the output of the   PREORDER traversal   output. (5.0 marks) 
b.    One main difference   between a binary search tree (BST) and an AVL (Adelson-Velski   and   Landis) tree   is that an AVL tree   has a   balance condition,   that   is,   for   every   node   in the AVL tree, the height of the left and right subtrees differ   by at   most   1.   Starting   with an empty BST and AVL tree, insert the following values   into the two trees   (BST   as   well   as   AVL   trees),   in   other   words,   first   insert   the   values   and   construct   a   BST,   then   using the same set of the values   insert and   construct   an AVL   tree.
48,   59,   38, 41,   51, 49,   61,   59,   60
If a   key   is already existed,   insert the   new   key to the   LEFT   sub-tree. (5.0 marks) c.    Based   on   what   you    have   done   for   Question    1b,   what   is   the   big-O   (worst case)   complexity of the total time   required to build a   binary search   tree   (BST)   consisting   of n    nodes?   Explain your answer. Answer without explanation gains   no   mark.   (Hint.   A   tricky   question.   The   question   asks   for worst case complexity.   Think   properly.) (5.0 marks)
Question 2 (15.0 marks) 
The   following   two   algorithms   claim   to   solve   the   same   problem.   To   do   so,   the   two   algorithms   receive as in input argument   a   reference   pointing to   a   root   of a   tree: 
ALGORITHM 1 
Function A1(root) if (root == NULL) 
return − 1 endIf 
x = root. data 
Q = new Queue()               ENQUEUE(Q, root) 
wℎile (!ISEMPTY(Q)) do t = PEEK(Q) 
if (t. data < x) x = t. data 
else 
ENQUEUE(Q, t. left) ENQUEUE(Q, t. rigℎt)   DEQUEUE(Q) 
endIf 
endwℎile return x 
End of function A1 
ALGORITHM 2 Function A2 (root) if (root == NULL) return − 1 endIf t = root wℎile (t. left ! = NULL) do t = t. left endwℎile return t. data 
End of function A2 
Note: the function ENQUEUE only inserts a new element in the queue if this element is different from NULL. 
a)   For the following   Binary Tree:

What is   returned   by the function call A2(root)? (5.0 marks)
b)   For   the   Binary   Tree   in   part   (a),   what   is   the   content   of   the   queue   immediately   before   returning from the execution of function A1(root)? (5.0 marks) 
c)    Re-write the function A2, in pseudocode, using recursive   function   calls. You may not use any form. of   iteration. (5.0 marks) 
Question 3 (20 marks) Consider a   hash table of size   11   with   hash   function h(x) = 2x mod 11.   Draw   the   table   that results after inserting, in the   given   order, the   following   values:   65,   75,   68,   26,   59,   31, 41, 73,   114 for each   of the   three   scenarios   below:
a)   When collisions are   handled   by separate chaining; (5 marks) 
b)   When collisions are   handled   by   linear   probing; (5 marks) 
c)    When collisions are   handled   by double   hashing   using a second   hash   function   ℎ’(x)   =   (x mod   5)   +   1.    Hint, the overall (combined) hash function is   H(x)   = (   ℎ(x)   +   i      ×    ℎ′(x) ) mod   11, where i =   0,   1,   2,   3,   … (5 marks) 
d)   When   collisions   are   handled   by   quadratic   probing   with   a   quadratic   probe   function ℎ′(x, i)   =   (ℎ(x)   +   0.5   i   +   0.5   i2) mod   11   where i    =    1, 2, 3,   …   . (5 marks) 
Question 4 (20.0 marks) 
a.   The operation convertToMinHeap(ℎ)   converts a maximum heap into a minimum heap.   Design   an   algorithm   of   convertToMinHeap that   runs   in   O(nlgn)    time. Show   that   your algorithm   runs   in   O(nlgn). (10.0 marks) b.    Given   the   following   maximum   heap,   illustrate   the   process   of   converting   it   into   a   minimum heap using your algorithm described    in (a). You need to show the   intermediate   processes. (10.0 marks) 
Part   B:   (30.0   marks)
Your task for this assignment is to investigate some of the properties of queues.
You should write a Java,   C++,   or   Python   program   which   simulates   the   queuing   and service of a set   of   requests   at   a fast-food   restaurant.
Input consists of the following   data:
•         The   number of primary servers   in   the   system.
•         The   number of secondary servers   in the   system.
•         A   set   of   service   requests   each   consisting   of   an   arrival   time   and   two   service   times. This set is terminated by a dummy record with arrival time and service times all equal to 0.   (Note: the arrival   times   are   sorted   in   ascending   order). 
For example, the data file: 
3   2
1   2   3
3   3   5
3   2   2
4   3   2
5   2   4
0   0   0indicates   there   are   3   primary   servers   and   2   secondary   servers.   The   first   service   (customer) arrives in minute 1 (first minute of simulation), and the service requires   2   minutes of primary server’s time and 3   minutes   of   secondary   server’s   time. The   second service (customer) arrives in minute 3, and it requires 3 minutes of primary   server’s time and 5 minutes of secondary   server’s   time,   etc.The   last entry of the data file   0   0   0   indicate the   end   of   simulation.   (Note   that   it   is   possible   to   have   two   customers   arrive   in   the   same   time   as   shown   in   the   above   sample data (second and third customers).)Your   program   should   read   the   name   of   the   data   file   from   standard   input   and   then   read   the   data   in   the   named   file   into   the   simulation.    For   example,   the   following   command   will   trigger   the   execution   of   your   program   by   reading   the   data file   provided:
./QueueSim datafile.dat                or   java   QueueSim   datafile.dat
The   simulation   is   to   be   of   代 写CSCI203 – Data Structures and Algorithm, 2024 S3C/C++
代做程序编程语言a   system   with   two   sets   of   servers,   primary   and secondary,   with a   single   queue   associated   with   each   set.   Customers   arrive   in   the   system   and   are   served first   by   a   primary   server   and,   on   completion   of this   service,   by   a   secondary   server.   If all   servers   of a   particular type   are   busy,   the   customer will enter either the   primary or secondary   queue   as   appropriate.
The simulation should   be   run   until the   last customer   has   left the   system.
Output, to standard output, for each   version   of the   queuing   process   will   consist   of the following data:
•          Number of customers   served.
•         Time   last service   request is   completed.
•         Average total service   time.
•         Average total time   in queue(s).   Both overall and   separate.
•         Average   length of queue.   For each queue   and   overall.
•          Maximum   Length of queue.   For each   queue   and   overall.
•         Total idle time   for   each   server.NOTE: Since the question is to assess your understanding of   the concept of Queue, you   are   NOT allowed to   use the   library of the   language that   implement   queue. You   need to   write the codes   (implementation) of Queue for this exercise.   (See   point   (iii).)The following is just a sample output for your reference. It is by no mean that your output must be the same because the simulation involves a random function (generator). You can also change the format, as long as the required output (The pointer specified above) are available. 
run:
Number of primary   servers:   3
Number of secondary servers:   2
----- Output   -----
Number of customers served:   100
Time   last service   request completed: 480   minutes.
Average total service time:   1888/100   =   18.88 minutes.
Average total time   in queue:
Primary: 716/100   =   7.16   minutes.
Secondary:   1716/100   =   17.16   minutes.   Total   (both)   = 24.32   minutes.
Average   length of queue:
Primary:   2636/480   =   5.49.
Secondary:   2527/480   = 5.26.   Total   (both)   =   10.76   minutes.Maximum   length of queue:Primary: 22    Secondary:   32Total   (both)   =   54
--- Server   data   ---
P1                  P2                  P3
330          315          314            Serve Time   (in   minutes.)
150          164            166            Idle Time   (in   minutes.)
S1               S2
466           463       Serve Time (in minutes.)
11               15           Idle Time (in minutes.)
End of simulation~
BUILD SUCCESSFUL (total time:   0   seconds)
Other requirements:
•                     Software   (programming language):
o   Java Version - JDK 6   update   17   or   above   (Using Windows)
o   C++ / C compiler -   g++   4.0   or   above   (Using   Linux)
o   Python   3.x
•                     Operating   System:
o   Windows XP   Professional,
o   Windows Vista   Home /   Business,
o   Windows   7,
o   Windows   10,
o   Ubuntu   Linux 8.04   LTS or   above.
•                   If you   use   a   different   environment,   please   make   sure   that   you   MUST   check   with   your   lecturers first!
•                   For   C++   solution,   students   are to   give   batch /   make   files   for   compilation.
•                   Students are   to   place   all   compilation   and   instructions   on   how   to   run   the   program   inside a readme.txt file. The markers   will   refer to   this   file   when   marking.
•                   Programs   should   be   appropriately   documented   with   comments.
Submissions 
This assignment   is due   by   10:00   pm Singapore time on   Monday,   12 August   2024.
•                      For    Part   A,   type   your   answer   for    each   question    in   a    MS   Word   or   equivalent   document    format      and      save      it      in      a      pdf    formatted      file,       name    your      file      as   YourUOWStudentNumber-A2-SolPartA.pdf.      You       may      also       hand-written      your   answer on   pieces of papers and   scan them   into   a   pdf format.
•                   For Part   B, the   name of your program   should   be   QueueSim.cpp,   QueueSim.java or   QuueSim.py,   depending   on   the   programming   language   that   you   use   to   develop   your   program.   Execute your   program and screen capture your   output.   Next,   zip   your   source   code,   libraries,   readme.txt   together   with   your   screen   capture   and   name your file as YourUOWStudentNumber-A2-SolPartB.zip.
•                   Zip                                    together                                 YourUOWStudentNumber-A2-SolPartA.pdf                                    and YourUOWStudentNumber-A2-SolPartB.zip                and                name                your                file                   as   YourUOWStudentNumber-A2.zip.   Do   not use your own filename.
•                   All   assignments that do   not   satisfy   the   submission   requirements   listed   above   will   not   be evaluated and will   be   returned to the   students   with   0   marks.
Submit the files YourUOWStudentNumber-A2.zip through   Moodle   in the following   way:
1) Access   Moodle at http://moodle.uowplatform.edu.au/ 
2)       To   login   use a   Login   link   located   in the   right   upper corner the   Web   page   or   in   the   middle of the   bottom of the Web   page
3)       When successfully   logged in,   select   a   site CSCI203 (SP324) Algorithms and Data Structures 
4)       Scroll down   to   a   section   Submissions   of Assignments
5)       Click   at   Submit your   Assignment   2   here   link.
6)         Click at a   button Add   Submission
7)       Move a file, for   example, YourUOWStudentNumber-A2.zip into   the
submission area. You can drag and drop files   here   to   add   them. You   can   also   use a   link Add… 
8)         Click at a   button   Save   changes,
9)       Click   at   a   button   Submit   assignment,
10)   Click at the checkbox with a text   attached:   By checking   this   box,   I   confirm
that this submission   is   my own work,   …   in   order to   confirm   authorship   of your   submission,
11)   Click at a   button   Continue.
A policy regarding late submissions is included in the subject outline. Only one submission per student is accepted. Assignment   2   is   an   individual   assignment,   and   it   is   expected   that   all   its   tasks   will   be   solved    individually   without    any   cooperation   with   the    other   students. Plagiarism    is   treated   seriously.   Students   involved   will   likely   receive   zero.   If   you   have   any   doubts,   questions, etc.   please consult your lecturer or tutor during   lab   classes   or   over   e-mail.



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
