# Nextcloud

[Nextcloud](https://nextcloud.com/) is a file sharing server that puts the control and security of your own data back into your hands.

This Community package pins the maintained Nextcloud 34 line and uses immutable
container digests. Optional HaRP, notify-push, Talk, recording, Imaginary,
PostgreSQL, Valkey and Nginx services are managed as one application while
retaining separate persistent storage and secret inputs.

<!-- x-readme:warnings:start -->

⚠️ **WARNING:** This app has access to the Docker socket, which gives it full control over all containers and effectively root access to the system.

Misconfiguration or a malicious update can compromise data integrity, security, or system stability. Install at your own risk.

<!-- x-readme:warnings:end -->
