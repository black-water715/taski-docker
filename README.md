# taski-docker
docker run --name db --env-file .env -v pg_data:/var/lib/postgresql/data postgres:13.10
docker run --env-file .env --net django-network --name taski_backend_container -p 8000:8000 taski_backend
docker compose exec backend python manage.py collectstatic --noinput --clear --directory /backend_static/static/
docker compose exec backend-1 python manage.py collectstatic