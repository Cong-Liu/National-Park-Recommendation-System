National Park Recommendation System

Please run the following commands:
```
python collect.py
python cluster.py
python classify.py
python summarize.py
```

Here is what each script did:

- `collect.py`: This collects data used in the analysis. It submits queries to Twitter API. The data is raw and come directly from the original source -- that is, it is not using data that others have already collected and processed for you (e.g., you may not use [SNAP](http://snap.stanford.edu/data/index.html) datasets). Running this script should create a file or files containing the data that you need for the subsequent phases of analysis.
- `cluster.py`: This reads the data collected in the previous steps and use any community detection algorithm to cluster users into communities. It would write "cluster_output.txt" to save the results. The screen name are selected depends on how many times they mentioned national parks in their tweets, and the "network.png" shows their follow/friends relationships of each others.
- `classify.py`: This classifies the tweets got from collect.py and new tweets depends on the most mentioned top 20 national parks, and using AFFIN to rank each national park.
- `summarize.py`: This should read the output of the previous methods to write a textfile called `summary.txt` containing the following entries:
  - Number of users collected: // read 'users.txt', length
  - Number of messages collected: // read 'num_tweets.txt', sum
  - Number of communities discovered: // read 'clusters.txt' len
  - Average number of users per community: // read 'clusters.txt' calc avg
  - Number of instances per class found: // read 'class.txt' split by '\'
  - One example from each class: // per class: <classname>\t<number>\t<example>\n

Additionally, please read the plain text file called 'description.txt' that contains a brief summary of what the code does and other conclusions I have made from the analysis.

