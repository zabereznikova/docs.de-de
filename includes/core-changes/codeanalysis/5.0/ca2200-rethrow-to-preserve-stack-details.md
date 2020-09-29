---
ms.openlocfilehash: b697bbf6844759de8babd4245667e7b333884ff8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538922"
---
### <a name="ca2200-rethrow-to-preserve-stack-details"></a><span data-ttu-id="6eba3-101">CA2200: Erneut ausführen, um Stapeldetails beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="6eba3-101">CA2200: Rethrow to preserve stack details</span></span>

<span data-ttu-id="6eba3-102">Die .NET-Codeanalyseregel [CA2200](/visualstudio/code-quality/ca2200) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6eba3-102">.NET code analyzer rule [CA2200](/visualstudio/code-quality/ca2200) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="6eba3-103">Sie erzeugt eine Buildwarnung für alle `catch`-Blöcke, die eine Ausnahme erneut auslösen, und die Ausnahme wird explizit in der `throw`-Anweisung angegeben.</span><span class="sxs-lookup"><span data-stu-id="6eba3-103">It produces a build warning for any `catch` blocks that rethrow an exception and the exception is explicitly specified in the `throw` statement.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6eba3-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6eba3-104">Change description</span></span>

<span data-ttu-id="6eba3-105">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="6eba3-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="6eba3-106">Mehrere dieser Regeln, einschließlich [CA2200](/visualstudio/code-quality/ca2200), sind standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6eba3-106">Several of these rules are enabled, by default, including [CA2200](/visualstudio/code-quality/ca2200).</span></span> <span data-ttu-id="6eba3-107">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="6eba3-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="6eba3-108">Regel CA2200 kennzeichnet Code, bei dem Ausnahmen erneut ausgelöst werden und die Ausnahmevariable in der `throw`-Anweisung angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6eba3-108">Rule CA2200 flags code where exceptions are rethrown and the exception variable is specified in the `throw` statement.</span></span> <span data-ttu-id="6eba3-109">Wenn eine Ausnahme ausgelöst wird, ist ein Teil der darin enthaltenen Informationen die Stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="6eba3-109">When an exception is thrown, part of the information it carries is the stack trace.</span></span> <span data-ttu-id="6eba3-110">Die Stapelüberwachung ist eine Liste der Hierarchie der Methodenaufrufe, die mit der Methode beginnt, die die Ausnahme auslöst, und mit der Methode endet, die die Ausnahme abfängt.</span><span class="sxs-lookup"><span data-stu-id="6eba3-110">The stack trace is a list of the method call hierarchy that starts with the method that throws the exception and ends with the method that catches the exception.</span></span> <span data-ttu-id="6eba3-111">Wenn eine Ausnahme durch Angabe der Ausnahme in der `throw`-Anweisung erneut ausgelöst wird, startet die Stapelüberwachung bei der aktuellen Methode neu. Die Liste der Methodenaufrufe zwischen der ursprünglichen Methode, die die Ausnahme ausgelöst hat, und der aktuellen Methode geht verloren.</span><span class="sxs-lookup"><span data-stu-id="6eba3-111">If an exception is rethrown by specifying the exception in the `throw` statement, the stack trace restarts at the current method and the list of method calls between the original method that threw the exception and the current method is lost.</span></span> <span data-ttu-id="6eba3-112">Um die ursprünglichen Stapelüberwachungsinformation mit der Ausnahme beizubehalten, verwenden Sie die `throw`-Anweisung ohne Angabe der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6eba3-112">To keep the original stack trace information with the exception, use the `throw` statement without specifying the exception.</span></span>

<span data-ttu-id="6eba3-113">Der folgende Codeausschnitt erzeugt für Regel CA2200 keine Warnung.</span><span class="sxs-lookup"><span data-stu-id="6eba3-113">The following code snippet does not produce a warning for rule CA2200.</span></span> <span data-ttu-id="6eba3-114">Die kommentierte Zeile *würde* jedoch einen Verstoß auslösen.</span><span class="sxs-lookup"><span data-stu-id="6eba3-114">The commented line *would* trigger a violation, however.</span></span>

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

#### <a name="version-introduced"></a><span data-ttu-id="6eba3-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6eba3-115">Version introduced</span></span>

<span data-ttu-id="6eba3-116">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="6eba3-116">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6eba3-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="6eba3-117">Recommended action</span></span>

- <span data-ttu-id="6eba3-118">Lösen Sie Ausnahmen erneut aus, ohne die Ausnahme explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6eba3-118">Rethrow exceptions without specifying the exception explicitly.</span></span> <span data-ttu-id="6eba3-119">Weitere Informationen finden Sie unter [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="6eba3-119">For more information, see [CA2200](/visualstudio/code-quality/ca2200).</span></span>

- <span data-ttu-id="6eba3-120">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6eba3-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="6eba3-121">Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="6eba3-121">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="6eba3-122">Category</span><span class="sxs-lookup"><span data-stu-id="6eba3-122">Category</span></span>

<span data-ttu-id="6eba3-123">Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="6eba3-123">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6eba3-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6eba3-124">Affected APIs</span></span>

<span data-ttu-id="6eba3-125">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="6eba3-125">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
