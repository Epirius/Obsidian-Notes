- Critical reference: a reference to a variable written to by another [[thread]]

an assignment statement x=e; satisfies A.M.O property if:
- either e contains at most one critical reference and x is not read by another thread
- or e contains no critical references, in which case x may be read by other threads