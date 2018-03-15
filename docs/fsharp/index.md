---
title: "Leitfaden für F#"
description: "Dieses Handbuch enthält einen Überblick über die verschiedenen Lernmaterialien für f#, funktionalen Programmiersprachen, die auf .NET ausgeführt wird."
author: jackfoxy
ms.author: phcart
ms.date: 02/28/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: b7cf3feb5699f85bf09a47f008fdaf70ac7c8d77
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="f-guide"></a><span data-ttu-id="3a249-103">Leitfaden für F#</span><span class="sxs-lookup"><span data-stu-id="3a249-103">F# Guide</span></span>

<span data-ttu-id="3a249-104">F# ist eine funktionale Programmiersprache, die auf .NET ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3a249-104">F# is a functional programming language that runs on .NET.</span></span> <span data-ttu-id="3a249-105">Zudem ist eine vollständige Unterstützung für Objekte, können Sie mit Blend funktionale und Objekt-Programmierung pragmatisches Lösungen für Probleme.</span><span class="sxs-lookup"><span data-stu-id="3a249-105">It also has full support for objects, letting you blend functional and object programming for pragmatic solutions to any problem.</span></span>

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    args                     // Use F# pipe operators to send the args into some functions.
    |> Array.map getGreeting // Turn each name into a friendly greeting.
    |> Array.iter printfn    // Print them!

    0
