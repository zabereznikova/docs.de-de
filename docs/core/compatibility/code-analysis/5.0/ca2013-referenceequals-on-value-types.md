---
title: 'Breaking Change: CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA2013“ ausgelöst wird.
ms.date: 09/03/2020
ms.openlocfilehash: ca2b845427eff547b996b577394c6859e30f50bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759192"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="e0a38-103">Warnung CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.</span><span class="sxs-lookup"><span data-stu-id="e0a38-103">Warning CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="e0a38-104">Die .NET-Codeanalyseregel [CA2013](/visualstudio/code-quality/ca2013) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e0a38-104">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="e0a38-105">Sie erzeugt eine Buildwarnung für Code, in dem <xref:System.Object.ReferenceEquals(System.Object,System.Object)> verwendet wird, um einen oder mehrere Werttypen auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e0a38-105">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

## <a name="change-description"></a><span data-ttu-id="e0a38-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e0a38-106">Change description</span></span>

<span data-ttu-id="e0a38-107">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0a38-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="e0a38-108">Einige dieser Regeln, darunter [CA2013](/visualstudio/code-quality/ca2013), sind standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e0a38-108">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="e0a38-109">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="e0a38-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="e0a38-110">Die Regel CA2013 ermittelt Instanzen, bei denen <xref:System.Object.ReferenceEquals(System.Object,System.Object)> verwendet wird, um einen oder mehrere Werttypen auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e0a38-110">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="e0a38-111">Das Überprüfen von Werttypen auf Gleichheit auf diese Weise kann zu falschen Ergebnissen führen, da die Werte vor dem Vergleich geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="e0a38-111">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="e0a38-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> gibt `false` zurück, auch wenn die verglichenen Werte dieselbe Instanz eines Werttyps darstellen.</span><span class="sxs-lookup"><span data-stu-id="e0a38-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e0a38-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e0a38-113">Version introduced</span></span>

<span data-ttu-id="e0a38-114">5.0</span><span class="sxs-lookup"><span data-stu-id="e0a38-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e0a38-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="e0a38-115">Recommended action</span></span>

- <span data-ttu-id="e0a38-116">Ändern Sie den Code so, dass ein geeigneter Gleichheitsoperator verwendet wird, z. B. `==`.</span><span class="sxs-lookup"><span data-stu-id="e0a38-116">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="e0a38-117">Sie sollten diese Warnung nicht unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="e0a38-117">You should not suppress this warning.</span></span>

- <span data-ttu-id="e0a38-118">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e0a38-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="e0a38-119">Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="e0a38-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e0a38-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e0a38-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
