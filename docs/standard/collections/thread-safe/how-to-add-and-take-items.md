---
title: "Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
caps.latest.revision: 7
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66b4e921a4c7285976694f4633ce1eeaadcb7cf9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a><span data-ttu-id="a3898-102">Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="a3898-102">How to: Add and Take Items Individually from a BlockingCollection</span></span>
<span data-ttu-id="a3898-103">Dieses Beispiel zeigt, wie einem <xref:System.Collections.Concurrent.BlockingCollection%601>-Objekt Elemente sowohl auf blockierende als auch auf nicht blockierende Weise hinzugefügt und wie Elemente auf diese Weisen aus dem Objekt entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="a3898-103">This example shows how to add and remove items from a <xref:System.Collections.Concurrent.BlockingCollection%601> in both a blocking and non-blocking manner.</span></span> <span data-ttu-id="a3898-104">Weitere Informationen zu <xref:System.Collections.Concurrent.BlockingCollection%601> finden Sie unter [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a3898-104">For more information on <xref:System.Collections.Concurrent.BlockingCollection%601>, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
 <span data-ttu-id="a3898-105">Ein Beispiel für das Entfernen von Elementen aus einer <xref:System.Collections.Concurrent.BlockingCollection%601> per Enumeration, bis sie leer ist und keine weiteren Elemente hinzugefügt werden, finden Sie unter [Vorgehensweise: Entfernen von Elementen in einer BlockingCollection mit ForEach](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).</span><span class="sxs-lookup"><span data-stu-id="a3898-105">For an example of how to enumerate a <xref:System.Collections.Concurrent.BlockingCollection%601> until it is empty and no more elements will be added, see [How to: Use ForEach to Remove Items in a BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3898-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3898-106">Example</span></span>  
 <span data-ttu-id="a3898-107">Dieses erste Beispiel zeigt, wie Elemente hinzuzufügen und zu entnehmen sind, damit die Vorgänge blockiert werden, wenn die Auflistung entweder vorübergehend leer ist (beim Entnehmen) oder ihre maximale Kapazität erreicht hat (beim Hinzufügen) oder wenn ein angegebenes Timeout erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="a3898-107">This first example shows how to add and take items so that the operations will block if the collection is either temporarily empty (when taking) or at maximum capacity (when adding), or a specified timeout period has elapsed.</span></span> <span data-ttu-id="a3898-108">Beachten Sie, dass Blockierung für maximale Kapazität nur aktiviert wird, wenn bei der Erstellung von BlockingCollection im Konstruktor eine maximale Kapazität angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a3898-108">Note that blocking on maximum capacity is only enabled when the BlockingCollection has been created with a maximum capacity specified in the constructor.</span></span>  
  
 <span data-ttu-id="a3898-109">[!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)] [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]</span><span class="sxs-lookup"><span data-stu-id="a3898-109">[!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)] [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3898-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3898-110">Example</span></span>  
 <span data-ttu-id="a3898-111">In diesem zweiten Beispiel wird veranschaulicht, wie Elemente hinzuzufügen bzw. zu entnehmen sind, damit die Vorgänge nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3898-111">This second example shows how to add and take items so that the operations will not block.</span></span> <span data-ttu-id="a3898-112">Ist kein Element vorhanden, oder ist die maximale Kapazität in einer begrenzten Auflistung erreicht, oder ist das Timeout erreicht, gibt der <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> -Vorgang oder der <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> -Vorgang „false“ zurück.</span><span class="sxs-lookup"><span data-stu-id="a3898-112">If no item is present, or maximum capacity on a bounded collection has been reached, or the timeout period has elapsed, then the <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> or <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> operation returns false.</span></span> <span data-ttu-id="a3898-113">Dies ermöglicht dem Thread, vorübergehend eine andere Aufgabe zu erledigen und später erneut zu versuchen, entweder ein neues Element abzurufen oder das Element hinzuzufügen, das zuvor nicht hinzugefügt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="a3898-113">This allows the thread to do some other useful work for awhile and then try again later to either retrieve a new item, or try to add the same item that could not be added previously.</span></span> <span data-ttu-id="a3898-114">Das Programm veranschaulicht außerdem, wie für den Zugriff auf eine <xref:System.Collections.Concurrent.BlockingCollection%601> ein Abbruch implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a3898-114">The program also demonstrates how to implement cancellation when accessing a <xref:System.Collections.Concurrent.BlockingCollection%601>.</span></span>  
  
 <span data-ttu-id="a3898-115">[!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)] [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]</span><span class="sxs-lookup"><span data-stu-id="a3898-115">[!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)] [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3898-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3898-116">See Also</span></span>  
 <span data-ttu-id="a3898-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a3898-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span></span>   
 [<span data-ttu-id="a3898-118">Übersicht über BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="a3898-118">BlockingCollection Overview</span></span>](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)

