---
title: "De zéro à l'auto-hébergement : un serveur maison sécurisé sous Windows 11"
date: 2026-06-17
draft: false
translated: false
tags: ["homelab", "self-hosting", "docker", "traefik", "wireguard", "security", "wsl2"]
summary: "Comment j'ai construit un serveur maison privé et cloud-native sur Windows 11 + WSL2 (Docker, Traefik, WireGuard, split DNS) et les bugs qui m'ont le plus appris."
ShowToc: true
TocOpen: false
# Absolute path to the English-bundle image: these translation stubs have no
# body, so their own bundle copy is never published. See index.md for the EN cover.
cover:
  image: "/blog/from-zero-to-self-hosted/screenshot-stack-healthy.png"
  alt: "Terminal montrant tous les services Docker du homelab actifs et sains"
  caption: "`docker ps` — la pile complète en marche : Traefik, CrowdSec, WireGuard, Watchtower, etc."
---
