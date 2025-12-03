# Lovable Guidelines

This is a set of guidelines for lovable projects that every project should follow.

## Constraints

### Security

 - Dependencies should be up to date, this can be verified by running `npm outdated`
 - Dependencies should not have known vulnerabilities, this can be verified by running `npm audit`
 - Unused dependencies should be removed
 - All pages should be protected by security headers (CSP, Strict-Transport-Security, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy)
   See: https://securityheaders.com/?q={{SITE_URL}}
 - File `robots.txt` should be present and contain:
   `User-agent: *
Disallow: /`

### Performance

 - All API requests should be paginated and load only one page at a time
   - If you need to count the total number of items, use the `itemsPerPage` query parameter with a value of `0`
   - Skeletons should be used to display the loading state

## Best practices

### Code

 - Eslint should be used to enforce code style, this can be verified by running `npm run lint`
   - Basics recommended rules should be used according to the project language
 - Unused files should be removed

## Deployment

Projects are deployed automatically to Clever Cloud. It needs to have a clear build and a start phase.

Example:

```json
{
  "scripts": {
      "build": "vite build",
      "start": "serve -s dist"
  },
  "devDependencies": {
      "vite": "^2.6.14",
      "serve": "^13.0.2"
  }
}
```
