# Mini API Reference (GitHub REST v2022-11-28)

> All requests need the header  
> `Authorization: Bearer <YOUR_TOKEN>`  
> `X-GitHub-Api-Version: 2022-11-28`  

| Endpoint | Verb | Key params | Pagination | Notes |
| -------- | ---- | ---------- | ---------- | ----- |
| **`/search/repositories`** | GET | `q`, `sort`, `order`, `per_page`, `page` |  Custom rate-limit: **30 req/min** when authed |
| **`/repos/{owner}/{repo}/commits`** | GET | `sha`, `path`, `since`, `until`, `per_page`, `page` |  Standard core limit 5 000 req/h  |
| **`/repos/{owner}/{repo}/contents/{path}`** | GET | `ref` (branch or SHA) | — | Returns file or directory contents, Base64-encoded for files |

### Rate limits
* **Core** (most endpoints): *5 000 requests per hour* per user/token
* **Search**: *30 requests per minute* (authenticated)
* Check your remaining quota anytime via **`GET /rate_limit`**.

### Required headers
Accept: application/vnd.github+json
Authorization: Bearer $GH_TOKEN
X-GitHub-Api-Version: 2022-11-28
