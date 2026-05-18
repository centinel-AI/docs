# Authentication

## API Token

```http
Authorization: Bearer YOUR_API_TOKEN
```

### Where to find your token
**centinelai.io → Connectors → any connector → API Token**

### Format
UUID v4: `fa8a4dd1-89e9-452b-9c98-a4c13cf0f469`

### Regenerate the token
```sql
UPDATE organizations 
SET api_token = gen_random_uuid() 
WHERE id = 'your-org-id'
RETURNING api_token;
```
