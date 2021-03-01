---
description: Run !
---

# Graphs

## Adjacency Matrix representation

```java
public class Graph {
  private boolean adjMatrix[][];
  private int numVertices;

  // Initialize the matrix
  public Graph(int numVertices) {
    this.numVertices = numVertices;
    adjMatrix = new boolean[numVertices][numVertices];
  }

  // Add edges
  public void addEdge(int i, int j) {
    adjMatrix[i][j] = true;
    adjMatrix[j][i] = true;
  }

  // Remove edges
  public void removeEdge(int i, int j) {
    adjMatrix[i][j] = false;
    adjMatrix[j][i] = false;
  }

  // Print the matrix
  public String toString() {
    StringBuilder s = new StringBuilder();
    for (int i = 0; i < numVertices; i++) {
      s.append(i + ": ");
      for (boolean j : adjMatrix[i]) {
        s.append((j ? 1 : 0) + " ");
      }
      s.append("\n");
    }
    return s.toString();
  }

  public static void main(String args[]) {
    Graph g = new Graph(4);

    g.addEdge(0, 1);
    g.addEdge(0, 2);
    g.addEdge(1, 2);
    g.addEdge(2, 0);
    g.addEdge(2, 3);

    System.out.print(g.toString());
  }
}
```

## Adjacency List representation

```java
import java.util.*; 

class Graph { 

    static void addEdge(ArrayList<ArrayList<Integer> > adj, int u, int v) 
    { 
        adj.get(u).add(v); 
        adj.get(v).add(u); 
    } 

    static void printGraph(ArrayList<ArrayList<Integer>> adj) 
    { 
        for (int i = 0; i < adj.size(); i++) { 
            for (int j = 0; j < adj.get(i).size(); j++) { 
                System.out.print(adj.get(i).get(j)+" "); 
            } 
            System.out.println(); 
        } 
    } 

    public static void main(String[] args) 
    {  
        int V = 4; 
        ArrayList<ArrayList<Integer> > adj = new ArrayList<ArrayList<Integer> >(V); 

        for (int i = 0; i < V; i++) 
            adj.add(new ArrayList<Integer>()); 

        // Adding edges one by one 
        addEdge(adj, 0, 1); 
        addEdge(adj, 0, 2); 
        addEdge(adj, 1, 2); 
        addEdge(adj, 1, 3); 

        printGraph(adj); 
    } 
}
```
