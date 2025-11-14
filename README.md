# Suffix Array and LCP Implementation (Kasai's Algorithm)

## Overview
This repository contains a Java implementation of constructing a suffix array and LCP (Longest Common Prefix) array using Kasai's algorithm. The code reads input from a file, computes the arrays, and writes the output to another file.

## Algorithm Details
- Suffix Array is constructed by sorting all suffixes lexicographically (O(n log n) complexity due to sorting).
- LCP Array is built in O(n) time with Kasai's algorithm.
- The suffix array stores starting indices of sorted suffixes.
- The LCP array stores the lengths of longest common prefixes between adjacent suffixes in the suffix array.

## Testing
- Input string length and content are read from `input1.txt`.
- This example uses the string `"banana"` of moderate length.
- Output is written to `output1.txt` showing the suffix array, LCP array, and the list of suffixes.

## Results Summary
For input `"banana"`:
- Suffix Array: [5, 3, 1, 0, 4, 2]
- LCP Array: [1, 3, 0, 0, 2, 0]  

This matches the expected lexicographic order of suffixes and their longest common prefixes.

## How to Run
1. Compile:
