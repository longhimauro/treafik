# Treafik
This is a Load balancer.
To publish resources add to the docker compose of the service you need to publish these lines.

    labels:
      - "traefik.enable=true"
      - "traefik.http.routers.n8n.rule=Host(`${SERVICE_HOST}`)"
      - "traefik.http.routers.n8n.entrypoints=websecure"
      - "traefik.http.routers.n8n.tls.certresolver=letsencrypt"
      - "traefik.http.services.n8n.loadbalancer.server.port=5678"


SERVICE_HOST = hostname configured in .env
