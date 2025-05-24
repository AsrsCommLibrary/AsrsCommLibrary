## Dependency Injection

- We must define two interfaces to handle Api message logging and Log Publisher message processing. `ILogPublisherMessageHandler` and `ILogAsrsApiMessages`

### Task Interface

Production
```c#
builder.Services.AddAsrsTaskInterfaceHttp<AsrsLPMessageHandlerLogger, AsrsApiMessageHandlerLogger>(options =>
{
    options.LogPublisherIp = "127.0.0.1";
    options.LogPublisherPort = 44000;
    options.Timeout = TimeSpan.FromSeconds(5);
});
```

Simulation
```c#
builder.Services.AddAsrsTaskInterfaceSim<AsrsLPMessageHandlerLogger, AsrsApiMessageHandlerLogger>();
```

### Bin Interface

Production
```c#
builder.Services.AddAsrsBinInterfaceHttp<AsrsLPMessageHandlerLogger, AsrsApiMessageHandlerLogger>(options =>
{
    options.LogPublisherIp = "127.0.0.1";
    options.LogPublisherPort = 44000;
    options.Timeout = TimeSpan.FromSeconds(5);
});
```

Simulation (Not currently supported)

```c#
builder.Services.AddAsrsTaskInterfaceSim<AsrsLPMessageHandlerLogger, AsrsApiMessageHandlerLogger>();
```