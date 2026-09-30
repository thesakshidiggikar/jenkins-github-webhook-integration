# Jenkins GitHub Webhook Integration

> Event-Driven CI Automation using Jenkins, GitHub Webhooks and ngrok

This project demonstrates an event-driven Continuous Integration workflow where GitHub repository changes automatically trigger Jenkins jobs through GitHub Webhooks.

The implementation connects a locally hosted Jenkins instance with GitHub using an HTTPS tunnel created through ngrok. This allows GitHub to communicate with a Jenkins server running inside a local development environment without exposing the machine directly through router port forwarding.

The project focuses on understanding the complete webhook-driven CI flow, Jenkins job configuration, source-control integration, secure service exposure, webhook validation, and automated build triggering.

---

# 1. Project Overview

Traditional CI workflows may require developers or operators to manually trigger builds after pushing code changes.

This project removes that manual step by introducing an event-driven workflow:

```text
Developer
    |
    | git push
    v
GitHub Repository
    |
    | Webhook Event
    v
ngrok HTTPS Tunnel
    |
    | HTTP/HTTPS Forwarding
    v
Local Jenkins Server
    |
    | Webhook Trigger
    v
Jenkins Job / Pipeline
    |
    v
Build & Validation
