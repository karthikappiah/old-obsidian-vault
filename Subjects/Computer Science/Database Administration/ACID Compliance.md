- A ==transaction== is a series of ==queries== that perform a task.

  ```sql
	START TRANSACTION;
	
	UPDATE accounts 
	SET balance -= 100 
	WHERE user = "Mr. Krabs";
	
	UPDATE accounts 
	SET balance += 100 
	WHERE user = "SpongeBob";
	
	COMMIT;
  ```

- ==Atomicity== ensures the queries that make up a transaction act as one logical unit to maintain ==data integrity==.
	- Therefore, a transaction is only ==committed== if every query is successful; otherwise, the transaction is ==rolled back==.
- ==Isolation== ensures that concurrent transactions don't interfere with each other when making changes to data.
	- [[Isolation Levels|Isolation levels]] determine how isolated transactions are from each other's changes to combat [[Read Phenomena|read phenomena]].
- ==Consistency== ensures that transactions predictably change data to maintain data integrity.
- ==Durability== ensures that the changes made by committed transactions survive any type of failure.
	- Changes are written to the write-ahead log (WAL) before being applied to database files.