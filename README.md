# A-Credit-Card-Frauds-analysis

In today's digital life, day by day, more and more, we buy online. Clothes, perfumes, home appliances, basically everything seems sellable on the internet at a lower price. Most of the times, we use our credit cards for our purchases, and we need to be confident that our data won't be catched by cyber-attackers. This confidence is crucial for the whole sector because, if it goes away, people will stop buying online. So we need to protect those data and we need to be able to distinguish the shady transactions from the good ones.

The dataset we're gonna use, released on Kaggle, contains transactions made by credit cards in September 2013 by European cardholders. It presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions. It contains only numerical input variables which are the result of a PCA transformation. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

In this notebook, we will explore the credit card frauds issue, and we will do it using neural network models. In the first part, we will use the Autoencoder model. An autoencoder is a special type of neural network that is trained to copy its input to its output. For example, given an image of a handwritten digit, an autoencoder first encodes the image into a lower dimensional latent representation, then decodes the latent representation back to an image. An autoencoder learns to compress the data while minimizing the reconstruction error. Our idea is that, if we train this network on regular transactions, the moment the model will see some fraudulent transactions, it will show a different reconstruction loss. If this happen, we'll have a tool that we can use to distinguish 'bad' from 'good' transactions. In the second part, we will build a simple and theoretically meaningless model, that we called, just to play, BalloonNet because of its shape, and we will see how with this, with a shorter training, we will get possibly even better results. In the last part, we will find an explanation for this apparently crezy behaviour, ending up our analysis with an old but always good lesson.

The file creditcard.csv I used for this analysis can be downloaded at the sequent address: 
https://www.kaggle.com/mlg-ulb/creditcardfraud
