# Hubble

By @msaug and @neeeekitos

Hubble is an onchain router that gathers all the existing pairs of an AMM and searches the most optimal route to perform a swap.
We created our own implementation of a graph, in which we store all the tokens used as liquidity in the AMM as vertices and liquidity pools between two tokens are bi-directional edges.
When all the possible routes are indentified given a maximum number of hops, we can easily evaluate the amount of tokens that each route leads to (by calling `get_amounts_out` or implementing our own algorith if we want to expand the usage to several AMMs. 
From there, it's also possible to split the orders between different routes - e.g. 30% in route n.1 and 70% in route n.2, to dispatch the liquidity more efficiently.

It was a challenging project to develop in cairo, so the docs might not be on point as we had to rush a little bit - feel free to open a PR if you spot a bug! 

### Installation
```
yarn && yarn dev
```
### Testing
```
protostar test
```
