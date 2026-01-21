---
title:      "Ansible"
ring:       hold
quadrant:   languages-and-frameworks
tags:       [automation, configuration-management, legacy]
guid:       a7b8c9d0-e1f2-3456-7890-123456ghijkl
---

Ansible is a configuration management and automation tool that uses agentless architecture and YAML-based playbooks. While it has been widely used for infrastructure automation, newer approaches are often more suitable.

For new projects, consider Terraform for infrastructure provisioning and Kubernetes operators for configuration management. Ansible's imperative nature can lead to drift and doesn't align well with declarative, GitOps-driven workflows.

If you're maintaining existing Ansible deployments, continue using it. But for new infrastructure automation projects, evaluate declarative alternatives like Terraform, Pulumi, or cloud-native tools.

Note: This doesn't mean Ansible is bad—just that for most modern cloud-native infrastructure work, there are better-suited tools.

Further reading:
- [Ansible Documentation](https://docs.ansible.com/)
- [Terraform vs Ansible](https://www.terraform.io/intro/vs/ansible)
- [Modern Infrastructure Automation](https://www.cncf.io/blog/)
