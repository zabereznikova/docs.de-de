---
title: "Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection | Microsoft-Dokumentation"
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
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 442e2f9a80c4c0624c90e8a7509cd22f6be9a4a0
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a>Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection
Dieses Beispiel zeigt, wie einer <xref:System.Collections.Concurrent.BlockingCollection%601> Elemente sowohl auf blockierende als auch auf nicht blockierende Weise hinzugefügt und ebenso daraus entfernt werden können. Weitere Informationen zu <xref:System.Collections.Concurrent.BlockingCollection%601> finden Sie unter [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
 Ein Beispiel für das Aufzählen einer <xref:System.Collections.Concurrent.BlockingCollection%601>, bis sie leer ist und keine weiteren Elemente mehr hinzugefügt werden, finden Sie unter [Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)  
  
## <a name="example"></a>Beispiel  
 Dieses erste Beispiel zeigt, wie Elemente hinzuzufügen und zu entnehmen sind, damit die Vorgänge blockiert werden, wenn die Auflistung entweder vorübergehend leer ist (beim Entnehmen) oder ihre maximale Kapazität erreicht hat (beim Hinzufügen) oder wenn ein angegebenes Timeout erreicht ist. Beachten Sie, dass Blockierung für maximale Kapazität nur aktiviert wird, wenn bei der Erstellung von BlockingCollection im Konstruktor eine maximale Kapazität angegeben wurde.  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a>Beispiel  
 In diesem zweiten Beispiel wird veranschaulicht, wie Elemente hinzuzufügen bzw. zu entnehmen sind, damit die Vorgänge nicht blockiert werden. Wenn kein Element vorhanden ist, die maximale Kapazität für eine begrenzte Sammlung erreicht wurde oder das Zeitlimit verstrichen ist, gibt der <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>- oder <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>-Vorgang FALSCH zurück. Dies ermöglicht dem Thread, vorübergehend eine andere Aufgabe zu erledigen und später erneut zu versuchen, entweder ein neues Element abzurufen oder das Element hinzuzufügen, das zuvor nicht hinzugefügt werden konnte. Das Programm stellt auch ein Beispiel für die Abbruchimplementierung beim Zugriff auf eine <xref:System.Collections.Concurrent.BlockingCollection%601> dar.  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)
