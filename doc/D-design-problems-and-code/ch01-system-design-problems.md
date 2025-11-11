# System Design Problems

.. :**DRAFT**

For each problem, we will follow the following steps:

- Requirements
- Back-of-the-envelope calculations
- System APIs
- Database Design
- High-Level Design
- Detailed Design
- Scaling
- Additional Notes
- References
- Summary

Each problem will be categorized into the following categories:

- Read-heavy or Write-heavy or update-heavy (in-place update or append-only)
- Small or Large Data Size (1MB -> 1GB for single content)
- Relationship between data (One-to-One, One-to-Many, Many-to-Many)
- Latency-sensitive or Throughput-sensitive or Resource-intensive
- Memory-intensive or CPU-intensive or IO-intensive (storage) or Network-intensive
- High Availability or Consistency
- Very Short session, Short session or Long session
- Collaborative session (one session per Entity) or Independent session (one session per User)
- Event Drive or Request-Driven

Non Functional Requirements for each problem:

- Latency: ~100ms at 95th percentile
- Availability: 99.99% (4 nines)
- Consistency: Strong consistency or Eventual consistency

Common System Design solutions for solving the fundamental problems:

- Indexing for solving the search problem
- Caching for solving the read-heavy problem
- Sharding for solving the write-heavy problem
- Replication for solving the availability problem
- Load Balancing for solving the throughput problem
- Consistent Hashing for solving the scaling problem
- Rate Limiting for solving the resource-intensive problem
- Leader Election for solving the consistency problem
- Pub-Sub for solving the event-driven problem
- Map-Reduce for solving the batch processing problem
- Two-Phase Commit for solving the distributed transaction problem
- CAP Theorem for solving the distributed system problem
- Paxos, Raft, Zab for solving the distributed consensus problem
- CDN for solving the global traffic problem or latency problem
- Bloom Filter for solving the set membership problem
- LRU Cache for solving the caching problem
- B-Tree for solving the indexing problem
- Trie for solving the prefix search problem
- BitMap for solving the counting problem
- Topological Sort for solving the dependency problem
- Dijkstra for solving the shortest path problem

Pattern for solving the system design problems:

- Storing large binary objects (images, videos, files) in the cloud storage (S3, GCS, Azure Blob Storage)
- storing the metadata in the database (RDS, DynamoDB, BigTable)
- Storing the time-series data in the time-series database (InfluxDB, TimescaleDB, OpenTSDB)
- Using websocket for real-time communication
- using REST API for request-driven communication
- using gRPC for low-latency communication
- using Kafka for event-driven communication
- using memcached or redis for distributed caching that can scale horizontally
- using the CDN for global traffic

## 1.1. Design a URL Shortening service like TinyURL

- Data Size: 1 billion URLs per month (write) and 100 billion URL redirections per month (read)
- Traffic: 1000 URL redirections per second at peak time (read)
- Total Data Size:
  - Write: 1 billion URLs * 6 bytes = 6 GB
  - Read: 100 billion URLs * 6 bytes = 600 GB
- Problem Category: read-heavy, small data size, latency-sensitive, one-to-one mapping, short session, request-drive
- Additional Notes:
  - Use the hash function for generating the short URL
  - Use the database for storing the mapping between the short URL and the long URL
  - Use the cache for storing the frequently accessed short URL
  - Use the rate-limiting for preventing the spamming of the short URL redirection
  - Use the CDN for caching the short URL redirection

## 1.2. Design a Web Crawler like Google

- Data Size: 1 billion web pages
- Traffic: 5 requests per second
- Total Data Size: 1 billion web pages * 100KB = 100PB
- Problem Category: write-heavy, large data size, latency-sensitive, one-to-many mapping, long session, request-driven
- Additional Notes:
  - Use the bloom filter for checking the set membership
  - Use the LRU cache for storing the web pages
  - Use the B-Tree for indexing the web pages

## 1.3. Design a Typeahead Suggestions like Google Search

- Data Size: 1 billion searches per month
- Traffic: 1000 searches per second
- Total Data Size: 1 billion searches * 100 bytes = 100 GB
- Problem Category: read-heavy, small data size, latency-sensitive, many-to-many mapping, short session, request-driven
- Additional Notes:
  - Use the trie for storing the search queries
  - Use the autocomplete for suggesting the search queries

