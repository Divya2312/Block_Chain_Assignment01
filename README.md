# Block_Chain_Assignment01

Below is the image of blockchain which is created.


![Screenshot (1538)](https://user-images.githubusercontent.com/81798803/194301606-82a9d26b-49c6-4406-a0b1-ee54e1517435

1)The Blocks are created by below given code, which is shown in daigram.
class Block:
  def _init_(self,data,hash,prev_hash):
    self.data=data
    self.hash=hash
    self.prev_hash=prev_hash

2)To create a blockchain we had used the hash , so hash is generated so for generating hash we had used the sha-256.
SHA-256 is an algorithm used for hash functions and is a vital component of contemporary cybersecurity.SHA-256 is a patented cryptographic hash function that outputs a value that is 256 bits long.

for  generating hash , we import the hashlib which  will provide the sha-256 function (import hashlib).

3)Now, Blockchain is created.The first block created is genesis Block,so
for creation, two variables are used hashLast and Hashstart.
hashLast=hashGenerator('gen_last'),hashStart=hashGenerator('gen_hash').Then the genesis block is created which consist of data(gen_data),hashStart(has),hashlast(previous data) and it is chained using self.chain.After that  add_block function is created inside the same class
code:
class Blockchain:
  def _init_(self):
    hashLast=hashGenerator('gen_last')
    hashStart=hashGenerator('gen_hash')
    
    genesis=Block('gen_data',hashStart,hashLast)
    self.chain=[genesis]
    
  def add_block(self,data):
    prev_hash=self.chain[-1].hash
    hash=hashGenerator(data+prev_hash)
    block=Block(data,hash,prev_hash)
    self.chain.append(block)





    
