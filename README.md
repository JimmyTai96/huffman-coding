# huffman-coding

Huffman encoding and decoding in Java, built on a hand-written generic min-heap.

## How it works

1. Count how often each character appears in the input
2. Put one single-node tree per character into a **min-heap**, keyed by frequency
3. Repeatedly merge the two lightest trees until one **Huffman tree** remains
4. Walk the tree to give every character a prefix-free bit code (left = `0`, right = `1`)
5. Encode the text, write it to a file, then decode it back by walking the tree

```
Character encodings:
{ =1100, a=01, b=1011, c=11010, d=11011, e=10010, f=001, h=1110, ...}
```

The encoded output is written as a text string of `0`s and `1`s, so you can read it.

## Run

```bash
javac *.java
java HuffmanEncodeDecode
```

The program asks for the input file, the output file, and the file to decode. It reads the first line of the input file.

## Files

| File | Role |
| --- | --- |
| `HuffmanEncodeDecode.java` | Main program: frequency count, tree building, encode, decode |
| `MinHeap.java` | Generic array-based min-heap |
| `HuffTree.java`, `HuffBaseNode.java`, `HuffLeafNode.java`, `HuffInternalNode.java` | Huffman tree and node classes |

Data structures coursework. The node classes follow the design in Shaffer's *Data Structures and Algorithm Analysis*.
