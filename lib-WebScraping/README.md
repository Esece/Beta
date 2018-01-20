# lib-WebScraping

This is a class library that contains a series of functions for web scraping.

## Getting Started

No compilation needed.

### Dependencies

```
System.Web.dll
```

## Examples (selected)
See unit tests for more examples.

### Extracting text...

```c#
[WebMapSource("https://www.crateandbarrel.com/all-clad-d5-10-piece-cookware-set-with-bonus/s{Sku}")]
class ProductInfo
{
    public string Sku { get; set; }

    [WebMap("id=\"productNameHeader\"", ">", "<")]
    public string ProductName { get; set; }
}
```

```c#
var productInfo = new ProductInfo { Sku = "650616" }.MapFromWeb();
```
##### productInfo
| Sku         | ProductName                                 |
|:----------- |:--------------------------------------------|
| 650616      | Ravenna Nesting Ceramic Bowls Set of 4      |

#### Features

* HTML decode
* Type conversion
* Extension methods avaliable for easy discovery (Add S2.Extensions namespace)

#### Options

* Disable HTML Decoding
* Source URL override


## Running the tests

A unit test project is available for viewing and downloading for all the supported operations.

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

## Versioning

We use an auto incrementing version number in Visual Studio. See the rules at https://msdn.microsoft.com/en-us/library/system.reflection.assemblyversionattribute.aspx. 

```c#
[assembly: AssemblyVersion("1.0.*")]
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

Copyright (c) 2017 sekoguchi.net

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
