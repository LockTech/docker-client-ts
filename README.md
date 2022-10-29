<div align="center">
  <h1>🐳&nbsp;&nbsp;&nbsp;Docker Engine API Client</h1>
  <p>(a) NodeJS client for the Docker Engine API with support for TypeScript</p>
  <br />
  <div style="display:flex;flex-direction:row;justify-content:center;">
    <a href="https://www.npmjs.com/package/@locktech/docker-client">
      <img src="https://img.shields.io/badge/NPM-%40locktech%2Fdocker--client-red?logo=node.js&logoColor=white">
    </a>
    <a href="https://github.com/LockTech/docker-client-ts/releases/" style="margin:0 1rem;">
      <img src="https://img.shields.io/github/release/LockTech/docker-client-ts?include_prereleases=&sort=semver&color=2ea44f">
    </a>
    <a href="#license">
      <img src="https://img.shields.io/badge/License-MIT-2ea44f">
    </a>
  </div>
  <br />
  <br />
</div>

> **Note** <br />
> See [the contributing section](#contributing) for details on generating a different version of the client.

## Getting Started

Start by installing the client using your preferred package manager, below is an example of Yarn.

```bash
yarn add @locktech/docker-client
```

## Contributing

This repository acts as a template for generating, building, and publishing a client for the Docker Engine API. This process is triggered when [a new release is created](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository#creating-a-release), which will use [the configured specification](./.github/workflows/release.yml) as a reference for generation. After being generated, the built package is published to the npm registry - versioned using the release's `tag`.

```YAML
name: CI — Generate and Release

env:
  # Update the following to change the reference used for generating the client.
  DOCKER_ENGINE_API: https://docs.docker.com/engine/api/v1.41.yaml

...
```

### Building Manually

The following steps will build the client locally, and is the same set of steps used by the repository's CI runner.

1. `git clone https://github.com/LockTech/docker-client-ts.git`
2. `npm install`
3. `npm run generate https://docs.docker.com/engine/api/vX.XX.yaml`
   - Generate a client using the given specification as a reference.
   - You can get the published version via [the `release` workflow](./.github/workflows/release.yml).
4. `npm run build`

## License

This repository and the generated code is provided under the [MIT license](./LICENSE). The reference Swagger specification used to generate the client is licensed under [Apache 2.0](https://github.com/docker/engine#licensing).

## References

- [Docker Engine API](https://docs.docker.com/engine/api/)
  - [Latest Reference](https://docs.docker.com/engine/api/latest/)
- [swagger-typescript-api](https://github.com/acacode/swagger-typescript-api)
