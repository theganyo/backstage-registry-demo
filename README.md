# Backstage Demo

A basic [Backstage](https://backstage.io) app using Docker, configured to show API Hub data.

To use:

1. Install prerequisites:

```sh
curl -L https://raw.githubusercontent.com/apigee/registry/main/downloadLatest.sh | sh -
curl -L https://raw.githubusercontent.com/apigee/registry-experimental/main/downloadLatest.sh | sh -
export PATH=$PATH:$HOME/.registry/bin

git clone git@github.com:theganyo/backstage-registry-demo.git
cd backstage-registry-demo
```

2. Import your Apigee data into API Hub (use `--help` for further information on commands)

```sh
registry-connect discover apigee proxies YOUR-ORGANIZATION > apigee-registry.yaml

registry apply -f apigee-registry.yaml
```

3. Export your API Hub data for Backstage

```sh
registry-connect publish backstage apihub-backstage --owner-name "TEAM NAME" --owner-desc "TEAM DESC"
```

4. Run Backstage

```sh
docker-compose up
```

[Open Backstage UI](http://localhost:7007)
