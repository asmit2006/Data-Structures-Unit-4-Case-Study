# Data-Structures-Unit-4-Case-Study

# Case Study: Dictionary Application Using Hash Tables

## Aim
To implement a dictionary application that stores words and their meanings and retrieves them efficiently using hashing, with collision resolution.

## Description
The application uses a **hash table** to map each word to a bucket. A simple hash function calculates a bucket index from the characters in the word. If multiple words map to the same bucket, **separate chaining** resolves the collision: each bucket contains a linked list of entries.

The application includes starter vocabulary and an interactive menu.

## Features
- Add a new word and meaning.
- Update the meaning of an existing word.
- Search for a word (case-insensitive).
- Delete a word.
- Display all entries in alphabetical order.
- Display hash-table buckets to observe collisions.
- Validate empty words and meanings.

## Requirements
- Python 3.x
- No external packages required.

## How to Run
Save `dictionary_hash_table.py` and run:

```bash
python dictionary_hash_table.py
```

Choose an operation from the menu and follow the prompts.

## Collision Resolution
A hash function maps each word to an array index:

`index = hash(word) % capacity`

This implementation uses a deterministic character-based hash function. When two different words map to the same index, both entries are stored in that bucket's linked list. Searching and deleting traverse the chain to find the matching word.

## Time Complexity
Let `n` be the number of stored words and `m` the number of buckets.

| Operation | Average case | Worst case |
|---|---:|---:|
| Add / update | O(1) | O(n) |
| Search | O(1) | O(n) |
| Delete | O(1) | O(n) |
| Display all entries | O(n log n) | O(n log n) |

Average-case performance assumes a reasonably distributed set of keys. If many words collide into one bucket, operations can take O(n). Displaying all entries sorts them alphabetically, which takes O(n log n).

## Example
- Add `python` with meaning `A high-level programming language.`
- Search `PYTHON` — the search is case-insensitive.
- Display all words to view the dictionary entries.
- Choose **Show hash-table buckets** to see which words share a bucket.

## Conclusion
This case study demonstrates how hashing supports fast dictionary lookup and how separate chaining handles collisions. It also illustrates adding, updating, searching, deleting, and displaying key-value pairs.
