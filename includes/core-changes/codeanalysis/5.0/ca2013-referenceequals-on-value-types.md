---
ms.openlocfilehash: b01424c63d6e7956127bf889c53422b60ba2f219
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065163"
---
### <a name="ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="14c2f-101">CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.</span><span class="sxs-lookup"><span data-stu-id="14c2f-101">CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="14c2f-102">Die .NET-Codeanalyseregel [CA2013](/visualstudio/code-quality/ca2013) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="14c2f-102">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="14c2f-103">Sie erzeugt eine Buildwarnung für Code, in dem <xref:System.Object.ReferenceEquals(System.Object,System.Object)> verwendet wird, um einen oder mehrere Werttypen auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="14c2f-103">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

#### <a name="change-description"></a><span data-ttu-id="14c2f-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="14c2f-104">Change description</span></span>

<span data-ttu-id="14c2f-105">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="14c2f-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="14c2f-106">Einige dieser Regeln, darunter [CA2013](/visualstudio/code-quality/ca2013), sind standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="14c2f-106">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="14c2f-107">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="14c2f-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="14c2f-108">Die Regel CA2013 ermittelt Instanzen, bei denen <xref:System.Object.ReferenceEquals(System.Object,System.Object)> verwendet wird, um einen oder mehrere Werttypen auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="14c2f-108">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="14c2f-109">Das Überprüfen von Werttypen auf Gleichheit auf diese Weise kann zu falschen Ergebnissen führen, da die Werte vor dem Vergleich geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="14c2f-109">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="14c2f-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> gibt `false` zurück, auch wenn die verglichenen Werte dieselbe Instanz eines Werttyps darstellen.</span><span class="sxs-lookup"><span data-stu-id="14c2f-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="14c2f-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="14c2f-111">Version introduced</span></span>

<span data-ttu-id="14c2f-112">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="14c2f-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="14c2f-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="14c2f-113">Recommended action</span></span>

- <span data-ttu-id="14c2f-114">Ändern Sie den Code so, dass ein geeigneter Gleichheitsoperator verwendet wird, z. B. `==`.</span><span class="sxs-lookup"><span data-stu-id="14c2f-114">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="14c2f-115">Sie sollten diese Warnung nicht unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="14c2f-115">You should not suppress this warning.</span></span>

- <span data-ttu-id="14c2f-116">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="14c2f-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="14c2f-117">Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="14c2f-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="14c2f-118">Category</span><span class="sxs-lookup"><span data-stu-id="14c2f-118">Category</span></span>

<span data-ttu-id="14c2f-119">Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="14c2f-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="14c2f-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="14c2f-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

-->
