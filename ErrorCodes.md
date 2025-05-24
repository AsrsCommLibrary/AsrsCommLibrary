## Error Codes

- AutoStore has hundreds of error codes, each with their own unique description.
- AsrsCommLibrary provides a simple interface to convert those values to human readable errors.

## Example Usage:
```c#
public class ErrorCodeExample(IAsrsFaultCodeService faultCodeService)
{
    public string ConvertAsrsErrorCode(int faultCode) 
    {
        return faultCodeService.GetFaultCodeDesc(faultCode);
    }
}
```