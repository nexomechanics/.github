# Security Checklist

## General (all projects)

- [ ] No API keys or passwords hardcoded
- [ ] Admin pages are protected
- [ ] Authentication works correctly
- [ ] User input is validated
- [ ] Debug mode is disabled
- [ ] Dependencies checked for vulnerabilities
- [ ] Client credentials not stored unnecessarily
- [ ] GitHub repo access limited to required developers only
- [ ] `.env` files are in `.gitignore`
- [ ] Secrets managed via environment variables, not config files

## Go

- [ ] `govulncheck` run, no known vulnerable dependencies
- [ ] `gosec` run, no unsafe patterns or hardcoded secrets
- [ ] No broker/exchange credentials hardcoded in bot configs
- [ ] API tokens loaded from environment, not source code

## Python

- [ ] `pip audit` run, no known vulnerable packages
- [ ] No secrets in committed `.env` or config files
- [ ] Input validation on any API endpoints
- [ ] No `eval()` or `exec()` on user-controlled input

## Node / Astro

- [ ] `npm audit` run, no known vulnerable packages
- [ ] OWASP ZAP scan completed (web/API projects)
- [ ] Security headers set (CSP, HSTS, X-Frame-Options)
- [ ] No sensitive data exposed in client-side code

## PHP

- [ ] `composer audit` run, no known vulnerable packages
- [ ] No SQL queries built with string concatenation
- [ ] `display_errors` disabled in production
- [ ] User input sanitised before output (`htmlspecialchars`)
- [ ] No sensitive data in URL parameters

## Ruby

- [ ] `bundle audit` run, no known vulnerable gems
- [ ] No `eval` on user-controlled input
- [ ] `secret_key_base` loaded from environment, not hardcoded
- [ ] Mass assignment protected (`strong_parameters`)

## Java

- [ ] `OWASP Dependency-Check` run, no known vulnerable dependencies
- [ ] No hardcoded credentials in `.properties` or `.xml` files
- [ ] No deserialization of untrusted data
- [ ] Input validated and sanitised before use

## Rust

- [ ] `cargo audit` run, no known vulnerable crates
- [ ] `unsafe` blocks documented and justified
- [ ] No hardcoded secrets in source

## C#

- [ ] `dotnet list package --vulnerable` run
- [ ] No hardcoded connection strings or API keys
- [ ] Input validated with model binding, not manual string parsing
- [ ] `DEBUG` mode disabled in production builds

## Shell Scripts

- [ ] No hardcoded credentials or tokens
- [ ] User input quoted to prevent injection
- [ ] Scripts not world-writable

## MQL / Pine Script

- [ ] No broker credentials hardcoded in strategy code
- [ ] No API keys or webhook URLs exposed in published scripts
- [ ] Webhook URLs treated as secrets, not committed to repo
