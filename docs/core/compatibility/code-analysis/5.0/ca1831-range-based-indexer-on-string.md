---
title: 'Breaking Change: CA1831: Anstelle von bereichsbasierten Indexern AsSpan für Zeichenfolgen verwenden'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA1831“ ausgelöst wird.
ms.date: 08/21/2020
ms.openlocfilehash: 74f34af04a56b73478ffb3305d69ed49f3a30072
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759193"
---
# <a name="warning-ca1831-use-asspan-instead-of-range-based-indexers-for-string"></a><span data-ttu-id="aa734-103">Warnung CA1831: Anstelle von bereichsbasierten Indexern AsSpan für Zeichenfolgen verwenden</span><span class="sxs-lookup"><span data-stu-id="aa734-103">Warning CA1831: Use AsSpan instead of Range-based indexers for string</span></span>

<span data-ttu-id="aa734-104">Die .NET-Codeanalyseregel [CA1831](/visualstudio/code-quality/ca1831) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa734-104">.NET code analyzer rule [CA1831](/visualstudio/code-quality/ca1831) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="aa734-105">Sie erzeugt eine Buildwarnung für Code, bei dem ein auf <xref:System.Range> basierender Indexer für eine Zeichenfolge verwendet wird, aber keine Kopie vorgesehen war.</span><span class="sxs-lookup"><span data-stu-id="aa734-105">It produces a build warning for any code where a <xref:System.Range>-based indexer is used on a string, but no copy was intended.</span></span>

## <a name="change-description"></a><span data-ttu-id="aa734-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="aa734-106">Change description</span></span>

<span data-ttu-id="aa734-107">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="aa734-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="aa734-108">Mehrere dieser Regeln, einschließlich [CA1831](/visualstudio/code-quality/ca1831), werden standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa734-108">Several of these rules are enabled, by default, including [CA1831](/visualstudio/code-quality/ca1831).</span></span> <span data-ttu-id="aa734-109">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="aa734-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="aa734-110">Die Regel CA1831 ermittelt Instanzen, bei denen ein auf <xref:System.Range> basierender Indexer für eine Zeichenfolge verwendet wird, aber keine Kopie vorgesehen war.</span><span class="sxs-lookup"><span data-stu-id="aa734-110">Rule CA1831 finds instances where a <xref:System.Range>-based indexer is used on a string, but no copy was intended.</span></span> <span data-ttu-id="aa734-111">Wenn der auf <xref:System.Range> basierende Indexer direkt für eine Zeichenfolge verwendet wird, um eine implizite Umwandlung durchzuführen, wird eine überflüssige Kopie des angeforderten Zeichenfolgenabschnitts erstellt.</span><span class="sxs-lookup"><span data-stu-id="aa734-111">If the <xref:System.Range>-based indexer is used directly on a string to produce an implicit cast, then an unnecessary copy of the requested portion of the string is created.</span></span> <span data-ttu-id="aa734-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="aa734-112">For example:</span></span>

```csharp
ReadOnlySpan<char> slice = str[1..3];
```

<span data-ttu-id="aa734-113">Laut CA1831 soll der auf <xref:System.Range> basierende Indexer stattdessen für eine *Spanne* der Zeichenfolge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa734-113">CA1831 suggests using the <xref:System.Range>-based indexer on a *span* of the string, instead.</span></span> <span data-ttu-id="aa734-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="aa734-114">For example:</span></span>

```csharp
ReadOnlySpan<char> slice = str.AsSpan()[1..3];
```

## <a name="version-introduced"></a><span data-ttu-id="aa734-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="aa734-115">Version introduced</span></span>

<span data-ttu-id="aa734-116">5.0</span><span class="sxs-lookup"><span data-stu-id="aa734-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="aa734-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="aa734-117">Recommended action</span></span>

- <span data-ttu-id="aa734-118">Rufen Sie <xref:System.MemoryExtensions.AsSpan(System.String)> oder <xref:System.MemoryExtensions.AsMemory(System.String)> vor dem auf <xref:System.Range> basierenden Indexer auf, um Ihren Code zu korrigieren und unnötige Zuteilungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="aa734-118">To correct your code and avoid unnecessary allocations, call <xref:System.MemoryExtensions.AsSpan(System.String)> or <xref:System.MemoryExtensions.AsMemory(System.String)> before using the <xref:System.Range>-based indexer.</span></span> <span data-ttu-id="aa734-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="aa734-119">For example:</span></span>

  ```csharp
  ReadOnlySpan<char> slice = str.AsSpan()[1..3];
  ```

- <span data-ttu-id="aa734-120">Wenn Sie Ihren Code nicht ändern möchten, können Sie die Regel deaktivieren, indem Sie ihren Schweregrad auf `suggestion` oder `none` festlegen.</span><span class="sxs-lookup"><span data-stu-id="aa734-120">If you don't want to change your code, you can disable the rule by setting its severity to `suggestion` or `none`.</span></span> <span data-ttu-id="aa734-121">Weitere Informationen finden Sie unter [Konfigurieren von Codeanalyseregeln](../../../../fundamentals/productivity/configure-code-analysis-rules.md).</span><span class="sxs-lookup"><span data-stu-id="aa734-121">For more information, see [Configure code analysis rules](../../../../fundamentals/productivity/configure-code-analysis-rules.md).</span></span>

- <span data-ttu-id="aa734-122">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="aa734-122">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="aa734-123">Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="aa734-123">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="aa734-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="aa734-124">Affected APIs</span></span>

- <xref:System.Range?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Range`

### Category

Code analysis

-->
