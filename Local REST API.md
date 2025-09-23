## Examples
GET
/active/
Return the content of the active file open in Obsidian.:
```
curl -X 'GET' \
  'http://127.0.0.1:27123/active/' \
  -H 'accept: application/vnd.olrapi.note+json' \
  -H 'Authorization: Bearer db5d4d1b6683393abd11ba9ea37c7a0e5bd47d131841a1c708dd1a8b15250e71'
  
```


