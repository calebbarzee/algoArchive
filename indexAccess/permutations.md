## Problem
Given a sequence of n integers, p(1),p(2),...,p(n) where each element is distinct and satisfies 1<=p(x)<=n. For each x where 1<=x<=n, that is x increments from 1 to n, find any integer such that p(p(y))->x  and keep a history of the values of y in a return array.

## Function Description
permutationEquation has the following parameter(s):
int p[n]: an array of integers

## Returns
int[n]: the values of y for all x in the arithmetic sequence 1 to n

## Input Format 
Contains n space-separated integers p[i] where 1<=i<=n.

## Constraints
1<=n<=50
1<=p[i]<=50 where 1<=i<=n
Each element in the sequence is distinct.

## Solution
#### Pseudocode
```
FUNCTION permutation(p: [INTEGER]) -> [INTEGER] {
   SET indices: [INTEGER] = [1...n]
   SET result: [INTEGER]

   // n = number of elements in array (length of p)
   FOR i in 1...n {
      SET indices[p[i-1]-1] = i
   }
   FOR j in 1...n {
      SET result.append(indices[indices[j-1]-1])
   }
   RETURN result
}
```
#### Swift

```
func permutationEquation(p: [Int]) -> [Int] {
    assert(p.count>0)
    var indices: [Int] = Array(1...p.count)
    var result: [Int] = []
    for i in 1...p.count {
        indices[p[i-1]-1] = i
    }
    for j in 1...p.count {
        result.append(indices[indices[j-1]-1])
    }
    return result
}
```