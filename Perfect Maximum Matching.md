# Matching
- In graph theory, a matching in a graph is a set of edges that do not have a set of common vertices.
- In other words, a matching is a graph where each node has either zero or one edge incident to it.
- Graph matching is not to be confused with graph isomorphism. 
- Graph isomorphism checks if two graphs are the same whereas a matching is a particular subgraph of a graph.
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/vLRCoBVQEP-twomatchings.png?width=2400)

# Usage
- flow network
- scheduling and planning
- modeling bonds in Chemistry
- graph coloring
- stable marriage problem
- neural network
- artificial intelligence 
# Definitions and Terminology
## Matching
Given a graph G = (V, E), a matching is a subgraph of G, P, where every node has a degree of at most 1. The matching consists of edges that do not share nodes.
## Maximal matching
A matching, P, of graph, G, is said to be maximal if no other edges of G can be added to P because every node is matched to another node.
![](assets/https://ds055uzetaobb.cloudfront.net/brioche/uploads/TlnTxvVpr8-300px-maximal-matchingsvg.png?width=2400)
## Maximum matching
- A matching is a maximum matching if it is a matching that contains the largest possible number of edges matching as many nodes as possible. 
- Simply stated, a maximum matching is the maximal matching with the maximum number of edges. 
- Every maximum matching is maximal, but not every maximal matching is a maximum matching.
- In weighted graphs, sometimes it is useful to find a matching that maximizes the weight.
- A graph may contain more than one maximum matching if the same maximum weight is achieved with a different subset of edges. 
- The size, or total weight, of the maximum matching in a graph is called the `matching number`.
![](assets/https://ds055uzetaobb.cloudfront.net/brioche/uploads/1DKrbNPWdv-300px-maximum-matching-labelssvg.png?width=2400)
## Minimum weight matchings
- Can also be performed if the purpose of a maximal matching is to minimize the overall weight of the graph
## Perfect matching
- A perfect matching is a matching where every vertex is connected to exactly one edge; where the matching matches all vertices in the graph. 
- In an unweighted graph, every perfect matching is a maximum matching and is, therefore, a maximal matching as well. 
- If the graph is weighted, there can be many perfect matchings of different matching numbers. 
- Formally speaking, a matching of a graph G=(V,E) is perfect if it has V/2 edges.
## Near-perfect matching
- A near-perfect matching, on the other hand, can occur in a graph that has an odd number of vertices. 
- In this case, it is clear that a perfect matching as described above is impossible as one node will be left unmatched. 
- This scenario also results in a maximum matching for a graph with an odd number of nodes.
## Bipartite matching
- In order to model matching problems more clearly, graphs are usually transformed into bipartite graph
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/cbz5zJj7w1-220px-simple-bipartite-graphsvg.png?width=2400)
Matching graph
![](assets/https://ds055uzetaobb.cloudfront.net/brioche/uploads/wR6Du8D6wL-matched_bipartie.png?width=2400)

# Examples of Matching Problems
## The Stable Marriage Problem
- The purpose of the stable marriage problem is to facilitate matchmaking between two sets of people. 
- Given a list of potential matches among an equal number of brides and grooms
- The stable marriage problem gives a necessary and sufficient condition on the list for everyone to be married to an agreeable match. 
- This theorem can be applied to any situation where two vertices must be matched together so as to maximize utility, or overall happiness.
## Vertex Cover
- Vertex cover, sometimes called node cover, is a famous optimization problem that uses matching.
- For a graph G = (V,E) a vertex cover is a set of vertices V' in V ∈ V such that every edge in the graph has at least one endpoint that is in V' 
- Below are two graphs and their vertex cover sets represented in red
- Basically, a vertex cover "covers" all of the edges.
![](assets/https://ds055uzetaobb.cloudfront.net/brioche/uploads/X2FHSXszen-200px-vertex-coversvg.png?width=2400)
- Vertext cover is not unique 
![](assets/https://ds055uzetaobb.cloudfront.net/brioche/uploads/5Lb7TFq3R0-342px-triangulation_3-coloringsvg.png?width=2400)
- A more theoretical concept relating to vertex cover is Konig's theorem that states that for any bipartite graph, the maximum size of a matching is equal to the minimum size of a vertex cover.
## Transportation Theory
- Matching algorithms also have tremendous application in resource allocation problems, also known as flow network problems. 
- In mathematics and economics, the study of resource allocation and optimization in travel is called transportation theory. 
# Matching Algorithms
Matching algorithms are algorithms used to solve graph matching problems in graph theory. 
## Alternating and Augmenting Paths
- Graph matching algorithms often use specific properties in order to identify sub-optimal areas in a matching, where improvements can be made to reach a desired goal. 
- Two famous properties are called augmenting paths and alternating paths, which are used to quickly determine whether a graph contains a maximum, or minimum, matching, or the matching can be further improved.
- Graph 1 shows all the edges, in blue, that connect the bipartite graph. The goal of a matching algorithm, in this and all bipartite graph cases, is to maximize the number of connections between vertices in subset A, above, to the vertices in subset B, below.
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/VSdDT2ZaxY-screen-shot-2016-06-28-at-35538-pm.png?width=2400)
- Most algorithms begin by randomly creating a matching within a graph, and further refining the matching in order to attain the desired objective.
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/bJ2r2WyHs2-screen-shot-2016-06-28-at-35422-pm.png?width=2400)
- Graph 1, with the matching, M, is said to have an alternating path if there is a path whose edges are in the matching, M, and not in the matching, in an alternating fashion. An alternating path usually starts with an unmatched vertex and terminates once it cannot append another edge to the tail of the path while maintaining the alternating sequence.
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/0QOAWL9GpD-screen-shot-2016-06-28-at-35010-pm.png?width=2400)
- An augmenting path, then, builds up on the definition of an alternating path to describe a path whose endpoints, the vertices at the start and the end of the path, are free, or unmatched, vertices; vertices not included in the matching. Finding augmenting paths in a graph signals the lack of a maximum matching.
- The matching, MM, for Graph 1, does not start and end on free vertices, so it does not have an augmenting path. This implies that the matching M is a maximum matching
Does the matching in this graph have an augmenting path, or is it a maximum matching?
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/ddYIVtG8Nx-screen-shot-2016-06-28-at-125550-pm.png?width=2400)
The graph does contain an alternating path, represented by the alternating colors below.
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/74k2Tq8NUS-screen-shot-2016-06-28-at-125546-pm.png?width=2400)

