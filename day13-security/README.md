# Day 13 — Docker Security

## Objective
Compare a vulnerable Docker image with a hardened image and verify container security controls.

## Security Risks Identified
- Running containers as root.
- Writable container root filesystem.
- Unrestricted CPU and memory consumption.
- Excessive Linux capabilities.
- Potential privilege escalation.
- Unnecessary packages and image layers.
- Vulnerable operating-system or application dependencies.

## Remediations Applied
- Run the application as a non-root user.
- Enable a read-only root filesystem.
- Drop unnecessary Linux capabilities.
- Set `no-new-privileges`.
- Configure CPU, memory, and process limits.
- Use a minimal base image and `.dockerignore`.
- Scan images using Trivy.
- Verify application health and runtime restrictions.

## Build and Scan Commands
Document the actual commands used to build both images, scan them, and run the hardened container.

## Before vs. After Comparison
Include vulnerability counts, image sizes, user identity, filesystem settings, resource limits, and runtime security options.

## Remaining Findings
Document unresolved HIGH and CRITICAL vulnerabilities, if any, along with relevant package names and remediation plans. Do not claim zero vulnerabilities unless the scan confirms it.

## Evidence
- Vulnerability scan results.
- Image sizes.
- Non-root container identity.
- Runtime security configuration.
- Application and health endpoint responses.

## Security Notes
Do not commit credentials, `.env`, or `token.txt`. Do not publish the vulnerable lab image to a public registry.
