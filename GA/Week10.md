# Graded Assignment 10

Q1)
Which of the following option represents the fail function (or prefix function) for pattern ABABACA in Knuth-Morris-Pratt (KMP) algorithm? <br>
A1) [0, 0, 1, 2, 3, 0, 1]
__________________________________________________________________________________________________________________________
Q2) 
For searching the pattern **aaab** by Brute force algorithm on which of the following text will result in worst case behavior?
<br>
A2) aaaaaaaaaaaa
__________________________________________________________________________________________________________________________
Q3)
We want to search a pattern in the text using Boyer-Moore skipping heuristic. For which of the following patterns the last dictionary (as discussed in the lectures) will be the biggest in size?
<br>
A3) hypothetic
__________________________________________________________________________________________________________________________
Q4)
Which of the following is True with respect to the Rabin-Karp string matching algorithm?
<br>
A4)
- [x] If the hash value of a substring of the text matches that of the pattern, then we have to match the actual substring to the pattern to guarantee that the pattern has been found.
- [x] Rabin Karp algorithm and brute force pattern searching algorithm have the same worst case time complexity.
- [x] Rabin Karp algorithm and Boyer Moore pattern searching algorithm have the same worst case time complexity
__________________________________________________________________________________________________________________________
Q5)
Consider the Rabin-Karp algorithm using modulo arithmetic to match pattern in base 10 . Taking modulo q=11 , how many **false positives** matches does the Rabin-Karp matcher encounter while searching pattern 36 in the text 591464256 ?
<br>
A5) 3
__________________________________________________________________________________________________________________________
Q6)We want to search the pattern **strawberry** in the text **straw plus berry is strawberry** what is the count of character comparisons using Boyer-Moore skipping heuristic and Brute force pattern matching respectively?
<br>
A6)
14, 37

__________________________________________________________________________________________________________________________
Q7)
Which of the following combination of input text T and pattern P will exhibit the worst case running time behavior for Boyer-Moore skipping heuristic?</br>
A7) T = 'aaaaaaaaaaaaaaa' and P = 'baa'

__________________________________________________________________________________________________________________________
Q8)
Consider the following finite automaton where q0 is the starting state and q2 is the final or accepting state , and input symbols are ∑ = {a, b, c}.
 </br>![W10G9](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/29d585cb-337b-44ea-a1e7-4e4b5a1b6d87)
</br>
Which of the following string(s) will be accepted by the given finite automaton?</br>
A8)
- [x] aaaaaaaa
- [x] aabbaabccbaab
- [x] bcbcabcbcabcbcaa
__________________________________________________________________________________________________________________________
Q9)Which of the following string(s) match the pattern ^ab(ba)*cd$?
</br>
A9)
- [x] abbacd
- [x] abcd
- [x] abbabababacd

__________________________________________________________________________________________________________________________
