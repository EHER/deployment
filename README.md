# 🚀 Deployments for Pet Projects

This repository contains Docker Compose configurations to deploy and manage various applications, including a WordPress site and an Nginx Proxy Manager. It's designed to help you deploy pet projects and learn about Docker deployments in the process. 🐳

## 📦 Services Included

- **Nginx Proxy Manager**: A simple interface for managing Nginx proxy hosts.
- **WordPress**: A popular content management system (CMS) for building websites.
- **MySQL**: A relational database to store your WordPress data.
- **DB Backup**: A utility container for performing MySQL database backups using `mysqldump`.

## 🚀 Getting Started

### Prerequisites

- Ensure you have Docker and Docker Compose installed on your machine.

### 📂 Setting Up

1. **Clone the Repository**

   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Configure Environment Variables**

   Create a `.env` file based on the template in the `docker-compose.yml` with your desired configuration for WordPress and MySQL.

3. **Start the Services**

   Launch all the services in detached mode:

   ```bash
   docker compose up -d
   ```

### 🛑 Stopping the Services

To stop and remove the containers, network, and volumes (except named volumes):

```bash
docker compose down
```

### 🔄 Performing a Database Backup

To perform a backup of your MySQL database using `mysqldump`, execute the following steps:

1. **Access the Backup Container**

   ```bash
   docker exec -it <db-backup-container-name> bash
   ```

2. **Run `mysqldump`**

   Inside the container, execute:

   ```bash
   mysqldump -h db -u exampleuser -pexamplepass exampledb > /db_backups/backup.sql
   ```

   The backup will be saved to the `./db_backups` directory on your host machine.

### 🌐 Accessing Nginx Proxy Manager

You can access the Nginx Proxy Manager dashboard at `http://localhost:81`. The default credentials are:

- **Email**: `admin@example.com`
- **Password**: `changeme`

### 📁 WordPress Persistence

- **Plugins, Themes, and Uploads**: These are stored in a Docker volume named `wordpress_data`, which is mapped to `/var/www/html/wp-content`. This ensures that all your WordPress changes are persistent across container restarts and recreations.

### 📚 Learning and Contributing

This repository is designed for learning purposes. Feel free to modify, experiment, and learn. If you'd like to contribute, please fork the repository and submit a pull request. Contributions are welcome! 🙌

### 📃 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
