---
title: Delegaten (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1d3dc2252b086f9df9e64a059a53ec8792e11b45
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="8b253-102">Delegaten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8b253-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="8b253-103">Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) ist ein Typ, der Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="8b253-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="8b253-104">Wenn Sie einen Delegaten instanziieren, können Sie jeder Methode seine Instanz mit einer kompatiblen Signatur und dem Rückgabetyp zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8b253-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="8b253-105">Sie können die Methode über die Delegatinstanz aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8b253-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="8b253-106">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="8b253-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="8b253-107">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8b253-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="8b253-108">Wenn Sie eine benutzerdefinierte Methode erstellen, kann eine Klasse wie das Windows-Steuerelement diese Methode aufrufen, sobald ein bestimmtes Ereignis eintritt.</span><span class="sxs-lookup"><span data-stu-id="8b253-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="8b253-109">Das folgende Beispiel veranschaulicht die Deklaration eines Delegaten:</span><span class="sxs-lookup"><span data-stu-id="8b253-109">The following example shows a delegate declaration:</span></span>  
  
 <span data-ttu-id="8b253-110">[!code-cs[CsProgGuideDelegates 20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8b253-110">[!code-cs[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]</span></span>  
  
 <span data-ttu-id="8b253-111">Jede Methode einer beliebigen verfügbaren Klasse oder Struktur, die mit dem Delegattyp übereinstimmt, kann dem Delegaten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8b253-111">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="8b253-112">Bei der Methode kann es sich um eine statische Methode oder um eine Instanzenmethode handeln.</span><span class="sxs-lookup"><span data-stu-id="8b253-112">The method can be either static or an instance method.</span></span> <span data-ttu-id="8b253-113">Dies ermöglicht das programmgesteuerte Ändern von Methodenaufrufen sowie die Integration von neuem Code in bereits vorhandene Klassen.</span><span class="sxs-lookup"><span data-stu-id="8b253-113">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b253-114">In Verbindung mit dem Überladen von Methoden schließt die Signatur einer Methode den Rückgabewert nicht ein.</span><span class="sxs-lookup"><span data-stu-id="8b253-114">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="8b253-115">Bei Delegaten ist der Rückgabewert jedoch in die Signatur eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8b253-115">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="8b253-116">Mit anderen Worten muss eine Methode denselben Rückgabetyp haben wie der Delegat.</span><span class="sxs-lookup"><span data-stu-id="8b253-116">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="8b253-117">Diese Fähigkeit, als Parameter auf eine Methode zu verweisen, macht Delegaten ideal für das Definieren von Rückrufmethoden.</span><span class="sxs-lookup"><span data-stu-id="8b253-117">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="8b253-118">Beispielsweise kann ein Verweis auf eine Methode, die zwei Objekte vergleicht, als Argument an einen Sortieralgorithmus übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8b253-118">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="8b253-119">Da sich der Vergleichscode in einer separaten Prozedur befindet, kann der Sortieralgorithmus allgemeiner geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8b253-119">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="8b253-120">Übersicht über Delegaten</span><span class="sxs-lookup"><span data-stu-id="8b253-120">Delegates Overview</span></span>  
 <span data-ttu-id="8b253-121">Delegaten verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8b253-121">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="8b253-122">Delegaten ähneln C++-Funktionszeigern, sind aber typsicher.</span><span class="sxs-lookup"><span data-stu-id="8b253-122">Delegates are like C++ function pointers but are type safe.</span></span>  
  
-   <span data-ttu-id="8b253-123">Delegaten ermöglichen es, Methoden als Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="8b253-123">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="8b253-124">Delegaten können zum Definieren von Rückrufmethoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b253-124">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="8b253-125">Delegaten können miteinander verkettet werden. So können beispielsweise mehrere Methoden für ein einziges Ereignis aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8b253-125">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="8b253-126">Methoden müssen nicht exakt mit dem Typ des Delegaten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8b253-126">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="8b253-127">Weitere Informationen finden Sie unter [Verwenden von Varianz in Delegaten](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="8b253-127">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="8b253-128">In C#, Version 2.0, wurde das Konzept der [anonymen Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) eingeführt, durch die anstelle einer separat definierten Methode Codeblöcke als Parameter übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="8b253-128">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="8b253-129">In C# 3.0 wurden Lambdaausdrücke als eine präzisere Methode zum Schreiben von Inlinecodeblöcken eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8b253-129">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="8b253-130">Sowohl anonyme Methoden als auch Lambda-Ausdrücke werden (in bestimmten Kontexten) in Delegattypen kompiliert.</span><span class="sxs-lookup"><span data-stu-id="8b253-130">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="8b253-131">Zusammen werden diese Funktionen jetzt als anonyme Funktionen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8b253-131">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="8b253-132">Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="8b253-132">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b253-133">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8b253-133">In This Section</span></span>  
  
-   [<span data-ttu-id="8b253-134">Verwenden von Delegaten</span><span class="sxs-lookup"><span data-stu-id="8b253-134">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="8b253-135">Verwenden von Delegaten anstelle Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8b253-135">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](http://msdn.microsoft.com/en-us/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [<span data-ttu-id="8b253-136">Delegate mit benannten im Vergleich zu anonymen Methoden</span><span class="sxs-lookup"><span data-stu-id="8b253-136">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="8b253-137">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="8b253-137">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="8b253-138">Verwenden von Varianz bei Delegaten</span><span class="sxs-lookup"><span data-stu-id="8b253-138">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="8b253-139">How to: Combine Delegates (Multicast Delegates) (Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten))</span><span class="sxs-lookup"><span data-stu-id="8b253-139">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="8b253-140">Gewusst wie: Deklarieren, Instanziieren und Verwenden von Delegaten</span><span class="sxs-lookup"><span data-stu-id="8b253-140">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="8b253-141">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="8b253-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="8b253-142">Enthaltene Buchkapitel</span><span class="sxs-lookup"><span data-stu-id="8b253-142">Featured Book Chapters</span></span>  
 <span data-ttu-id="8b253-143">[Delegaten, Ereignisse und Lambda-Ausdrücke](http://go.microsoft.com/fwlink/?LinkId=195395) im [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="8b253-143">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="8b253-144">[Delegaten und Ereignisse](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="8b253-144">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b253-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b253-145">See Also</span></span>  
 <span data-ttu-id="8b253-146"><xref:System.Delegate></span><span class="sxs-lookup"><span data-stu-id="8b253-146"><xref:System.Delegate></span></span>   
 <span data-ttu-id="8b253-147">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8b253-147">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8b253-148">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8b253-148">Events</span></span>](../../../csharp/programming-guide/events/index.md)

