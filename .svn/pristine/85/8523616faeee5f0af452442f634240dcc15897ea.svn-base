package graph;
import java.util.ArrayList;
/* See restrictions in Graph.java. */

/** Represents a general unlabeled directed graph whose vertices are denoted by
 *  positive integers. Graphs may have self edges.
 *
 *  @author Doron Reuven.
 */
public class DirectedGraph extends GraphObj {

    @Override
    public boolean isDirected() {
        return true;
    }

    @Override
    public int inDegree(int v) {
        int count = 0;
        if (gethashSucc().containsKey(v)) {
            for (int key : gethashSucc().keySet()) {
                for (int elem : gethashSucc().get(key)) {
                    if (elem == v) {
                        count += 1;
                        continue;
                    }
                }
            }
            return count;
        }
        return 0;
    }

    @Override
    public int predecessor(int v, int k) {
        if (!gethashPred().containsKey(v) || k < 0
            || k >= gethashPred().get(v).size()) {
            return 0;
        }
        return gethashPred().get(v).get(k);
    }

    @Override
    public Iteration<Integer> predecessors(int v) {
        if (!contains(v)) {
            return Iteration.iteration(new ArrayList<Integer>());
        }
        return Iteration.iteration(gethashPred().get(v));
    }
}
