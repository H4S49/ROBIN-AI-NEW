# 🤖 ROBIN-AI-NEW
## AI-Powered Dark Web OSINT Tool

---

### 🎬 Video Demonstration

[![Watch the ROBIN AI Video Demo(CLICK IMAGE)](assets/thumnail.png)](https://t.me/robinainew/2)

Watch a full 20-minute demonstration of ROBIN-AI's OSINT capabilities.

## 💻 Kali Linux (WSL) Installation

This section details how to set up **Kali Linux** using **Windows Subsystem for Linux (WSL)**.

1.  **Enable Virtual Machine Platform:**
    ```bash
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    ```
2.  **Enable Windows Subsystem for Linux (WSL):**
    ```bash
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    ```
3.  **Install Kali Linux App:**
       [Microsoft Store Link](https://apps.microsoft.com/detail/9pkr34tncv07?launch=true&mode=full&hl=en-us&gl=bd&ocid=bingwebsearch)

4.  **Install Kali Linux via WSL:**
    ```bash
    wsl --install -d kali-Linux
    ```
5.  **Run Kali Linux:**
    ```bash
    wsl -d kali-linux
    ```

---

## 🐳 Docker Installation

Docker is required to run the Robin AI tool.

1.  **Install Docker Desktop for Windows:**
    [Docker Desktop Download Site](https://docs.docker.com/desktop/setup/install/windows-install/)


2. ## 🛠️ Kali-WSL Docker Integration

### Ensure Docker Desktop is correctly configured to use Kali Linux:

1.  **Open Docker Desktop Application:** Launch the Docker Desktop application on your host system (Windows).
2.  **Access Settings:** Navigate to **Settings** (usually accessible via the gear icon ⚙️).
3.  **Go to Resources:** In the sidebar menu, select **Resources**.
4.  **Find WSL Integration:** Within the Resources section, locate the **WSL integration** tab.
5.  **Enable Kali Integration:** **Turn ON** the integration toggle switch for **Kali-Linux**.
6.  **Apply Settings:** Click **Apply & Restart** if prompted, to save your changes and restart Docker.

> 💡 **Pro Tip:** For reliable performance, ensure **ALL** listed WSL distributions are turned ON under this setting.
---

## ⚙️ ROBIN AI Setup

Follow these steps to set up and configure the Robin AI tool.

1.  **Reference (Optional):**
    [NetworkChuck Dark Web Scraping Guide](https://github.com/theNetworkChuck/dark-web-scraping-guide)

2.  **Clone the Robin Repository:**
    ```bash
    git clone https://github.com/apurvsinghgautam/robin.git
    ```
3.  **Navigate to the Directory:**
    ```bash
    cd robin
    ```
4.  **Make Scripts Executable:**
    ```bash
    sudo chmod +x *
    ```
5.  **Update Package Lists:**
    ```bash
    sudo apt update
    ```
6.  **Install Tor (The Onion Router):**
    ```bash
    sudo apt install tor
    ```
7.  **Create Environment File:**
    ```bash
    cp .env.example .env
    ```
8.  **Edit Environment Variables:**
    ```bash
    nano .env
    ```
9.  **OpenRouter Base URL:**
    ```bash

    https://openrouter.ai/api/v1

    ```
10. **Build the Docker Image:**
    ```bash
    docker build -t robin .
    ```

11. **Gemini API Key:**
    [Google AI Studio - Get API Keys](https://aistudio.google.com/api-keys)

12. **OpenRouter Platform:**
    [OpenRouter Website](https://openrouter.ai/)

13. **Owners GitHub Repository:**
    [https://github.com/apurvsinghgautam/robin](https://github.com/apurvsinghgautam/robin)

---

## 🚀 Running Robin (Standard Docker)

14.  **Use this command to run Robin as a detached container.**

```bash
sudo docker run -d \
  --name robin \
  -p 8501:8501 \
  -v $(pwd):/app \
  --env-file .env \
  robin
```

15. **Update For latest Docker Pull.**

```bash
docker pull apurvsg/robin:latest

```

16. **Run AI.**

```bash
sudo docker run --rm \
   -v "$(pwd)/.env:/app/.env" \
   --add-host=host.docker.internal:host-gateway \
   -p 8501:8501 \
   apurvsg/robin:latest ui --ui-port 8501 --ui-host 0.0.0.0

   ```

## 🔄 Robin Full Update

### Keep your Robin installation current with these commands.

1.  **Update, Upgrade, and Navigate:**
    ```bash
    sudo apt update -y && sudo apt upgrade -y && cd robin
    ```
2.  **Pull Latest Changes from GitHub:**
    ```bash
    git pull origin main
    ```
3.  **Rebuild the Docker Image:**
    ```bash
    docker build -t robin .
    ```
4.  **Pull the Latest Pre-built Image:**
    ```bash
    docker pull apurvsg/robin:latest
    ```

---

## ▶️ Daily Execution Workflow

### Follow these steps every time you want to run Robin.

| Step | Action | Command/Link |
| :--- | :--- | :--- |
| **1** | **Turn on Kali Linux WSL** | `wsl -d kali-Linux` |
| **2** | **Update Robin** | Execute all commands from the **[Robin Full Update](#robin-full-update)** section above. |
| **3** | **Run Docker Desktop** | Start the Docker Desktop application (or service). |
| **4** | **Run Robin** | `sudo docker run --rm \ -v "$(pwd)/.env:/app/.env" \ --add-host=host.docker.internal:host-gateway \ -p 8501:8501 \ apurvsg/robin:latest ui --ui-port 8501 --ui-host 0.0.0.0` |
| **5** | **Access the UI** | Go to this link: **[http://localhost:8501/](http://localhost:8501/)** |
| **6** | **Stop Robin** | Stop the running process by pressing **`Ctrl+C`**. |
| **7** | **Stop Kali WSL** | `wsl --terminate kali-Linux` |
| **8** | **Turn off Docker** | `wsl --terminate docker-desktop` |



