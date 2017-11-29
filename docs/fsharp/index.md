---
title: "Leitfaden für F#"
description: "Erfahren Sie, bis der F#-Programmiersprache, eine Open-Source-Sprache für .NET, die erstklassige Unterstützung für die funktionale Programmierung bereitstellt."
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 4ddd77cef6cf70a63f1af81359d82eda27a01593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="f-guide"></a><span data-ttu-id="c47ee-104">Leitfaden für F#</span><span class="sxs-lookup"><span data-stu-id="c47ee-104">F# Guide</span></span>

<span data-ttu-id="c47ee-105">F# ist eine plattformübergreifende, Oopen-Source-Programmiersprache für .NET und bietet erstklassige Unterstützung für funktionale Programmierung, zusammen mit Unterstützung für objektorientierte und imperative Programmierung.</span><span class="sxs-lookup"><span data-stu-id="c47ee-105">F# is a cross-platform, open source programming language for .NET which provides first-class support for functional programming, along with support of object-oriented and imperative programming.</span></span>  <span data-ttu-id="c47ee-106">Der Visual F#-Compiler und die dazugehörigen Tools sind die Implementierung und das Tool von Microsoft für die Programmiersprache F#, was F# zu einem hochwertigen Member von .NET macht.</span><span class="sxs-lookup"><span data-stu-id="c47ee-106">The Visual F# compiler and tooling are Microsoft's implementation and tooling for the F# programming language, making F# a first-class member of .NET.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="c47ee-107">Wenn Sie in F#-vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="c47ee-107">If You're New to F#</span></span> #

<span data-ttu-id="c47ee-108">Wenn Sie in F#-vertraut sind, beginnen Sie mit der [Tour von f#](tour.md) abzurufenden einen Überblick über die Sprache.</span><span class="sxs-lookup"><span data-stu-id="c47ee-108">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language.</span></span>

<span data-ttu-id="c47ee-109">Es wird empfohlen, dass Sie durchlaufen die [Funktionen als erstrangige Werte](introduction-to-functional-programming/functions-as-first-class-values.md) <!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> funktionale Programmierung Konzepte erfahren Sie, die für das Arbeiten mit f# unverzichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="c47ee-109">It's also recommended that you go through the [Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> to learn Functional Programming concepts which are essential to working with F#.</span></span>

<span data-ttu-id="c47ee-110">In den [Tutorials](tutorials/getting-started/index.md) erhalten Sie auch ausführliche Anleitungen für unterschiedliche Fähigkeitslevel und Funktionen der Sprache.</span><span class="sxs-lookup"><span data-stu-id="c47ee-110">The [Tutorials](tutorials/getting-started/index.md) also have step-by-step guides for various skill levels and features of the language.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="c47ee-111">Wenn Sie bereits Erfahrung mit [F#]</span><span class="sxs-lookup"><span data-stu-id="c47ee-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="c47ee-112">Wenn Sie mit F# vertraut sind, finden Sie viel Interessantes in der [Sprachreferenz](language-reference/index.md), worin jeder Aspekt der Sprache gründlich dokumentiert ist und durch viele Codebeispiele wird.</span><span class="sxs-lookup"><span data-stu-id="c47ee-112">If you know your way around F#, you'll find a lot of use in the [Language Reference](language-reference/index.md), which documents each aspect of the language thoroughly, supplemented by numerous code samples.</span></span>  <span data-ttu-id="c47ee-113">Die [Referenz zur F#-Kernbibliothek](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) wird ebenso sehr interessant für Sie sein.</span><span class="sxs-lookup"><span data-stu-id="c47ee-113">You'll also find a lot of use in the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference).</span></span>  <span data-ttu-id="c47ee-114">Der F#-Referenz zur Kernbibliothek werden schließlich von MSDN und in diese aktuelle Docs verschoben.</span><span class="sxs-lookup"><span data-stu-id="c47ee-114">The F# Core Library Reference will eventually move away from MSDN and into these current docs.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="c47ee-115">Die F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="c47ee-115">The F# Software Foundation</span></span>

<span data-ttu-id="c47ee-116">Obwohl Microsoft der Hauptentwickler der Programmiersprache F# und Visual F#-Tools ist, wird F# auch durch eine unabhängige Stiftung unterstützt, nämlich von der F# Software Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="c47ee-116">Although Microsoft is the primary developer of the F# language and Visual F# Tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="c47ee-117">Das Ziel der F# Software Foundation ist, die Programmiersprache F# zu fördern, zu schützen und weiterzuentwickeln sowie das Wachstum einer vielfältigen und internationalen Community von F#-Programmierern zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c47ee-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="c47ee-118">Um mehr zu erfahren und mitzumachen, gehen Sie unter [fsharp.org](http://fsharp.org).</span><span class="sxs-lookup"><span data-stu-id="c47ee-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="c47ee-119">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="c47ee-119">Documentation</span></span>

* [<span data-ttu-id="c47ee-120">Tutorials</span><span class="sxs-lookup"><span data-stu-id="c47ee-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="c47ee-121">[Funktionen als erstrangige Werte](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="c47ee-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="c47ee-122">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c47ee-122">Language Reference</span></span>](language-reference/index.md)
* [<span data-ttu-id="c47ee-123">Referenz zur F#-Kernbibliothek</span><span class="sxs-lookup"><span data-stu-id="c47ee-123">F# Core Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)

## <a name="online-reading-resources"></a><span data-ttu-id="c47ee-124">Onlineressourcen zum Lesen</span><span class="sxs-lookup"><span data-stu-id="c47ee-124">Online Reading Resources</span></span>

* [<span data-ttu-id="c47ee-125">F# for Fun and Profit Gitbook (F# für Fun und Profit – Gitbook)</span><span class="sxs-lookup"><span data-stu-id="c47ee-125">F# for Fun and Profit Gitbook</span></span>](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 
* [<span data-ttu-id="c47ee-126">F# Programming Wikibook (F#-Programmierung – Wikibook)</span><span class="sxs-lookup"><span data-stu-id="c47ee-126">F# Programming Wikibook</span></span>](https://en.wikibooks.org/wiki/F_Sharp_Programming)

## <a name="video-learning-resources"></a><span data-ttu-id="c47ee-127">Videolernressourcen</span><span class="sxs-lookup"><span data-stu-id="c47ee-127">Video Learning Resources</span></span>

* [<span data-ttu-id="c47ee-128">Introduction to Programming with F# series on YouTube (Einführung in die Programmierung mit der F#-Reihe auf YouTube)</span><span class="sxs-lookup"><span data-stu-id="c47ee-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="c47ee-129">Introduction to F# series on FSharpTV (Einführung in die F#-Reihe auf FSharpTV)</span><span class="sxs-lookup"><span data-stu-id="c47ee-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="c47ee-130">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c47ee-130">Further Resources</span></span>

* [<span data-ttu-id="c47ee-131">F#-Lernressourcen auf fsharp.org</span><span class="sxs-lookup"><span data-stu-id="c47ee-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="c47ee-132">Website für F#-Ausschnitte</span><span class="sxs-lookup"><span data-stu-id="c47ee-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="c47ee-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="c47ee-133">F# Software Foundation</span></span>](http://fsharp.org)
