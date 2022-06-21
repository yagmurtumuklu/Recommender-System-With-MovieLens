# Recommender-System-With-MovieLens
This recommendation system generates a recommendation list with "Collaborative Filtering".  The path followed in the notebook is summarized below, and the details of the methods used are explained in "extra_descriptions.md".

1. Data Preprocessing

2. Train-test split. Using the leave-one-out methodology 

3. Converting the dataset into an implicit feedback dataset. Because If I take the rating results as an interaction, the number of reviews that we accept as interaction will be less since the number of reviews is generally low. Example: Is every video on Youtube evaluated after watching? No. If we count every user choice as an interaction instead of a score, we're using quite a bit of interaction. The problem here is having to accept every choice of the user as a positive example. I have added the solution to this in the comments in the notebook.
4. Model Architecture
5. 5.  Define this NCF model using PyTorch Lightning.

6. "Hit Ratio" evaluation. With this common method, the following evaluation protocol was run to generate a list of 10 recommended items for each user.

- For each user, randomly select 99 items that the user has not interacted with
- Combine these 99 items with the test item (the actual item that the user interacted with). We now have 100 items.
- Run the model on these 100 items, and rank them according to their predicted probabilities
- Select the top 10 items from the list of 100 items. If the test item is present within the top 10 items, then we say that this is a hit.
- Repeat the process for all users. The Hit Ratio is then the average hits.