## 1.4. Design a system like Facebook Newsfeed

- Data Size: 1 billion users with 100 friends each
- Traffic: 10M new stories per day
- Total Data Size: 1 billion users * 100 friends * 10 stories * 100KB = 10PB
- Problem Category: read-heavy, large data size, latency-sensitive, many-to-many mapping, long session, request-driven
- Additional Notes:
  - Use the graph database for storing the relationship between the users and the stories
  - Use the recommendation system for recommending the stories to the users

## 1.5. Design a system like Twitter

- Data Size: 500 million tweets per day
- Traffic: 100 million tweets per day
- Total Data Size: 500 million tweets * 100 bytes = 50 GB
- Problem Category: write-heavy, small data size, latency-sensitive, one-to-many mapping, short session, request-driven
- Additional Notes:
  - Use the tweet compression for storing the tweets and transferring the tweets
  - Use the tweet search for finding the tweets

## 1.6. Design a system like Instagram

- Data Size: 500 million photos per day
- Traffic: 100 million photos per day
- Total Data Size: 500 million photos * 1MB = 500TB
- Problem Category: write-heavy, large data size, latency-sensitive, one-to-many mapping, short session, request-driven
- Additional Notes:
  - Use the image compression for storing the photos and transferring the photos
  - Use the image search for finding the photos

## 1.7. Design a system like Youtube

- Data Size: 500 million videos per day
- Traffic: 100 million videos per day
- Total Data Size: 500 million videos * 1GB = 500PB
- Problem Category: write-heavy, large data size, latency-sensitive, one-to-many mapping, short session, request-driven
- Additional Notes:
  - Use the video compression for storing the videos and transferring the videos
  - Use the video streaming for playing the videos
  - Use kafka for processing the videos in real-time

## 1.8. Design a system like Dropbox

- Data Size: 500 million files per day
- Traffic: 100 million files per day
- Total Data Size: 500 million files * 1GB = 500PB
- Problem Category: write-heavy, large data size, latency-sensitive, one-to-many mapping, short session, request-driven
- Additional Notes:
  - Use the file system for storing the binary files
  - Use the database for storing the metadata of the files

## 1.9. Design a system like Google Docs

- Data Size: 500 million documents per day
- Traffic: 100 million documents per day
- Total Data Size: 500 million documents * 1GB = 500PB
- Problem Category: write-heavy, large data size, latency-sensitive, one-to-many mapping, collaborative session, request-driven
- Additional Notes:
  - Use the Operational Transformation for handling the concurrent editing of the documents
  - Use the CRDT for handling the concurrent editing of the documents

## 1.10. Design a system like Google Drive

- Data Size: 500 million files per day
- Traffic: 100 million files per day
- Total Data Size: 500 million files * 1GB = 500PB
- Problem Category: write-heavy, large data size, latency-sensitive, one-to-many mapping, independent session, request-driven
- Additional Notes:
  - Use the file system for storing the binary files
  - Use the database for storing the metadata of the files

## 1.11 Design a system like giphy

- Data Size: 500 million gifs per day
- Traffic: 100 million gifs per day
- Total Data Size: 500 million gifs * 1MB = 500TB
- Problem Category: read-heavy, small data size, latency-sensitive, one-to-many mapping, short session, request-driven
- Additional Notes:
  - Use the image search for finding the gifs
  - Use the image compression for storing the gifs and transferring the gifs

## 1.12 Design a system like Pinterest

- Data Size: 500 million pins per day
- Traffic: 100 million pins per day
- Total Data Size: 500 million pins * 1MB = 500TB
- Problem Category: write-heavy, large data size, latency-sensitive, one-to-many mapping, short session, request-driven
- Additional Notes:
  - Use the graph database for storing the relationship between the pins and the users
  - Use the recommendation system for recommending the pins to the users

## 1.13 Design a system like Uber
- Data Size: 500 million rides per day
- Traffic: 100 million rides per day
- Total Data Size: 500 million rides * 1KB = 500GB
- Problem Category: write-heavy, small data size, latency-sensitive, one-to-many mapping, short session, request-driven
- Additional Notes:
  - Use the geospatial index for finding the nearest driver
  - Use the rate-limiting for preventing the spamming of the ride request
