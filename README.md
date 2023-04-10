# Backstage Demo

A basic [Backstage](https://backstage.io) app using Docker, configured to show API Hub data.

To use:

1. Install API Registry tools:

```sh
curl -L https://raw.githubusercontent.com/apigee/registry/main/downloadLatest.sh | sh -

curl -L https://raw.githubusercontent.com/apigee/registry-experimental/main/downloadLatest.sh | sh -
```

1. Import your Apigee data into API Hub (use `--help` for further information on commands)

```sh
registry-connect discover apigee proxies YOUR-ORGANIZATION > apigee-registry.yaml

registry apply -f apigee-registry.yaml
```

1. Export your API Hub data for Backstage

```sh
registry-connect publish backstage /tmp/apihub-backstage --owner-name "TEAM NAME" --owner-desc "TEAM DESC"
```

1. Start Backstage

```sh
docker-compose up
```
