---
title: "Neues in C# – Leitfaden für C#"
description: Wie sich die C#-Programmiersprache weiterentwickelt
keywords: C#, neueste Funktionen, Neues, Roslyn
author: BillWagner
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0a328f62a02aea223340fcc00e839e841041a7d6
ms.contentlocale: de-de
ms.lasthandoff: 08/29/2017

---

# <a name="whats-new-in-c"></a><span data-ttu-id="39dae-104">Neues in C#</span><span class="sxs-lookup"><span data-stu-id="39dae-104">What's new in C#</span></span> #

<span data-ttu-id="39dae-105">Diese Seite enthält eine Roadmap zu den neuen Funktionen in jeder Hauptversion der C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="39dae-105">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="39dae-106">Die folgenden Links bieten ausführliche Informationen zu den wichtigsten Funktionen, die in jeder Version hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="39dae-106">The links below provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39dae-107">Für einige der Funktionen ist die C#-Sprache von Typen und Methoden in einer *Standardbibliothek* abhängig.</span><span class="sxs-lookup"><span data-stu-id="39dae-107">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="39dae-108">Ein Beispiel ist die Ausnahmeverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="39dae-108">One example is exception processing.</span></span> <span data-ttu-id="39dae-109">Alle `throw`-Anweisungen oder -Ausdrücke werden überprüft, um sicherzustellen, dass das ausgelöste Objekt von @System.Exception abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="39dae-109">Every `throw` statement or expression is checked to ensure the object being thrown is derived from @System.Exception.</span></span> <span data-ttu-id="39dae-110">Auf ähnliche Weise wird jedes `catch` überprüft, um sicherzustellen, dass der abgefangen Typ von @System.Exception abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="39dae-110">Similarly, every `catch` is checked to ensure that the type being caught is derived from @System.Exception.</span></span> <span data-ttu-id="39dae-111">Jede Version kann neue Anforderungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="39dae-111">Each version may add new requirements.</span></span> <span data-ttu-id="39dae-112">Um die neuesten Sprachfunktionen in älteren Umgebungen verwenden zu können, müssen Sie vielleicht bestimmte Bibliotheken installieren.</span><span class="sxs-lookup"><span data-stu-id="39dae-112">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="39dae-113">Diese sind auf der jeweiligen Seite für eine spezifische Version dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="39dae-113">These are documented in the page for each specific version.</span></span> <span data-ttu-id="39dae-114">Sie können mehr über die [Beziehungen zwischen Sprache und Bibliothek](relationships-between-language-and-library.md) erfahren, um Hintergrundinformationen zu dieser Abhängigkeit zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="39dae-114">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 

* <span data-ttu-id="39dae-115">[C# 7.1](csharp-7-1.md):</span><span class="sxs-lookup"><span data-stu-id="39dae-115">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="39dae-116">Auf dieser Seite werden die neuesten Funktionen der Programmiersprache C# vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="39dae-116">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="39dae-117">Dies deckt auch C# 7.1 ab, das aktuell in [Visual Studio 2017 Version 15.3](https://www.visualstudio.com/vs/whatsnew/) und im [.NET Core 2.0 SDK](../../core/whats-new/index.md) zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="39dae-117">This covers C# 7.1, currently available in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="39dae-118">[C# 7](csharp-7.md):</span><span class="sxs-lookup"><span data-stu-id="39dae-118">[C# 7](csharp-7.md):</span></span>
    - <span data-ttu-id="39dae-119">Auf dieser Seite werden die Funktionen vorgestellt, die in C# 7 hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="39dae-119">This page describes the features added in C# 7.</span></span> <span data-ttu-id="39dae-120">Diese wurden in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) und in [.NET Core 1.0](../../core/whats-new/index.md) und höher hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="39dae-120">Theses were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="39dae-121">[C# 6](csharp-6.md):</span><span class="sxs-lookup"><span data-stu-id="39dae-121">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="39dae-122">Auf dieser Seite werden die Funktionen vorgestellt, die in C# 6 eingefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="39dae-122">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="39dae-123">Diese Funktionen stehen für Windows-Entwickler in Visual Studio 2015 zur Verfügung; Entwickler, die C# unter macOS und Linux verwenden, können dazu .NET Core 1.0 nutzen.</span><span class="sxs-lookup"><span data-stu-id="39dae-123">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="39dae-124">[Plattformübergreifender Support](../../core/index.md):</span><span class="sxs-lookup"><span data-stu-id="39dae-124">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="39dae-125">C# kann aufgrund des .NET Core Supports auf mehreren Plattformen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="39dae-125">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="39dae-126">Wenn Sie C# unter macOS oder unter einer der vielen unterstützten Linux-Distributionen ausprobieren möchten, informieren Sie sich über .NET Core.</span><span class="sxs-lookup"><span data-stu-id="39dae-126">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="39dae-127">Frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="39dae-127">Previous Versions</span></span>
<span data-ttu-id="39dae-128">Im Folgenden sind die Hauptfunktionen aufgelistet, die mit vorherigen Versionen von C# und Visual Studio .NET eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="39dae-128">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="39dae-129">Visual Studio .NET 2013:</span><span class="sxs-lookup"><span data-stu-id="39dae-129">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="39dae-130">Diese Version von Visual Studio enthielt Fehlerkorrekturen, Leistungsoptimierungen und eine Technologievorschau von .NET Compiler Platform („Roslyn“), die zum <!--Link to ../roslyn/index.md-->.NET Compiler Platform SDK wurde.</span><span class="sxs-lookup"><span data-stu-id="39dae-130">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="39dae-131">C# 5, Visual Studio .NET 2012:</span><span class="sxs-lookup"><span data-stu-id="39dae-131">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="39dae-132">`Async` / `await` und [Aufruferinformationsattribute](../programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="39dae-132">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="39dae-133">C# 4, Visual Studio .NET 2010:</span><span class="sxs-lookup"><span data-stu-id="39dae-133">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="39dae-134">`Dynamic`, [benannte Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optionale Parameter, generische [Ko-/Kontravarianz](../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="39dae-134">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="39dae-135">C# 3, Visual Studio .NET 2008:</span><span class="sxs-lookup"><span data-stu-id="39dae-135">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="39dae-136">Objekt- und Auflistungsinitialisierer, Lambdaausdrücke, Erweiterungsmethoden, anonyme Typen, automatische Eigenschaften, lokaler `var`-Typrückschluss und [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="39dae-136">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="39dae-137">C# 2, Visual Studio .NET 2005:</span><span class="sxs-lookup"><span data-stu-id="39dae-137">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="39dae-138">Anonyme Methoden, generische Typen, auf NULL festlegbare Typen, Iteratoren/Yield, `static`-Klassen und Ko-/Kontravarianz für Delegaten.</span><span class="sxs-lookup"><span data-stu-id="39dae-138">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="39dae-139">C# 1.1, Visual Studio .NET 2003:</span><span class="sxs-lookup"><span data-stu-id="39dae-139">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="39dae-140">`#line`-Pragma und XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="39dae-140">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="39dae-141">C# 1, Visual Studio .NET 2002:</span><span class="sxs-lookup"><span data-stu-id="39dae-141">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="39dae-142">Die erste Version von [C#](../csharp.md).</span><span class="sxs-lookup"><span data-stu-id="39dae-142">The first release of [C#](../csharp.md).</span></span>   

