# Cogito.AspNet.ServiceModel

[![Build](https://github.com/alethic/Cogito.AspNet.ServiceModel/actions/workflows/Cogito.AspNet.ServiceModel.yml/badge.svg)](https://github.com/alethic/Cogito.AspNet.ServiceModel/actions/workflows/Cogito.AspNet.ServiceModel.yml)

Routes WCF services through ASP.NET routing, so endpoint addresses are decided at runtime rather than fixed in web.config.

## Packages

**[Cogito.AspNet.ServiceModel](https://www.nuget.org/packages/Cogito.AspNet.ServiceModel)** — Route WCF services through ASP.NET routing, with the route known at runtime rather than baked into `web.config`.

Each package carries its own README with the detail; the links above go to nuget.org.

## Building

```shell
dotnet restore Cogito.AspNet.ServiceModel.slnx
dotnet msbuild -p:Configuration=Release Cogito.AspNet.ServiceModel.dist.msbuildproj
```

Packages are staged into `dist/nuget` and test suites into `dist/tests`; run a suite with
`dotnet test -f <tfm> <path to its assembly>`.

## License

MIT — see [LICENSE](LICENSE).
