---
title: Anonyme Methoden (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 96e78257c5aab84562cd8cdb336bb5a91ba59534
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="anonymous-methods-c-programming-guide"></a><span data-ttu-id="4b0c8-102">Anonyme Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4b0c8-102">Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="4b0c8-103">In Versionen von C# vor 2.0 bestand die einzige Möglichkeit zum Deklarieren eines [Delegaten](../../../csharp/language-reference/keywords/delegate.md) in der Verwendung von [benannten Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4b0c8-103">In versions of C# before 2.0, the only way to declare a [delegate](../../../csharp/language-reference/keywords/delegate.md) was to use [named methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span></span> <span data-ttu-id="4b0c8-104">Mit C# 2.0 wurden anonyme Methoden eingeführt, und in C# 3.0 und höher lösen Lambdaausdrücke anonyme Methoden als bevorzugten Weg zum Schreiben von Inlinecode ab.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-104">C# 2.0 introduced anonymous methods and in C# 3.0 and later, lambda expressions supersede anonymous methods as the preferred way to write inline code.</span></span> <span data-ttu-id="4b0c8-105">Die Informationen zu anonymen Methoden in diesem Thema gelten jedoch auch für Lambdaausdrücke.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-105">However, the information about anonymous methods in this topic also applies to lambda expressions.</span></span> <span data-ttu-id="4b0c8-106">In einem Fall bietet eine anonyme Methode eine Funktion, über die Lambdaausdrücke nicht verfügen.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-106">There is one case in which an anonymous method provides functionality not found in lambda expressions.</span></span> <span data-ttu-id="4b0c8-107">Anonyme Methoden ermöglichen das Auslassen der Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-107">Anonymous methods enable you to omit the parameter list.</span></span> <span data-ttu-id="4b0c8-108">Das bedeutet, dass eine anonyme Methode in Delegaten mit verschiedenen Signaturen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-108">This means that an anonymous method can be converted to delegates with a variety of signatures.</span></span> <span data-ttu-id="4b0c8-109">Dies ist bei Lambdaausdrücken nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-109">This is not possible with lambda expressions.</span></span> <span data-ttu-id="4b0c8-110">Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4b0c8-110">For more information specifically about lambda expressions, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="4b0c8-111">Das Erstellen anonymer Methoden ist im Grunde genommen ein Weg, um einen Codeblock als Delegatparameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-111">Creating anonymous methods is essentially a way to pass a code block as a delegate parameter.</span></span> <span data-ttu-id="4b0c8-112">Hier sind zwei Beispiele:</span><span class="sxs-lookup"><span data-stu-id="4b0c8-112">Here are two examples:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 <span data-ttu-id="4b0c8-113">Mit anonymen Methoden verringern Sie den Mehraufwand an Codierung beim Instanziieren von Delegaten, da Sie keine separate Methode erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-113">By using anonymous methods, you reduce the coding overhead in instantiating delegates because you do not have to create a separate method.</span></span>  
  
 <span data-ttu-id="4b0c8-114">So kann es nützlich sein, einen Codeblock anstatt eines Delegaten anzugeben, wenn das Erstellen einer Methode mit unnötigem Aufwand verbunden scheint.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-114">For example, specifying a code block instead of a delegate can be useful in a situation when having to create a method might seem an unnecessary overhead.</span></span> <span data-ttu-id="4b0c8-115">Ein gutes Beispiel ist das Starten eines neuen Threads.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-115">A good example would be when you start a new thread.</span></span> <span data-ttu-id="4b0c8-116">Diese Klasse erstellt einen Thread und enthält zudem den Code, den der Thread ausführt, ohne dass eine zusätzliche Methode für den Delegaten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-116">This class creates a thread and also contains the code that the thread executes without creating an additional method for the delegate.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="4b0c8-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b0c8-117">Remarks</span></span>  
 <span data-ttu-id="4b0c8-118">Der Bereich der Parameter einer anonymen Methode ist der *anonyme Methodenblock*.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-118">The scope of the parameters of an anonymous method is the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="4b0c8-119">Es ist ein Fehler, wenn sich eine Sprunganweisung wie [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) oder [continue](../../../csharp/language-reference/keywords/continue.md) innerhalb des anonymen Methodenblocks befindet, wenn das Ziel außerhalb des Blocks liegt.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-119">It is an error to have a jump statement, such as [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), or [continue](../../../csharp/language-reference/keywords/continue.md), inside the anonymous method block if the target is outside the block.</span></span> <span data-ttu-id="4b0c8-120">Es ist auch ein Fehler, wenn sich eine Sprunganweisung wie `goto`, `break` oder `continue` außerhalb des anonymen Methodenblocks befindet, wenn das Ziel innerhalb des Blocks liegt.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-120">It is also an error to have a jump statement, such as `goto`, `break`, or `continue`, outside the anonymous method block if the target is inside the block.</span></span>  
  
 <span data-ttu-id="4b0c8-121">Die lokalen Variablen und Parameter, deren Bereich eine anonyme Methodendeklaration enthält, werden als *äußere* Variablen der anonymen Methode bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-121">The local variables and parameters whose scope contains an anonymous method declaration are called *outer* variables of the anonymous method.</span></span> <span data-ttu-id="4b0c8-122">Beispielsweise ist im folgenden Codesegment `n` eine äußere Variable:</span><span class="sxs-lookup"><span data-stu-id="4b0c8-122">For example, in the following code segment, `n` is an outer variable:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 <span data-ttu-id="4b0c8-123">Ein Verweis auf die äußere Variable `n` gilt als *erfasst*, wenn der Delegat erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-123">A reference to the outer variable `n` is said to be *captured* when the delegate is created.</span></span> <span data-ttu-id="4b0c8-124">Anders als bei lokalen Variablen erstreckt sich die Lebensdauer einer erfassten Variablen so lange, bis die Delegaten, die auf die anonymen Methoden verweisen, für die automatische Speicherbereinigung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-124">Unlike local variables, the lifetime of a captured variable extends until the delegates that reference the anonymous methods are eligible for garbage collection.</span></span>  
  
 <span data-ttu-id="4b0c8-125">Eine anonyme Methode kann nicht auf die Parameter [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) oder [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) eines äußeren Bereichs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-125">An anonymous method cannot access the [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters of an outer scope.</span></span>  
  
 <span data-ttu-id="4b0c8-126">Auf unsicheren Code kann nicht innerhalb des *anonymen Methodenblocks* zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-126">No unsafe code can be accessed within the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="4b0c8-127">Anonyme Methoden sind auf der linken Seite des [is](../../../csharp/language-reference/keywords/is.md)-Operators nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-127">Anonymous methods are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b0c8-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b0c8-128">Example</span></span>  
 <span data-ttu-id="4b0c8-129">Im folgenden Beispiel werden zwei Möglichkeiten veranschaulicht, um einen Delegaten zu instanziieren:</span><span class="sxs-lookup"><span data-stu-id="4b0c8-129">The following example demonstrates two ways of instantiating a delegate:</span></span>  
  
-   <span data-ttu-id="4b0c8-130">Zuordnen des Delegaten zu einer anonymen Methode.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-130">Associating the delegate with an anonymous method.</span></span>  
  
-   <span data-ttu-id="4b0c8-131">Zuordnen des Delegaten zu einer benannten Methode (`DoWork`).</span><span class="sxs-lookup"><span data-stu-id="4b0c8-131">Associating the delegate with a named method (`DoWork`).</span></span>  
  
 <span data-ttu-id="4b0c8-132">In beiden Fällen wird eine Meldung angezeigt, wenn der Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4b0c8-132">In each case, a message is displayed when the delegate is invoked.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4b0c8-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b0c8-133">See Also</span></span>  
 [<span data-ttu-id="4b0c8-134">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4b0c8-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4b0c8-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4b0c8-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4b0c8-136">Delegaten</span><span class="sxs-lookup"><span data-stu-id="4b0c8-136">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="4b0c8-137">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4b0c8-137">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [<span data-ttu-id="4b0c8-138">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="4b0c8-138">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="4b0c8-139">Methoden</span><span class="sxs-lookup"><span data-stu-id="4b0c8-139">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="4b0c8-140">Delegate mit benannten im Vergleich zu anonymen Methoden</span><span class="sxs-lookup"><span data-stu-id="4b0c8-140">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
