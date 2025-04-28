## Dependency Injection

- We must define two interfaces to handle Api message logging and Log Publisher message processing. `ILogPublisherMessageHandler` and `ILogAutoStoreApiMessages`

### Task Interface

Production

```c#
builder.Services.AddAutoStoreTaskInterfaceHttp<AutoStoreLPMessageHandlerLogger, AutoStoreApiMessageHandlerLogger>(options =>
{
    options.LogPublisherIp = "127.0.0.1";
    options.LogPublisherPort = 44000;
    options.Timeout = TimeSpan.FromSeconds(5);
});
```

Simulation

```c#
builder.Services.AddAutoStoreTaskInterfaceSim<AutoStoreLPMessageHandlerLogger, AutoStoreApiMessageHandlerLogger>();
```

### Bin Interface

