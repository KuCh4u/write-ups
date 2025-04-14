# 📂 Repositorio de Write-ups – Nicolas Cartagena

Este repositorio contiene una recopilación de write-ups técnicos realizados durante mi aprendizaje y práctica en **ciberseguridad ofensiva**, a través de laboratorios y plataformas como:

- [Hack The Box](https://www.hackthebox.com/)
- [TryHackMe](https://tryhackme.com/)
- [VulnHub](https://www.vulnhub.com/)
- DockerLabs y entornos personalizados
- OSINT e investigaciones simuladas

> ⚠️ Todos los ejercicios fueron realizados en entornos controlados, con fines exclusivamente educativos.

---

## 🧠 Contenido

Los write-ups están organizados por plataforma en carpetas individuales:

- VulnHub
- TryHackMe
- HTB
- Dockerlabs
- OSINT

---

Cada archivo contiene:

- Descripción de la máquina o reto
- Herramientas utilizadas (Nmap, Burp, Hydra, etc.)
- Técnicas aplicadas (RCE, escalación, SQLi, etc.)
- Referencias a MITRE ATT&CK (cuando aplica)
- Recomendaciones y lecciones aprendidas

---

## 📘 Ejemplo de estructura de un write-up

```markdown
# VulnHub – Lame

## Herramientas utilizadas
- Nmap
- Searchsploit
- Metasploit

## Técnicas aplicadas
- RCE a través de vsftpd 2.3.4
- Acceso root vía shell inversa

## Recomendaciones
Actualizar servicios obsoletos y deshabilitar accesos anónimos por FTP.
