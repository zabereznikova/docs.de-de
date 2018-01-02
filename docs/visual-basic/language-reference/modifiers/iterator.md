---
title: Iterator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Iterator
helpviewer_keywords: Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd6c0b1fa422dc4ab659d8c59472e5c098c729bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="3b124-102">Iterator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b124-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="3b124-103">Gibt an, dass eine Funktion oder `Get` Accessor, der ein Iterator.</span><span class="sxs-lookup"><span data-stu-id="3b124-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b124-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b124-104">Remarks</span></span>  
 <span data-ttu-id="3b124-105">Ein *Iterator* führt eine benutzerdefinierte Iteration durch eine Auflistung.</span><span class="sxs-lookup"><span data-stu-id="3b124-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="3b124-106">Ein Iterator verwendet die [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) Anweisung, um jedes Element in der Auflistung zu einem Zeitpunkt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3b124-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="3b124-107">Wenn eine `Yield` Anweisung erreicht wird, wird die aktuelle Position im Code wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3b124-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="3b124-108">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="3b124-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="3b124-109">Ein Iterator kann implementiert werden, wie eine Funktion oder als eine `Get` Accessor, der eine Eigenschaftsdefinition.</span><span class="sxs-lookup"><span data-stu-id="3b124-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="3b124-110">Die `Iterator` Modifizierer wird angezeigt, in der Deklaration der Iteratorfunktion oder `Get` Accessor.</span><span class="sxs-lookup"><span data-stu-id="3b124-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="3b124-111">Sie rufen einen Iterator im Clientcode mithilfe einer [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3b124-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="3b124-112">Der Rückgabetyp einer Funktion Iterator oder `Get` Accessor kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="3b124-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="3b124-113">Ein Iterator keine `ByRef` Parameter.</span><span class="sxs-lookup"><span data-stu-id="3b124-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="3b124-114">Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.</span><span class="sxs-lookup"><span data-stu-id="3b124-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="3b124-115">Ein Iterator kann mit einer anonymen Funktion sein.</span><span class="sxs-lookup"><span data-stu-id="3b124-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="3b124-116">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="3b124-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="3b124-117">Verwendung</span><span class="sxs-lookup"><span data-stu-id="3b124-117">Usage</span></span>  
 <span data-ttu-id="3b124-118">Der `Iterator`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3b124-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="3b124-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3b124-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="3b124-120">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3b124-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="3b124-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b124-121">Example</span></span>  
 <span data-ttu-id="3b124-122">Im folgende Beispiel wird eine Iteratorfunktion veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3b124-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="3b124-123">Der Iteratorfunktion verfügt über eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife.</span><span class="sxs-lookup"><span data-stu-id="3b124-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="3b124-124">Jede Iteration der der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisungstexts in `Main` erzeugt einen Aufruf an die `Power` Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="3b124-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="3b124-125">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3b124-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3b124-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b124-126">Example</span></span>  
 <span data-ttu-id="3b124-127">Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="3b124-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="3b124-128">Die `Iterator` Modifizierer ist in der Eigenschaftendeklaration.</span><span class="sxs-lookup"><span data-stu-id="3b124-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 <span data-ttu-id="3b124-129">Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="3b124-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b124-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b124-130">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [<span data-ttu-id="3b124-131">Iteratoren</span><span class="sxs-lookup"><span data-stu-id="3b124-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)  
 [<span data-ttu-id="3b124-132">Yield-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3b124-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
