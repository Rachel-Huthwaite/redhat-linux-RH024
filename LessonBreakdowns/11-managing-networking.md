# 11 - Managing Networking

## Overall Summary
This lesson covers Linux network management using NetworkManager tools (`nmcli` and `nmtui`) alongside low-level network commands (`ip` and `/etc/resolv.conf` inspection)[cite: 11]. It breaks down network interface naming standards, connection profile architectures, and step-by-step creation of static IP network profiles[cite: 11]. Additionally, it covers interface verification techniques, routing and DNS validation, connection removal, and terminal interface navigation[cite: 11].

## New Jargon
* **Network Interface:** A hardware or virtual network controller represented in Linux by names like `eth0`, `enp1s0` (Ethernet), or `wlp2s0` (Wi-Fi)[cite: 11].
* **Network Profile:** A collection of network configuration properties (IP addresses, gateways, DNS servers) applied to a single network interface[cite: 11].
* **NetworkManager:** The underlying daemon in Linux responsible for managing network interfaces and connection profiles[cite: 11].
* **`nmcli`:** The command-line tool used to create, view, modify, and delete NetworkManager profiles[cite: 11].
* **`nmtui`:** A text-based, menu-driven user interface (TUI) for interactive network profile configuration[cite: 11].

## Commands Learnt
* **`sudo -i`:** Elevates privileges to an interactive root shell required for network profile management[cite: 11].
* **`nmcli connection show`** (or `nmcli con show` / `nmcli c s`): Displays all existing network connection profiles[cite: 11].
* **`nmcli connection show <profile_name>`:** Shows detailed properties and configuration values for a specific network profile[cite: 11].
* **`ip address show`** (or `ip a s`): Displays assigned IP addresses, subnets, and status for active interfaces[cite: 11].
* **`ip address show <interface>`:** Shows address information for a specific interface (e.g., `ip a s enp7s0`)[cite: 11].
* **`ip route show`** (or `ip r s`): Displays the system routing table, including the default gateway[cite: 11].
* **`cat /etc/resolv.conf`:** Inspects active system DNS name server configurations[cite: 11].
* **`nmcli connection add`:** Creates a new connection profile[cite: 11].
  * `nmcli connection add con-name datacenter type ethernet ifname enp7s0 ipv4.method manual ipv4.addresses "192.168.1.114/24" ipv4.gateway 192.168.1.1 ipv4.dns "1.1.1.1"`: Creates a static Ethernet profile named `datacenter` bound to `enp7s0`[cite: 11].
* **`nmcli connection delete <profile_name>`** (or `nmcli con del <profile_name>`): Deletes a specified network profile (e.g., `nmcli con del datacenter`)[cite: 11].
* **`nmtui`:** Opens an interactive text-user-interface menu to add, edit, or activate network connections[cite: 11].
* **`Ctrl + l`:** Keyboard shortcut to clear the terminal screen[cite: 11].

## Key Concepts

### 1. Interfaces vs. Profiles
* **Interface:** Represents physical or virtual networking hardware (e.g., `enp7s0`)[cite: 11].
* **Profile:** A set of configuration parameters (IP address, gateway, DNS)[cite: 11].
* **Relationship:** An interface can have multiple saved profiles, but only **one profile can be active** on an interface at a given time[cite: 11].

### 2. Breakdown of the `nmcli connection add` Command
Creating a static network configuration requires specific key-value parameters[cite: 11]:
* `con-name datacenter`: Sets the administrative profile display name to `datacenter`[cite: 11].
* `type ethernet`: Specifies physical Ethernet connection type[cite: 11].
* `ifname enp7s0`: Binds the profile to hardware interface `enp7s0`[cite: 11].
* `ipv4.method manual`: Configures static IP assignment instead of dynamic DHCP[cite: 11].
* `ipv4.addresses "192.168.1.114/24"`: Assigns IPv4 address and CIDR subnet mask[cite: 11].
* `ipv4.gateway 192.168.1.1`: Sets default outbound routing gateway[cite: 11].
* `ipv4.dns "1.1.1.1"`: Defines primary DNS resolver server[cite: 11].

### 3. Verification Workflow
After adding or modifying network profiles, configuration changes should be verified step-by-step[cite: 11]:
1. **Profile Check:** Confirm profile creation using `nmcli con show`[cite: 11].
2. **IP Verification:** Confirm active address binding with `ip a s enp7s0`[cite: 11].
3. **Gateway Check:** Verify default route presence using `ip r s`[cite: 11].
4. **DNS Verification:** Verify active resolver entries in `/etc/resolv.conf`[cite: 11].

### 4. `nmtui` Text User Interface
`nmtui` provides an interactive terminal interface for managing network connections without memorizing CLI syntax[cite: 11]. Selecting **Edit a connection** allows navigating interface fields using arrow keys to adjust IP, gateway, and DNS settings directly[cite: 11].

## Main Notes
* Enclosing IP addresses and CIDR notations in quotes (e.g., `"192.168.1.114/24"`) prevents shell parsing errors during profile creation[cite: 11].
* `/etc/resolv.conf` is dynamically managed by NetworkManager; direct manual edits will be overwritten when network profiles restart[cite: 11].

## My Key Learning
NetworkManager decouples hardware interfaces from configuration profiles, allowing single interfaces to switch between different pre-configured static or dynamic profile settings[cite: 11].