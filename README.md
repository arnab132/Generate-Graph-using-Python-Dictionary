# Generate-Graph-using-Python-Dictionary

To draw graph using in built libraries – Graph plotting in Python

Here, we will see how to implement graph in python using dictionary data structure in python. 

The keys of the dictionary used are the nodes of our graph and the corresponding values are lists with each nodes, which are connecting by an edge. 

This simple graph has six nodes (a-f) and five arcs: 
 

a -> c
b -> c
b -> e
c -> a
c -> b
c -> d
c -> e
d -> c
e -> c
e -> b


It can be represented by the following Python data structure. This is a dictionary whose keys are the nodes of the graph. For each key, the corresponding value is a list containing the nodes that are connected by a direct arc from this node. 
 

graph = { "a" : ["c"],
          "b" : ["c", "e"],
          "c" : ["a", "b", "d", "e"],
          "d" : ["c"],
          "e" : ["c", "b"],
          "f" : []
        } 


Graphical representation of above example: 
 
![image](https://user-images.githubusercontent.com/22562694/120111341-2f1f5a00-c18f-11eb-8eba-8118bf6a3a25.png)

defaultdict: Usually, a Python dictionary throws a KeyError if you try to get an item with a key that is not currently in the dictionary. defaultdict allows that if a key is not found in the dictionary, then instead of a KeyError being thrown, a new entry is created. The type of this new entry is given by the argument of defaultdict. 

Python Function to generate graph: 

# definition of function
def generate_edges(graph):
    edges = []

    # for each node in graph
    for node in graph:

        # for each neighbour node of a single node
        for neighbour in graph[node]:
            # if edge exists then append
            edges.append((node, neighbour))
    return edges
 
