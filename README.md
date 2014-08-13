MoqExtensions
=============

A library of extensions for the Moq framework (currently only .ReturnsInOrder)

All credit goes to Phil Haack's blog post http://haacked.com/archive/2010/11/24/moq-sequences-revisited.aspx/

Code usage:

```C#
var mock = new Mock<ISomeInterface>();
mock.Setup(r => r.GetNext())
    .ReturnsInOrder(1, 2, new InvalidOperationException());

Console.WriteLine(mock.Object.GetNext());
Console.WriteLine(mock.Object.GetNext());
Console.WriteLine(mock.Object.GetNext()); // Throws InvalidOperationException
```
