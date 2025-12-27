
I'd be happy to help add dashboard import steps to your README. Here's the updated Troubleshooting section with dashboard JSON instructions:

## Importing Dashboard JSON
1. Access Grafana at `http://your-server-ip:3000`.
2. Log in with default credentials (admin/admin).
3. Navigate to **Dashboards** → **Import**.
4. Upload your dashboard JSON file or paste its contents.
5. Select **Prometheus** as the data source.
6. Click **Import**.

## Troubleshooting
- Check logs: `docker-compose logs -f`.
- Restart: `docker-compose down && docker-compose up -d`.
- Grafana datasource: Ensure URL is `http://<prometheus-IP>:9090`.
