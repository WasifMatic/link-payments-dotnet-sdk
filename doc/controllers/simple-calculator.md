# Simple Calculator

```csharp
SimpleCalculatorApi simpleCalculatorApi = client.SimpleCalculatorApi;
```

## Class Name

`SimpleCalculatorApi`


# Calculate

Calculates the expression using the specified operation.

```csharp
CalculateAsync(
    Models.OperationType operation,
    double x,
    double y)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `operation` | [`OperationType`](../../doc/models/operation-type.md) | Template, Required | The operator to apply on the variables |
| `x` | `double` | Query, Required | The LHS value |
| `y` | `double` | Query, Required | The RHS value |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type double.

## Example Usage

```csharp
OperationType operation = OperationType.Sum;
double x = 222.14;
double y = 165.14;
try
{
    ApiResponse<double> result = await simpleCalculatorApi.CalculateAsync(
        operation,
        x,
        y
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
}
```

