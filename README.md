## XsltEditor.Sdk

[![NuGet](https://img.shields.io/nuget/v/XsltEditor.Sdk)](https://www.nuget.org/packages/XsltEditor.Sdk)

SDK for building plugins for [XSLT Editor](https://github.com/Rckov/Xslt-Editor).

### Installation
```
dotnet add package XsltEditor.Sdk
```

### Usage

```csharp
using XsltEditor.Sdk;
using XsltEditor.Sdk.Abstractions;
using XsltEditor.Sdk.Extensions;

public class MyPlugin : PluginBase
{
    public override string Name => "My Plugin";
    public override string Description => "Does something useful";

    public override void Execute(IDocumentContext context)
    {
        var xml = context.GetDocument(DocumentType.Xml);
        var xsl = context.GetDocument(DocumentType.Xsl);

        // read/write content
        xml?.Content = ProcessXml(xml.Content);
    }
}
```

### Deployment
Build your plugin and copy the output dll to `plugins/{plugin-name}/` next to the editor executable.

## License
[MIT License](LICENSE) | [Report an Issue](https://github.com/Rckov/Xslt-Editor.Sdk/issues)
