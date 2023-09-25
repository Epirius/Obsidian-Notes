- Two kinds of [[process|processes]] (readers, writers) share a [[database]]
- Readers: examine database records
- Writers: both examine and update the database
- each transaction (if executed in isolation): transforms the database from one consistent state to another

- Writers: must have exclusive access to the database
- Readers: any number of readers may concurrently execute transactions, assuming no writer accessing the database

- Readers: must wait until no writers are accessing the database
- Writers: must wait until no readers or other writers are accessing the database

- this mimics the [[rust]] [[borrow checker]]

