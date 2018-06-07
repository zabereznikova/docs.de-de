---
title: Leitfaden für F#
description: Dieses Handbuch enthält einen Überblick über die verschiedenen Lernmaterialien für F#, funktionalen Programmiersprachen, die auf .NET ausgeführt wird.
author: jackfoxy
ms.date: 03/19/2018
ms.openlocfilehash: cb829e904c006467e1470752b4fe8757ca694b05
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
ms.locfileid: "34312000"
---
# <a name="f-guide"></a><span data-ttu-id="5c8f3-103">Leitfaden für F#</span><span class="sxs-lookup"><span data-stu-id="5c8f3-103">F# Guide</span></span>

<span data-ttu-id="5c8f3-104">F# ist eine funktionale Programmiersprache, die auf .NET ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-104">F# is a functional programming language that runs on .NET.</span></span> <span data-ttu-id="5c8f3-105">Dank vollständiger Unterstützung von Objekten können Sie für pragmatische Lösungen zu jedem Problem die funktionale und die objektorientierte Programmierung miteinander kombinieren.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-105">It also has full support for objects, letting you blend functional and object programming for pragmatic solutions to any problem.</span></span>

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="5c8f3-106">Im Fokus von F# steht die Steigerung der Produktivität.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-106">F# is about productivity at its heart.</span></span> <span data-ttu-id="5c8f3-107">F# bietet eine umfassende Toolunterstützung mit zahlreichen modernen Features.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-107">The tooling support for F# is ubiquitous and full of advanced features.</span></span>

## <a name="learning-f"></a><span data-ttu-id="5c8f3-108">Learning [F#]</span><span class="sxs-lookup"><span data-stu-id="5c8f3-108">Learning F#</span></span> #

