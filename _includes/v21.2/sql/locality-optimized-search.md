Note that there is a performance benefit for queries that select a single row (e.g., `SELECT * FROM users WHERE email = 'anemailaddress@gmail.com'`). If `'anemailaddress@gmail.com'` is found in the local region, there is no need to search remote regions. This feature, whereby the SQL engine will avoid sending requests to nodes in other regions when it can read a value from a unique column that is stored locally, is known as _locality optimized search_.