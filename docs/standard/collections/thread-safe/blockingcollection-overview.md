---
title: "Übersicht über BlockingCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BlockingCollection, overview
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 10e59c246914c17c4a0803de52cf891b2e0d3a3f
ms.contentlocale: de-de
ms.lasthandoff: 09/19/2017

---
# <a name="blockingcollection-overview"></a>Übersicht über BlockingCollection
<xref:System.Collections.Concurrent.BlockingCollection%601> ist eine threadsichere Auflistungsklasse, die die folgenden Features bietet:  
  
-   Eine Implementierung des Producer-Consumer-Musters.  
  
-   Gleichzeitiges Hinzufügen und Entfernen von Elementen aus mehreren Threads.  
  
-   Optionale maximale Kapazität.  
  
-   Einfüge- und Löschvorgänge, die blockiert werden, wenn die Auflistung leer oder voll ist.  
  
-   „Versuchs“-Einfüge- und Löschvorgänge, die nicht oder nur für eine angegebene Zeitspanne blockiert werden.  
  
-   Kapselt jeden Auflistungstyp, der <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> implementiert.  
  
-   Abbruch mit Abbruchtoken.  
  
-   Zwei Arten von Enumeration mit `foreach` (`For Each` in Visual Basic):  
  
    1.  Schreibgeschützte Enumeration.  
  
    2.  Enumeration, in deren Verlauf Elemente entfernt werden.  
  
## <a name="bounding-and-blocking-support"></a>Unterstützung von Begrenzen und Blockieren  
 <xref:System.Collections.Concurrent.BlockingCollection%601> unterstützt das Begrenzen und Blockieren Begrenzen bedeutet, dass Sie die maximale Kapazität der Auflistung festlegen können. Begrenzen ist in bestimmten Szenarien wichtig, da es Ihnen ermöglicht, die maximale Größe der Auflistung im Arbeitsspeicher zu steuern, und es verhindert, dass die erzeugenden Threads sich zu weit vor die verbrauchenden Threads bewegen.  
  
 Mehrere Threads oder Tasks können gleichzeitig der Auflistung Elemente hinzufügen, und wenn die Auflistung die angegebene maximale Kapazität erreicht, werden die erzeugenden Threads blockiert, bis ein Element entfernt wird. Mehrere Consumer können gleichzeitig Elemente entfernen, und wenn die Auflistung leer ist, werden die verbrauchenden Threads blockiert, bis ein Producer ein Element hinzufügt. Ein Producer-Thread kann <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> aufrufen, um anzuzeigen, dass keine Elemente mehr hinzugefügt werden. Consumer überwachen die <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A>-Eigenschaft, um zu wissen, wann die Auflistung leer ist, und keine Elemente mehr hinzugefügt werden. Das folgende Beispiel zeigt eine einfache BlockingCollection mit einer begrenzten Kapazität von 100. Ein Producer-Task fügt der Auflistung Elemente hinzu, solange eine externe Bedingung wahr ist, und ruft dann <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> auf. Der Consumer-Task entnimmt Elemente, bis die <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A>-Eigenschaft wahr ist.  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 Ein vollständiges Beispiel finden Sie unter [Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## <a name="timed-blocking-operations"></a>Zeitgesteuerte Blockierungsvorgänge  
 In zeitgesteuerten <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>- und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>-Blockierungsvorgängen, die für begrenzte Sammlungen durchgeführt werden, versucht die Methode, ein Element hinzuzufügen oder zu entnehmen. Wenn ein Element verfügbar ist, wird es in die Variable eingesetzt, die durch Verweis übergeben wurde, und die Methode gibt WAHR zurück. Wenn nach einer angegebenen Timeoutfrist kein Element abgerufen wird, gibt die Methode FALSCH zurück. Der Thread ist dann vor dem erneuten Versuch, auf die Auflistung zuzugreifen, frei für andere nützliche Aufgaben. Ein Beispiel für das zeitgesteuerte Blockieren des Zugriffs ist das zweite Beispiel unter [Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## <a name="cancelling-add-and-take-operations"></a>Abbrechen von Hinzufüge- und Nehmevorgängen  
 Hinzufüge- und Nehmevorgänge werden in der Regel in einer Schleife ausgeführt. Sie können eine Schleife durch die Übergabe eines <xref:System.Threading.CancellationToken> an die <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>- oder <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>-Methode abbrechen und dann den Wert der <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>-Eigenschaft des Tokens in jeder Iteration überprüfen. Wenn der Wert WAHR ist, liegt es an Ihnen, auf die Abbruchanforderung durch Bereinigen aller Ressourcen und Beenden der Schleife zu reagieren. Das folgende Beispiel zeigt eine Überladung von <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>, die ein Abbruchtoken entgegennimmt, und den Code, der es verwendet:  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 Ein Beispiel für das Hinzufügen von Abbruchunterstützung ist das zweite Beispiel unter [Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## <a name="specifying-the-collection-type"></a>Angeben des Auflistungstyps  
 Beim Erstellen einer <xref:System.Collections.Concurrent.BlockingCollection%601> können Sie nicht nur die begrenzte Kapazität angeben, sondern auch den Typ der zu verwendenden Auflistung. Sie könnten z.B. einen <xref:System.Collections.Concurrent.ConcurrentQueue%601> für das First-in-First-out-Verhalten (FIFO) oder einen <xref:System.Collections.Concurrent.ConcurrentStack%601> für das Last-in-First-out-Verhalten (LIFO) angeben. Sie können jede Auflistungsklasse verwenden, die die <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>-Schnittstelle implementiert. Der standardmäßige Auflistungstyp für <xref:System.Collections.Concurrent.BlockingCollection%601> ist <xref:System.Collections.Concurrent.ConcurrentQueue%601>. Das folgende Codebeispiel veranschaulicht das Erstellen einer <xref:System.Collections.Concurrent.BlockingCollection%601> von Zeichenfolgen, die eine Kapazität von 1000 hat und einen <xref:System.Collections.Concurrent.ConcurrentBag%601> verwendet:  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Begrenzungs- und Blockadefunktionen zu einer Auflistung](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md).  
  
## <a name="ienumerable-support"></a>IEnumerable-Unterstützung  
 <xref:System.Collections.Concurrent.BlockingCollection%601> bietet eine <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>-Methode, mit der Consumer eine `foreach` (`For Each` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]) verwenden können, um Elemente zu entfernen, bis die Sammlung abgeschlossen ist, d.h. bis sie leer ist und keine Elemente mehr hinzugefügt werden. Weitere Informationen finden Sie unter [Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).  
  
## <a name="using-many-blockingcollections-as-one"></a>Verwenden vieler BlockingCollections als eine einzige  
 Für Szenarien, in denen ein Consumer Elemente aus mehreren Auflistungen gleichzeitig nehmen muss, können Sie Arrays von <xref:System.Collections.Concurrent.BlockingCollection%601> erstellen und statische Methoden wie <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A> verwenden, die Elemente beliebigen Auflistungen im Array hinzufügen bzw. daraus entnehmen. Wenn eine Auflistung blockiert wird, versucht die Methode sofort, eine andere zu verwenden, bis sie eine findet, die den Vorgang ausführen kann. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von Arrays mit blockierenden Auflistungen in einer Pipeline](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Auflistungen und Datenstrukturen](../../../../docs/standard/collections/index.md)   
 [threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)

