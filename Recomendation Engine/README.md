# Recommedation System
Recommender systems are defined as recommendation inputs given by the people, which the system then aggregates and directs to appropriate recipients. There are three basic, commonly used, types of recommender systems:

+ Collaborative filtering
- Content-based filtering
+ Hybrid recommendation systems.


Let’s have a closer look at each of these types:

## Collaborative Filtering

First we dive into collaborative filtering models. They are built on a dataset of user/item feedback. This may be either explicit feedback such as a star rating or thumb-up/thumb-down, or implicit feedback such as the number of episodes watched in a TV show. We categorize these models further in how they process this data.

### User-User

The most commonly used recommendation algorithm follows the “people like you like that” logic. We call it a “user-user” algorithm because it recommends to a user an item that similar users liked before. The similarity between two users is computed from the amount of items they have in common in the dataset. This algorithm is very efficient when the number of users is way smaller than the number of items. You can think of a medium sized online shop with millions of products. The major drawback is that adding a new user is expensive since it requires to update all similarities between users.

### Item-Item

The “item-item” algorithm uses the same approach but reverses the view between users and items. It follows the logic “if you like this you might also like that”. It recommends items that are similar to the ones you previously liked. As before the similarity between two items is computed using the amount of users they have in common in the dataset. This algorithm is best when the number of items is way smaller than the number of users, such as large-scale online shops. It is well suited if your items don’t change too much, since you can pre-compute the full table of item-item similarities and then serve recommendations in real-time. Updating this table for adding a new item is unfortunately hard.

### User-Item

There are multiple forms of “user-item” recommendation algorithms which combines both approach to generate recommendations. The simplest ones are based on matrix factorization techniques. The goal is to learn low-dimensional vectors (“embeddings”) for all users and all items, such that multiplying them together can recover if a user likes an item or not. You can view these vectors as encoding how much an item has a certain feature (like a movie being a drama), and respectively how much a user likes this feature in items (it can also be negative!).

This factorization is best trained using SVD, but since this algorithm is computationally intensive and does not scale well, we often prefer alternatives. For medium-scale datasets ALS will give reasonable performances. For large dataset, only the SGD algorithm will be able to scale, but will be very slow.

Once the users embeddings and the items embeddings have been pre-computed recommendations can be served in real time. Another benefit of this approach is that you can learn more about users and items using their embeddings. For example you can cluster users or items accordingly to their item preferences.

User-Item algorithms share the drawback that there is no efficient method to update the embeddings after adding a new item or a new user.

## Content-Based

All the previous models suffer from what is called the cold-start problem. Because the recommendations are computed using a dataset of users feedback on items, they can’t recommend items with no or only a few feedback, such as new items. Similarly they can’t recommend anything to a new user before they started to bootstrap by giving some feedback on enough items (this explains the tedious onboarding steps you surely experienced online). These issues are mitigated using Content-Based models. The approach is identical to the previous User-User or Item-Item algorithms, except that the similarities are computed using only content-based features. To train a model solving the item cold-start (resp. user cold-start) you need a dataset including detailed descriptions of your items (resp. of your users), such as the genre of a movie, its budget, its duration, or any variable that may help the recommendation. The recent progress of pattern recognition in machine learning unlocked great improvements in content-based model using information extracted from raw images or raw text description. Plenty of tools and pre-trained deep learning models of Computer Vision or Natural Language Processing can be found online. The obvious benefit of using a pre-trained model is that you don’t need enormous datasets and expensive servers to train your recommendation engine.



## Hybrid Models and Deep Learning

The most modern approaches in recommendation engine algorithm leverage deep learning to combine both collaborative filtering and content-based models. Deep Learning allows to learn much finer interactions between users and items. Because they are non-linear, they are less prone to over-simplify the users profiles. Deep learning models can represent complex tastes over various range of items, even from cross-domain datasets (for instance covering both music, movies and TV shows). In Hybrid Deep Learning algorithms, users and items are modeled using both embeddings that are learnt using the collaborative filtering approach, and content-based features. Once embeddings and features are computed, the recommendations can also be served in real time.

The learning schemes of such algorithms is close to traditional deep learning, that is mini-batch SGD with acceleration heuristics. But the fact that recommendation datasets are quite different from usual computer vision datasets makes it much more complex to use existing implementation and tools (for instance many optimizers in libraries like TensorFlow or PyTorch do not support sparse update of the momentum, which is a cornerstone of training deep models for recommendation). Engineers and researchers are often left out implementing and training more on their own, which requires both expert time and a lot of computing resources.

Another drawback of deep learning models is that they need extensive hyper-parameter optimization. Compared to the plethora of open-source architectures and pre-trained models in computer vision, recommendation engines have almost no well known architecture nor pre-trained model. Also as before, updating your model to add a new item or a new user is difficult.




_______________________________
## Author
+ Name: Md Jahid Hasan
+ 𝐏𝐡𝐨𝐧𝐞: (+880) 1772905097 (Whatsapp)
+ 𝘔𝘢𝘪𝘭: jahidnoyon36@gmail.com
+ LinkedIn: http://linkedin.com/in/hellojahid

____________________


