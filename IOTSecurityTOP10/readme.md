# Tester IoT Security Guidance 物聯網測試安全指南

## I1. Insecure Web Interface 不安全的WEB介面
+ Assess any web interface to determine if weak passwords are allowed
> - Assess the account lockout mechanism
> - Assess the web interface for XSS, SQLi and CSRF vulnerabilities and other web application vulnerabilities
> - Assess the use of HTTPS to protect transmitted information
> - Assess the ability to change the username and password
> - Determine if web application firewalls are used to protect web interfaces

> ## I2: Insufficient Authentication/Authorization 認證/授權不足
> - Assess the solution for the use of strong passwords where authentication is needed
> - Assess the solution for multi-user environments and ensure it includes functionality for role separation
> - Assess the solution for Implementation two-factor authentication where possible
> - Assess password recovery mechanisms
> - Assess the solution for the option to require strong passwords
> - Assess the solution for the option to force password expiration after a specific period
> - Assess the solution for the option to change the default username and password
