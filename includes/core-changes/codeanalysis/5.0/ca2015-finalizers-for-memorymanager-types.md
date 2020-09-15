---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065158"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="bed04-101">CA2015: Keine Finalizer für von MemoryManager abgeleitete Typen definieren\<T></span><span class="sxs-lookup"><span data-stu-id="bed04-101">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="bed04-102">Die .NET-Codeanalyseregel [CA2015](/visualstudio/code-quality/ca2015) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bed04-102">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="bed04-103">Sie erzeugt eine Buildwarnung für alle Typen, die von <xref:System.Buffers.MemoryManager%601> abgeleitet werden und einen Finalizer definieren.</span><span class="sxs-lookup"><span data-stu-id="bed04-103">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bed04-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="bed04-104">Change description</span></span>

<span data-ttu-id="bed04-105">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="bed04-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="bed04-106">Mehrere dieser Regeln, einschließlich [CA2015](/visualstudio/code-quality/ca2015), werden standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bed04-106">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="bed04-107">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="bed04-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="bed04-108">Mithilfe der Regel CA2015 werden Typen gekennzeichnet, die von <xref:System.Buffers.MemoryManager%601> abgeleitet werden und einen Finalizer definieren.</span><span class="sxs-lookup"><span data-stu-id="bed04-108">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="bed04-109">Wenn ein Finalizer zu einem von <xref:System.Buffers.MemoryManager%601> abgeleiteten Typen hinzugefügt wird, liegt wahrscheinlich ein Fehler vor.</span><span class="sxs-lookup"><span data-stu-id="bed04-109">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="bed04-110">Dieser deutet darauf hin, dass eine native Ressource, die in einer <xref:System.Span%601>-Struktur abgerufen werden könnte, bereinigt wird, während sie möglicherweise noch von <xref:System.Span%601> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bed04-110">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bed04-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="bed04-111">Version introduced</span></span>

<span data-ttu-id="bed04-112">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="bed04-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bed04-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="bed04-113">Recommended action</span></span>

- <span data-ttu-id="bed04-114">Entfernen Sie die Definition des Finalizers.</span><span class="sxs-lookup"><span data-stu-id="bed04-114">Remove the finalizer definition.</span></span> <span data-ttu-id="bed04-115">Weitere Informationen finden Sie unter [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="bed04-115">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="bed04-116">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bed04-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="bed04-117">Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="bed04-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="bed04-118">Category</span><span class="sxs-lookup"><span data-stu-id="bed04-118">Category</span></span>

<span data-ttu-id="bed04-119">Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="bed04-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bed04-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="bed04-120">Affected APIs</span></span>

<span data-ttu-id="bed04-121">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="bed04-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
