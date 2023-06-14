---
layout: post
title: Page Map @ Acreom
published: false
---

Adding new features while working in a small startup (5 people), you often have to build the whole solution yourself - from user request(s), research, feature specs through implementation and marketing (we are here). At [acreom](https://acreom.com) we recently got requests from users for a graph view of their Pages.

We took on the challenge of creating the best Page Map ever, and we have some interesting takeaways from the journey we would love to share. In this blog, I'd love to talk about some technical challenges we encountered in our use case and how we solved them.

In our original [force graph tutorial](https://medium.com/@petttr1/vue3-and-force-graph-f5dff98a5970), we got to a point where we were using the force graph with real data and got an aesthetically pleasing visualization purely by tweaking the rendering of the data. We are now going to have a look at the 'internal' working of the graph to enhance our visualization even more. To do so, here is a quick intro into the Force Directed Graph.

## What is a Force Directed Graph?

A force-directed graph is a type of data visualization technique for graph data that uses simulated forces to lay out nodes (representing entities) and edges (representing relationships) in a 2D space. The nodes repel each other and edges act as springs to pull connected nodes together, leading to an aesthetically pleasing and often informative arrangement of the nodes and edges. This approach is often used for visualizing complex relationships within networks.

The force-directed graph algorithm is based on a physical simulation approach. Instead of using domain-specific knowledge, it calculates the layout of the graph solely based on the information contained in the graph structure. The algorithm works by iteratively determining the forces acting on each node and adjusting their positions to reach a stable equilibrium. The goal is to reach a state where the positions of the nodes remain unchanged.

## Applications

(from gpt, will edit + add examples)

- Social network analysis: visualizing the structure of online social networks such as Facebook, Twitter, or LinkedIn.
- Biological networks: visualizing protein-protein interaction networks or gene regulatory networks in cellular biology.
- Concept maps: visualizing relationships between academic disciplines, topics, or concepts in education or research.
- Information visualization: visualizing relationships between news articles, documents, or keywords in digital libraries or search engines.
- Transportation networks: visualizing the relationships between airports, airlines, or flights in a global air transportation network.
- Financial networks: visualizing relationships between banks, financial institutions, or interbank lending in a financial network.
- Political networks: visualizing relationships between political entities, such as political parties, candidates, or interest groups in a national or regional political network.
- Software networks: visualizing relationships between software components, classes, or functions in a software development project.
- Energy networks: visualizing relationships between power stations, energy sources, or energy grids in a national or regional energy network.
- Supply chain networks: visualizing relationships between suppliers, manufacturers, distributors, and customers in a global supply chain network.

If you want to learn more about the inner workings of Force Directed Graphs, I recommend the following: 
- [Force-Directed Drawing Algorithms](https://cs.brown.edu/people/rtamassi/gdhandbook/chapters/force-directed.pdf)
- [Introduction to Network Analysis and Representation](http://dhs.stanford.edu/dh/networks/)

To recap, FDG is a vis method, uses simulated forces to lay out the data, the nodes repel each other and the edges pull connected nodes together.

## Setting up

Now that we got the basics down, let's get down to coding (and playing with some nodes). I have recently published a tutorial on how to set up a Force Graph with Vue3. It covers the basic project setup, creating of a simple graph, usage of real data and some interesting enhancements. I will therefore skip these parts, but if you are interested, be sure to check out [the tutorial](https://medium.com/@petttr1/vue3-and-force-graph-f5dff98a5970), or clone the [repo](https://github.com/petttr1/vue3-force-graph) for a quick start.

I will include interactive demos in this post, but will link to an updated repo with all the changes incorporated, so if you would like to skip to the good part, you can do so {{here (link to new git)}}

## Playing with forces

inspo: https://www.d3indepth.com/force-layout/
https://observablehq.com/@ben-tanen/a-tutorial-to-using-d3-force-from-someone-who-just-learned-ho

### Charge Force

explain charge

{% include charge.html %}

### Link Forces

Together with charge, the basic of forces making the technique work.
- graph with all nodes linked
- sliders for charge and link force

### Radial Force

explain circular - keep together
- used to contain nodes in a certain area
- graph with multiple nodes multiple sizes
- draw circle, applying the force fills the circle with the nodes

### Collide Force

explain collide + problem with performance

## Visual

Compare to maps - zooming makes the distances the same (makes the nodes smaller), add map gif + GV gif

add batch loading

