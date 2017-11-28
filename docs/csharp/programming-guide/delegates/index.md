---
title: Delegaten (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a6649537238af38e073eeb8747487822d058b7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="9e112-102">Delegaten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9e112-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="9e112-103">Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) ist ein Typ, der Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="9e112-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="9e112-104">Wenn Sie einen Delegaten instanziieren, können Sie jeder Methode seine Instanz mit einer kompatiblen Signatur und dem Rückgabetyp zuordnen.</span><span class="sxs-lookup"><span data-stu-id="9e112-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="9e112-105">Sie können die Methode über die Delegatinstanz aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9e112-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="9e112-106">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="9e112-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="9e112-107">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e112-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="9e112-108">Wenn Sie eine benutzerdefinierte Methode erstellen, kann eine Klasse wie das Windows-Steuerelement diese Methode aufrufen, sobald ein bestimmtes Ereignis eintritt.</span><span class="sxs-lookup"><span data-stu-id="9e112-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="9e112-109">Das folgende Beispiel veranschaulicht die Deklaration eines Delegaten:</span><span class="sxs-lookup"><span data-stu-id="9e112-109">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="9e112-110">Jede Methode einer beliebigen verfügbaren Klasse oder Struktur, die mit dem Delegattyp übereinstimmt, kann dem Delegaten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9e112-110">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="9e112-111">Bei der Methode kann es sich um eine statische Methode oder um eine Instanzenmethode handeln.</span><span class="sxs-lookup"><span data-stu-id="9e112-111">The method can be either static or an instance method.</span></span> <span data-ttu-id="9e112-112">Dies ermöglicht das programmgesteuerte Ändern von Methodenaufrufen sowie die Integration von neuem Code in bereits vorhandene Klassen.</span><span class="sxs-lookup"><span data-stu-id="9e112-112">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e112-113">In Verbindung mit dem Überladen von Methoden schließt die Signatur einer Methode den Rückgabewert nicht ein.</span><span class="sxs-lookup"><span data-stu-id="9e112-113">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="9e112-114">Bei Delegaten ist der Rückgabewert jedoch in die Signatur eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9e112-114">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="9e112-115">Mit anderen Worten muss eine Methode denselben Rückgabetyp haben wie der Delegat.</span><span class="sxs-lookup"><span data-stu-id="9e112-115">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="9e112-116">Diese Fähigkeit, als Parameter auf eine Methode zu verweisen, macht Delegaten ideal für das Definieren von Rückrufmethoden.</span><span class="sxs-lookup"><span data-stu-id="9e112-116">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="9e112-117">Beispielsweise kann ein Verweis auf eine Methode, die zwei Objekte vergleicht, als Argument an einen Sortieralgorithmus übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9e112-117">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="9e112-118">Da sich der Vergleichscode in einer separaten Prozedur befindet, kann der Sortieralgorithmus allgemeiner geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9e112-118">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="9e112-119">Übersicht über Delegaten</span><span class="sxs-lookup"><span data-stu-id="9e112-119">Delegates Overview</span></span>  
 <span data-ttu-id="9e112-120">Delegaten verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9e112-120">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="9e112-121">Delegaten ähneln C++-Funktionszeigern, sind aber typsicher.</span><span class="sxs-lookup"><span data-stu-id="9e112-121">Delegates are like C++ function pointers but are type safe.</span></span>  
  
-   <span data-ttu-id="9e112-122">Delegaten ermöglichen es, Methoden als Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="9e112-122">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="9e112-123">Delegaten können zum Definieren von Rückrufmethoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e112-123">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="9e112-124">Delegaten können miteinander verkettet werden. So können beispielsweise mehrere Methoden für ein einziges Ereignis aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e112-124">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="9e112-125">Methoden müssen nicht exakt mit dem Typ des Delegaten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9e112-125">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="9e112-126">Weitere Informationen finden Sie unter [Verwenden von Varianz in Delegaten](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="9e112-126">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="9e112-127">In C#, Version 2.0, wurde das Konzept der [anonymen Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) eingeführt, durch die anstelle einer separat definierten Methode Codeblöcke als Parameter übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="9e112-127">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="9e112-128">In C# 3.0 wurden Lambdaausdrücke als eine präzisere Methode zum Schreiben von Inlinecodeblöcken eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9e112-128">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="9e112-129">Sowohl anonyme Methoden als auch Lambda-Ausdrücke werden (in bestimmten Kontexten) in Delegattypen kompiliert.</span><span class="sxs-lookup"><span data-stu-id="9e112-129">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="9e112-130">Zusammen werden diese Funktionen jetzt als anonyme Funktionen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9e112-130">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="9e112-131">Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="9e112-131">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e112-132">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9e112-132">In This Section</span></span>  
  
-   [<span data-ttu-id="9e112-133">Verwenden von Delegaten</span><span class="sxs-lookup"><span data-stu-id="9e112-133">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="9e112-134">Verwenden von Delegaten anstelle Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9e112-134">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](http://msdn.microsoft.com/en-us/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [<span data-ttu-id="9e112-135">Delegate mit benannten im Vergleich zu anonymen Methoden</span><span class="sxs-lookup"><span data-stu-id="9e112-135">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="9e112-136">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="9e112-136">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="9e112-137">Verwenden von Varianz bei Delegaten</span><span class="sxs-lookup"><span data-stu-id="9e112-137">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="9e112-138">How to: Combine Delegates (Multicast Delegates) (Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten))</span><span class="sxs-lookup"><span data-stu-id="9e112-138">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="9e112-139">Gewusst wie: Deklarieren, Instanziieren und Verwenden von Delegaten</span><span class="sxs-lookup"><span data-stu-id="9e112-139">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9e112-140">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9e112-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="9e112-141">Enthaltene Buchkapitel</span><span class="sxs-lookup"><span data-stu-id="9e112-141">Featured Book Chapters</span></span>  
 <span data-ttu-id="9e112-142">[Delegaten, Ereignisse und Lambda-Ausdrücke](http://go.microsoft.com/fwlink/?LinkId=195395) im [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="9e112-142">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="9e112-143">[Delegaten und Ereignisse](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="9e112-143">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e112-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e112-144">See Also</span></span>  
 <xref:System.Delegate>  
 [<span data-ttu-id="9e112-145">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9e112-145">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9e112-146">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9e112-146">Events</span></span>](../../../csharp/programming-guide/events/index.md)
