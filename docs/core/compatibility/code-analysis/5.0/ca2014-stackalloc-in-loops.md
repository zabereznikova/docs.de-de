---
title: 'Breaking Change: CA2014: Verwenden Sie stackalloc nicht in Schleifen.'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA2014“ ausgelöst wird.
ms.date: 09/03/2020
ms.openlocfilehash: 7ad6203c0edd930bbbe43cdb8df0413cba833d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759191"
---
# <a name="warning-ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="49319-103">Warnung CA2014: Verwenden Sie stackalloc nicht in Schleifen.</span><span class="sxs-lookup"><span data-stu-id="49319-103">Warning CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="49319-104">Die .NET-Codeanalyseregel [CA2014](/visualstudio/code-quality/ca2014) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="49319-104">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="49319-105">Sie erzeugt eine Buildwarnung für jeden C#-Code, in dem ein [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md)-Ausdruck innerhalb einer Schleife verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="49319-105">It produces a build warning for any C# code where a [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

## <a name="change-description"></a><span data-ttu-id="49319-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="49319-106">Change description</span></span>

<span data-ttu-id="49319-107">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="49319-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="49319-108">Mehrere dieser Regeln, einschließlich [CA2014](/visualstudio/code-quality/ca2014), werden standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="49319-108">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="49319-109">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="49319-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="49319-110">Die Regel CA2014 sucht nach C#-Code, in dem ein [stackalloc-Ausdruck](../../../../csharp/language-reference/operators/stackalloc.md) innerhalb einer Schleife verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="49319-110">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="49319-111">Mit [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) wird Speicher aus dem aktuellen Stapelrahmen belegt.</span><span class="sxs-lookup"><span data-stu-id="49319-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="49319-112">Der Speicher wird erst wieder freigegeben, wenn der aktuelle Methodenaufruf zurückgegeben wird. Dies kann zu Stapelüberläufen führen.</span><span class="sxs-lookup"><span data-stu-id="49319-112">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="49319-113">Da Ausnahmen von Stapelüberläufen nicht abgefangen werden können, wird die App im Falle eines Stapelüberlaufs beendet.</span><span class="sxs-lookup"><span data-stu-id="49319-113">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="49319-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="49319-114">Version introduced</span></span>

<span data-ttu-id="49319-115">5.0</span><span class="sxs-lookup"><span data-stu-id="49319-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="49319-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="49319-116">Recommended action</span></span>

- <span data-ttu-id="49319-117">Verwenden Sie [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) nicht innerhalb von Schleifen.</span><span class="sxs-lookup"><span data-stu-id="49319-117">Avoid using [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="49319-118">Weisen Sie den Speicherblock außerhalb der Schleife zu, und verwenden Sie ihn innerhalb der Schleife wieder.</span><span class="sxs-lookup"><span data-stu-id="49319-118">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="49319-119">Weitere Informationen finden Sie unter [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="49319-119">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="49319-120">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="49319-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="49319-121">Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="49319-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="49319-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="49319-122">Affected APIs</span></span>

<span data-ttu-id="49319-123">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="49319-123">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