## Graph Labeling
- The majority of realistic matching problems are much more complex than those presented above. 
- This added complexity often stems from graph labeling, where edges or vertices labeled with quantitative attributes, such as weights, costs, preferences or any other specifications, which adds constraints to potential matches.
- A common characteristic investigated within a labeled graph is a known as feasible labeling, where the label, or weight assigned to an edge, never surpasses in value to the addition of respective vertices’ weights. This property can be thought of as the triangle inequality.
- A feasible labeling acts opposite an augmenting path; namely, the presence of a feasible labeling implies a maximum-weighted matching, according to the Kuhn-Munkres Theorem.
- When a graph labeling is feasible, yet vertices’ labels are exactly equal to the weight of the edges connecting them, the graph is said to be an equality graph.
## Hungarian Maximum Matching Algorithm
- A common bipartite graph matching algorithm is the Hungarian maximum matching algorithm, which finds a maximum matching by finding augmenting paths. 
- More formally, the algorithm works by attempting to build off of the current matching, M, aiming to find a larger matching via augmenting paths. 
- Each time an augmenting path is found, the number of matches, or total weight, increases by 1. 
- The main idea is to augment M by the shortest augmenting path making sure that no constraints are violated.
## Blossom Algorithm / Edmonds’ matching algorithm
- Unfortunately, not all graphs are solvable by the Hungarian Matching algorithm as a graph may contain cycles that create infinite alternating paths.
- In this specific scenario, the blossom algorithm can be utilized to find a maximum matching. 
- Also known as the Edmonds’ matching algorithm, the blossom algorithm improves upon the Hungarian algorithm by shrinking odd-length cycles in the graph down to a single vertex in order to reveal augmenting paths and then use the Hungarian Matching algorithm.
- A blossom is a cycle in G consisting of 2k + 1 edges of which exactly k belong to M, and where one of the vertices, v, the base, in the cycle is at the head of an alternating path of even length, the path being named stem, to an exposed vertex, w
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/OKZ6FcgOB3-500px-edmonds_blossomsvg.png?width=2400)
- The blossom algorithm works by running the Hungarian algorithm until it runs into a blossom, which it then shrinks down into a single vertex. Then, it begins the Hungarian algorithm again. If another blossom is found, it shrinks the blossom and starts the Hungarian algorithm yet again, and so on until no more augmenting paths or cycles are found. [5]
## Hopcroft–Karp Algorithm
- The poor performance of the Hungarian Matching Algorithm sometimes deems it unuseful in dense graphs, such as a social network. 
- Improving upon the Hungarian Matching algorithm is the Hopcroft–Karp algorithm, which takes a bipartite graph, G(E,V), and outputs a maximum matching. 
# Hungarian Maximum Matching Algorithm
- The Hungarian matching algorithm, also called the Kuhn-Munkres algorithm, is a O(|V|^3) algorithm that can be used to find maximum-weight matchings in bipartite graphs, which is sometimes called the assignment problem.
- A bipartite graph can easily be represented by an adjacency matrix, where the weights of edges are the entries. 
- Thinking about the graph in terms of an adjacency matrix is useful for the Hungarian algorithm.
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/LviKNwDdBm-matching.png?width=2400)
- The Hungarian algorithm solves the following problem:
> In a complete bipartite graph G, find the maximum-weight matching. (Recall that a maximum-weight matching is also a perfect matching.)
- This can also be adapted to find the minimum-weight matching.
## The Hungarian Algorithm Using an Adjacency Matrix
1. Subtract the smallest entry in each row from all the other entries in the row. This will make the smallest entry in the row now equal to 0.
2. Subtract the smallest entry in each column from all the other entries in the column. This will make the smallest entry in the column now equal to 0.
3. Draw lines through the row and columns that have the 0 entries such that the fewest lines possible are drawn.
4. If there are n lines drawn, an optimal assignment of zeros is possible and the algorithm is finished. If the number of lines is less than n, then the optimal number of zeroes is not yet reached. Go to the next step.
5. Find the smallest entry not covered by any line. Subtract this entry from each row that isn’t crossed out, and then add it to each column that is crossed out. Then, go back to Step 3.
6. After algorithm is finished, The assignment will be where the 0's are in the matrix such that only one 0 per row and column is part of the assignment.
7. Replace  0 with the original values
## The Hungarian Algorithm Using a Graph

