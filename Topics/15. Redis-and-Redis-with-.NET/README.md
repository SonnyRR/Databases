<!-- section start -->
<!-- attr: {id: 'title', class: 'slide-title', hasScriptWrapper: true} -->
# Redis and Redis with .NET
## In-memory store

<div class="signature">
    <p class="signature-course">Databases</p>
    <p class="signature-initiative">Telerik Software Academy</p>
    <a href="https://telerikacademy.com" class="signature-link">https://telerikacademy.com</a>
</div>

<!-- section start -->
<!-- attr: {id: 'table-of-contents'} -->
# Table of Contents
- Redis overview
  - Setup
- Data types
  - Commands
- Transactions
- Messages
- Persistent storage
- Using Redis with .NET

<!-- section start -->
<!-- attr: {class: 'slide-section', showInPresentation: true} -->
# Redis overview
## What is Redis?

<!-- attr: {showInPresentation: true} -->
<!-- # Redis overview -->
- **Redis** is in-memory data structure store
  - Open source (BSD 3-clause license)
- **Source**: https://github.com/antirez/redis/
- **Site**: https://redis.io/
  - **Interactive tutorial**: http://try.redis.io/
- Has bindings for a lot of languages

<!-- attr: {showInPresentation: true} -->
# Setup
- Install from package manager
  - or download `msi` for Windows from
  https://github.com/MSOpenTech/redis/releases
- `redis-cli` command is installed
  - Has cool autocomplete

<!-- section start -->
<!-- attr: {class: 'slide-section', showInPresentation: true} -->
# Data types
## Data manipulation

<!-- attr: {showInPresentation: true} -->
<!-- # Data types -->
- **Redis** saves values under keys
- Values may be:
  - Strings
  - Lists
  - Sets, Sorted sets
  - Hashes

<!-- attr: {showInPresentation: true} -->
<!-- # Data types -->
- Strings
  - May be used as numbers
  - May be used as bitsets
- Commands:
  - `GET` key
  - `SET` key value
  - `APPEND` key value
  - `SETRANGE` key offset value
  - `GETRANGE` key start end

<!-- attr: {showInPresentation: true} -->
<!-- # Data types -->
- Strings
  - `INCR`, `DECR` key
  - `INCRBY`, `DECRBY` key increment
  - `INCRBYFLOAT`, `DECRBYFLOAT` key increment

<!-- attr: {showInPresentation: true} -->
<!-- # Data types -->
- Lists
 - `LPOP`, `LPUSH`
 - `RPOP`, `RPUSH`
 - `LLEN`
 - `LRANGE`

<!-- attr: {showInPresentation: true} -->
<!-- # Data types -->
- Sets
  - `SADD`
  - `SREM`
  - `SISMEMBER`
  - `SCARD`

<!-- attr: {showInPresentation: true} -->
<!-- # Data types -->
- Sorted sets
  - `ZADD`
  - `ZREM`
  - `ZRANGE`
  - `ZCARD`

<!-- attr: {showInPresentation: true} -->
<!-- # Data types -->
- Hashes
  - `HSET`
  - `HGET`
  - `HGETALL`
  - `HDEL`

<!-- section start -->
<!-- attr: {class: 'slide-section', showInPresentation: true} -->
# Transactions
## Executing multiple operations

<!-- attr: {showInPresentation: true} -->
<!-- # Transactions -->
- Transactions starts with `MULTI` command
  - Commands are queued
  - Execute them with `EXEC` command
  - No revert on failure
- `EVAL` command can be used to execute Lua script
  - Redis has builtin Lua interpreter

<!-- section start -->
<!-- attr: {class: 'slide-section', showInPresentation: true} -->
# Messages
## Subscriptions and publishing

<!-- attr: {showInPresentation: true} -->
<!-- # Messages -->
- `SUBSCRIBE` - listen
- `PSUBSCRIBE` - pattern subscribe
- `PUBLISH` - publish data
- `UNSUBSCRIBE`
- `PUNSUBSCRIBE`

<!-- section start -->
<!-- attr: {class: 'slide-section', showInPresentation: true} -->
# Persistent storage
## Saving data to disk

<!-- attr: {showInPresentation: true} -->
<!-- # Persistent storage -->
- Automatic save
  - Every `N` seconds
  - Every `M` changes
  - Can be configured with
    - `CONFIG SET save`
- Manual save with `SAVE` and `BGSAVE`

<!-- section start -->
<!-- attr: {class: 'slide-section', showInPresentation: true} -->
# Using Redis with .NET
## Bindings for `C#`

<!-- attr: {showInPresentation: true} -->
<!-- # Using Redis with .NET -->
- Use `ServiceStack.Redis`
  - https://github.com/ServiceStack/ServiceStack.Redis
- `BasicRedisClientManager`
- `RedisManagerPool`
```cs
var redisManager = new PooledRedisClientManager();
var redis = redisManager.GetClient();
```

<!-- section start -->
<!-- attr: {id: 'questions', class: 'slide-questions', showInPresentation: true} -->
<!-- # Redis and Redis with .NET
## Questions -->
