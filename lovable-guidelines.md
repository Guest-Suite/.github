# Lovable – Guidelines

## Rule Levels

These levels define the normative strength of rules and their execution priority.

- **MUST**: mandatory, cannot be violated
- **SHOULD**: strongly recommended, allowed only with strong justification
- **MAY**: optional

---

## Constraints

### Security

*Purpose: minimize attack surface and prevent misconfigurations.*

 - Dependencies **MUST** be up to date, check with `npm outdated`.
 - Projects with known vulnerable dependencies **MUST** be rejected, check with `npm audit`.
 - Secrets **MUST NOT** be hardcoded.
 - Credentials **MUST** use environment variables.
 - User input **MUST** be validated and sanitized.
 - Security headers **MUST** be enabled, check with https://securityheaders.com/?q={{SITE_URL}} where {{SITE_URL}} is the URL of the deployed site.
 - `robots.txt` **MUST** be restrictive.

### Code

*Purpose: maintain a stable, readable, and controllable codebase.*

 - ESLint **MUST** be configured.
 - The build **SHOULD** fail if linting fails.
 - Code **SHOULD** be modular and readable.
 - Dead code **MUST NOT** be committed.

---

## Best Practices

### Performance

*Purpose: ensure smooth and scalable user experience.*

 - Pagination **MUST** be implemented for large datasets.
 - Loading skeletons **SHOULD** be used.
 - Heavy components **SHOULD** be lazy-loaded.
 - Server-side rendering **SHOULD** be used.
 - You **SHOULD** reduce the number of dependencies.

### Quality

*Purpose: reduce the risk of defects in production.*

 - Errors **MUST** be handled gracefully.
 - Logs **SHOULD** be structured and meaningful.
 - Tests **SHOULD** cover critical paths.

---

## Deployment

*Purpose: guarantee reliable deployments.*

For Node projects, the following scripts should be added to the `package.json` file:

```json
{
  "scripts": {
      "build": "vite build",
      "start": "serve -s dist"
  },
  "devDependencies": {
      "vite": "^7.2.7",
      "serve": "^14.2.5"
  }
}
```
