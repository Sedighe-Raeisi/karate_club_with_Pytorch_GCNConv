# karate club with Pytorch Geometric-Graph Neural Network 




https://user-images.githubusercontent.com/67642255/177542082-cfd51418-daab-46c7-b149-40923ff031cc.mp4


# Section-1: Prepairing the model
I prepaired this repository to show how we prepaire the data for Pytorch GNN and how we can make a model for a node classification problem.
In the first section we make our model. It is a combination of two GCNConv layer, and a linear layer. In two first layer we derive the node embeddings and in the linear layer we use them to do classification task. 
In this part I hope you are familiar with the structure of models in pytorch. If you have a question about the init method and forward method, you can see the instructing page of torch [Link](https://pytorch-geometric.readthedocs.io/en/latest/modules/nn.html)   

# Section-2: Defining the graph
This is a very simple code which shows you how to prepaire the graph structure which is accepted to feed in the torch model. We use edge index, which is specified by the index of source nodes and the index of destination nodes. 
Then we should prepaire the features of nodes. In order to make the problem very simple and focuse on the structure, I use an unreal assumption that we have one feature and its value is constant and the same for all nodes. Later in the next sections we would reformd this.
# Section-3: 

# Section-4: 

# Section-5: 
