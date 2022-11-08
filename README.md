- Download project and run `npm install`
- Use `npm run dev` to start the development server.
- If a `.env` file does not currently exist in the repo root directory, create one with:
```
# Express API Environment Variables
API_PORT=<api port>

PSQL_PORT=<psql port>
PSQL_USER=<psql user>
PSQL_PASS=<psql password>
PSQL_URI=<psql uri>

# Python Helper Environment Variables
S3_ACCESSKEYID=<aws s3 access key id>
S3_SECRETACCESSKEY=<aws s3 secret access key>
S3_ENDPOINT=<s3 endpoint uri>
S3_GAMES_BUCKET="devcade-games"
S3_SAVES_BUCKET="devcade-saves"
```

# Podman

First, build the container.
```
podman build . --tag devcade-api
```

You can run the container on your local machine with
```
podman run --rm -it --name devcade-api -p 8277:8277 --env-file=.env devcade-api
```
