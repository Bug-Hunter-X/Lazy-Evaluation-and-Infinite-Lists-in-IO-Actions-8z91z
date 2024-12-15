# Haskell Lazy Evaluation Bug

This repository demonstrates a subtle bug in Haskell related to lazy evaluation and the interaction between `IO` actions and infinite lists.

The `bug.hs` file contains the buggy code.  The core issue is that the program attempts to print a portion of an infinite list inside an IO action.  Due to Haskell's lazy evaluation, the `print` function will never terminate because the next element of the infinite list is continuously evaluated.

The `bugSolution.hs` file provides a corrected version using `force` to explicitly evaluate the list segment.