# 🧪 Lab 01 — Linux Networking Fundamentals

## Why Linux + Networking Matter

Linux and networking are foundational skills for **IT support, cloud engineering, and cybersecurity** roles. Most servers, cloud workloads, containers, and security tools run on Linux, and all of them depend on reliable network connectivity.

Understanding Linux networking means being able to:
- Determine **why a system cannot reach the network**
- Distinguish between **IP issues vs DNS issues**
- Validate **routing and gateway configuration**
- Troubleshoot connectivity **without a GUI**

These are baseline expectations in real-world environments — not advanced skills.

---

## Business / Architecture Context

**What business problem does this solve?**  
It ensures systems can reliably communicate with users, services, and the internet. Without working networking, applications, authentication, updates, logging, and monitoring all fail.

**What would break if this didn’t exist?**  
Servers would be unreachable, cloud services would fail, users couldn’t authenticate, monitoring agents would stop reporting, and security tooling could not receive updates or send alerts.

**What are the alternatives?**  
GUI-based tools or automated network management systems exist, but engineers must still understand the underlying Linux networking commands to diagnose failures when automation or abstraction breaks down.

**When would I NOT use this?**  
On highly abstracted or locked-down platforms where networking is fully managed (e.g., some PaaS services). Even then, understanding Linux networking is required to reason about failures and limitations.

**Trade-offs:**  
Command-line tools are powerful and precise, but they require understanding. Incorrect changes can quickly misconfigure systems if applied without intent or validation.

---

## Security Considerations

**Attack surface:**  
Misconfigured network interfaces, exposed services, or incorrect routing can unintentionally expose systems to internal or external access.

**Misconfiguration risks:**
- Incorrect DNS settings can redirect traffic or cause denial of service
- Improper gateway configuration can bypass intended security controls
- Overly permissive firewall or routing rules can expose services unnecessarily

**Least privilege networking:**  
Only required interfaces, routes, and ports should be enabled. Network access should be restricted to what the system explicitly needs to function.

---

## Engineering & Failure Thinking

**Will this actually work?**  
Yes. These commands inspect the kernel’s view of networking directly, without relying on higher-level abstractions.

**What happens when something fails?**  
A system may still have an IP address but no DNS resolution, or routing may exist but traffic is blocked upstream. This lab teaches how to identify *where* the failure occurs instead of guessing.

**Edge cases:**  
Virtual machines, NAT, VPNs, and firewalls can all change expected behavior. This lab documents those differences rather than assuming a single environment.

**Under load or misuse:**  
Misconfigured networking can silently break systems. Knowing how to inspect state prevents trial-and-error troubleshooting and reduces downtime.

---

## What Broke (Intentional)

For this lab, failures are intentionally introduced later to demonstrate diagnosis rather than assumption-based troubleshooting, including:
- Breaking DNS configuration
- Removing or misconfiguring the default gateway

Each failure is documented with symptoms, root cause, and resolution.

---

## Lab Goal

By completing this lab, I will be able to:
- Identify active network interfaces
- Verify IP addressing and routing
- Test connectivity to local and external systems
- Confirm DNS resolution
- Explain *why* connectivity works or fails

---

## Environment

- OS: Ubuntu Desktop (ARM)
- Platform: Parallels Desktop on Apple Silicon
- Network mode: NAT

**Why this matters:**  
Virtualized NAT networking introduces an abstraction layer that can affect routing, DNS behavior, and visibility compared to bare-metal or cloud environments.

---

## Evidence & Execution

> All commands, outputs, failure scenarios, and screenshots for this lab are documented **below in this README**.

(Execution steps, command output, and screenshots follow in later sections.)
