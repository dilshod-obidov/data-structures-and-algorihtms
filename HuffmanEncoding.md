# Huffman Encoding

## Common Encoding Types

- **ASCII**: 
    1. 8 bits a char 
    2. 256 chars encodable
- **Unicode**: 
    1. 16 bits a char 
    2. 65536 chars encodable 
    3. Includes ASCII encoded chars

> Both of them are fixed length encoding algorithms which brings a space wastage problem

## Huffman Encoding Binary Tree

- Each leaf node contains a char
- Label the left child's edge as "0"
- Label the right child's edge as "1"
- The above labeling gives us the code for getting the binary value for a char in the leaf 

## Building a Huffman Tree

- Find the frequencies of each symbol in the message
- Begin with the single node trees (each node contains the char val and frequency)

> Keep doing:
- Get two trees with smallest frequency
- Create a new parent node that has the sum of the values inside the two smallest nodes that you chose from the list of leaf nodes.
- The process ends when we get the root node