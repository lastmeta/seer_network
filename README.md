# Seer Network


## Initial Idea

https://www.reddit.com/r/CryptoTechnology/comments/ki9gii/why_dont_we_make_a_seer_network/

Why don't we make a Seer Network?

The premise behind this idea is simple, but kind of "hidden in plain sight" for most people. Let me try to motivate the idea with a short paragraph about the brain.

When you walk into a familiar room you're not surprised. The door opens the way you would expect, the light switch is in the place you would have expected it to be and everything's normal. The only reason you aren't surprised is that you're brain, under the hood, actually is making predictions all the time about what you're going to experience next. That's how it knows what you expect, and you feel like the room is familiar. But if something unexpected happens then that means some real predictions, produced by real neurons in the subconscious, were violated and you're attention gets directed to the anomaly, and you notice it consciously.

Ok, that's the basic premise: if you have a network of nodes that behave somewhat intelligently (like neurons or cortical columns), and if they work together to predict the future of their individual and therefore collective inputs the network can become generally intelligent.

Since this network is fundamentally focused on predicting the future we could call it a Seer Network. And I think we could make a prototypical distributed Seer Network in a pretty simple way using distributed consensus technologies. I could use some help designing this but I think I have a basic, highest-level implementation that would work. Please give me your thoughts...

First, use a blockchain to establish a distributed datastream publisher and subscriber database. It contains no data from datastreams but does contain information on who subscribes to who. You can issue a transaction saying, "I am making my datastream available, here's how you access it, and here's how much it costs." Subscribers will issue transactions saying, "I'd like to subscribe to your datastream, here's some coin, let me sign this so everyone has proof of who I am." That's basically the entire blockchain because the actual data is transferred directly, peer to peer off-chain.

Secondly, we must have some simple mechanism for validating the subscription: a publisher should be forced to give every subscriber the same data.

In order to achieve this we'll use the "natural consensus" algorithm, you know the one Hashgraph tried to steal from the world. Natural consensus requires that all the members of the network be known to all the other members of the network. Well, that's exactly what we have on the blockchain, members A, B, C, and D are subscribed to datastream X. So A, B, C, and D can connect directly and gossip about what is being published on X datastream. Maybe A and B both subscribe to datastream Y so they gossip about that too. On really popular datastreams natural consensus may be the chosen way to broadcast the information in the first place (rather than the publisher sending it to everyone directly).

Alright, only one last piece. I know what you're thinking, "what does this have to do with prediction?" Well, that was all just establishing the network; the infrastructure to run the Seer network on. (And I'm sure there are other ways to do it like there is the ocean protocol and other stuff like it, but I don't know how all the other options work, I just think this is the simplest design I could come up with, but in theory, publishers could use anything to make their datastreams available).

So what makes it a Seer network is its efficiency to facilitate, and its economic incentive structure to encourage publishers to publish datastreams that are predictions of other datastreams. That's it.

We need to make a protocol for transactions to easily say, "the contents of this datastreams is a prediction of X datastream Y moments into the future, at Z resolution." To economically incentivize predictive datastreams the network would have to carve out some of the coinbase reward for predictors that the future proves to be most useful and most accurate.

Now, to discuss the real-world application of the Seer Network we can just imagine what would happen if all of the world's datastreams were on it. In order to understand all the data of the world in the context of all the other data of the world, you need lots and lots of eyes looking at the data. You can't do it with one supercomputer, you need bandwidth. And you need all those computers which are looking at the data to communicate with each other where appropriate. That communication, on the most fundamental level could be and probably should be some form of a prediction on the data because predictions, by definition, take all available information into account - they imply the model that produced them.

If you have one datastream, like the price of a stock, you can only predict it in terms of its own history. But if you have other stock histories you can begin to make correlations, and if you have predictions of other stocks made by others who are collectively looking at a larger picture than you, you can take many many more times the number of correlations you can discover into account. There's an exponential return on investment when you have a network of predictors, rather than just one.

With more layers on top of this network - layers that translate the underlying streams into human speech, for example - you could make a "Google of the future," essentially the Seer network's combined understanding of how everything will evolve. With NLP layers on top all you'd have to do is ask and you'd almost know what's going to happen to anything you queried.

A lot of distributed intelligent systems in mainstream thought today are about sharing models. This is a mistake. Once you share a model the recipient needs a model in order to know how to interpret the results. That's not to say there isn't any value in doing so, even the brain learns by analogy but, fundamentally, on the lowest, subconscious layers of general intelligence it is best to share a prediction of the future because the prediction is immediately consumable and still contains all the implied correlations of hidden data that produced the hidden model.

Sharing predictions allows intelligence to scale.

_Let your workings remain a mystery._
_Just show people the results._
_-Lao Tzu_

In conclusion the idea is basically made of 3 parts:

Blockchain is used as a distributed database of publishers and subscribers, (providing identity with cryptographic signature connected to real datastream costs and blockchain fees).

The blockchain identity allows us to implement the natural consensus amongst subscribers per datastream which shoulders the bandwidth burden so anyone can be a popular publisher and gives subscribers a high degree of confidence in the data.

Transaction protocol optimizations (and facilitating smart contracts) plus economic incentives produce a layered hierarchy of predictive datastreams.

The entire world is understood.

Please let me know what you think of this idea, and thank you so much for your attention.

## About this Repo

So to start developing this I'm first of all attempting to bring simple examples of these elements together under the three top-level folders:

- Natural Consensus is the Hashgraph permissioned consensus algorithm.
- peer to peer is some code for creating a peer to peer network.
- blockchain is the distributed database element.

Once all these pieces are gathered and understood they'll be incorporated into a main architecture that runs the whole thing.
