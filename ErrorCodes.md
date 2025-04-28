## Error Codes

- AutoStore has hundreds of error codes, each with their own unique description.
- AutoStoreCommLibrary provides a simple interface to convert those values to human readable errors.

## Example Usage:
```c#
public class ErrorCodeExample(IAutoStoreFaultCodeService faultCodeService)
{
    public string ConvertAutoStoreErrorCode(int faultCode) 
    {
        return faultCodeService.GetFaultCodeDesc(faultCode);
    }
}
```