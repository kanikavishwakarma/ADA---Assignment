# Implement the Huffman coding algorithm to compress a given string in C or Python.

from heapq import heappush, heappop
from collections import defaultdict
import sys


class HuffmanNode:
    def __init__(self, freq, char=None, left=None, right=None):
        self.freq = freq
        self.char = char
        self.left = left
        self.right = right

    def __lt__(self, other):
        return self.freq < other.freq


def build_freq_dict(string):
    freq_dict = defaultdict(int)
    for char in string:
        freq_dict[char] += 1
    return freq_dict


def build_huffman_tree(freq_dict):
    heap = []
    for char, freq in freq_dict.items():
        node = HuffmanNode(freq, char)
        heappush(heap, node)

    while len(heap) > 1:
        node1 = heappop(heap)
        node2 = heappop(heap)
        freq = node1.freq + node2.freq
        parent_node = HuffmanNode(freq, left=node1, right=node2)
        heappush(heap, parent_node)

    return heap[0]


def build_code_table(node, code, code_table):
    if node.char:
        code_table[node.char] = code
    else:
        build_code_table(node.left, code + '0', code_table)
        build_code_table(node.right, code + '1', code_table)


def huffman_encode(string):
    freq_dict = build_freq_dict(string)
    root = build_huffman_tree(freq_dict)
    code_table = {}
    build_code_table(root, '', code_table)

    encoded_string = ''
    for char in string:
        encoded_string += code_table[char]

    return encoded_string, code_table


def huffman_decode(encoded_string, code_table):
    rev_table = {code: char for char, code in code_table.items()}
    decoded_string = ''
    code = ''
    for bit in encoded_string:
        code += bit
        if code in rev_table:
            decoded_string += rev_table[code]
            code = ''
    return decoded_string


# example usage
s = "Hello, world!"
encoded_str, code_table = huffman_encode(s)
print(f"Original string: {s}")
print(f"Encoded string: {encoded_str}")
print(f"Code table: {code_table}")
decoded_str = huffman_decode(encoded_str, code_table)
print(f"Decoded string: {decoded_str}")
