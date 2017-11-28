---
title: Expression Trees
description: "Weitere Informationen zu Ausdrucksbaumstrukturen in .NET Core und wie sie verwendet werden, um Code als Strukturen darzustellen, die Sie überprüfen, ändern und ausführen können."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: aceb4719-0d5a-4b19-b01f-b51063bcc54f
ms.openlocfilehash: 3935906d9fca81a094999eefdd49ae4ed56990bf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="expression-trees"></a><span data-ttu-id="539a2-104">Expression Trees</span><span class="sxs-lookup"><span data-stu-id="539a2-104">Expression Trees</span></span>

<span data-ttu-id="539a2-105">Wenn Sie LINQ verwendet haben, verfügen Sie über Erfahrung mit einer umfangreichen Bibliothek, in der die `Func`-Typen Teil des API-Satzes sind.</span><span class="sxs-lookup"><span data-stu-id="539a2-105">If you have used LINQ, you have experience with a rich library where the `Func` types are part of the API set.</span></span> <span data-ttu-id="539a2-106">(Wenn Sie nicht mit LINQ vertraut sind, möchten Sie möglicherweise vorher [das LINQ-Tutorial](linq/index.md) und das Tutorial zu [lambda expressions (Lambdaausdrücke)](lambda-expressions.md) lesen.) *Ausdrucksbaumstrukturen* bieten eine umfangreichere Interaktion mit den Argumenten, die Funktionen sind.</span><span class="sxs-lookup"><span data-stu-id="539a2-106">(If you are not familiar with LINQ, you probably want to read [the LINQ tutorial](linq/index.md) and the tutorial on [lambda expressions](lambda-expressions.md) before this one.) *Expression Trees* provide richer interaction with the arguments that are functions.</span></span>

<span data-ttu-id="539a2-107">Sie schreiben die Argumente der Funktion in der Regel mithilfe von Lambdaausdrücken, wenn Sie LINQ-Abfragen erstellen.</span><span class="sxs-lookup"><span data-stu-id="539a2-107">You write function arguments, typically using Lambda Expressions, when you create LINQ queries.</span></span> <span data-ttu-id="539a2-108">In einer normalen LINQ-Abfrage werden die Funktionsargumente in einen Delegaten transformiert, den der Compiler erstellt.</span><span class="sxs-lookup"><span data-stu-id="539a2-108">In a typical LINQ query, those function arguments are transformed into a delegate the compiler creates.</span></span> 

<span data-ttu-id="539a2-109">Wenn Sie eine umfangreichere Interaktion haben möchten, müssen Sie *Ausdrucksbaumstrukturen* verwenden.</span><span class="sxs-lookup"><span data-stu-id="539a2-109">When you want to have a richer interaction, you need to use *Expression Trees*.</span></span>
<span data-ttu-id="539a2-110">Ausdrucksbaumstrukturen stellen Code wie eine Struktur dar, die Sie untersuchen, ändern oder ausführen können.</span><span class="sxs-lookup"><span data-stu-id="539a2-110">Expression Trees represent code as a structure that you can examine, modify, or execute.</span></span> <span data-ttu-id="539a2-111">Diese Tools bieten Ihnen die Möglichkeit, Code während der Laufzeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="539a2-111">These tools give you the power to manipulate code during run time.</span></span> <span data-ttu-id="539a2-112">Sie können Code schreiben, der ausgeführte Algorithmen untersucht oder neue Funktionen einfügt.</span><span class="sxs-lookup"><span data-stu-id="539a2-112">You can write code that examines running algorithms, or injects new capabilities.</span></span> <span data-ttu-id="539a2-113">In erweiterten Szenarios können Sie ausgeführte Algorithmen ändern und sogar C#-Ausdrücke für die Ausführung in einer anderen Umgebung in eine andere Form übersetzen.</span><span class="sxs-lookup"><span data-stu-id="539a2-113">In more advanced scenarios, you can modify running algorithms, and even translate C# expressions into another form for execution in another environment.</span></span>

