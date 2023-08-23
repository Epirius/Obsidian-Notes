a stable matching algorithm is an [[Algorithm]] that match to sets, where each item in each set has a preference list for who they want to match with in the opposite set.

for example a set of men and a set of women who each has a preference for who they want to match with of the opposite sex.


a stable matching algorithm would match all items in the sets in such a way as to maximize preference.

an [[unstable matching]] algorithm would be an algorithm where if one item finds a better match, this would result in lots of other matches braking up because each of the items in the other matches might find a better match.






------
def:

A matching of H (hospital), S (student) is a set M of pairs: M = {(h,s), {h',s'}, (h'', s'') ... }. such that each h ∈ H and s ∈ S appears in at most one pair.
A matching M is perfect if |M| = |H| = |S|

A perfect relation for a student S is an ordering where h > s > h'

given a perfect matching M with (h, s) ∈ M and (h', s') ∈ M, if s' > h > s & h > s' > h', then (h, s') is an unstable pair.

-----


-----
Stable Matching 

Input: Sets S, H, with preference relations for all s and h
Output: A stable, perfect matching M.

-----
