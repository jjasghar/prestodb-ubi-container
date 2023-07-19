# PrestoDB UBI9 Container

## Scope

This is a update from thet `openjdk:8-jre` container to the UBI9 container from Red Hat.

## Build

- Login to the Red Hat Registry:
```bash
$ docker login registry.redhat.io
Username: {REGISTRY-SERVICE-ACCOUNT-USERNAME}
Password: {REGISTRY-SERVICE-ACCOUNT-PASSWORD}
Login Succeeded!
```
- Close this repostiroy, `cd` into it.
- Build the container, check the version `.282` was the newest at testing:
```bash
docker build --build-arg PRESTO_VERSION=0.282 . -t prestodb:latest
```
- Run the container:
```bash
docker run --name presto prestodb:latest
```

## Run

In another terminal, you can run the `presto` cli via:
```bash
docker exec -it presto presto
```
Then with sanity check:
```sql
SHOW SCHEMAS FROM tpch;
```
If the scheme list comes back, then you are talking to Presto.

## License & Authors

If you would like to see the detailed LICENSE click [here](./LICENSE).

- Author: JJ Asghar <awesome@ibm.com>

```text
Copyright:: 2023- IBM, Inc

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

