# Troubleshooting & Data-Cleaning Cheatsheet

## Quick Reference Table

| Error Code | Issue | Cause | Solution | Prevention |
|------------|-------|-------|----------|------------|
| **401** | Unauthorized | Invalid/missing token | Generate new Personal Access Token | Store token securely, check expiration |
| **403** | Rate Limited | Too many requests | The Python script has built-in logic to wait for the reset time specified in the X-RateLimit-Reset header, and retry. |
| **404** | Not Found | Repository/path doesn't exist | Verify owner/repo names | Validate inputs before API calls |
| **422** | Unprocessable | Invalid search query | Check query syntax | Use API documentation examples |
| **500** | Server Error | GitHub API issue | Retry after delay retry logic exists (3) re-tries |

## Detailed Solutions

###  Authentication Issues (401)

**Symptoms:**
```json
{
  "message": "Requires authentication",
  "documentation_url": "https://docs.github.com/rest"
}
```

**Quick Fixes:**
1. **Check Token Format**
   ```python
   # ❌ Wrong
   headers = {"Authorization": "your_token_here"}
   
   # ✅ Correct
   headers = {"Authorization": "Bearer your_token_here"}
   ```

2. **Verify Token Permissions**
   - Go to GitHub → Settings → Developer settings → Personal access tokens
   - Ensure `public_repo` scope is checked
   - Token should not be expired

3. **Test Token Validity**
   ```bash
   curl -H "Authorization: token YOUR_TOKEN" https://api.github.com/user
   ```

###  Rate Limiting (403)

**Symptoms:**
```json
{
  "message": "API rate limit exceeded",
  "documentation_url": "https://docs.github.com/rest/overview/resources-in-the-rest-api#rate-limiting"
}
```
Check your rate limit https://docs.github.com/en/rest/rate-limit/rate-limit?apiVersion=2022-11-28

### 📂 Repository Access Issues (404)

**Symptoms:**
```json
{
  "message": "Not Found",
  "documentation_url": "https://docs.github.com/rest"
}
```

**Common Causes & Fixes:**
1. **Typo in Owner or Repository Name**