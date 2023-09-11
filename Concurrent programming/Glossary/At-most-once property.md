- Critical reference: a reference to a variable written to by another [[thread]]

an assignment statement x=e; satisfies A.M.O property if:
- either e contains at most one critical reference and x is not read by another thread
- or e contains no critical references, in which case x may be read by other threads


------

An attribute of an assignment statement x = e in which either: 
- x is not read by another process and e contains at most one reference to a variable changed by another process, or 
- x is not written by another process and e contains no references to variables changed by other processes.
Such an assignment statement will appear to execute as an atomic action.