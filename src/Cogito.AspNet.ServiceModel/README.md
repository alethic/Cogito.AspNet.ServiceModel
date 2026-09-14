# Cogito.AspNet.ServiceModel

Route WCF services through ASP.NET routing, with the route known at runtime rather than baked into
`web.config`.

## Why

WCF service activation normally means a `.svc` file per service and a `web.config` section to match.
That is fixed at deploy time, which does not work when the set of endpoints depends on configuration
or on tenant — and it puts `.svc` in every URL.

## Install

```shell
dotnet add package Cogito.AspNet.ServiceModel
```

## Use

Register a route for a service host at startup:

```csharp
RouteTable.Routes.AddDynamicServiceRoute<OrderService>("services/orders");
```

Or mark the service and let it register itself:

```csharp
[DynamicServiceRoute("services/orders")]
public class OrderService : IOrderService
{
}
```

`DynamicServiceRouteEndpointBehavior` keeps the endpoint's address consistent with the route it was
reached through, so generated WSDL points back at the routed URL rather than the physical one.
`DynamicServiceRouteMessageProperty` carries the matched route data onto the message for the service
to read.

Targets .NET Framework.

## License

MIT.