<span data-ttu-id="539a2-114">Sie haben wahrscheinlich bereits Code geschrieben, der Ausdrucksbaumstrukturen verwendet.</span><span class="sxs-lookup"><span data-stu-id="539a2-114">You've likely already written code that uses Expression Trees.</span></span> <span data-ttu-id="539a2-115">LINQ-APIs von Entity Framework akzeptieren Ausdrucksbaumstrukturen als Argumente für das LINQ-Abfrageausdrucksmuster.</span><span class="sxs-lookup"><span data-stu-id="539a2-115">Entity Framework's LINQ APIs accept Expression Trees as the arguments for the LINQ Query Expression Pattern.</span></span>
<span data-ttu-id="539a2-116">So kann [Entity Framework](http://docs.efproject.net/en/latest/) die Abfrage übersetzen, die Sie in C# in SQL geschrieben haben, die im Datenbankmodul ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="539a2-116">That enables [Entity Framework](http://docs.efproject.net/en/latest/) to translate the query you wrote in C# into SQL that executes in the database engine.</span></span> <span data-ttu-id="539a2-117">Ein weiteres Beispiel ist [Moq](https://github.com/Moq/moq), was ein beliebtes Mockingframework für .NET ist.</span><span class="sxs-lookup"><span data-stu-id="539a2-117">Another example is [Moq](https://github.com/Moq/moq), which is a popular mocking framework for .NET.</span></span>

<span data-ttu-id="539a2-118">In den verbleibenden Abschnitten dieses Tutorials wird untersucht, was Ausdrucksbaumstrukturen sind, es werden die Framework-Klassen untersucht, die Ausdrucksbaumstrukturen unterstützen, und es wird gezeigt, wie Sie mit Ausdrucksbaumstrukturen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="539a2-118">The remaining sections of this tutorial will explore what Expression Trees are, examine the framework classes that support expression trees, and show you how to work with expression trees.</span></span> <span data-ttu-id="539a2-119">Sie erfahren, wie Sie Ausdrucksbaumstrukturen lesen und diese erstellen, wie Sie geänderte Ausdrucksbaumstrukturen erstellen und wie Sie Code von dargestellten Ausdrucksbaumstrukturen ausführen.</span><span class="sxs-lookup"><span data-stu-id="539a2-119">You'll learn how to read expression trees, how to create expression trees, how to create modified expression trees, and how to execute the code represented by expression trees.</span></span> <span data-ttu-id="539a2-120">Nach dem Lesen können Sie mit diesen Strukturen umfangreiche adaptive Algorithmen erstellen.</span><span class="sxs-lookup"><span data-stu-id="539a2-120">After reading, you will be ready to use these structures to create rich adaptive algorithms.</span></span>

1. [<span data-ttu-id="539a2-121">Ausdrucksbaumstrukturen mit Erläuterung</span><span class="sxs-lookup"><span data-stu-id="539a2-121">Expression Trees Explained</span></span>](expression-trees-explained.md)

    <span data-ttu-id="539a2-122">Verstehen der Struktur und der Konzepte hinter *Ausdrucksbaumstrukturen*.</span><span class="sxs-lookup"><span data-stu-id="539a2-122">Understand the structure and concepts behind *Expression Trees*.</span></span>
    
2. [<span data-ttu-id="539a2-123">Framework-Typen, die Ausdrucksbaumstrukturen unterstützen</span><span class="sxs-lookup"><span data-stu-id="539a2-123">Framework Types Supporting Expression Trees</span></span>](expression-classes.md)
    
    <span data-ttu-id="539a2-124">Erfahren Sie mehr über die Strukturen und Klassen, die Ausdrucksbaumstrukturen definieren und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="539a2-124">Learn about the structures and classes that define and manipulate expression trees.</span></span>
    
3. [<span data-ttu-id="539a2-125">Ausführen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="539a2-125">Executing Expressions</span></span>](expression-trees-execution.md)

    <span data-ttu-id="539a2-126">Erfahren Sie, wie Sie eine Ausdrucksbaumstruktur, die als Lambdaausdruck dargestellt wird, in einen Delegaten konvertieren, und wie Sie den resultierenden Delegaten ausführen.</span><span class="sxs-lookup"><span data-stu-id="539a2-126">Learn how to convert an expression tree represented as a Lambda Expression into a delegate and execute the resulting delegate.</span></span>

4. [<span data-ttu-id="539a2-127">Interpretieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="539a2-127">Interpreting Expressions</span></span>](expression-trees-interpreting.md)

    <span data-ttu-id="539a2-128">Erfahren Sie, wie Sie *Ausdrucksbaumstrukturen* durchlaufen und untersuchen, um zu verstehen, welchen Code die Ausdrucksbaumstruktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="539a2-128">Learn how to traverse and examine *expression trees* to understand what code the expression tree represents.</span></span>

5. [<span data-ttu-id="539a2-129">Erstellen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="539a2-129">Building Expressions</span></span>](expression-trees-building.md)

    <span data-ttu-id="539a2-130">Erfahren Sie, wie Sie die Knoten für eine Ausdrucksbaumstruktur erstellen, und wie Sie Ausdrucksbaumstrukturen erstellen.</span><span class="sxs-lookup"><span data-stu-id="539a2-130">Learn how to construct the nodes for an expression tree and build expression trees.</span></span>

6. [<span data-ttu-id="539a2-131">Übersetzen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="539a2-131">Translating Expressions</span></span>](expression-trees-translating.md)

    <span data-ttu-id="539a2-132">Erfahren Sie, wie Sie eine geänderte Kopie einer Ausdrucksbaumstruktur erstellen oder wie Sie eine Ausdrucksbaumstruktur in ein anderes Format übersetzen.</span><span class="sxs-lookup"><span data-stu-id="539a2-132">Learn how to build a modified copy of an expression tree, or translate an expression tree into a different format.</span></span>

7. [<span data-ttu-id="539a2-133">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="539a2-133">Summing up</span></span>](expression-trees-summary.md)

    <span data-ttu-id="539a2-134">Überprüfen Sie die Informationen zu Ausdrucksbaumstrukturen.</span><span class="sxs-lookup"><span data-stu-id="539a2-134">Review the information on expression trees.</span></span>
    
