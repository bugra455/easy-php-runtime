# 🐘 easy-php-runtime

A basic setup that mimics a real (sad) plain PHP server setup, based on Docker.

---

## 🚀 Includes

-   Apache
-   PHP and lots of plugins
-   MariaDB

---

## 📋 Prerequisites

-   [Docker](https://www.docker.com/)
-   [Docker Compose](https://docs.docker.com/compose/)
-   [Lazydocker](https://github.com/jesseduffield/lazydocker) (if you want a panel to look at the logs)

---

## 🛠️ How to Use

1.  Clone this repository:
    ```bash
    git clone [https://github.com/bugra455/easy-php-runtime.git](https://github.com/bugra455/easy-php-runtime.git) --depth 1
    ```

2.  Paste all the contents into the root of your project. It should look like this:
    ```sh
    YOUR_PROJECT_ROOT/
    ├── docker/
    │   ├── apache/
    │   │   ├── 000-default.conf
    │   │   └── httpd.conf
    │   └── php/
    │       └── Dockerfile
    ├── docker-compose.yml
    ├── index.php
    └── public/
    ```

3.  Edit the parameters in `docker-compose.yml` as you like. As an example, my project's starting point is on the root of my project, so edit them as you like.

4.  If you need any special configuration, paste your `.htaccess` file into the root too.

5.  Just run the following command in the root of your project:
    ```bash
    docker compose up -d --build
    ```

6.  🎉 Congrats! You saved yourself from installing three databases, two web-servers, and 10 different versions of a programming language to the root of your daily driver.

![image](https://github.com/user-attachments/assets/f7af7237-7ba9-4a9f-ab00-e8a057d7a1ca)
