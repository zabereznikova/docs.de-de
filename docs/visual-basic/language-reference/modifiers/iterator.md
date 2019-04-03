---
title: Iterator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 499949d1f4c20e1f465355bd076ba39f1496779b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822699"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="c2aa8-102">Iterator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2aa8-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="c2aa8-103">Gibt an, dass eine Funktion oder `Get` Accessor ist ein Iterator.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2aa8-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2aa8-104">Remarks</span></span>  
 <span data-ttu-id="c2aa8-105">Ein *Iterator* führt eine benutzerdefinierte Iteration durch eine Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="c2aa8-106">Ein Iterator verwendet die [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) Anweisung, um jedes Element in der Auflistung zu einem Zeitpunkt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="c2aa8-107">Wenn eine `Yield` Anweisung erreicht wird, wird die aktuelle Position im Code wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="c2aa8-108">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="c2aa8-109">Ein Iterator kann implementiert werden, als eine Funktion oder als eine `Get` Accessor einer Eigenschaft-Definition.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="c2aa8-110">Die `Iterator` Modifizierer wird angezeigt, in der Deklaration der Iteratorfunktion oder `Get` Accessor.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="c2aa8-111">Sie rufen einen Iterator im Clientcode mithilfe einer [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c2aa8-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="c2aa8-112">Der Rückgabetyp einer Funktion Iterator oder `Get` Accessor möglich <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="c2aa8-113">Ein Iterator kann keins besitzen `ByRef` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="c2aa8-114">Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="c2aa8-115">Ein Iterator kann es sich um eine anonyme Funktion sein.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="c2aa8-116">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="c2aa8-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="c2aa8-117">Verwendung</span><span class="sxs-lookup"><span data-stu-id="c2aa8-117">Usage</span></span>  
 <span data-ttu-id="c2aa8-118">Der `Iterator`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c2aa8-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="c2aa8-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c2aa8-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="c2aa8-120">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c2aa8-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="c2aa8-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2aa8-121">Example</span></span>  
 <span data-ttu-id="c2aa8-122">Das folgende Beispiel zeigt eine Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="c2aa8-123">Die Iteratorfunktion verfügt über eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="c2aa8-124">Jeder Iteration der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisungstexts in `Main` erstellt einen Aufruf an die `Power` Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="c2aa8-125">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="c2aa8-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2aa8-126">Example</span></span>  
 <span data-ttu-id="c2aa8-127">Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="c2aa8-128">Die `Iterator` Modifizierer ist in der Deklaration der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c2aa8-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="c2aa8-129">Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="c2aa8-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2aa8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2aa8-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="c2aa8-131">Iteratoren</span><span class="sxs-lookup"><span data-stu-id="c2aa8-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="c2aa8-132">Yield-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c2aa8-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
