# Immich + PowerTools on Synology (via Portainer)

This repository provides **stack `.env` and `docker-compose.yml` files** to deploy [Immich](https://immich.app) together with the [Immich PowerTools service](https://immich-power-tools.featureos.app/b/integrations) on a **Synology NAS** using [Portainer](https://www.portainer.io/).

## About

- **[Immich](https://github.com/immich-app/immich)**  
  A high-performance self-hosted photo and video backup solution.  
  Docs: [immich.app/docs](https://immich.app/docs/overview/welcome)

- **[Immich PowerTools](https://github.com/varun-raj/immich-power-tools)**  
  A companion service that extends Immich with advanced features such as integrations and automation.

This project is **not the official Immich or PowerTools repository**.  
It is a community example to help you configure the two services together on **Synology NAS with Portainer**.

## Why this repo?

- Synology users often run Docker containers via **Portainer** instead of raw CLI.
- Environment variables (`stack.env`) and compose files differ slightly depending on the NAS environment.  
- This repo gives a **ready-to-adapt baseline** for your own setup.

## Structure

- `stack.env.example` → editable environment variables (e.g. DB settings, ports, volumes).  
- `docker-compose.yml` → services definition for both Immich and PowerTools.  
- `README.md` → this documentation.

## Prerequisites

- Synology NAS with Docker installed  
- [Portainer](https://www.portainer.io/) running on your NAS you can follow [MariusHosting](https://mariushosting.com/synology-30-second-portainer-install-using-task-scheduler-docker/) guide for this.   
- Basic knowledge of editing `.env` files and Portainer stacks  

## Usage

1. Clone/download this repo to your NAS.
2. Make sure the following folders exist on your nas `/yourvolume/docker/immich`
3. Make sure that in the `immich` folder you have the following folders present `redis`, `db`, `matplotlib`, `micro`, `cache`, `redis` and `upload`   
4. Copy `stack.env.` to `stack.env` and adjust values for your environment. or just copy and paste the contents in the advanced env editor in Portainer  
5. Deploy the `docker-compose.yml` as a stack in Portainer.  
6. Verify both services are running:
   - Immich: `http://<NAS-IP>:8212` (default)  
   - PowerTools: `http://<NAS-IP>:8001` (default)

## References

- Immich GitHub: [github.com/immich-app/immich](https://github.com/immich-app/immich)  
- Immich Docs: [immich.app/docs](https://immich.app/docs/overview/welcome)  
- PowerTools GitHub: [github.com/varun-raj/immich-power-tools](https://github.com/varun-raj/immich-power-tools)  
- PowerTools Site: [immich-power-tools.featureos.app](https://immich-power-tools.featureos.app/b/integrations)

---

⚠️ **Disclaimer**:  
These files are provided as an example only.  
Always review and adjust to your specific Synology environment before deploying.
