# Lithic – Crack the Code

## How I found the hidden challenge

While reading the job listing for Technical Support Lead at Lithic, I noticed that the word **"problem-solving"** in the requirements section was a hyperlink — unusual for a job post. I inspected the URL and saw it was a long encoded string rather than a normal web address.

## How I decoded it

The URL was **Base64-encoded**. I decoded it using Claude (AI) and it revealed a Python script (`puzzle.py`) along with instructions for completing the challenge.

## What the script does

`puzzle.py` decrypts a short password using a simple **XOR cipher**, then generates a candidate-specific **proof code** by computing a SHA-256 hash of the candidate's name, the decrypted answer, and a fixed salt string. The first 12 characters of that hash are returned as the proof code.

The script also requires the environment variable `DONT_PANIC=1` to be set before it will run — a nod to *The Hitchhiker's Guide to the Galaxy*.

## Command I ran

DONT\_PANIC=1 python3 puzzle.py \--candidate "Ivan Kucera"

## Exact output

Decrypted password: 42

Candidate: Ivan Kucera

Proof code: e11e6935e2d6

## The final decrypted answer

**42** — the answer to life, the universe, and everything (*The Hitchhiker's Guide to the Galaxy*, Douglas Adams).

## Tools used

- **Claude (Anthropic)** — to identify the Base64 encoding, decode the URL, explain the script, and compute the proof code  
- **Visual Studio** —   
- **Python 3** — to run the script and verify the output

