# 14 - Using Image Mode with Bootc

## Overall Summary
This lesson introduces Image Mode for Red Hat Enterprise Linux using `bootc` (bootable containers). It explores transactional, container-native operating system management where the entire OS host is packaged, shipped, and updated as an OCI container image. The lesson covers connecting to a `bootc` host over SSH, checking host image status, verifying package non-existence on immutable systems, testing containerized applications, and performing atomic OS image updates using `bootc switch` followed by a system reboot.

## New Jargon
* **`bootc` (Bootable Containers):** A tool and architecture that allows operating systems to be built, deployed, and updated directly using standard container images (OCI images).
* **Image Mode:** A deployment model where the entire host OS is managed like a container image rather than an assembly of individually installed RPM packages.
* **Transactional / Atomic Updates:** Operating system updates that are applied as a complete unit; if an update fails, the system safely rolls back without leaving half-installed packages.
* **Container Registry (`quay.io`):** A centralized image repository used to store and distribute bootable host container images.

## Commands Learnt
* **`ssh bootchost`:** Establishes a remote Secure Shell connection to the target `bootc` managed host.
* **`sudo -i`:** Opens an interactive root shell session for administrative execution.
* **`bootc status`:** Displays the current active host image, origin container registry, image digest, boot state, and pending staged updates.
* **`systemctl status httpd`:** Checks the operational status of the Apache HTTP web server service.
* **`rpm -q httpd`:** Queries the local RPM database to verify if the `httpd` package is installed individually on the host[cite: 15].
* **`bootc switch <registry_image_tag>`:** Replaces or updates the operating system deployment image by staging a new container image tag from a registry[cite: 15].
  * Example: `bootc switch quay.io/name/bootc_httpd:2`[cite: 15]
* **`reboot`:** Restarts the operating system to boot into the newly staged image layer[cite: 15].

## Key Concepts

### 1. Deep Dive: What is `bootc` and Why Use It?
Traditional Linux operating systems are managed package-by-package using tools like `dnf`[cite: 1, 10, 15]. Over time, servers can experience "configuration drift" where environment states diverge[cite: 15].

**Image Mode with `bootc` changes this paradigm:**
* **Container-Native OS:** The OS is built using a standard `Containerfile` / `Dockerfile` and pushed to a container registry like `quay.io`[cite: 15].
* **Consistency:** The exact same OS image deployed in testing is booted in production[cite: 15].
* **Atomic Updates & Rollbacks:** OS upgrades occur transactionally[cite: 15]. You pull a new image tag and reboot[cite: 15]. If something breaks, rolling back to the prior deployment is instant and deterministic[cite: 15].
* **Unified Tooling:** System administrators use familiar container workflows (CI/CD pipelines, container registries) to manage both application code and host operating systems[cite: 15].

### 2. Step-by-Step Lesson Walkthrough

#### Step 1: Accessing the Host & Inspecting Base State
```bash
ssh bootchost
sudo -i
bootc status
```
Connects to the host and inspects bootc status, which displays the currently booted image commit and active OS version[cite: 15].

#### Step 2: Package & Service Verification
```bash
systemctl status httpd
rpm -q httpd
```
Checks if httpd is running[cite: 15]. Running rpm -q httpd illustrates that in image-mode systems, software isn't managed via standard individual package installation scripts on the live server, but is baked into the immutable base image layer[cite: 15].

#### Step 3: Application Testing
Connect to the web application running on the bootc host using Firefox to confirm network access and application delivery[cite: 15].

#### Step 4: Atomic OS Upgrades via bootc switch
To deploy an updated version of the host OS containing updated application code or configurations[cite: 15]:

```bash
bootc switch quay.io/name/bootc_httpd:2
reboot
```

* How it works: bootc switch pulls the quay.io/name/bootc_httpd:2 image tag in the background and stages it for the next boot loader entry[cite: 15].

* Executing reboot restarts the host into the new OS image state cleanly and transactionally[cite: 15].

* Re-running bootc status after reboot verifies that the host is running version :2 of the image[cite: 15].

### Main Notes

* Under bootc, system modifications are not made directly on production servers; instead, changes are committed to a Containerfile, built into a new container tag, and deployed using bootc switch[cite: 15].

* System reboots are required after running bootc switch to pivot the root filesystem into the staged bootable container image[cite: 15].

### My Key Learning

bootc bridges container workflows with host operating system management, enabling atomic OS updates, elimination of configuration drift, and consistent deployments using OCI container registries[cite: 15].