## Sending Messages

1. Inject the respective interface into your service:
- `ITaskInterface`
- `IBinInterface`

```c#
public class MyAutoStoreService(ITaskInterface autostoreInterface)
{
    // ...
}
```
```c#
public class MyAutoStoreService
{
    private readonly ITaskInterface _autostoreInterface;
    public MyAutoStoreService(ITaskInterface autostoreInterface) 
    {
        _autostoreInterface = autostoreInterface;
    }
    // ...
}
```

2. Call the desired message:
- Use the [Factory Pattern](https://en.wikipedia.org/wiki/Factory_method_pattern) to generate messages.
- Use the [Result Type](https://en.wikipedia.org/wiki/Result_type) to handle responses without exceptions.

```c#
public async void OpenPortExample(short portId)
{
    var openPortMessage = OpenPortMsg.Create(portId); // Create message using factory
    var autostoreResponse = await autostoreInterface.OpenPortAsync(openPortMessage);

    if (autostoreResponse is null) 
    {
        // Handle Null response
    }

    if (autostoreResponse.Failure)
    {
        // Handle Failure response
    }

    // Handle successful response
    // ...
});
```

3. Logging
- When you implement the proper interfaces required during DI, the library will automatically call the logging functions. That is, you cannot forget to log when using the interfaces provide in the library.
