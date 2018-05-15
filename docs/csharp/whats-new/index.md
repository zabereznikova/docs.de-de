---
title: Neues in C# – Leitfaden für C#
description: Wie sich die C#-Programmiersprache weiterentwickelt
ms.date: 11/13/2017
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 3fc42809943b10d09d59780576dd9768d9e16ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c"></a><span data-ttu-id="cc8fa-103">Neues in C#</span><span class="sxs-lookup"><span data-stu-id="cc8fa-103">What's new in C#</span></span> #

<span data-ttu-id="cc8fa-104">Diese Seite enthält eine Roadmap zu den neuen Funktionen in jeder Hauptversion der C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-104">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="cc8fa-105">Die folgenden Links bieten ausführliche Informationen zu den wichtigsten Funktionen, die in jedem Release hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-105">The following links provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc8fa-106">Für einige der Funktionen ist die C#-Sprache von Typen und Methoden in einer *Standardbibliothek* abhängig.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-106">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="cc8fa-107">Ein Beispiel ist die Ausnahmeverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-107">One example is exception processing.</span></span> <span data-ttu-id="cc8fa-108">Alle `throw`-Anweisungen oder -Ausdrücke werden überprüft, um sicherzustellen, dass das ausgelöste Objekt von <xref:System.Exception> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-108">Every `throw` statement or expression is checked to ensure the object being thrown is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="cc8fa-109">Auf ähnliche Weise wird jedes `catch` überprüft, um sicherzustellen, dass der abgefangen Typ von <xref:System.Exception> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-109">Similarly, every `catch` is checked to ensure that the type being caught is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="cc8fa-110">Jede Version kann neue Anforderungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-110">Each version may add new requirements.</span></span> <span data-ttu-id="cc8fa-111">Um die neuesten Sprachfunktionen in älteren Umgebungen verwenden zu können, müssen Sie vielleicht bestimmte Bibliotheken installieren.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-111">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="cc8fa-112">Diese Abhängigkeiten werden auf der jeweiligen Seite für eine spezifische Version dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-112">These dependencies are documented in the page for each specific version.</span></span> <span data-ttu-id="cc8fa-113">Sie können mehr über die [Beziehungen zwischen Sprache und Bibliothek](relationships-between-language-and-library.md) erfahren, um Hintergrundinformationen zu dieser Abhängigkeit zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-113">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 


* <span data-ttu-id="cc8fa-114">[C# 7.2](csharp-7-2.md):</span><span class="sxs-lookup"><span data-stu-id="cc8fa-114">[C# 7.2](csharp-7-2.md):</span></span>
    - <span data-ttu-id="cc8fa-115">Auf dieser Seite werden die neuesten Funktionen der Programmiersprache C# vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-115">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="cc8fa-116">C# 7.2 steht aktuell in [Visual Studio 2017 Version 15.5](https://www.visualstudio.com/vs/whatsnew/) und im [.NET Core 2.0 SDK](../../core/whats-new/index.md) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-116">C# 7.2 is currently available in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="cc8fa-117">[C# 7.1](csharp-7-1.md):</span><span class="sxs-lookup"><span data-stu-id="cc8fa-117">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="cc8fa-118">Auf dieser Seite werden die Features vorgestellt, die in C# 7.1 hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-118">This page describes the features in C# 7.1.</span></span> <span data-ttu-id="cc8fa-119">Diese Features wurden in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/) und im [.NET Core 2.0 SDK](../../core/whats-new/index.md) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-119">These features were added in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="cc8fa-120">[C# 7.0](csharp-7.md):</span><span class="sxs-lookup"><span data-stu-id="cc8fa-120">[C# 7.0](csharp-7.md):</span></span>
    - <span data-ttu-id="cc8fa-121">Auf dieser Seite werden die Features vorgestellt, die in C# 7.0 hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-121">This page describes the features added in C# 7.0.</span></span> <span data-ttu-id="cc8fa-122">Diese Features wurden in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) und in [.NET Core 1.0](../../core/whats-new/index.md) und höher hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-122">These features were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="cc8fa-123">[C# 6](csharp-6.md):</span><span class="sxs-lookup"><span data-stu-id="cc8fa-123">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="cc8fa-124">Auf dieser Seite werden die Funktionen vorgestellt, die in C# 6 eingefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-124">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="cc8fa-125">Diese Funktionen stehen für Windows-Entwickler in Visual Studio 2015 zur Verfügung; Entwickler, die C# unter macOS und Linux verwenden, können dazu .NET Core 1.0 nutzen.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-125">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="cc8fa-126">[Plattformübergreifender Support](../../core/index.md):</span><span class="sxs-lookup"><span data-stu-id="cc8fa-126">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="cc8fa-127">C# kann aufgrund des .NET Core Supports auf mehreren Plattformen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-127">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="cc8fa-128">Wenn Sie C# unter macOS oder unter einer der vielen unterstützten Linux-Distributionen ausprobieren möchten, informieren Sie sich über .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-128">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="cc8fa-129">Frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="cc8fa-129">Previous Versions</span></span>
<span data-ttu-id="cc8fa-130">Im Folgenden sind die Hauptfunktionen aufgelistet, die mit vorherigen Versionen von C# und Visual Studio .NET eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-130">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="cc8fa-131">Visual Studio .NET 2013:</span><span class="sxs-lookup"><span data-stu-id="cc8fa-131">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="cc8fa-132">Diese Version von Visual Studio enthielt Fehlerkorrekturen, Leistungsoptimierungen und eine Technologievorschau von .NET Compiler Platform („Roslyn“), die zum <!--Link to ../roslyn/index.md-->.NET Compiler Platform SDK wurde.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-132">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="cc8fa-133">C# 5, Visual Studio .NET 2012:</span><span class="sxs-lookup"><span data-stu-id="cc8fa-133">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="cc8fa-134">`Async` / `await` und [Aufruferinformationsattribute](../programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="cc8fa-134">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="cc8fa-135">C# 4, Visual Studio .NET 2010:</span><span class="sxs-lookup"><span data-stu-id="cc8fa-135">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="cc8fa-136">`Dynamic`, [benannte Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optionale Parameter, generische [Ko-/Kontravarianz](../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="cc8fa-136">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="cc8fa-137">C# 3, Visual Studio .NET 2008:</span><span class="sxs-lookup"><span data-stu-id="cc8fa-137">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="cc8fa-138">Objekt- und Auflistungsinitialisierer, Lambdaausdrücke, Erweiterungsmethoden, anonyme Typen, automatische Eigenschaften, lokaler `var`-Typrückschluss und [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="cc8fa-138">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="cc8fa-139">C# 2, Visual Studio .NET 2005:</span><span class="sxs-lookup"><span data-stu-id="cc8fa-139">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="cc8fa-140">Anonyme Methoden, generische Typen, auf NULL festlegbare Typen, Iteratoren/Yield, `static`-Klassen und Ko-/Kontravarianz für Delegaten.</span><span class="sxs-lookup"><span data-stu-id="cc8fa-140">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="cc8fa-141">C# 1.1, Visual Studio .NET 2003:</span><span class="sxs-lookup"><span data-stu-id="cc8fa-141">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="cc8fa-142">`#line`-Pragma und XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="cc8fa-142">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="cc8fa-143">C# 1, Visual Studio .NET 2002:</span><span class="sxs-lookup"><span data-stu-id="cc8fa-143">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="cc8fa-144">Die erste Version von [C#](../csharp.md).</span><span class="sxs-lookup"><span data-stu-id="cc8fa-144">The first release of [C#](../csharp.md).</span></span>   
