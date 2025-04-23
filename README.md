# 🚀 Deploy Django on DigitalOcean with Docker

This repo accompanies a [step-by-step tutorial](https://dev.to/thierry-django/how-to-deploy-a-django-app-on-digitaloceans-app-platform-with-docker-3b6i) on deploying a Django app using Docker and DigitalOcean’s App Platform.

## 🛠️ Quick Start (Local)

- Clone the repo

```
git clone https://github.com/Rojohasina-R/digital-ocean-deployment-tutorial.git
cd digital-ocean-deployment-tutorial
```

- Create a .env.docker file

```
cat > .env.docker <<EOF
DATABASE_URL=postgresql://postgres:password@db:5432/tuto
DEBUG=1
SECRET_KEY=secret
DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1
CSRF_TRUSTED_ORIGINS=http://localhost,http://127.0.0.1
EOF
```

- Create a .env.db file

```
cat > .env.db <<EOF
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password
POSTGRES_DB=tuto
EOF
```

- Then start the app:

```
docker compose up
```

- Apply migrations and create a superuser (in a **new terminal** while the app is running):

```
docker compose exec web python manage.py migrate
docker compose exec web python manage.py createsuperuser
```

## 📦 Deployment to DigitalOcean's App Platform

👉 Follow step 5 of the tutorial for detailed deployment instructions: [Read the tutorial on dev.to](https://dev.to/thierry-django/how-to-deploy-a-django-app-on-digitaloceans-app-platform-with-docker-3b6i)
