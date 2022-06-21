
I tried to explain in more detail the methods and methods used in this text as much as I could. :)


## COLLABORATIVE FILTERING:

It is based on the assumption that users who agree in the past will agree in the future, and that they will like items in the future that they liked in the past.

-The system generates recommendations using information about rating profiles for different users and items only.
This approach builds a model from a user's past behavior, i.e. past interactions and similar decisions made by other users.

There are two ways to get interaction from the user.
1) Explicit Feedback
2) Implicit Feedback

The Implicit Feedback method will be used in this project.

### IMPLICIT FEEDBACK

Implicit feedback are collected indirectly from user interactions, and they act as a proxy for user preference. For example. videos that you watch on YouTube are used as implicit feedback to tailor recommendations for you, even if you don't rate the videos explicitly. 


The advantage of implicit feedback is that it is abundant. Recommender systems built using implicit feedback also allows us to tailor recommendations in real time, with every click and interaction. Today, online recommender systems are built using implicit feedback, which allows the system to tune its recommendation in real-time, with every user interaction.

However, implicit feedback has its shortcomings as well. Unlike explicit feedback, every interaction is assumed to be positive and we are unable to capture negative preference from users. How then do we capture negative feedback? One technique that can be applied is negative sampling, which we will go through in a later section.



 ### CONVERTING THE DATASET INTO A IMPLICIT FEEDBACK DATASET

This project will train a recommender system using implicit feedback. However, the MovieLens dataset that we're using is based on explicit feedback. To convert this dataset into an implicit feedback dataset, we'll simply binarize the ratings such that they are '1' (positive class). The value of '1' represents that the user has interacted with the item.


 After binarizing our dataset, we see that every sample in the dataset now belongs to the positive class. However we also require negative samples to train our models, to indicate movies that the user has not interacted with. We assume that such movies are those that the user are not interested in.

## the ratio of negative to positive samples is 4:1. 


## MODEL: NCF (Neural Collaborative Filtering)

### User Embeddings: 
It is a lower dimensional space that captures the relationship of vectorized users from another higher dimensional space.


### Learned Embeddings: 

It is a lower dimensional space that captures the relationship of vectorized items from another higher dimensional space.

Model Architecture: 
It's already in readme.md.
