# Autenticación

## API Token

```http
Authorization: Bearer TU_API_TOKEN
```

### Dónde encontrar tu token
**centinelai.io → Conectores → cualquier conector → API Token**

### Formato
UUID v4: `fa8a4dd1-89e9-452b-9c98-a4c13cf0f469`

### Regenerar el token
```sql
UPDATE organizations 
SET api_token = gen_random_uuid() 
WHERE id = 'tu-org-id'
RETURNING api_token;
```
