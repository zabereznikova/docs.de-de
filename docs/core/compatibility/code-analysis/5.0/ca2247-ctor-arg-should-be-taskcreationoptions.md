---
title: 'Breaking Change: CA2247: Das Argument für den Konstruktor „TaskCompletionSource“ muss ein TaskCreationOptions-Wert sein'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA2247“ ausgelöst wird.
ms.date: 09/03/2020
ms.openlocfilehash: 323fd5a05da4dfeb68ef75d88d5d293ba01c8ade
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759473"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="0a487-103">Warnung CA2247: Das Argument für den Konstruktor „TaskCompletionSource“ muss ein TaskCreationOptions-Wert sein</span><span class="sxs-lookup"><span data-stu-id="0a487-103">Warning CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="0a487-104">Die .NET-Codeanalyseregel [CA2247](/visualstudio/code-quality/ca2247) wird ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0a487-104">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="0a487-105">Sie erzeugt eine Buildwarnung für Aufrufe des Konstruktors <xref:System.Threading.Tasks.TaskCompletionSource%601>, die ein Argument des Typs <xref:System.Threading.Tasks.TaskContinuationOptions> übergeben.</span><span class="sxs-lookup"><span data-stu-id="0a487-105">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

## <a name="change-description"></a><span data-ttu-id="0a487-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0a487-106">Change description</span></span>

<span data-ttu-id="0a487-107">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="0a487-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="0a487-108">Mehrere dieser Regeln, einschließlich [CA2247](/visualstudio/code-quality/ca2247), werden standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0a487-108">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="0a487-109">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="0a487-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="0a487-110">Die Regel CA2247 findet Aufrufe des Konstruktors <xref:System.Threading.Tasks.TaskCompletionSource%601>, die ein Argument des Typs <xref:System.Threading.Tasks.TaskContinuationOptions> übergeben.</span><span class="sxs-lookup"><span data-stu-id="0a487-110">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="0a487-111">Der Typ <xref:System.Threading.Tasks.TaskCompletionSource%601> verfügt über einen Konstruktor, der einen <xref:System.Threading.Tasks.TaskCreationOptions>-Wert annimmt, und einen weiteren Konstruktor, der eine <xref:System.Object>-Klasse akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="0a487-111">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="0a487-112">Wenn Sie versehentlich einen <xref:System.Threading.Tasks.TaskContinuationOptions>-Wert anstelle eines <xref:System.Threading.Tasks.TaskCreationOptions>-Werts übergeben, wird der Konstruktor mit dem <xref:System.Object>-Parameter zur Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0a487-112">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="0a487-113">Ihr Code wird kompiliert und ausgeführt, später jedoch nicht das beabsichtigte Verhalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0a487-113">Your code will compile and run but won't have the intended behavior.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0a487-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="0a487-114">Version introduced</span></span>

<span data-ttu-id="0a487-115">5.0</span><span class="sxs-lookup"><span data-stu-id="0a487-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0a487-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="0a487-116">Recommended action</span></span>

- <span data-ttu-id="0a487-117">Ersetzen Sie das Argument <xref:System.Threading.Tasks.TaskContinuationOptions> durch den entsprechenden <xref:System.Threading.Tasks.TaskCreationOptions>-Wert.</span><span class="sxs-lookup"><span data-stu-id="0a487-117">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="0a487-118">Unterdrücken Sie diese Warnung nicht, da sie fast immer auf einen Fehler in Ihrem Code hinweist.</span><span class="sxs-lookup"><span data-stu-id="0a487-118">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="0a487-119">Weitere Informationen finden Sie unter [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="0a487-119">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="0a487-120">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0a487-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="0a487-121">Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="0a487-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0a487-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0a487-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