# Blossom Algorithm
- The blossom algorithm, sometimes called the Edmonds’ matching algorithm, can be used on any graph to construct a maximum matching. 
- The blossom algorithm improves upon the Hungarian algorithm by shrinking cycles in the graph to reveal augmenting paths. 
- Additionally, the Hungarian algorithm only works on weighted bipartite graphs but the blossom algorithm will work on any graph.
- The blossom algorithm is a polynomial time maximum graph matching algorithm.
- This algorithm has many applications, for example, assignment problems such as the Hall's marriage theorem, and path problems such as the Hamiltonian path problem.
![](assets/https://ds055uzetaobb.cloudfront.net/brioche/uploads/OKZ6FcgOB3-500px-edmonds_blossomsvg.png?width=2400)
## Motivating The Algorithm and Intuition
- The Hungarian algorithm is a very efficient graph matching algorithm, but it only works on weighted bipartite graphs as it cannot deal with odd length cycles. 
- The issue lies in finding augmenting paths, since if there is an odd cycle, the algorithm will calculate the wrong augmenting path because it will miss some of the edges. 
- Additionally, a cycle may make the algorithm loop forever, reducing, in the case of minimum-weight optimization, the weight infinitely many times, inhibiting proper termination. 
- The Blossom algorithm aims to fill this gap by solving more generalized graph matching problems, and can be used when the graph is not guaranteed to be bipartite.
- This algorithm improves the Hungarian algorithm by having a way to deal with odd-length cycles. 
- It does this by finding a way to trick the algorithm into thinking it is operating on a simple bipartite graph, collapsing a cycle into a single vertex, so it can run the Hungarian algorithm on the matching.
- The algorithm is named as such since a cycle looks much like a blossom, alluding to a flower. 
- These cycles can be shrunk and the search is then restarted recursively. 
- If the algorithm finds an augmenting path in a shrunken graph, it can be expanded up through the blossoms to yield an augmenting path in the original graph. 
- This alternating path can be used to augment the matching by one edge. 
- If the recursive process ever runs into a state where there is no augmenting path, then the algorithm can return that there is no augmenting path in the original graph.
## The Blossom Algorithm
- The blossom algorithm takes a general graph G = (V, E) and finds a maximum matching M. 
- The algorithm starts with an empty matching and then iteratively improves it by adding edges, one at a time, to build augmenting paths in the matching M.
- Adding to an augmenting path can grow a matching since every other edge in an augmenting path is an edge in the matching; as more edges are added to the augmenting path, more matching edges are discovered. 
- The blossom algorithm has three possible results after each iteration. 
    - Either the algorithm finds no augmenting paths, in which case it has found a maximum matching; 
    - an augmenting path can be found in order to improve the outcome; 
    - or a blossom can be found in order to manipulate it and discover a new augmenting path.
### Augmenting Paths
- An augmenting path is an odd length path that has unmatched nodes for endpoints. 
- The edges in an augmenting path alternate: one segment will be in the matching, the next segment is not in the matching, the next segment is in the matching, and so on.
- The algorithm works by finding augmenting paths so it can increase the size of the matching by one each iteration. 
- To do this, it starts by finding unmatched vertices (vertices that are not connected to an edge that is in the matching). 
- Then, it builds up an alternating path from these nodes. 
- This means that the path begins at a node not in the matching — to be an augmenting path, it must start and end with unmatched nodes.
- The algorithm continues to build on the augmenting path until it can’t anymore. 
- When it stops building an augmenting path, it is either the case that the graph has run out of edges that are not already in the augmenting path, in which case, there is no maximum matching, or the algorithm gets to a point where an augmenting path cannot be made, at which point the algorithm returns a maximum matching.
### Blossoms
- The idea behind blossoms is that an odd-length cycle in the graph can be contracted to a single vertex so that the search can continue iteratively in the now contracted graph. 
- Here, these odd-length cycles are the blossoms. 
- The algorithm can just go on through the graph and treat the tricky cycle as if it were only a single node — fooling the algorithm into thinking there is an even number of nodes in the graph (it has explored so far) so that it can run the Hungarian algorithm on it.
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/OKZ6FcgOB3-500px-edmonds_blossomsvg.png?width=2400)
- The goal of the algorithm is to shrinks a blossom into a single node in order to reveal augmenting paths. 
- It works by running the Hungarian algorithm until it runs into a blossom, which it then shrinks down into a single vertex. 
- Then, it begins the Hungarian algorithm again. 
- If another blossom is found, it shrinks the blossom and starts the Hungarian algorithm, and so on.
![](assets/https://ds055uzetaobb.cloudfront.net/brioche/uploads/7fHzIvhC0s-blossom2.png?width=2400)
Notice the toggling in edges to make another matched edge the stem of the blossom.
![](https://ds055uzetaobb.cloudfront.net/brioche/uploads/Gf8UQGlfTy-blossom3.png?width=2400)
### Pseudocode
Formally, the algorithm is performed by maintaining a forest of scanned edges.
```
for vertex u in Graph G
    if u is unlabelled
       path = findAlternatingPath(u)
       if (path not Empty)
       		if (path is a pseudoNode)
       		      while ((path not Empty) && (path not pseudoNode))
       		          path = findAlternatingPath(u)
      		if (path not Empty)
      		        //update the augmenting path
           		remove the edges in the path that are in matching
                        replace them in the matching with those that are not
          
           
  
 findAlternatingPath(u)
      label(u) =  EVEN
      for each vertex v, in nbrs(u)
         if (v is unlabelled) //found alternating path
            parent(v) = u
            label(v) = ODD
            return v
         else
            if(label(v)== EVEN) //there is an odd cycle
               contract the odd cycle into a pseudonode 
               add to nbrs of every node in the cycle the edge to pseudnode
               remove  the edges from nbrs to the nodes in the cycle.
               label(pseudonode) = EVEN
               return pseudonode
            else 
               label(v) = ODD
               w  = matched(v)
               parent(w) = v
               label(w) = EVEN
               path = findAlternatingPath(w)
               if (path not Empty)
                  return path
               else
                  continue //take the next nbr 
```














# Reference 
https://brilliant.org/wiki/matching/#
http://theory.stanford.edu/~tim/w16/l/l6.pdf
https://www.ics.uci.edu/~eppstein/PADS/CardinalityMatching.py