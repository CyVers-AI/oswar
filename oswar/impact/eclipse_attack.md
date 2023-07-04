# 5. Eclipse Attack

Category: User Target
Tags: Impact

### What is an eclipse attack?
An eclipse attack is where a malicious actor isolates a node from the rest of the network. 

It works by redirecting the target node's inbound and outbound connections to nodes that the malicious actor controls, resulting in that node not being able to communicate with the legitimate network.

This can lead to the target node wasting processing power mining blocks that can not be included on the legitimate network. In theory, this could lead to a 51% attack if the malicious actor is able to isolate enough nodes on the network and increase the value of their own processing power.

The target node could also then be a victim of a double spend attack if misdirected to accept an input that has already been used in a transaction on the legitimate network.
  

### Example
An N-confirmation double spend attack would involve a malicious actor isolating mining nodes and a merchant node from the legitimate network. The malicious actor can then broadcast a transaction with the merchant to the mining nodes, which would lead to the transaction being approved and added to a blockchain that is only in use between these eclipsed nodes. This compromised network could then mine a number of nodes until the required confirmation number is met, at which point the merchant would release the goods/services. 
  
### Mitigation
An individual node could protect itself by blocking incoming connections and whitelisting trusted nodes for outbound connections. However, if all nodes in a network were to take this approach it would prevent the network from accepting new nodes thus the network would be unable to grow.
