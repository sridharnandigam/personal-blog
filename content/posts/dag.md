---
title: "DAGs Are Cool"
date: 2022-07-27T21:56:35-05:00
draft: false 
tags:
    - "data engineering"
---
[REUPLOAD FROM LINKEDIN]

I found an interesting topic from my discrete math class while exploring ways to design tools for data engineers. When designing data pipelines, it is common to visualize them as DAGs or directed acyclic graphs.

To break it down, a graph is essentially a collection of points or nodes that are connected by edges. When those edges have a specific direction, the graph is said to be directed. These edges can be used to map out various paths between nodes. When those paths never lead back to a certain node, the graph is said to be acyclic. 

This seemingly overcomplicated mathematical representation is actually quite useful when visualizing data pipelines. The sequence of transformations in a data pipeline are merely nodes that direct into each other while making sure that there isn’t an infinite loop. 

This application of discrete math can even be extended into machine learning pipelines in the MLOps field, where data consistency is key to maintaining a model’s reliability.