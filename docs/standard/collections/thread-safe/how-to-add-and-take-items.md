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
dev_langs:
- csharp
- vb
helpviewer_keywords: thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b365d6d3236919f65c840343ec3b33edebea758b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a>Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection
Dieses Beispiel zeigt, wie einem <xref:System.Collections.Concurrent.BlockingCollection%601>-Objekt Elemente sowohl auf blockierende als auch auf nicht blockierende Weise hinzugefügt und wie Elemente auf diese Weisen aus dem Objekt entfernt werden können. Weitere Informationen zu <xref:System.Collections.Concurrent.BlockingCollection%601> finden Sie unter [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
 Ein Beispiel für das Entfernen von Elementen aus einer <xref:System.Collections.Concurrent.BlockingCollection%601> per Enumeration, bis sie leer ist und keine weiteren Elemente hinzugefügt werden, finden Sie unter [Vorgehensweise: Entfernen von Elementen in einer BlockingCollection mit ForEach](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).  
  
## <a name="example"></a>Beispiel  
 Dieses erste Beispiel zeigt, wie Elemente hinzuzufügen und zu entnehmen sind, damit die Vorgänge blockiert werden, wenn die Auflistung entweder vorübergehend leer ist (beim Entnehmen) oder ihre maximale Kapazität erreicht hat (beim Hinzufügen) oder wenn ein angegebenes Timeout erreicht ist. Beachten Sie, dass Blockierung für maximale Kapazität nur aktiviert wird, wenn bei der Erstellung von BlockingCollection im Konstruktor eine maximale Kapazität angegeben wurde.  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a>Beispiel  
 In diesem zweiten Beispiel wird veranschaulicht, wie Elemente hinzuzufügen bzw. zu entnehmen sind, damit die Vorgänge nicht blockiert werden. Ist kein Element vorhanden, oder ist die maximale Kapazität in einer begrenzten Auflistung erreicht, oder ist das Timeout erreicht, gibt der <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> -Vorgang oder der <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> -Vorgang „false“ zurück. Dies ermöglicht dem Thread, vorübergehend eine andere Aufgabe zu erledigen und später erneut zu versuchen, entweder ein neues Element abzurufen oder das Element hinzuzufügen, das zuvor nicht hinzugefügt werden konnte. Das Programm veranschaulicht außerdem, wie für den Zugriff auf eine <xref:System.Collections.Concurrent.BlockingCollection%601> ein Abbruch implementiert wird.  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)
