# 1 Caching

Caching is a technique used to store frequently accessed data in a temporary storage location to improve performance and reduce redundant computations or database queries. It is benefit for an application that requires read more than write.

# 1.1 Strategies

- Cache-Aside (Lazy Loading) – The application checks the cache first; if the data is missing, it fetches from the database and stores it in the cache.

- Read-Through Cache – If data is not in the cache, it is fetched from the database and stored in the cache for future use.

- Write-Through Cache – Data is written to both the cache and the database simultaneously. Ensures consistency but can be slower.

- Write-Back (Lazy Write) Cache – Data is written to the cache first and then asynchronously updated in the database. Improves write speed but risks data loss if the cache fails.