<span data-ttu-id="5c8f3-109">Die [Tour durch F#](tour.md) bietet einen Überblick über die wichtigsten Sprachfeatures und viele Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-109">[Tour of F#](tour.md) gives an overview of major language features with lots of code samples.</span></span> <span data-ttu-id="5c8f3-110">Sie wird für den Einstieg in F# empfohlen, um sich mit der Funktionsweise der Sprache vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-110">This is recommended if you are new to F# and want to get a feel for how the language works.</span></span>

<span data-ttu-id="5c8f3-111">Lesen Sie [Erste Schritte mit F# in Visual Studio](get-started/get-started-visual-studio.md), wenn Sie für Windows entwickeln und die vollständige Visual Studio-IDE (Integraded Development Environment) nutzen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-111">[Get started with F# in Visual Studio](get-started/get-started-visual-studio.md) if you're on Windows and want the full Visual Studio IDE (Integraded Development Environment) experience.</span></span>

<span data-ttu-id="5c8f3-112">Lesen Sie [Erste Schritte mit F# in Visual Studio für Mac](get-started/get-started-with-visual-studio-for-mac.md), wenn Sie MacOS nutzen und eine Visual Studio-IDE verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-112">[Get started with F# in Visual Studio for Mac](get-started/get-started-with-visual-studio-for-mac.md) if you're on macOS and want to use a Visual Studio IDE.</span></span>

<span data-ttu-id="5c8f3-113">Lesen Sie [Erste Schritte mit F# in Visual Studio Code](get-started/get-started-vscode.md), wenn Sie eine schlanke, plattformübergreifende und leistungsstarke IDE nutzen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-113">[Get Started with F# in Visual Studio Code](get-started/get-started-vscode.md) if you want a lightweight, cross-platform, and feature-packed IDE experience.</span></span>

<span data-ttu-id="5c8f3-114">[Erste Schritte mit F# mit der .NET Core-CL](get-started/get-started-command-line.md), wenn Sie die Befehlszeilentools verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-114">[Get started with F# with the .NET Core CLI](get-started/get-started-command-line.md) if you want to use command-line tools.</span></span>

<span data-ttu-id="5c8f3-115">[Erste Schritte mit F#- und Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) für die mobile-Programmierung mit F#.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-115">[Get started with F# and Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) for mobile programming with F#.</span></span>

<span data-ttu-id="5c8f3-116">[F# for Azure Notebooks](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb) (in englischer Sprache) ist ein Tutorial zum Erlernen von F# in einem kostenlosen gehosteten Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-116">[F# for Azure Notebooks](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb) is a tutorial for learning F# in a free, hosted Jupyter Notebook.</span></span>

## <a name="references"></a><span data-ttu-id="5c8f3-117">Verweise</span><span class="sxs-lookup"><span data-stu-id="5c8f3-117">References</span></span>

<span data-ttu-id="5c8f3-118">Die [F#-Sprachreferenz](language-reference/index.md) ist die offizielle, umfassende Referenz zu allen F#-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-118">[F# Language Reference](language-reference/index.md) is the official, comprehensive reference for all F# language features.</span></span> <span data-ttu-id="5c8f3-119">Jeder Artikel erklärt die Syntax und zeigt Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-119">Each article explains the syntax and shows code samples.</span></span> <span data-ttu-id="5c8f3-120">Nutzen Sie die Filterleiste im Inhaltsverzeichnis, um nach bestimmten Artikeln zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-120">You can use the filter bar in the table of contents to find specific articles.</span></span>

<span data-ttu-id="5c8f3-121">Die [Referenz zur F#-Kernbibliothek](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) (in englischer Sprache) ist die API-Referenz für die F#-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-121">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is the API reference for the F# Core Library.</span></span>


## <a name="additional-guides"></a><span data-ttu-id="5c8f3-122">Zusätzliche Anleitungen</span><span class="sxs-lookup"><span data-stu-id="5c8f3-122">Additional guides</span></span>

<span data-ttu-id="5c8f3-123">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) (in englischer Sprache) ist ein umfassendes und sehr detailliertes Buch zum Erlernen von F#.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-123">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) is a comprehensive and very detailed book on learning F#.</span></span> <span data-ttu-id="5c8f3-124">Inhalt und Autor werden von der F#-Community hoch geschätzt.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-124">Its contents and author are beloved by the F# community.</span></span> <span data-ttu-id="5c8f3-125">Die Zielgruppe sind in erster Linie Entwickler aus dem Bereich der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-125">The target audience is primarily developers with an object oriented programming background.</span></span>

<span data-ttu-id="5c8f3-126">Das [Wikibook zur F#-Programmierung](https://en.wikibooks.org/wiki/F_Sharp_Programming) (in englischer Sprache) ist ein Wikibook zum Erlernen von F#</span><span class="sxs-lookup"><span data-stu-id="5c8f3-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) is a wikibook about learning F#.</span></span> <span data-ttu-id="5c8f3-127">und ebenfalls ein Produkt der F#-Community.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-127">It is also a product of the F# community.</span></span> <span data-ttu-id="5c8f3-128">Zielgruppe sind Neueinsteiger in F#, die bereits über ein wenig Erfahrung mit der objektorientierten Programmierung verfügen.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-128">The target audience is people who are new to F#, with a little bit of object oriented programming background.</span></span>

## <a name="learn-f-through-videos"></a><span data-ttu-id="5c8f3-129">F#-Lernvideos</span><span class="sxs-lookup"><span data-stu-id="5c8f3-129">Learn F# through videos</span></span>

<span data-ttu-id="5c8f3-130">Das [Tutorial zu F# auf YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) (in englischer Sprache) ist eine hervorragende Einführung in F#. Anhand von Visual Studio und zahlreichen guten Beispielen erhalten Sie hier innerhalb von 1,5 Stunden einen Einblick in F#.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-130">[F# tutorial on YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) is a great introduction to F# using Visual Studio, showing lots of great examples over the course of 1.5 hours.</span></span> <span data-ttu-id="5c8f3-131">Die Zielgruppe sind Visual Studio-Entwickler, die neu in F# einsteigen.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-131">The target audience is Visual Studio developers who are new to F#.</span></span>

<span data-ttu-id="5c8f3-132">[Einführung in die Programmierung mit F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) (in englischer Sprache) ist eine hervorragende Videoreihe, in der Visual Studio Code als Haupt-Editor verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-132">[Introduction to Programming with F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) is a great video series that uses Visual Studio Code as the main editor.</span></span> <span data-ttu-id="5c8f3-133">Die Videoreihe startet von Grund auf und endet mit der Erstellung eines textbasierten RPG-Videospiels.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-133">The video series starts from nothing and ends with building a text-based RPG video game.</span></span> <span data-ttu-id="5c8f3-134">Die Zielgruppe sind Entwickler, die Visual Studio Code (oder eine einfache IDE) nutzen möchten und neu in F# einsteigen.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-134">The target audience is developers who prefer Visual Studio Code (or a lightweight IDE) and are new to F#.</span></span>

<span data-ttu-id="5c8f3-135">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) (in englischer Sprache) ist ein Videkours, der die neueren Funktionen von F# in Visual Studio 2017 zeigt.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-135">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) is a video course that shows some of the newer features for F# in Visual Studio 2017.</span></span> <span data-ttu-id="5c8f3-136">Die Zielgruppe sind Visual Studio-Entwickler, die neu in F# einsteigen.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-136">The target audience is Visual Studio developers who are new to F#.</span></span>

## <a name="other-useful-resources"></a><span data-ttu-id="5c8f3-137">Andere nützliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5c8f3-137">Other useful resources</span></span>

<span data-ttu-id="5c8f3-138">Auf der [Website mit F#-Codeausschnitten](http://www.fssnip.net) (in englischer Sprache) werden vielfältige Codeausschnitte zu allen Aspekten von F# bereitgestellt. Interessant sowohl für F#-Einsteiger als auch für Fortgeschrittene.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-138">The [F# Snippets Website](http://www.fssnip.net) contains a massive set of code snippets showing how to do just about anything in F#, ranging from absolute beginner to highly advanced snippets.</span></span>

<span data-ttu-id="5c8f3-139">Die [F# Software Foundation Slack](http://fsharp.org/guides/slack/) (in englischer Sprache) ist für Einsteiger und Experten gleichermaßen hervorragend geeignet. Sie ist sehr aktiv und bietet die Möglichkeit zum Chat mit einigen der weltweit besten F#-Programmierer.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-139">The [F# Software Foundation Slack](http://fsharp.org/guides/slack/) is a great place for beginners and experts alike, is highly active, and has some of world's best F# programmers available for a chat.</span></span> <span data-ttu-id="5c8f3-140">Teilnahme dringend empfohlen!</span><span class="sxs-lookup"><span data-stu-id="5c8f3-140">We highly recommend joining.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="5c8f3-141">Die F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="5c8f3-141">The F# Software Foundation</span></span>

<span data-ttu-id="5c8f3-142">Wenngleich die Programmiersprache F# und alle zugehörigen Tools in Visual Studio primär durch Microsoft entwickelt werden, wird F# durch die F# Software Foundation (FSSF) auch von unabhängiger Seite gestützt.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-142">Although Microsoft is the primary developer of the F# language and its tools in Visual Studio, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="5c8f3-143">Das Ziel der F# Software Foundation ist, die Programmiersprache F# zu fördern, zu schützen und weiterzuentwickeln sowie das Wachstum einer vielfältigen und internationalen Community von F#-Programmierern zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5c8f3-143">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="5c8f3-144">Um mehr zu erfahren und mitzumachen, besuchen Sie [fsharp.org](http://fsharp.org). Mitmachen ist kostenlos, und das Netzwerk der F#-Entwickler der Foundation ist etwas, das Sie garantiert nicht verpassen möchten!</span><span class="sxs-lookup"><span data-stu-id="5c8f3-144">To learn more and get involved, check out [fsharp.org](http://fsharp.org). It's free to join, and the network of F# developers in the foundation is something you don't want to miss out on!</span></span>
