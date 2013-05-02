Basic_Lees_Routing_Algorithm_with_GUI
=====================================
This project report describes the implementation of CAD routing algorithm named as Lee’s Basic Algorithm in Java Applet with proper GUI. These two algorithms generally used for Grid routing in VLSI design. The application needs web browser or applet viewer for displaying the running of the algorithms.

The Lee algorithm is one possible solution for maze routing problems based on Breadth-first search. The basic Lee’s algorithm steps are as follows:
1) Initialisation
 - Select start point, mark with 0
 - i := 0
2) Wave expansion
 - REPEAT
     - Mark all unlabeled neighbors of points marked with i with i+1
     - i := i+1
   UNTIL ((target reached) or (no points can be marked))
3) Backtrace
   - go to the target point
   REPEAT
     - go to next node that has a lower mark than the actual node
     - add this node to path
   UNTIL (start point reached)
4) Clearance
 - Block the path for future wirings
 - Delete all marks
Of course the wave expansion marks only points in the routable area of the chip, not in the blocks or already wired parts, and to minimize segmentation we should keep in one direction as long as possible i.e minimize the number of bends.  This algorithm has space complexity of O(N^2) for a grid of dimension N*N. Each cell needs store a number between 1 and L, where L is the maximum path length. So each cell needs log(L+2)bits. The additional two bits need for representing empty the cell is empty and obstacles occupy cell.
