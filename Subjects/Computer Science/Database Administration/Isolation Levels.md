- Different databases implement ==isolation levels== differently.
	1. `READ UNCOMMITTED` provides no isolation, allowing for dirty reads.
	2. `READ COMMITTED` ensures that each query in a transaction only reads committed changes made by other transactions, avoiding dirty reads.
	3. `REPEATABLE READ` ensures that any row a query reads in a transaction doesn't change, avoiding non-repeatable reads.
	4. `SNAPSHOT` ensures that every query only reads changes committed up to the start of the transaction, avoiding phantom reads.
	5. `SERIALIZABLE` ensures no read phenomena nor concurrency, so transactions run one after another.