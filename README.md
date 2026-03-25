# \## XsltEditor.Sdk

# 

# \[!\[NuGet](https://img.shields.io/nuget/v/XsltEditor.Sdk)](https://www.nuget.org/packages/XsltEditor.Sdk)

# 

# SDK for building plugins for \[XSLT Editor](https://github.com/Rckov/Xslt-Editor).

# 

# \### Installation

# ```

# dotnet add package XsltEditor.Sdk

# ```

# 

# \### Usage

# 

# ```csharp

# using XsltEditor.Sdk;

# using XsltEditor.Sdk.Abstractions;

# using XsltEditor.Sdk.Extensions;

# 

# public class MyPlugin : PluginBase

# {

# &nbsp;   public override string Name => "My Plugin";

# &nbsp;   public override string Description => "Does something useful";

# 

# &nbsp;   public override void Execute(IDocumentContext context)

# &nbsp;   {

# &nbsp;       var xml = context.GetDocument(DocumentType.Xml);

# &nbsp;       var xsl = context.GetDocument(DocumentType.Xsl);

# 

# &nbsp;       // read/write content

# &nbsp;       xml?.Content = ProcessXml(xml.Content);

# &nbsp;   }

# }

# ```

# 

# \### Deployment

# Build your plugin and copy the output dll to `plugins/{plugin-name}/` next to the editor executable.

# 

# \## License

# \[MIT](LICENSE)

# 

