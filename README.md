# 🌐 Self-Host Docker Composes

Welcome to my self-hosted hobby project! This repository contains configuration files for running various services on my server using Docker Compose. 🚀

## 🛠️ Services

### 🏠 Home Automation: **Home Assistant (HA)**
Manage and automate your smart home devices with Home Assistant, your centralized control system for a smarter home. 🤖

---

### 🎥 Media Server: **Jellyfin**
Your all-in-one media server solution, supported by these awesome tools:
- 📺 **Sonarr**: TV show download manager.
- 🎬 **Radarr**: Movie download manager.
- 🎟️ **Jellyseerr**: Media request management.
- 🛡️ **Gluetun**: VPN support for secure connections.
- 🌊 **qBittorrent**: Torrenting made easy.
- 🔍 **Prowlarr**: Indexer management.
- 🎵 **Lidarr**: Music download manager.

---

### 🔐 Password Manager: **Vaultwarden**
Keep your credentials safe and secure with Vaultwarden, a lightweight and efficient password manager. 🗝️

---

### ☁️ Photo Storage Cloud: **Nextcloud**
Store and manage your photos and files privately with Nextcloud, your personal cloud solution. 📸

---

### Installation and usage
To install and use these services, follow the steps below:

### 🚀 Installation and Usage

1. **Clone the Repository**  
    Start by cloning this repository to your desired server or machine:
    ```bash
    git clone https://github.com/qwerti/selfhost-docker-composes.git
    cd selfhost-docker-composes
    ```

2. **Set Up Environment Variables**  
    Configure the `.env` file for each service if required. Refer to the documentation of each service for specific environment variable settings.

3. **Edit the `docker-compose.yml` File**  
    Before running the services, ensure the `docker-compose.yml` file is properly configured. Update the file paths for volumes, such as configuration files and service data directories, to match your desired locations. For example:
    ```yaml
    volumes:
      - /path/to/your/config:/config
      - /path/to/your/data:/data
    ```

4. **Run Docker Compose**  
    Navigate to the directory of the service you want to deploy and run it in detached mode:
    ```bash
    docker-compose up -d
    ```
    This will start the service in detached mode.

5. **Access the Services**  
    Access the services locally using the ports defined in the `docker-compose.yml` files. For example:
    - Home Assistant: `http://[server_ip]:8123`
    - Jellyfin: `http://[server_ip]:8096`

6. **Expose Services to the Internet (Optional)**  
    If you want to access these services over the internet:
    - Forward the necessary ports on your router.
    - Use a reverse proxy (e.g., Caddy) to map your services to your domain name (DNS). Example Caddyfile configuration:
      ```caddyfile
      your-domain.com {
            reverse_proxy [server_ip]:8123
      }
      ```

7. **Secure Your Setup**  
    Always use HTTPS for secure connections and consider additional security measures like firewalls and VPNs.

### Default Ports for Services

Here are the default ports used by the services in this repository:

- **Home Assistant**: `8123`
- **Jellyfin**: `8096`
- **Sonarr**: `8989`
- **Radarr**: `7878`
- **Jellyseerr**: `5055`
- **qBittorrent**: `8081`
- **Prowlarr**: `9696`
- **Lidarr**: `8686`
- **Vaultwarden**: `6207`
- **Nextcloud**: `1212`

## 📝 Notes
⚠️ **Disclaimer**: This project is tailored for personal use and is not intended for production environments.

💡 **Contributions & Suggestions**: Feel free to share your ideas or improvements! Your input is always welcome. 🌟