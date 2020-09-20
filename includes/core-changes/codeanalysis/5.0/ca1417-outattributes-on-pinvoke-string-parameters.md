---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065157"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="ce4ee-101">CA1417: OutAttribute für Zeichenfolgenparameter für P/Invoke</span><span class="sxs-lookup"><span data-stu-id="ce4ee-101">CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="ce4ee-102">Die .NET-Codeanalyseregel [CA1417](/visualstudio/code-quality/ca1417) ist ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-102">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="ce4ee-103">Sie erzeugt eine Buildwarnung für alle Methodendefinitionen für [Plattformaufrufe (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md), bei denen ein <xref:System.String>-Parameter im Wert übergeben und mit <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-103">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ce4ee-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ce4ee-104">Change description</span></span>

<span data-ttu-id="ce4ee-105">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="ce4ee-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="ce4ee-106">Einige dieser Regeln, darunter [CA1417](/visualstudio/code-quality/ca1417), sind standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-106">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="ce4ee-107">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="ce4ee-108">Die Regel CA1417 kennzeichnet [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md)-Methodendefinitionen, bei denen ein <xref:System.String>-Parameter mit dem Attribut <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnet und im Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-108">Rule CA1417 flags [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="ce4ee-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ce4ee-109">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="ce4ee-110">Die .NET-Runtime verwaltet eine als Internpool bezeichnete Tabelle, die einen einzelnen Verweis auf jedes eindeutige Zeichenfolgenliteral in einem Programm enthält.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-110">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="ce4ee-111">Wenn eine mit <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnete internalisierte Zeichenfolge im Wert an eine P/Invoke-Methode übergeben wird, kann die Runtime destabilisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-111">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="ce4ee-112">Weitere Informationen zur Internalisierung von Zeichenfolgen finden Sie in den Hinweisen zu <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-112">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ce4ee-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ce4ee-113">Version introduced</span></span>

<span data-ttu-id="ce4ee-114">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="ce4ee-114">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ce4ee-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ce4ee-115">Recommended action</span></span>

- <span data-ttu-id="ce4ee-116">Wenn Sie geänderte Zeichenfolgendaten zurück zum Aufrufer marshallen müssen, übergeben Sie die Zeichenfolge stattdessen in einem Verweis.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-116">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="ce4ee-117">Wenn Sie geänderte Zeichenfolgendaten nicht zurück zum Aufrufer marshallen müssen, entfernen Sie einfach <xref:System.Runtime.InteropServices.OutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-117">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="ce4ee-118">Weitere Informationen finden Sie unter [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="ce4ee-118">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="ce4ee-119">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-119">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="ce4ee-120">Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="ce4ee-120">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="ce4ee-121">Category</span><span class="sxs-lookup"><span data-stu-id="ce4ee-121">Category</span></span>

<span data-ttu-id="ce4ee-122">Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="ce4ee-122">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ce4ee-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ce4ee-123">Affected APIs</span></span>

<span data-ttu-id="ce4ee-124">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="ce4ee-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
