# Security checklist before production

- [ ] Written confirmation that required repost endpoints/actions are available and allowed
- [ ] TikTok app registered and all required products/scopes approved
- [ ] OAuth `state` is cryptographically random and checked on callback
- [ ] OAuth code exchanged on server only
- [ ] Client secret and access/refresh tokens never shipped to the browser
- [ ] HTTPS enforced; secure, HttpOnly, SameSite session cookies
- [ ] CSRF protection and rate limiting on state-changing endpoints
- [ ] Tokens encrypted at rest and excluded from logs
- [ ] User can disconnect TikTok and request deletion of stored data
- [ ] Privacy policy and terms accurately describe what is collected and why
- [ ] Destructive actions require confirmation and verify API response
- [ ] Error handling avoids claiming success when an action failed
- [ ] TikTok review/approval completed before public release
- [ ] Payment and refund terms reviewed before charging users
