---
title: My Homelab Architecture Explained (2025 Edition)
date: 2025-11-19 10:00:00 -0500
categories: [HOMELAB FUNDAMENTALS]
tags: [homelab, self hosting, networking, synology, proxmox, cybersecurity, ai development, devops]
---
# My Homelab Architecture Explained (2025 Edition)

*A practical introduction to why I built The Curiosity Stack and how you can begin your own homelab journey*

## Introduction: Who I Am and How I Got Here

A homelab is not a server rack in a basement. It is a personal ecosystem. It is a space to learn, to build, to automate, to experiment, to break things safely, and to improve how your household uses technology. I did not begin with a detailed blueprint. I began with simple questions.

- Why do I need a homelab?
- What problems will it solve?
- How do I design something that fits within a normal home budget?

This article introduces *The Curiosity Stack*, the homelab that now powers my AI experiments, my game development, and my family’s everyday digital life. More importantly, I want it to help you decide whether a homelab makes sense for you and how to start thinking about one.

### How I Began Designing a Homelab

Before I bought a single piece of hardware, I forced myself to answer one question.

*What problems am I trying to solve?*

A lot of people get stuck because they begin with equipment instead of needs. They try to recreate a datacenter at home or copy someone else's setup. I approached it differently. I identified practical use cases and let those drive the architecture. My goal was to design something that was useful, maintainable, and financially reasonable.

If you are exploring a homelab, you might be asking yourself the same questions. You may be trying to justify the cost or understand the purpose. In my experience, clarity comes from listing your needs first.

### The Use Cases That Shaped My Homelab

Here are the core responsibilities I wanted my homelab to handle. Every major architectural decision came from this small list.

| Use Case | Purpose |
| -------- | ------- |
| VPN Access | Secure external connection to the home network |
| File Sharing and Serving | NFS and SMB shares for documents, media, and backups |
| Photo Storage and Serving | Centralized family photo management using Synology Photos |
| Media Streaming | Jellyfin as a child-safe media center |
| Video Games | Local Minecraft as a child-safe server |
| AI Development | AI app prototyping, Docker automation, LM Studio endpoints |

This list became the blueprint for everything else.

### From Use Cases to Architecture: The Broad-Brush Design

This introduction is not a deep dive into VLAN diagrams or Ansible automation. Instead, I want to show the direct path from needs to architecture.

#### Storage, Photos, and Media: Synology NAS

Three of my main needs were storage, photo management, and secure media streaming. Synology provided all three. It quickly became the center of my digital life. Once I saw how much data flowed through it, the next decision was simple. I added a second Synology unit as a dedicated backup.

#### Family Safety and Network Segmentation: Firewalla and VLANs

I wanted a safe, reliable, and segmented home network that protected my family and isolated smart devices. A Firewalla Gold SE, paired with a managed switch, gave me that control. Clear VLAN design meant I could separate homelab devices, IoT, guests, and private systems while still giving my son access to media and games in a controlled way.

#### Child-Safe Gaming: Local Minecraft

My son loves Minecraft. Public servers come with risks I was not interested in managing. A local Minecraft server solved that instantly. No strangers, no ads, no surprises. Just a space for him to explore and play with friends.

#### AI Development and Automation: Local LLMs and ProxMox

As I grew deeper into AI development and automation, the homelab became a full development platform. That led to:

- A dedicated AI laptop running LM Studio
- Two ProxMox hypervisors
- Development VMs for apps and databases
- A CI/CD workflow with Docker registries and automation nodes
- A full automation VM to orchestrate tasks and agentic workflows

This was the moment the homelab stopped being a convenience and became the foundation of my creative and technical work.

### Conclusion: What Comes Next

This article is the first step in a larger series here on *The Curiosity Stack*. In the coming posts, I will break down the specific components of this architecture and walk through the practical lessons learned as I built it.

Topics will include:

- How to plan and segment a home network
- How to build and harden ProxMox VMs
- How to deploy local LLMs for development
- How to set up Jellyfin or Synology Photos
- How to design a personal CI/CD and automation pipeline
- How to start simple and scale your homelab over time

If you are curious about building something similar or want to follow along with future deep dives, you are exactly where you need to be.

Welcome to *The Curiosity Stack*!