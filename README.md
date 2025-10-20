## **Dynamic Subdomain Sync** - syncsd.sh
**Automate DNS ↔ Docker ↔ Caddy reverse proxy**  
**Created by: Revi9x**

---

## 🔧 What it does  
- Fetches A-records from cPanel zone for your domain  
- Scans running Docker containers to discover host ports  
- Prioritises UDP ports (for game servers) → TCP ports as fallback  
- Builds a Caddyfile with reverse_proxy entries for each subdomain  
- Removes stale entries automatically  
- Validates config, reloads Caddy safely and rolls back on failure  
- No external config files needed after the first run  
- Interactive setup for first use  

---

## ✅ Requirements  
- `bash` (version 5 or higher)  
- `curl`  
- `jq`  
- `docker` (with `caddy` container running, named e.g. `revive-caddy`)  
- cPanel (via API) for DNS zone management  

---

## 📥 Installation  
```bash
sudo curl -L -o /usr/local/bin/syncsd.sh https://raw.githubusercontent.com/revi9x/syncsd/main/syncsd.sh
sudo chmod +x /usr/local/bin/syncsd.sh
