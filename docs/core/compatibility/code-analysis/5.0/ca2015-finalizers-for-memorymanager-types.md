---
title: 'Breaking Change: CA2015: Keine Finalizer für von MemoryManager abgeleitete Typen definieren<T>'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA2015“ ausgelöst wird.
ms.date: 09/03/2020
ms.openlocfilehash: 5d0ba0546b5a72363559f23713c8af4bb4e26e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759190"
---
# <a name="warning-ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="8f345-103">Warnung CA2015: Keine Finalizer für von MemoryManager abgeleitete Typen definieren\<T></span><span class="sxs-lookup"><span data-stu-id="8f345-103">Warning CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="8f345-104">Die .NET-Codeanalyseregel [CA2015](/visualstudio/code-quality/ca2015) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f345-104">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="8f345-105">Sie erzeugt eine Buildwarnung für alle Typen, die von <xref:System.Buffers.MemoryManager%601> abgeleitet werden und einen Finalizer definieren.</span><span class="sxs-lookup"><span data-stu-id="8f345-105">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

## <a name="change-description"></a><span data-ttu-id="8f345-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8f345-106">Change description</span></span>

<span data-ttu-id="8f345-107">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="8f345-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="8f345-108">Mehrere dieser Regeln, einschließlich [CA2015](/visualstudio/code-quality/ca2015), werden standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f345-108">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="8f345-109">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="8f345-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="8f345-110">Mithilfe der Regel CA2015 werden Typen gekennzeichnet, die von <xref:System.Buffers.MemoryManager%601> abgeleitet werden und einen Finalizer definieren.</span><span class="sxs-lookup"><span data-stu-id="8f345-110">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="8f345-111">Wenn ein Finalizer zu einem von <xref:System.Buffers.MemoryManager%601> abgeleiteten Typen hinzugefügt wird, liegt wahrscheinlich ein Fehler vor.</span><span class="sxs-lookup"><span data-stu-id="8f345-111">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="8f345-112">Dieser deutet darauf hin, dass eine native Ressource, die in einer <xref:System.Span%601>-Struktur abgerufen werden könnte, bereinigt wird, während sie möglicherweise noch von <xref:System.Span%601> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f345-112">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="8f345-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8f345-113">Version introduced</span></span>

<span data-ttu-id="8f345-114">5.0</span><span class="sxs-lookup"><span data-stu-id="8f345-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8f345-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="8f345-115">Recommended action</span></span>

- <span data-ttu-id="8f345-116">Entfernen Sie die Definition des Finalizers.</span><span class="sxs-lookup"><span data-stu-id="8f345-116">Remove the finalizer definition.</span></span> <span data-ttu-id="8f345-117">Weitere Informationen finden Sie unter [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="8f345-117">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="8f345-118">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f345-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="8f345-119">Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="8f345-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8f345-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8f345-120">Affected APIs</span></span>

<span data-ttu-id="8f345-121">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="8f345-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
