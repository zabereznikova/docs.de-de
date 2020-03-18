---
title: 'Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
ms.openlocfilehash: 3f4270d2ec71421bad8974a3e5cd8f1d65db3b74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711297"
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a>Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection
Dieses Beispiel zeigt, wie einem <xref:System.Collections.Concurrent.BlockingCollection%601>-Objekt Elemente sowohl auf blockierende als auch auf nicht blockierende Weise hinzugefügt und wie Elemente auf diese Weisen aus dem Objekt entfernt werden können. Weitere Informationen zu <xref:System.Collections.Concurrent.BlockingCollection%601> finden Sie unter [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
 Ein Beispiel für das Entfernen von Elementen aus einer <xref:System.Collections.Concurrent.BlockingCollection%601> per Enumeration, bis sie leer ist und keine weiteren Elemente hinzugefügt werden, finden Sie unter [Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).
  
## <a name="example"></a>Beispiel  
 Dieses erste Beispiel zeigt, wie Elemente hinzuzufügen und zu entnehmen sind, damit die Vorgänge blockiert werden, wenn die Auflistung entweder vorübergehend leer ist (beim Entnehmen) oder ihre maximale Kapazität erreicht hat (beim Hinzufügen) oder wenn ein angegebenes Timeout erreicht ist. Beachten Sie, dass Blockierung für maximale Kapazität nur aktiviert wird, wenn bei der Erstellung von BlockingCollection im Konstruktor eine maximale Kapazität angegeben wurde.  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a>Beispiel  
 In diesem zweiten Beispiel wird veranschaulicht, wie Elemente hinzuzufügen bzw. zu entnehmen sind, damit die Vorgänge nicht blockiert werden. Ist kein Element vorhanden, ist die maximale Kapazität in einer begrenzten Auflistung erreicht, oder ist das Timeout erreicht, gibt der <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>-Vorgang oder der <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>-Vorgang „false“ zurück. Dies ermöglicht dem Thread, vorübergehend einen anderen Task zu erledigen und später erneut zu versuchen, entweder ein neues Element abzurufen oder das Element hinzuzufügen, das zuvor nicht hinzugefügt werden konnte. Das Programm veranschaulicht außerdem, wie für den Zugriff auf ein <xref:System.Collections.Concurrent.BlockingCollection%601>-Objekt ein Abbruch implementiert wird.  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)
