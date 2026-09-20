# 13 - Deploying an Application Runtime to Host a Simple Application

## Overall Summary
This lesson demonstrates how to deploy a custom application as a production-grade `systemd` service on Red Hat Enterprise Linux. It shifts application management away from manual background execution tools (like `tmux` or `screen`) toward `systemd` unit files. By creating and installing a custom `.service` unit file, configuring `systemd` reloading, managing runtime states, opening necessary firewall TCP ports, and validating through local web browsing, the application achieves automated boot startup, self-healing crash recovery, and centralized logging.

## New Jargon
* **`systemd` Custom Unit File:** A configuration file (typically ending in `.service`) placed in `/etc/systemd/system/` that defines how `systemd` should start, stop, monitor, and recover a user application.
* **`daemon-reload`:** A `systemctl` command that instructs `systemd` to rescan configuration directories and load new or modified unit files into memory.
* **Self-Healing / Auto-Restart:** The capability of `systemd` to automatically restart an application service if it crashes or terminates unexpectedly[cite: 14].
* **Production Runtime Deployment:** Transitioning application execution from interactive sessions (`tmux`/`screen`) to managed system services for reliability, boot execution, and security[cite: 14].

## Commands Learnt
* **`sudo cp myapp.service /etc/systemd/system/`:** Copies a custom unit configuration file into the local `systemd` system directory[cite: 14].
* **`sudo systemctl daemon-reload`:** Reloads the `systemd` manager configuration to recognize newly created or updated service unit files[cite: 14].
* **`sudo systemctl enable --now myapp`:** Registers the custom service for boot autostart and immediately launches the process in runtime.
* **`systemctl status myapp`:** Checks the operational execution state, PID, memory usage, and recent log output of the custom service.
* **`sudo firewall-cmd --add-port=8080/tcp`:** Opens TCP port 8080 dynamically in the active firewall runtime rules[cite: 14].
* **`!! --permanent`:** Uses bash history expansion to re-run the previous command with `--permanent` appended, persisting the firewall port opening across reboots.

## Key Concepts

### 1. The Shift from Manual Execution to `systemd`
* **Legacy / Development Approach (`tmux`, `screen`, terminal backgrounding):** Requires manual intervention to start application scripts[cite: 14]. If the server reboots or the application encounters an unhandled exception, the application crashes and remains offline until manually restarted[cite: 14].
* **Enterprise Service Approach (`systemd` Service):** Applications start automatically on boot, automatically recover from unexpected crashes, integrate directly into system logs, and run as standard background services without babysitting processes[cite: 14].

### 2. Complete Walkthrough: Deploying a Custom Application
Based on the walkthrough repository steps (`gitlab.com/rgdacosta.nodejs_rhel10`):

1. **Install Service Unit File:**
   Copy the application service configuration file into the system-level `systemd` directory[cite: 14]:
   ```bash
   sudo cp myapp.service /etc/systemd/system/
   ```
2. **Reload systemd Manager:** Inform systemd of the new file so it scans and indexes    myapp.service[cite: 14]:
    ```bash
    sudo systemctl daemon-reload
    ```
3. **Enable and Launch Service:** Enable automatic execution at system boot and start the service immediately[cite: 12, 14]:
    ```bash
    sudo systemctl enable --now myapp
    ```
4. **Verify Application Health:** Confirm the process is active (running)[cite: 12, 14]:
    ```bash
    systemctl status myapp
    ```
5. **Configure Network Ports & Verify Endpoint:** Allow external/local TCP traffic through port 8080 and make the rule persistent across reboots[cite: 12, 14]:
    ```bash
    sudo firewall-cmd --add-port=8080/tcp
    !! --permanent
    ```
    Validate service connectivity by navigating to http://localhost:8080 in Firefox[cite: 14].

### Main Notes 
 * Unit files created or modified within /etc/systemd/system/ will not be recognized by systemctl until sudo systemctl daemon-reload is executed[cite: 14].
 * Always open network communication paths via specific ports (firewall-cmd --add-port=<port>/tcp) when deploying custom application runtimes that do not use standard predefined service profiles[cite: 14].

### My Key Learning

Running application code as a managed systemd service ensures reliability by providing automated boot startup, crash recovery, and logging, allowing developers and sysadmins to focus on building features rather than manually monitoring active tasks[cite: 14].

