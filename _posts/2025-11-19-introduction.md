---
title: My Homelab Architecture Explained (2025 Edition)
date: 2025-11-19 10:00:00 -0500
categories: [HOMELAB FUNDAMENTALS]
tags: [homelab, self hosting, networking, synology, proxmox, cybersecurity, ai development, devops]
---
*A practical introduction to why I built The Curiosity Stack and how you can begin your own homelab journey*

## Introduction: Who I Am and How I Got Here

I'm Nick.  I'm a Wargame Modeling & Simulation developer and I'm infinitely curious when it comes to new technologies.  A few years ago, I got very interested in the idea of data sovereignty and getting off the multitude of cloud services.  Frankly, I was getting weirded out by the idea that all of these companies had my family's information, scraping it for who knows what.  And if a company decided to sunset a product - what then?  So I started looking for ways to get our information out of the cloud and into something we controlled.

While I didn't realize it then, this was the beginning of my journey into creating a homelab.

A homelab is more than a server rack in a basement (and heck, it doesn't even need a server rack!).  It's a personal ecosystem.  It's a space to learn, to build, to automate, to experiment, to break things (sometimes), and to improve how you and your household uses technology.  Believe it or not, I didn't begin with a detailed blueprint.  But I did begin with simple questions.

- What problems do I need to solve?
- What can I build that can solve those problems?
- And probably most importantly, how do I design something that fits within a normal home budget?

This article introduces *The Curiosity Stack*, describing the homelab that now powers my development, my AI experimentation, and my family’s everyday digital life.  I'm hoping these articles can help others who are also thinking about making the plunge into building their own homelabs.  

### How I Began Designing a Homelab

At the start, I realized that I need to answer one question before I started spending money.

*What problem am I trying to solve?*

A lot of people get stuck because they begin with equipment instead of needs.  (Ask me how I know.)  Don't try recreating a datacenter at home or start by copying someone else's setup.  Instead, identify practical use cases and let those drive the architecture.  In my case, my goal was to design something useful, maintainable, and financially reasonable.

If you're exploring a homelab, you're probably asking yourself the same questions.  You may be trying to justify the cost or understand the purpose.  List your needs first.

### The Use Cases That Shaped My Homelab

I categorized the problems and solutions into use cases, which were the core responsibilities I wanted my homelab to handle.  This list is the primary design driver for my homelab.  Every major architectural decision comes from this list.

| Use Case | Purpose |
| -------- | ------- |
| File Sharing and Serving | NFS and SMB shares for documents, media, and backups |
| Photo Storage and Serving | Centralized family photo management and backup |
| VPN Access | Secure external connection to the home network |
| AI & Development | AI app prototyping, Docker automation, LM Studio endpoints |
| Media Streaming | Jellyfin as a child-safe media center |
| Video Games | Local Minecraft as a child-safe server |

This list isn't in order of priority.  It happens to be in order of the timeline over which I considered my homelab design.  Regradless, this list is my homelab's blueprint.

### From Use Cases to Architecture: The Broad-Brush Design

This article is not a deep dive into VLAN diagrams or Ansible automation. (Those will come later!)  Instead, I want to show the straight-line from use cases to architecture.

#### Storage, Photos, and Media: Synology NAS

The main needs that started me on the journey were storage and photo management, and later secure media streaming.  Synology's Network Attached Servers (NAS) products provided stable, easy-to-use solutions for all three.  After picking up my first Synology NAS, it quickly became the center of my digital life.  And, once I saw how much data flowed through it, the next decision was simple:  I added a *second* Synology unit as a dedicated backup.

#### Family Safety and Network Segmentation: Firewalla, VPNs, and VLANs

I wanted a safe, reliable, and segmented home network that protected my family and isolated smart devices. A Firewalla Gold SE, paired with a managed switch, gave me that control.  Clear VLAN design meant I could separate homelab devices, IoT, guests, and private systems while still giving my son access to media and games in a controlled way.  My Firewalla also includes VPNs through OpenVPN and WireGuard protocols, so we can connect back to the home network when we're away.

Just so you know, I didn't start with this network solution.  Instead, my first Synology NAS was my firewall (and VPN!).  I grew into my current (preferred) network configuration over time.

#### Child-Safe Gaming: Local Minecraft

My child loves Minecraft.  Public servers come with risks I was not interested in managing (yet), and a local Minecraft server solved most issues instantly: No strangers, no ads, no surprises.  Just a space to explore and play with friends.  I connected our Nintendo Switch using a bit of networking magic (future article for sure) and now we enjoy playing together on our preferred devices!

#### AI Development and Automation: Local LLMs and ProxMox

As I grew into a better developer and started working with AI and automation, the homelab became a full development experimentation platform. That led to:

- Two ProxMox hypervisors
- A dedicated AI server (an available laptop)
- Development VMs for apps and databases
- A CI/CD workflow with Docker registries and automation nodes
- A full automation VM to orchestrate tasks and agentic workflows

As these services came online, the homelab became the foundation of my creative and technical work.

### Conclusion: What Comes Next

This article is the first step in a larger series here on *The Curiosity Stack*.  In upcoming posts, I will break down the specific components of this architecture and walk through the practical lessons I learned as I built it.

Planned topics include:

- How to plan and segment a home network
- How to build and manage ProxMox VMs
- How to deploy local LLMs for development
- How to set up family-safe media options
- How to design a personal CI/CD and automation pipeline
- How to start simple and scale your homelab over time
- How to document your homelab journey
- Future design and experimentation
- And more!

If you are curious about building something similar or just want to follow along with future deep dives, welcome to *The Curiosity Stack*!