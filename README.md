# Notable Regular Expressions
Contributions welcome.

## Domain
### Strict
Only allows values you can actually register with a registrar. e.g. the tld must have at least two characters.

`/^(?:(?![-])[a-z0-9-]{1,63}(?<![-])\.)+(?:[a-z]{2,63})$/i`

### RFC
Based on various RFCs. Allows public suffixes like "com", and single character labels like "a" even though you can't currently register a domain like that. e.g. "example.a" or literally just "com".

`/^(?:(?![-])[a-z0-9-]{1,63}(?<![-])\.)*(?:[a-z]{1,63})$/i`

### Cookie-Use
Similar to [RFC](#rfc), but also allows a leading ".". e.g. ".example.com".

`/^[.]?(?:(?![-])[a-z0-9-]{1,63}(?<![-])\.)*(?:[a-z]{1,63})$/i`

### Strict Cookie-use
Public suffixes like "com" are not allowed. At minimum, there must be a domain and a tld. e.g. "a.a" is valid.

`/^[.]?(?:(?![-])[a-z0-9-]{1,63}(?<![-])\.)+(?:[a-z]{1,63})$/i`
