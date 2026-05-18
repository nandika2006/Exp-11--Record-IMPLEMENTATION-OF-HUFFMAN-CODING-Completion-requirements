# EX. NO: 11
# Huffman-Coding
## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7

## Algorithm:
### Step1:
Get the input String

### Step2:
Calculate frequency of each character in the input string

### Step3:
Create tree nodes

### Step4:
Main function to implement Huffman coding

### Step5:
Generate Huffman codes

## Program:
Developed by: NAME - NANDIKA S
REGISTER NO - 212224230175

``` Python
input_string = "NANDIKA S"
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1
nodes = [[char, freq] for char, freq in frequency.items()]
while len(nodes) > 1:
    nodes = sorted(nodes, key=lambda x: x[1])
    left = nodes.pop(0)
    right = nodes.pop(0)

    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)

huffman_tree = nodes[0]
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)
print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")

```
## Output:

### Print the characters and its huffmancode
<img width="274" height="212" alt="image" src="https://github.com/user-attachments/assets/d9b03e63-d90e-48aa-b2df-1460115d7d9b" />

## Result
Thus the huffman coding was implemented to compress the data using python programming.