```

<span data-ttu-id="3a249-106">F# ist zur Steigerung der Produktivität im Wesentlichen.</span><span class="sxs-lookup"><span data-stu-id="3a249-106">F# is about productivity at its heart.</span></span> <span data-ttu-id="3a249-107">Die toolunterstützung für f# ist weit verbreitete und vollständige erweiterte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="3a249-107">The tooling support for F# is ubiquitous and full of advanced features.</span></span>

## <a name="learning-f"></a><span data-ttu-id="3a249-108">Learning F#</span><span class="sxs-lookup"><span data-stu-id="3a249-108">Learning F#</span></span> #

<span data-ttu-id="3a249-109">[Tour durch f#](tour.md) vermittelt einen Überblick über die wichtigsten Sprachfunktionen mit vielen Codebeispielen.</span><span class="sxs-lookup"><span data-stu-id="3a249-109">[Tour of F#](tour.md) gives an overview of major language features with lots of code samples.</span></span> <span data-ttu-id="3a249-110">Dies wird empfohlen, wenn Sie mit dem f# vertraut sind und ein Verhalten für die Funktionsweise der Sprache abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a249-110">This is recommended if you are new to F# and want to get a feel for how the language works.</span></span>

<span data-ttu-id="3a249-111">[Erste Schritte mit f# in Visual Studio](get-started/get-started-visual-studio.md) Wenn Sie auf Windows und die vollständige Visual Studio-IDE (Integraded Development Environment)-Erfahrung werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a249-111">[Get started with F# in Visual Studio](get-started/get-started-visual-studio.md) if you're on Windows and want the full Visual Studio IDE (Integraded Development Environment) experience.</span></span>

<span data-ttu-id="3a249-112">[Erste Schritte mit f# in Visual Studio für Mac](get-started/get-started-with-visual-studio-for-mac.md) Wenn Sie MacOS und eine Visual Studio-IDE verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a249-112">[Get started with F# in Visual Studio for Mac](get-started/get-started-with-visual-studio-for-mac.md) if you're on macOS and want to use a Visual Studio IDE.</span></span>

<span data-ttu-id="3a249-113">[Erste Schritte mit f# in Visual Studio Code](get-started/get-started-vscode.md) Wenn Sie eine einfache, plattformübergreifende und Feature-packed IDE auftreten.</span><span class="sxs-lookup"><span data-stu-id="3a249-113">[Get Started with F# in Visual Studio Code](get-started/get-started-vscode.md) if you want a lightweight, cross-platform, and feature-packed IDE experience.</span></span>

<span data-ttu-id="3a249-114">[Erste Schritte mit f# mit der .NET Core-CLI](get-started/get-started-command-line.md) , wenn Sie die Befehlszeilentools verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3a249-114">[Get started with F# with the .NET Core CLI](get-started/get-started-command-line.md) if you want to use command-line tools.</span></span>

## <a name="references"></a><span data-ttu-id="3a249-115">Verweise</span><span class="sxs-lookup"><span data-stu-id="3a249-115">References</span></span>

<span data-ttu-id="3a249-116">[F#-Sprachreferenz](language-reference/index.md) ist die offizielle, eine umfassende Referenz für alle F#-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="3a249-116">[F# Language Reference](language-reference/index.md) is the official, comprehensive reference for all F# language features.</span></span> <span data-ttu-id="3a249-117">Jeder Artikel erklärt die Syntax und zeigt Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="3a249-117">Each article explains the syntax and shows code samples.</span></span> <span data-ttu-id="3a249-118">Die Filterleiste können im Inhaltsverzeichnis Sie um bestimmte Artikeln zu suchen.</span><span class="sxs-lookup"><span data-stu-id="3a249-118">You can use the filter bar in the table of contents to find specific articles.</span></span>

<span data-ttu-id="3a249-119">[Referenz zur F#-Kernbibliothek](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) ist die API-Referenz für die f#-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="3a249-119">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is the API reference for the F# Core Library.</span></span>

## <a name="additional-guides"></a><span data-ttu-id="3a249-120">Zusätzliche Anleitungen</span><span class="sxs-lookup"><span data-stu-id="3a249-120">Additional guides</span></span>

<span data-ttu-id="3a249-121">[F# für lustige und Gewinn](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) ist eine umfassende und detaillierte Book auf learning f#.</span><span class="sxs-lookup"><span data-stu-id="3a249-121">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) is a comprehensive and very detailed book on learning F#.</span></span> <span data-ttu-id="3a249-122">Inhalt und der Autor sind von f#-Community geliebten.</span><span class="sxs-lookup"><span data-stu-id="3a249-122">Its contents and author are beloved by the F# community.</span></span> <span data-ttu-id="3a249-123">Die Zielgruppe wird in erster Linie Entwicklern eine objektorientierte Programmierung im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="3a249-123">The target audience is primarily developers with an object oriented programming background.</span></span>

<span data-ttu-id="3a249-124">[F#-Programmierung Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) ist eine Wikibook zu Lernressourcen f#.</span><span class="sxs-lookup"><span data-stu-id="3a249-124">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) is a wikibook about learning F#.</span></span> <span data-ttu-id="3a249-125">Es ist auch ein Produkt mit der f#-Community.</span><span class="sxs-lookup"><span data-stu-id="3a249-125">It is also a product of the F# community.</span></span> <span data-ttu-id="3a249-126">Die Zielgruppe wird Personen, die f# mit ein wenig objektorientierte Programmierung im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="3a249-126">The target audience is people who are new to F#, with a little bit of object oriented programming background.</span></span>

## <a name="learn-f-through-videos"></a><span data-ttu-id="3a249-127">Lernen F#-videos</span><span class="sxs-lookup"><span data-stu-id="3a249-127">Learn F# through videos</span></span>

<span data-ttu-id="3a249-128">[F#-Lernprogramm auf YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) ist eine gute Einführung in f# mithilfe von Visual Studio, viele gute Beispiele dafür im Verlauf von 1,5 Stunden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a249-128">[F# tutorial on YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) is a great introduction to F# using Visual Studio, showing lots of great examples over the course of 1.5 hours.</span></span> <span data-ttu-id="3a249-129">Die Zielgruppe ist Visual Studio-Entwickler, die für f# neu sind.</span><span class="sxs-lookup"><span data-stu-id="3a249-129">The target audience is Visual Studio developers who are new to F#.</span></span>

<span data-ttu-id="3a249-130">[Einführung in die Programmierung mit F#-](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) ist eine hervorragende Videoreihe, die Visual Studio-Code als der Haupt-Editor verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a249-130">[Introduction to Programming with F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) is a great video series that uses Visual Studio Code as the main editor.</span></span> <span data-ttu-id="3a249-131">Die Videoreihe aus einem unbenannten beginnt und endet mit einer textbasierten RPG-Video-Spiel erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a249-131">The video series starts from nothing and ends with building a text-based RPG video game.</span></span> <span data-ttu-id="3a249-132">Die Zielgruppe ist Entwickler, die dann Visual Studio Code (oder eine einfache IDE) und sind für f# neu.</span><span class="sxs-lookup"><span data-stu-id="3a249-132">The target audience is developers who prefer Visual Studio Code (or a lightweight IDE) and are new to F#.</span></span>

<span data-ttu-id="3a249-133">[Neues in Visual Studio 2017 für f# für Entwickler](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) ist ein video Kurs, die einige der neueren Funktionen für f# in Visual Studio 2017 anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3a249-133">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) is a video course that shows some of the newer features for F# in Visual Studio 2017.</span></span> <span data-ttu-id="3a249-134">Die Zielgruppe ist Visual Studio-Entwickler, die für f# neu sind.</span><span class="sxs-lookup"><span data-stu-id="3a249-134">The target audience is Visual Studio developers who are new to F#.</span></span>

## <a name="other-useful-resources"></a><span data-ttu-id="3a249-135">Andere nützliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="3a249-135">Other useful resources</span></span>

<span data-ttu-id="3a249-136">Die [f# Ausschnitte Website](http://www.fssnip.net) enthält eine umfassende Reihe von Codeausschnitte, so ziemlich alles in f# von Neueinsteiger bis hin zu fortschrittlichen Ausschnitte Vorgang zeigt.</span><span class="sxs-lookup"><span data-stu-id="3a249-136">The [F# Snippets Website](http://www.fssnip.net) contains a massive set of code snippets showing how to do just about anything in F#, ranging from absolute beginner to highly advanced snippets.</span></span>

<span data-ttu-id="3a249-137">Die [f# Software Foundation Slack](http://fsharp.org/guides/slack/) eignet sich hervorragend für Anfänger und Experten gleichermaßen, sehr aktiv ist und über einige der weltweit besten F#-Programmierer chatten.</span><span class="sxs-lookup"><span data-stu-id="3a249-137">The [F# Software Foundation Slack](http://fsharp.org/guides/slack/) is a great place for beginners and experts alike, is highly active, and has some of world's best F# programmers available for a chat.</span></span> <span data-ttu-id="3a249-138">Es wird dringend empfohlen, verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="3a249-138">We highly recommend joining.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="3a249-139">Die F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="3a249-139">The F# Software Foundation</span></span>

<span data-ttu-id="3a249-140">Obwohl Microsoft den primären Entwickler der Programmiersprache f# und die zugehörigen Tools in Visual Studio ist, wird f# auch von einer unabhängigen Foundation, die F#-Software Foundation (FSSF) gesichert.</span><span class="sxs-lookup"><span data-stu-id="3a249-140">Although Microsoft is the primary developer of the F# language and its tools in Visual Studio, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="3a249-141">Das Ziel der F# Software Foundation ist, die Programmiersprache F# zu fördern, zu schützen und weiterzuentwickeln sowie das Wachstum einer vielfältigen und internationalen Community von F#-Programmierern zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3a249-141">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="3a249-142">Um mehr zu erfahren und mitzumachen, gehen Sie unter [fsharp.org](http://fsharp.org). Es ist kostenlos zu verknüpfen, und das Netzwerk des F#-Entwickler in die Grundlage etwas, das Sie nicht verpassen möchten!</span><span class="sxs-lookup"><span data-stu-id="3a249-142">To learn more and get involved, check out [fsharp.org](http://fsharp.org). It's free to join, and the network of F# developers in the foundation is something you don't want to miss out on!</span></span>