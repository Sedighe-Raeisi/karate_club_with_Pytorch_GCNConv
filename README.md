# karate club with Pytorch Geometric-Graph Neural Network 

This is a task for learning how to do a node classification in PyTorch. 
This dataset is a social network that shows the relations of the members of a karate club. After a conflict between the administrator and the instructor of the club, the members separated into two communities. One community is labeled by the instructor and the other one by the administrator. This task shows how the structure of the graph of members can be used to predict their final choice of the communities. 

https://user-images.githubusercontent.com/67642255/177558585-311743bc-adcf-402a-a008-12877b5c42b3.mp4


# Section-1: Preparing the model
I prepared this repository to show how we prepare the data for Pytorch GNN and how we can make a model for a node classification problem.
In the first section, we make our model. It is a combination of two GCNConv layers and a linear layer. In the two first layers, we derive the node embeddings and in the linear layer, we use them to do classification tasks. 
In this part, I hope you are familiar with the structure of models in PyTorch. If you have a question about the init method and forward method, you can see the instructing page of torch [Link](https://pytorch-geometric.readthedocs.io/en/latest/modules/nn.html)   

# Section-2: Defining the graph and Training   
## Case 1: Constant number as the feature (unreal but simple for learning)
This is a very simple code that shows you how to prepare the graph structure which is accepted to feed in the torch model. We use the edge index, which is specified by the index of source nodes and the index of destination nodes. 
Then we should prepare the features of nodes. To make the problem very simple and focus on the structure, I use an unreal assumption that we have one feature and its value is constant and the same for all nodes. Later in the next sections, we would reform this.
## Case 2: Node degrees as feature 
Although we can define a function to compute node degrees, it is easier to use *Networkx* library. We define the graph in *Networkx*, then we use the *.degree* to reach the degrees. Then we prepare node degrees as a feature to feed into the model.

## Case 3: Node Embedding as feature
We can use an embedding vector with undefined parameters as node features. Then we would specify the embedding parameters during the training.   
Note that we should tell the optimizer to do optimization for both model parameters and the embedding parameters.
We have different choices for embedding, for more information, you can see [link](https://github.com/shenweichen/GraphEmbedding)
# Section-3: Networkx karate dataset  
For previous parts, I defined the data myself. But this dataset exists in the *Neworkx* library. In this dataset, we have the final labels of all nodes. So we can have an accurate estimation of the accuracy of our model. I show how to extract the edge index and labels from this dataset. I use the *accuracy_score* of *Sklearn* to compute the accuracy of the model.
# Section-4: Considering the edge weight in the model
In this section, I show you how to import the networkx graph using the Adjacency matrix in a text file. First, we read the matrix as a NumPy array, and we convert its element from a string to an integer.
Then we define the torch data from the networkx graph using *from_networkx*. This data structure has both the edge indexes and edge weights. We could define other features in networkx when making a graph. All these features would be available in torch data. (What an awesome tool is the networkx!)
We should change the model to accept the edge weights. 

In the final part, I made an animation that shows the prediction of the model for each node during the training. 
