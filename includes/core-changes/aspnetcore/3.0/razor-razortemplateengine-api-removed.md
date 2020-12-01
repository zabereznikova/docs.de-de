---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032633"
---
### <a name="razor-razortemplateengine-api-removed"></a><span data-ttu-id="b2aa4-101">Razor: RazorTemplateEngine-API wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b2aa4-101">Razor: RazorTemplateEngine API removed</span></span>

<span data-ttu-id="b2aa4-102">Die API [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) wurde entfernt und durch <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine> ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b2aa4-102">The [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) API was removed and replaced with <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.</span></span>

<span data-ttu-id="b2aa4-103">Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).</span><span class="sxs-lookup"><span data-stu-id="b2aa4-103">For discussion, see GitHub issue [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b2aa4-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b2aa4-104">Version introduced</span></span>

<span data-ttu-id="b2aa4-105">3.0</span><span class="sxs-lookup"><span data-stu-id="b2aa4-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b2aa4-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="b2aa4-106">Old behavior</span></span>

<span data-ttu-id="b2aa4-107">Ein Vorlagen-Engine kann erstellt und zum Analysieren und Generieren von Code für Razor-Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2aa4-107">A template engine can be created and used to parse and generate code for Razor files.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b2aa4-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="b2aa4-108">New behavior</span></span>

<span data-ttu-id="b2aa4-109">`RazorProjectEngine` kann erstellt und mit derselben Art von Informationen wie `RazorTemplateEngine` versorgt werden, um Code für Razor-Dateien zu analysieren und zu generieren.</span><span class="sxs-lookup"><span data-stu-id="b2aa4-109">`RazorProjectEngine` can be created and provided the same type of information as `RazorTemplateEngine` to parse and generate code for Razor files.</span></span> <span data-ttu-id="b2aa4-110">`RazorProjectEngine` stellt außerdem zusätzliche Konfigurationsebenen bereit.</span><span class="sxs-lookup"><span data-stu-id="b2aa4-110">`RazorProjectEngine` also provides extra levels of configuration.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b2aa4-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b2aa4-111">Reason for change</span></span>

<span data-ttu-id="b2aa4-112">`RazorTemplateEngine` war zu eng an die vorhandenen Implementierungen gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="b2aa4-112">`RazorTemplateEngine` was too tightly coupled to the existing implementations.</span></span> <span data-ttu-id="b2aa4-113">Diese enge Kopplung führte zu weiteren Fragen beim Versuch, eine Razor-Pipeline für die Analyse/Generierung von Code ordnungsgemäß zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b2aa4-113">This tight coupling led to more questions when trying to properly configure a Razor parsing/generation pipeline.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b2aa4-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="b2aa4-114">Recommended action</span></span>

<span data-ttu-id="b2aa4-115">Verwenden Sie `RazorProjectEngine` anstelle von `RazorTemplateEngine`.</span><span class="sxs-lookup"><span data-stu-id="b2aa4-115">Use `RazorProjectEngine` instead of `RazorTemplateEngine`.</span></span> <span data-ttu-id="b2aa4-116">Betrachten Sie die folgenden Beispiele.</span><span class="sxs-lookup"><span data-stu-id="b2aa4-116">Consider the following examples.</span></span>

##### <a name="create-and-configure-the-razorprojectengine"></a><span data-ttu-id="b2aa4-117">Erstellen und Konfigurieren der RazorProjectEngine-API</span><span class="sxs-lookup"><span data-stu-id="b2aa4-117">Create and configure the RazorProjectEngine</span></span>

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

##### <a name="generate-code-for-a-razor-file"></a><span data-ttu-id="b2aa4-118">Generieren von Code für eine Razor-Datei</span><span class="sxs-lookup"><span data-stu-id="b2aa4-118">Generate code for a Razor file</span></span>

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

#### <a name="category"></a><span data-ttu-id="b2aa4-119">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b2aa4-119">Category</span></span>

<span data-ttu-id="b2aa4-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aa4-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b2aa4-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b2aa4-121">Affected APIs</span></span>

- [<span data-ttu-id="b2aa4-122">RazorTemplateEngine</span><span class="sxs-lookup"><span data-stu-id="b2aa4-122">RazorTemplateEngine</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [<span data-ttu-id="b2aa4-123">RazorTemplateEngineOptions</span><span class="sxs-lookup"><span data-stu-id="b2aa4-123">RazorTemplateEngineOptions</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->
