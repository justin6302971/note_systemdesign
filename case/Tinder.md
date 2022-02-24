# Tinder Architecture
dive into the draft tinder architecture for system design

## Note
1. what kinds of features for this system should provide? with those features, you can think about how the system evolves ?
2. start from er diagram is a good way but might be too constrained, better think about what user's need as features. a lot easier for communication
3. start with 4 to 5 features cuz mostly you might only a an hour long interview

## Topic
1. features
2. constraints and assumptions

### Features with constraints
1. store profile 
   1. images => 5 images per user
   2. store data in blob instead of file
2. recommand matches
   1.  numbers of active users => 0.1 % of people in target market
3. note matches
4. direct messaging

#### store profile 
* client -> profile services -> db
* client -> image service -> dfs(distributed file system)

#### recommand and note matches
* client(try get recommand matches and save matches) -> matcher services -> db
* client(try send direct message )-> check matcher service and session store
  
#### direct message
* client -> xmpp ->tcp -> session store

### design detail tradeoffs
1. file vs blobs, file is cheaper, faster and can be use with cdn(content network delivery)

### tech detail
* sharding and horizontal concept concept
*  


## references
1. [tinder architecture video](https://www.youtube.com/watch?v=tndzLznxq40&list=WL&index=10)