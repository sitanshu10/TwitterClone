# Twitter Clone

This project implements a clone of Twitter. It consists of a Client, Client Parent, Server and Simulator.
It also has almost all of the functionalities that are present on a twitter engine such as tweet, retweet, followers, following, etc.

We also show the timelines of all users and the simulation of search queries on twitter.

## How to Run

Run the code using the following command in the terminal:
```bash
dotnet fsi --langversion:preview proj4.fsx arg1"
```
where arg1 = number of users to be simulated

## Main Components

The code consists of 4 main components that together simulate Twitter:

1. Server: This is the part of the code that implements the literal functionality of a server. Some examples of the functions in a server actor are distributing tweets, receiving tweets. Server aslo handles the querying part of this project, where we can search tweets according to hashtags and mentions.

2. Client: This part of the code is multiple actors that all hit the server and behave as the "users" of twitter. The clients can tweet, retweet, perform queries and can view all of their tweets / timeline if they are online.

3. Simulator: This is the main twitter simulator where it randomly assigns followers to users and follows other users. It also sends out instructions for clients to tweet, retweet, perform queries. etc.

4. Client Parent: This is the actor that spawns all of the clients and creates their respective actors.

## Format of Output

The output is printed in the terminal in the following way:
  The network (who follows who) is printed after network initialization.
  The users start tweeting.
  Feeds of the users who receive the tweets are shows in live time.
  Retweeting is performed and again, the updated feeds are shown in real time.
  The query to show the entire timesline of all users is run.
  Hashtag, Mention search queries are run and the results are shown.
  Connection/Disconnection Simulation is run to show how a user's timeline is affected depending on if the user is connected or disconnected.
  At the end, the time taken for each simulation os displayed.
  
  ## Performance / Testing
  
  The table below shows the time taken for the tasks performed. The first column indicated the number of users that were given as input during the simulation.
  
  | Number of Users | Tweeting | Re-tweeting | Printing Home Timeline (of all users) | # search queries | @ search queries | Connection/Disconnection Simulation |
  | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
  | 10 | 23.5 | 7.5 | 1023.9 | 1036.96 | 1032.96 | 3006.5 |
  | 100 | 146.47 | 134.29 | 10328.00 | 1036.464 | 1034.106 | 8041.62 |
  | 500 | 2172.57 | 2722.05 | 51459.11 | 1039.72 | 1041.90 | 56333.18 |
  | 1000 | 12114.54 | 12600.23 | 102905.01 | 1028.9 | 1037.03 | 71418.169 |
  | 2500 | 82594.91 | 143103.9 | 257955.48 | 1038.48 | 1036.20 | 176146.07 |

(All times are in ms)
