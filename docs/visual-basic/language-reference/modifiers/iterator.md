---
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 0b459a16317b8ba55886e52ecadb227ddf2fee83
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875437"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="b1474-102">Iterator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1474-102">Iterator (Visual Basic)</span></span>

<span data-ttu-id="b1474-103">Gibt an, dass eine Funktion oder ein `Get` Accessor ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="b1474-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1474-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b1474-104">Remarks</span></span>  

 <span data-ttu-id="b1474-105">Ein *Iterator* führt eine benutzerdefinierte iterierung für eine Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="b1474-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="b1474-106">Ein Iterator verwendet die [Yield](../statements/yield-statement.md) -Anweisung, um jedes Element in der Auflistung einzeln zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b1474-106">An iterator uses the [Yield](../statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="b1474-107">Wenn eine- `Yield` Anweisung erreicht wird, wird die aktuelle Position im Code beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b1474-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="b1474-108">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="b1474-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="b1474-109">Ein Iterator kann als Funktion oder als- `Get` Accessor einer Eigenschafts Definition implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="b1474-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="b1474-110">Der- `Iterator` Modifizierer wird in der Deklaration der Iteratorfunktion oder-Zugriffsmethode angezeigt `Get` .</span><span class="sxs-lookup"><span data-stu-id="b1474-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="b1474-111">Sie verwenden einen Iterator aus dem Client Code, indem Sie eine [for each-... Next-Anweisung](../statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1474-111">You call an iterator from client code by using a [For Each...Next Statement](../statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="b1474-112">Der Rückgabetyp einer Iteratorfunktion oder- `Get` Zugriffsmethode kann <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , oder sein <xref:System.Collections.IEnumerator> <xref:System.Collections.Generic.IEnumerator%601> .</span><span class="sxs-lookup"><span data-stu-id="b1474-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="b1474-113">Ein Iterator kann keine `ByRef` Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b1474-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="b1474-114">Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.</span><span class="sxs-lookup"><span data-stu-id="b1474-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="b1474-115">Ein Iterator kann eine anonyme Funktion sein.</span><span class="sxs-lookup"><span data-stu-id="b1474-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="b1474-116">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="b1474-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="b1474-117">Verwendung</span><span class="sxs-lookup"><span data-stu-id="b1474-117">Usage</span></span>  

 <span data-ttu-id="b1474-118">Der `Iterator`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b1474-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
- [<span data-ttu-id="b1474-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b1474-119">Function Statement</span></span>](../statements/function-statement.md)  
  
- [<span data-ttu-id="b1474-120">Property Statement</span><span class="sxs-lookup"><span data-stu-id="b1474-120">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="b1474-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1474-121">Example</span></span>  

 <span data-ttu-id="b1474-122">Im folgenden Beispiel wird eine Iteratorfunktion veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b1474-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="b1474-123">Die Iteratorfunktion weist eine- `Yield` Anweisung auf, die sich innerhalb einer [for... Nächste](../statements/for-next-statement.md) Schleife.</span><span class="sxs-lookup"><span data-stu-id="b1474-123">The iterator function has a `Yield` statement that is inside a [For…Next](../statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="b1474-124">Jede Iterationen des [foreach](../statements/for-each-next-statement.md) - `Main` Anweisungs Texts in erstellt einen-Rückruf für die `Power` Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="b1474-124">Each iteration of the [For Each](../statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="b1474-125">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b1474-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="b1474-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1474-126">Example</span></span>  

 <span data-ttu-id="b1474-127">Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="b1474-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="b1474-128">Der- `Iterator` Modifizierer befindet sich in der Eigenschafts Deklaration.</span><span class="sxs-lookup"><span data-stu-id="b1474-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="b1474-129">Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="b1474-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1474-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1474-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="b1474-131">Iteratoren</span><span class="sxs-lookup"><span data-stu-id="b1474-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="b1474-132">Yield-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b1474-132">Yield Statement</span></span>](../statements/yield-statement.md)
