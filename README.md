# OpenSearch Faceted Search Lab (Docker)

Link Video Explicativo
https://www.loom.com/share/b071f758d5d14616be70a5c189e6e1c5?sid=630a8659-ea3c-42e6-b95f-19eab8230dd2

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

git clone https://github.com/<tu-usuario>/<tu-repo>.git
cd <tu-repo>

# Copia el ejemplo y edita la contraseña del admin
cp .env.example .env
# Abre .env y cambia OPENSEARCH_INITIAL_ADMIN_PASSWORD por una contraseña fuerte

docker compose up -d
docker compose ps

curl -k -u admin:'TU_CLAVE_FUERTE' https://localhost:9200

🧹 Cómo apagar / resetear
# Detener (conserva datos)
docker compose down

# Borrar también volúmenes (reinicio limpio; PIERDE datos)
docker compose down -v


