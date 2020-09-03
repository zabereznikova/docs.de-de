---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 60dc0a11ebdd77f969f41891d5cca06335cda6a7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88957684"
---
### <a name="razor-razortemplateengine-api-removed"></a>Razor: RazorTemplateEngine-API wurde entfernt

Die API [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) wurde entfernt und durch <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine> ersetzt.

Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Ein Vorlagen-Engine kann erstellt und zum Analysieren und Generieren von Code für Razor-Dateien verwendet werden.

#### <a name="new-behavior"></a>Neues Verhalten

`RazorProjectEngine` kann erstellt und mit derselben Art von Informationen wie `RazorTemplateEngine` versorgt werden, um Code für Razor-Dateien zu analysieren und zu generieren. `RazorProjectEngine` stellt außerdem zusätzliche Konfigurationsebenen bereit.

#### <a name="reason-for-change"></a>Grund für die Änderung

`RazorTemplateEngine` war zu eng an die vorhandenen Implementierungen gekoppelt. Diese enge Kopplung führte zu weiteren Fragen beim Versuch, eine Razor-Pipeline für die Analyse/Generierung von Code ordnungsgemäß zu konfigurieren.

#### <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie `RazorProjectEngine` anstelle von `RazorTemplateEngine`. Betrachten Sie die folgenden Beispiele.

##### <a name="create-and-configure-the-razorprojectengine"></a>Erstellen und Konfigurieren der RazorProjectEngine-API

```csharp
RazorProjectEngine projectEngine =
    RazorProjectEngine.Create(RazorConfiguration.Default,
        RazorProjectFileSystem.Create(@"C:\source\repos\ConsoleApp4\ConsoleApp4"),
        builder =>
        {
            builder.ConfigureClass((document, classNode) =>
            {
                classNode.ClassName = "MyClassName";

                // Can also configure other aspects of the class here.
            });

            // More configuration can go here
        });
```

##### <a name="generate-code-for-a-razor-file"></a>Generieren von Code für eine Razor-Datei

```csharp
RazorProjectItem item = projectEngine.FileSystem.GetItem(
    @"C:\source\repos\ConsoleApp4\ConsoleApp4\Example.cshtml",
    FileKinds.Legacy);
RazorCodeDocument output = projectEngine.Process(item);

// Things available
RazorSyntaxTree syntaxTree = output.GetSyntaxTree();
DocumentIntermediateNode intermediateDocument =
    output.GetDocumentIntermediateNode();
RazorCSharpDocument csharpDocument = output.GetCSharpDocument();
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [RazorTemplateEngineOptions](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->
