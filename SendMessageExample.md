## Sending Messages

1. Inject the required interface into your service:
- `ITaskInterface`
- `IBinInterface`

```c#
public class MyAutoStoreService(ITaskInterface taskInterface)
{
    // ...
}
```
```c#
public class MyAutoStoreService
{
    private readonly ITaskInterface _taskInterface;
    public MyAutoStoreService(ITaskInterface taskInterface) 
    {
        _taskInterface = taskInterface;
    }
    // ...
}
```

2. Call the desired message:
- Use the [Factory Pattern](https://en.wikipedia.org/wiki/Factory_method_pattern) to generate messages.
- Use the [Result Type](https://en.wikipedia.org/wiki/Result_type) to handle responses without exceptions.

```c#
public async Task OpenPortExampleAsync(short portId)
{
    var openPortMessage = OpenPortMsg.Create(portId); // Create message using factory
    var asrsResponse = await taskInterface.OpenPortAsync(openPortMessage); // send the message

    if (asrsResponse is null) 
    {
        // Handle null response
        return;
    }

    if (asrsResponse.Failure)
    {
        // Handle Failure response
        return;
    }

    // Handle successful response
    // ...
});
```

3. Logging
- When you implement the proper interfaces required during DI, the library will automatically call your logging functions. With proper implementation of those interfaces, you cannot forget to log when using the interfaces provide in the library.
