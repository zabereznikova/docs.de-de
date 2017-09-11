---
title: 'Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b0f0ed30ae5192ed8a8f069d591855857bd2fa49
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a><span data-ttu-id="177da-102">Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach</span><span class="sxs-lookup"><span data-stu-id="177da-102">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>
<span data-ttu-id="177da-103">Zusätzlich zum Entnehmen von Elementen aus einer <xref:System.Collections.Concurrent.BlockingCollection%601> mithilfe der Methoden <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> können Sie auch eine [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) verwenden, um Elemente zu entfernen, bis der Hinzufügevorgang abgeschlossen und die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="177da-103">In addition to taking items from a <xref:System.Collections.Concurrent.BlockingCollection%601> by using the <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> method, you can also use a [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) to remove items until adding is completed and the collection is empty.</span></span> <span data-ttu-id="177da-104">Dies wird als *mutierende Enumeration* oder *verbrauchende Enumeration* bezeichnet, da dieser Enumerator, im Gegensatz zu einer typischen `foreach`- (`For Each`-)Schleife, die Quellsammlung durch Entfernen von Elementen verändert.</span><span class="sxs-lookup"><span data-stu-id="177da-104">This is called a *mutating enumeration* or *consuming enumeration* because, unlike a typical `foreach` (`For Each`) loop, this enumerator modifies the source collection by removing items.</span></span>  
  
## <a name="example"></a><span data-ttu-id="177da-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="177da-105">Example</span></span>  
 <span data-ttu-id="177da-106">Das folgende Beispiel zeigt das Entfernen aller Elemente in einer <xref:System.Collections.Concurrent.BlockingCollection%601> mithilfe einer `foreach`-Schleife (`For Each`).</span><span class="sxs-lookup"><span data-stu-id="177da-106">The following example shows how to remove all the items in a <xref:System.Collections.Concurrent.BlockingCollection%601> by using a `foreach` (`For Each`) loop.</span></span>  
  
 <span data-ttu-id="177da-107">[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)] [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]</span><span class="sxs-lookup"><span data-stu-id="177da-107">[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)] [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]</span></span>  
  
 <span data-ttu-id="177da-108">Dieses Beispiel verwendet eine `foreach`-Schleife mit der <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName>-Methode im verbrauchenden Thread, wodurch jedes Element beim Aufzählen aus der Auflistung entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="177da-108">This example uses a `foreach` loop with the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> method in the consuming thread, which causes each item to be removed from the collection as it is enumerated.</span></span> <span data-ttu-id="177da-109"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> begrenzt die maximale Anzahl von Elementen, die sich zu einem bestimmten Zeitpunkt in der Sammlung befinden können.</span><span class="sxs-lookup"><span data-stu-id="177da-109"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> limits the maximum number of items that are in the collection at any time.</span></span> <span data-ttu-id="177da-110">Durch Aufzählen der Auflistung auf diese Weise wird der Consumerthread blockiert, wenn keine Elemente verfügbar sind oder die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="177da-110">Enumerating the collection in this way blocks the consumer thread if no items are available or if the collection is empty.</span></span> <span data-ttu-id="177da-111">In diesem Beispiel ist eine Blockierung kein Problem, da der Producerthread Elemente schneller hinzufügt als sie verbraucht werden können.</span><span class="sxs-lookup"><span data-stu-id="177da-111">In this example blocking is not a concern because the producer thread adds items faster than they can be consumed.</span></span>  
  
 <span data-ttu-id="177da-112">Es gibt keine Garantie dafür, dass die Elemente in der gleichen Reihenfolge aufgezählt werden, in der sie von den Producerthreads hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="177da-112">There is no guarantee that the items are enumerated in the same order in which they are added by the producer threads.</span></span>  
  
 <span data-ttu-id="177da-113">Um die Auflistung aufzuzählen, ohne sie zu verändern, verwenden Sie einfach `foreach` (`For Each`) ohne die <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="177da-113">To enumerate the collection without modifying it, just use `foreach` (`For Each`) without the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> method.</span></span> <span data-ttu-id="177da-114">Es ist jedoch wichtig zu wissen, dass diese Art der Enumeration eine Momentaufnahme der Auflistung zu einem genauen Zeitpunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="177da-114">However, it is important to understand that this kind of enumeration represents a snapshot of the collection at a precise point in time.</span></span> <span data-ttu-id="177da-115">Wenn weitere Threads gleichzeitig Elemente hinzufügen oder entfernen, während die Schleife ausgeführt wird, stellt die Schleife möglicherweise nicht den tatsächlichen Zustand der Auflistung dar.</span><span class="sxs-lookup"><span data-stu-id="177da-115">If other threads are adding or removing items concurrently while you are executing the loop, then the loop might not represent the actual state of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="177da-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="177da-116">See Also</span></span>  
 <span data-ttu-id="177da-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="177da-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span></span>   
 [<span data-ttu-id="177da-118">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="177da-118">Parallel Programming</span></span>](../../../../docs/standard/parallel-programming/index.md)

