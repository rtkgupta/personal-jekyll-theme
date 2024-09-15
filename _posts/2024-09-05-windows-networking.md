---
layout: post
section-type: post
has-comments: true
title: Demystifying debugging Calico CNI for Windows Containers on CAPZ based Kubernetes clusters
category: tech
tags: ["debugging", "networking"]
---

Well I know I used a few fancy words in the blog title, for someone who is new to this space I am attaching links to provide further insights into the technologies at play here. For the ones who know it all feel free to jump on ahead to next section! 

### What is all this mumbo-jumbo ?

At the core of it Kubernetes is a container orchestration that helps deploy containerized applications. Kubernetes is usually provided as a service by most cloud providers. I use CAPZ (Cloud Provider For Azure) clusters. These clusters use a Container Networking Interface to ensure that the containers deployed will follow a set bunch of polcies. In our use case the CNI, is Calico. You can read more at the links shared below.

[Kubernetes](https://kubernetes.io/)

[Calico](https://docs.tigera.io/calico/latest/about/product-comparison#calico-open-source)

[Capz](https://capz.sigs.k8s.io/)

### Why am I writing this blog ?

I have spent countless hours understanding this space and I believe organizing my thoughts in this blog form can help developers who are new to this space learn how to interact with the environment.

### Diving Deep

The CNI allows cluster admins to set polcies which get transalated by the Host Network Service. So Calico sets polcies that get interpreted by HNS as ACL polcies. These are usually implemented on to the VMswitches that help control traffic. How do I do debugging a scenario where I apply a policy via calico but it is not being enforced? We want to get the latest scripts to collect logs from by running the below command.
    ```
    wget raw.githubusercontent.com/microsoft/SDN/master/Kubernetes/windows/debug/collectlogs.ps1 -o collectlogs.ps1 
    ```

Then we want to reproduce our scenario, then run the above script. 
One of the first things we can look at is the Control Path. 

<Insert a diagram ??>



## Option 1: Understand the Control Path 

If you have gathered traces using collect windows logs. 


## Data Path

