Suffix Array and LCP Array Implementation Report
Introduction
This project implements the construction of a suffix array and longest common prefix (LCP) array for a given input string. The suffix array is a powerful data structure widely used in string processing tasks such as pattern matching, data compression, and bioinformatics. The LCP array provides valuable information about the longest common prefixes between consecutive suffixes in the sorted suffix array, which enables efficient string queries.

The implementation uses a straightforward method for suffix array construction by sorting all suffixes lexicographically. The LCP array is computed efficiently using Kasai’s algorithm, which operates in linear time based on the suffix array.

Algorithm Description
Suffix Array Construction
The suffix array is built by:

Enumerating all suffixes of the input string, each represented by its start index and the substring starting there.
Sorting these suffixes in lexicographical order.
Extracting the starting indices of the sorted suffixes to form the suffix array.
The time complexity of this approach is O(n log n) where n is the length of the input string, due to sorting. Although more advanced algorithms can build suffix arrays in O(n) time, this method suffices for moderate input sizes and clarity.

LCP Array Construction (Kasai’s Algorithm)
The LCP array stores, for each pair of adjacent suffixes in the suffix array, the length of their longest common prefix. Kasai’s algorithm computes the LCP array in O(n) time by leveraging the suffix array and a rank array that maps suffix start indices to their positions in the suffix array. It minimizes repeated comparisons by reusing previous LCP results.

Testing and Results
The implementation was tested on three input strings of varying lengths:

Short input: banana
Medium input: (Several hundred characters, not shown here)
Long input: (Several thousand characters, not shown here)
Here we include the testing results for the short input example:

Input (input1.txt):


Copy code
abcabcd
Output (output1.txt):


Copy code
Suffix Array: [0, 3, 1, 4, 2, 5, 6]
LCP Array: [3, 0, 2, 0, 1, 0, 0]

Suffixes:
0: abcabcd
3: abcd
1: bcabcd
4: bcd
2: cabcd
5: cd
6: d
The suffix array correctly orders the suffixes of "abcabcd" lexicographically by their start indices. The corresponding LCP array values represent the length of the longest common prefix between consecutive suffixes.

Performance Observations
For long and longest length strings, the program executes quickly and outputs accurate suffix and LCP arrays.
The main bottleneck is the suffix array construction by sorting suffix strings via substring extraction, which may become costly for very long strings.
Kasai’s algorithm for LCP computation runs efficiently in linear time after the suffix array is built.
Future optimizations could include using advanced suffix array construction algorithms such as SA-IS for large-scale inputs.
Conclusion
The project successfully implements and tests suffix array and LCP array construction. The provided code and sample tests demonstrate correct behavior on strings of different sizes. This foundation can be extended for use in more complex string processing applications or optimized for performance on very large datasets.
