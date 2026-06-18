---
title: "من الصفر إلى الاستضافة الذاتية: بناء خادم منزلي آمن على Windows 11"
date: 2026-06-17
draft: false
translated: false
tags: ["homelab", "self-hosting", "docker", "traefik", "wireguard", "security", "wsl2"]
summary: "كيف بنيتُ خادمًا منزليًا خاصًا وسحابيَّ البنية على Windows 11 + WSL2 (Docker وTraefik وWireGuard وsplit DNS)، والأخطاء التي علّمتني أكثر من غيرها."
ShowToc: true
TocOpen: false
# Absolute path to the English-bundle image: these translation stubs have no
# body, so their own bundle copy is never published. See index.md for the EN cover.
cover:
  image: "/blog/from-zero-to-self-hosted/screenshot-stack-healthy.png"
  alt: "طرفية تُظهر جميع خدمات Docker في المختبر المنزلي تعمل وبصحة جيدة"
  caption: "‏`docker ps` — المنظومة الكاملة قيد التشغيل: Traefik وCrowdSec وWireGuard وWatchtower وغيرها."
---
