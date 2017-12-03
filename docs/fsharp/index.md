---
title: "Leitfaden für F#"
description: "Informationen Sie zu f#, funktionalen Programmiersprachen, die auf .NET ausgeführt wird."
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 12/01/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 45f5d2ca794ccea7a35cf6c0bf9d58a3e6500453
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="f-guide"></a><span data-ttu-id="15724-104">Leitfaden für F#</span><span class="sxs-lookup"><span data-stu-id="15724-104">F# Guide</span></span>

<span data-ttu-id="15724-105">F# ist eine funktionale Programmiersprache, die auf .NET ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15724-105">F# is a functional programming language which runs on .NET.</span></span>  <span data-ttu-id="15724-106">Zusätzlich zu den unterstützenden Konstrukte der funktionalen Programmierung hat es auch Programmierfunktionen Objekt.</span><span class="sxs-lookup"><span data-stu-id="15724-106">In addition to supporting functional programming constructs, it also has object programming capabilities.</span></span>  <span data-ttu-id="15724-107">Dieser hybridanwendung der funktionalen Programmierung mit objektorientierte Funktionen stellt f# eine pragmatische Sprache für das Ausführen einer Aufgabe an.</span><span class="sxs-lookup"><span data-stu-id="15724-107">This hybrid of functional programming with object-oriented capabilities makes F# a pragmatic language for accomplishing any task.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="15724-108">Wenn Sie in F#-vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="15724-108">If You're New to F#</span></span> #

<span data-ttu-id="15724-109">In F#-Einsteiger, beginnen Sie mit der [Tour von F#-](tour.md) um einen Überblick über die Sprache und einige seiner Programmierkonzepte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="15724-109">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language and some of its programming concepts.</span></span>  <span data-ttu-id="15724-110">Wenn Sie Visual Studio verwenden, die Vorlage Tutorial-Projekt mit den gleichen Inhalt enthält.</span><span class="sxs-lookup"><span data-stu-id="15724-110">If you're using Visual Studio, the Tutorial project template contains the same content.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="15724-111">Wenn Sie bereits Erfahrung mit [F#]</span><span class="sxs-lookup"><span data-stu-id="15724-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="15724-112">Wenn Sie zurechtfinden F# wissen- oder Weitere Informationen zu einem bestimmten Sprachkonstrukt erfahren möchten, finden Sie unter der [Sprachreferenz](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="15724-112">If you know your way around F#, or want to learn more about a specific language construct, see the [Language Reference](language-reference/index.md).</span></span>  <span data-ttu-id="15724-113">Es handelt sich um eine gründliche Handbuch alle F#-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="15724-113">It's a thorough guide of all F# language capabilities.</span></span>

<span data-ttu-id="15724-114">Darüber hinaus die [Referenz zur F#-Kernbibliothek](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) ist eine hervorragende Ressource zum Kennenlernen von FSharp.Core verwenden und die ist Bestandteil der F#-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="15724-114">Additionally, the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is a great resource for learning about FSharp.Core, the core library which is a part of F#.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="15724-115">Die F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="15724-115">The F# Software Foundation</span></span>

<span data-ttu-id="15724-116">Zwar Microsoft primären Entwickler von der Programmiersprache f# und die Tools, ist f# auch von einer unabhängigen Foundation, die F#-Software Foundation (FSSF) gesichert.</span><span class="sxs-lookup"><span data-stu-id="15724-116">Although Microsoft is the primary developer of the F# language and its tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="15724-117">Das Ziel der F# Software Foundation ist, die Programmiersprache F# zu fördern, zu schützen und weiterzuentwickeln sowie das Wachstum einer vielfältigen und internationalen Community von F#-Programmierern zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="15724-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="15724-118">Um mehr zu erfahren und mitzumachen, gehen Sie unter [fsharp.org](http://fsharp.org).</span><span class="sxs-lookup"><span data-stu-id="15724-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="15724-119">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="15724-119">Documentation</span></span>

* [<span data-ttu-id="15724-120">Tutorials</span><span class="sxs-lookup"><span data-stu-id="15724-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="15724-121">[Funktionen als erstrangige Werte](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="15724-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="15724-122">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="15724-122">Language Reference</span></span>](language-reference/index.md)
* [<span data-ttu-id="15724-123">Referenz zur F#-Kernbibliothek</span><span class="sxs-lookup"><span data-stu-id="15724-123">F# Core Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)

## <a name="online-reading-resources"></a><span data-ttu-id="15724-124">Onlineressourcen zum Lesen</span><span class="sxs-lookup"><span data-stu-id="15724-124">Online Reading Resources</span></span>

* [<span data-ttu-id="15724-125">F# for Fun and Profit Gitbook (F# für Fun und Profit – Gitbook)</span><span class="sxs-lookup"><span data-stu-id="15724-125">F# for Fun and Profit Gitbook</span></span>](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 
* [<span data-ttu-id="15724-126">F# Programming Wikibook (F#-Programmierung – Wikibook)</span><span class="sxs-lookup"><span data-stu-id="15724-126">F# Programming Wikibook</span></span>](https://en.wikibooks.org/wiki/F_Sharp_Programming)

## <a name="video-learning-resources"></a><span data-ttu-id="15724-127">Videolernressourcen</span><span class="sxs-lookup"><span data-stu-id="15724-127">Video Learning Resources</span></span>

* [<span data-ttu-id="15724-128">Introduction to Programming with F# series on YouTube (Einführung in die Programmierung mit der F#-Reihe auf YouTube)</span><span class="sxs-lookup"><span data-stu-id="15724-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="15724-129">Introduction to F# series on FSharpTV (Einführung in die F#-Reihe auf FSharpTV)</span><span class="sxs-lookup"><span data-stu-id="15724-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="15724-130">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="15724-130">Further Resources</span></span>

* [<span data-ttu-id="15724-131">F#-Lernressourcen auf fsharp.org</span><span class="sxs-lookup"><span data-stu-id="15724-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="15724-132">Website für F#-Ausschnitte</span><span class="sxs-lookup"><span data-stu-id="15724-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="15724-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="15724-133">F# Software Foundation</span></span>](http://fsharp.org)