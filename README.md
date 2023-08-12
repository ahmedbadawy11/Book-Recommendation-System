# Running the code

We run our code locally on our machines and for the notebook, we preprocess, clean and transform the data into word2vec form.  
We saved this representation into a `csv` file for later use


```
train_data.to_csv("Embeddings.csv" , sep = ";")
``` 

## Clustering
We cluster our data and get 5 labels and for each label we check for the most frequent genre to assign this cluster to it manually    
We use the code to check for the most frequent genre to each cluster 

```
genres = list()
for genre in random_sample_0["Genres"]:
    for i in range(len(genre)):
        genres.append(genre[i])
print(Counter(genres))
```
* **Note that there is usually two clusters with the same most frequent genres so we assign the genre `Children's literature` to one of them** 

Then assign the genre to all the books in the cluster manually .


```
random_sample.loc[random_sample["labels"] == 0, "Genres"] = "Science Fiction"
```

After we classify our data we save our dataframe with the all new features to a csv file to use later

```
random_sample.to_csv("Final_output.csv", index=False, sep=';')
```

* **Please note that the final accuracies of the model may vary every time we run the notebook because of the randomization of the data.**
## Chatbot
After we finished the work on notebook we install the ngrok application.    
And to start our server we use this command line to provide us with the https link

```
ngrok http 5000
```

Then we take this link and paste it in the `Dialogueflow` fulfillment 

```
https://1889-41-33-218-52.ngrok-free.app/webhook
```

And to start using our work in the chatbot and `Dialogueflow` we used the presaved dataframes to not rerun the notebook from the begining and instead of using the pickle file.

```
train_data = pd.read_csv("Embeddings.csv" , sep = ";")
random_sample = pd.read_csv("Final_output.csv", index=False, sep=';')
```
Then we run our .py file to connect the model to the chatbot