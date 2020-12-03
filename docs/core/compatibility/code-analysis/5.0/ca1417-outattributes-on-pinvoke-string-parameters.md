---
title: 'Breaking Change: CA1417: OutAttribute für Zeichenfolgenparameter für P/Invoke'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA1417“ ausgelöst wird.
ms.date: 09/29/2020
ms.openlocfilehash: 3316d07108ec7f9da985494413336cba6d560dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759196"
---
# <a name="warning-ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="74ca3-103">Warnung CA1417: OutAttribute für Zeichenfolgenparameter für P/Invoke</span><span class="sxs-lookup"><span data-stu-id="74ca3-103">Warning CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="74ca3-104">Die .NET-Codeanalyseregel [CA1417](/visualstudio/code-quality/ca1417) ist ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="74ca3-104">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="74ca3-105">Sie erzeugt eine Buildwarnung für alle Methodendefinitionen für [Plattformaufrufe (P/Invoke)](../../../../standard/native-interop/pinvoke.md), bei denen ein <xref:System.String>-Parameter im Wert übergeben und mit <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="74ca3-105">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

## <a name="change-description"></a><span data-ttu-id="74ca3-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="74ca3-106">Change description</span></span>

<span data-ttu-id="74ca3-107">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="74ca3-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="74ca3-108">Einige dieser Regeln, darunter [CA1417](/visualstudio/code-quality/ca1417), sind standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="74ca3-108">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="74ca3-109">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="74ca3-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="74ca3-110">Die Regel CA1417 kennzeichnet [P/Invoke](../../../../standard/native-interop/pinvoke.md)-Methodendefinitionen, bei denen ein <xref:System.String>-Parameter mit dem Attribut <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnet und im Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="74ca3-110">Rule CA1417 flags [P/Invoke](../../../../standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="74ca3-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74ca3-111">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="74ca3-112">Die .NET-Runtime verwaltet eine als Internpool bezeichnete Tabelle, die einen einzelnen Verweis auf jedes eindeutige Zeichenfolgenliteral in einem Programm enthält.</span><span class="sxs-lookup"><span data-stu-id="74ca3-112">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="74ca3-113">Wenn eine mit <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnete internalisierte Zeichenfolge im Wert an eine P/Invoke-Methode übergeben wird, kann die Runtime destabilisiert werden.</span><span class="sxs-lookup"><span data-stu-id="74ca3-113">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="74ca3-114">Weitere Informationen zur Internalisierung von Zeichenfolgen finden Sie in den Hinweisen zu <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74ca3-114">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="74ca3-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="74ca3-115">Version introduced</span></span>

<span data-ttu-id="74ca3-116">5.0</span><span class="sxs-lookup"><span data-stu-id="74ca3-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="74ca3-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="74ca3-117">Recommended action</span></span>

- <span data-ttu-id="74ca3-118">Wenn Sie geänderte Zeichenfolgendaten zurück zum Aufrufer marshallen müssen, übergeben Sie die Zeichenfolge stattdessen in einem Verweis.</span><span class="sxs-lookup"><span data-stu-id="74ca3-118">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="74ca3-119">Wenn Sie geänderte Zeichenfolgendaten nicht zurück zum Aufrufer marshallen müssen, entfernen Sie einfach <xref:System.Runtime.InteropServices.OutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="74ca3-119">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="74ca3-120">Weitere Informationen finden Sie unter [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="74ca3-120">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="74ca3-121">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="74ca3-121">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="74ca3-122">Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="74ca3-122">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="74ca3-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="74ca3-123">Affected APIs</span></span>

<span data-ttu-id="74ca3-124">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="74ca3-124">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
