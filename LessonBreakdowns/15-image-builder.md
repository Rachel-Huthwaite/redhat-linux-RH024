# 15 - Image Builder

## Overall Summary
This lesson covers the concept of "Golden Images" and explores Red Hat's Image Builder tools[cite: 16]. It explains how pre-configured OS templates enable rapid, consistent, and predictable server deployments[cite: 16]. The lesson provides a deep dive into the two primary Red Hat Image Builder variants—**Insights Image Builder** (hosted SaaS) and **RHEL Image Builder** (on-premise tool)—comparing their architectures and use cases[cite: 16]. Finally, it details the step-by-step workflow for creating an image blueprint on `console.redhat.com` and generating bootable virtual machine disk images, such as standard `QCOW2` files[cite: 16].

## New Jargon
* **Golden Image:** A pre-configured, tested master template of an operating system used as a clean starting point to deploy virtual machines or cloud instances rapidly and predictably[cite: 16].
* **Image Blueprint:** A custom specification file (template) defining the packages, system configurations, user accounts, and security baselines to include in a built image[cite: 16].
* **Red Hat Insights Image Builder:** A cloud-hosted SaaS tool on `console.redhat.com` that builds customized OS images for cloud providers, hypervisors, and bare metal without consuming local build resources[cite: 16].
* **RHEL Image Builder (`composer-cli` / `osbuild`):** An on-premise local utility hosted directly on a RHEL server to build custom operating system images locally inside secure or disconnected networks[cite: 16].
* **QCOW2 (QEMU Copy-On-Write 2):** A flexible virtual disk image format widely used by KVM, QEMU, and OpenStack hypervisors[cite: 16].

## Commands Learnt
*(No direct CLI commands were executed in this lesson; operations were conducted via the web platform `console.redhat.com`)*[cite: 16]

## Key Concepts

### 1. What is a "Golden Image" and Why Use It?
A Golden Image is an optimized, pre-baked operating system template containing enterprise compliance policies, standard security agents, custom software packages, and system configurations[cite: 16].
* **Speed:** Eliminates manual post-installation configuration steps[cite: 16].
* **Consistency:** Ensures every virtual machine or cloud instance boots up matching organizational standards[cite: 16].
* **Predictability:** Minimizes configuration drift across development, staging, and production environments[cite: 16].

### 2. Deep Dive: Insights Image Builder vs. RHEL Image Builder

Red Hat provides two distinct implementations of Image Builder[cite: 16]:

| Feature | Insights Image Builder (Hosted) | RHEL Image Builder (On-Premise) |
| :--- | :--- | :--- |
| **Location** | Hosted on Red Hat Hybrid Cloud Console (`console.redhat.com`)[cite: 16]. | Installed locally on a RHEL host (`osbuild` / `composer-cli`)[cite: 16]. |
| **Resource Consumption** | Builds images using Red Hat's cloud infrastructure[cite: 16]. | Uses local host CPU, RAM, and disk storage to generate images[cite: 16]. |
| **Internet Requirement** | Requires outbound internet access to `console.redhat.com`[cite: 16]. | Works offline in air-gapped / disconnected networks[cite: 16]. |
| **Cloud Integration** | Automatically uploads built images directly to AWS, Azure, or GCP accounts[cite: 16]. | Generates local image files (`.qcow2`, `.iso`, `.vhd`) to be uploaded manually[cite: 16]. |
| **Best Used For** | Cloud deployments, hybrid infrastructure, and offloading build workloads[cite: 16]. | Isolated networks, edge locations, and strict data sovereignty rules[cite: 16]. |

---

### 3. Step-by-Step Blueprint Creation Workflow (`console.redhat.com`)

To generate a Golden Image via Insights Image Builder[cite: 16]:

1. **Accessing the Console:**
   Navigate to `console.redhat.com` $\rightarrow$ Select **Red Hat Enterprise Linux** $\rightarrow$ Open **Insights for RHEL** $\rightarrow$ Expand **Inventory** $\rightarrow$ Select **Images**[cite: 16].
2. **Create Image Blueprint:**
   Click **Create Image** to launch the step-by-step wizard[cite: 16]:
   * **Target Environment / Output Type:** Select target format (e.g., **QEMU / KVM (`.qcow2`)** for local virtualization, or select cloud providers like AWS/Azure/GCP)[cite: 16].
   * **Registration & Subscriptions:** Choose whether new instances automatically register with Red Hat Subscription Manager upon first boot[cite: 10, 16].
   * **File System Configuration:** Set custom storage partition sizing (e.g., expanding `/var` or `/usr` layout)[cite: 16].
   * **Custom Packages:** Search for and include required runtime applications or tools directly into the image build[cite: 16].
   * **User Credentials:** Define default administrative users, SSH public keys, and password policies[cite: 16].
3. **Build & Download `QCOW2` Image:**
   * Review the blueprint summary and click **Build Image**[cite: 16].
   * Red Hat cloud service builds the custom disk image in the background[cite: 16].
   * Once status changes to **Ready**, click **Download** to obtain the `.qcow2` virtual disk file to import into hypervisors (such as KVM/QEMU)[cite: 16].

## Main Notes
* Utilizing Insights Image Builder offloads compute overhead from local hypervisors, allowing admins to generate complex cloud or VM images on demand[cite: 16].
* Images built with embedded SSH keys and predefined package sets enable zero-touch automation when provisioning new servers[cite: 16].

## My Key Learning
Golden images built via Red Hat Image Builder streamline infrastructure deployment by packaging OS settings, compliance baselines, and packages into standardized, ready-to-deploy virtual disk templates like `QCOW2`[cite: 16].