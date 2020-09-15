---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065159"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="6b337-101">CA2014: Verwenden Sie stackalloc nicht in Schleifen.</span><span class="sxs-lookup"><span data-stu-id="6b337-101">CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="6b337-102">Die .NET-Codeanalyseregel [CA2014](/visualstudio/code-quality/ca2014) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6b337-102">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="6b337-103">Sie erzeugt eine Buildwarnung für jeden C#-Code, in dem ein [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md)-Ausdruck innerhalb einer Schleife verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b337-103">It produces a build warning for any C# code where a [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6b337-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6b337-104">Change description</span></span>

<span data-ttu-id="6b337-105">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="6b337-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="6b337-106">Mehrere dieser Regeln, einschließlich [CA2014](/visualstudio/code-quality/ca2014), werden standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6b337-106">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="6b337-107">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="6b337-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="6b337-108">Die Regel CA2014 sucht nach C#-Code, in dem ein [stackalloc-Ausdruck](../../../../docs/csharp/language-reference/operators/stackalloc.md) innerhalb einer Schleife verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b337-108">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../docs/csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="6b337-109">Mit [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) wird Speicher aus dem aktuellen Stapelrahmen belegt.</span><span class="sxs-lookup"><span data-stu-id="6b337-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="6b337-110">Der Speicher wird erst wieder freigegeben, wenn der aktuelle Methodenaufruf zurückgegeben wird. Dies kann zu Stapelüberläufen führen.</span><span class="sxs-lookup"><span data-stu-id="6b337-110">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="6b337-111">Da Ausnahmen von Stapelüberläufen nicht abgefangen werden können, wird die App im Falle eines Stapelüberlaufs beendet.</span><span class="sxs-lookup"><span data-stu-id="6b337-111">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6b337-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6b337-112">Version introduced</span></span>

<span data-ttu-id="6b337-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="6b337-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6b337-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="6b337-114">Recommended action</span></span>

- <span data-ttu-id="6b337-115">Verwenden Sie [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) nicht innerhalb von Schleifen.</span><span class="sxs-lookup"><span data-stu-id="6b337-115">Avoid using [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="6b337-116">Weisen Sie den Speicherblock außerhalb der Schleife zu, und verwenden Sie ihn innerhalb der Schleife wieder.</span><span class="sxs-lookup"><span data-stu-id="6b337-116">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="6b337-117">Weitere Informationen finden Sie unter [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="6b337-117">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="6b337-118">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6b337-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="6b337-119">Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="6b337-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="6b337-120">Category</span><span class="sxs-lookup"><span data-stu-id="6b337-120">Category</span></span>

<span data-ttu-id="6b337-121">Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="6b337-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6b337-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6b337-122">Affected APIs</span></span>

<span data-ttu-id="6b337-123">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="6b337-123">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
