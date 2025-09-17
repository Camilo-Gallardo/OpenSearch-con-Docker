# OpenSearch Faceted Search Lab (Docker)

Montaje local de **OpenSearch + OpenSearch Dashboards** con Docker Compose, carga de datos de ejemplo y creación de un **dashboard con búsqueda facetada** (controles dinámicos).

## ✨ Qué incluye
- Stack local con Docker Compose (2 nodos + Dashboards).
- Dataset oficial de muestra (Flights) opcional desde la UI.
- Dataset manual `events-demo` (mapping + bulk).
- 3 visualizaciones base y dashboard con **facetas** (city, event_type, amount).

---

## 🧩 Prerrequisitos
- Ubuntu 25.04 (o similar)
- Docker y Docker Compose v2

```bash
sudo apt update
sudo apt install -y docker.io docker-compose-plugin
# Ajuste recomendado del kernel
echo "vm.max_map_count=262144" | sudo tee -a /etc/sysctl.conf
sudo sysctl -p
