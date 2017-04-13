---
title: "&#220;bersicht &#252;ber BlockingCollection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BlockingCollection, Übersicht"
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber BlockingCollection
<xref:System.Collections.Concurrent.BlockingCollection%601> ist eine threadsichere Auflistungsklasse, die folgende Funktionen bereitstellt:  
  
-   Eine Implementierung des Producer\-Consumer\-Musters  
  
-   Gleichzeitiges Hinzufügen und Entfernen von Elementen zu bzw. in mehreren Threads  
  
-   Optionale maximale Kapazität  
  
-   Einfügungs\- und Löschvorgänge, die blockiert werden, wenn die Auflistung leer oder voll ist  
  
-   Einfügen und Löschen von "try"\-Vorgängen, die nicht oder nur für einen bestimmten Zeitraum blockiert werden  
  
-   Kapselt jeden Auflistungstyp, der <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> implementiert.  
  
-   Abbruch mit Abbruchtokens  
  
-   Zwei Arten von Enumeration mit `foreach` \(`For Each` in Visual Basic\):  
  
    1.  Schreibgeschützte Enumeration  
  
    2.  Enumeration, die Elemente bei der Aufzählung entfernt  
  
## Unterstützung für Begrenzungs\- und Blockierungsvorgänge  
 <xref:System.Collections.Concurrent.BlockingCollection%601> unterstützt Begrenzungs\- und Blockierungsvorgänge.  Durch Begrenzung können Sie die maximale Kapazität der Auflistung festlegen.  Das Begrenzen ist in bestimmten Szenarien wichtig, da so die maximale Größe der Auflistung im Arbeitsspeicher gesteuert werden kann. Außerdem wird verhindert, dass sich die Producer\-Threads zu weit von den Consumer\-Threads entfernen.  
  
 Der Auflistung können von zahlreichen Threads oder Aufgaben gleichzeitig Elemente hinzugefügt werden. Wenn die Auflistung dann die angegebene maximale Kapazität erreicht, werden die Producer\-Threads so lange blockiert, bis ein Element entfernt wird.  Mehrere Consumer können gleichzeitig Elemente entfernen. Ist die Auflistung leer, werden die Consumer\-Threads so lange blockiert, bis von einem Producer ein Element hinzugefügt wird.  Von einem Producer\-Thread kann <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> aufgerufen werden, um anzugeben, dass keine Elemente mehr hinzugefügt werden.  Die <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A>\-Eigenschaft wird von Consumern überwacht, damit keine Elemente mehr hinzugefügt werden, sobald die Auflistung leer ist.  Das folgende Beispiel zeigt eine einfache BlockingCollection mit einer begrenzten Kapazität von 100.  Von einer Producer\-Aufgabe werden der Auflistung nur solange Elemente hinzugefügt, wie eine externe Bedingung den Wert "true" aufweist. Anschließend wird <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> aufgerufen.  Die Consumeraufgabe entnimmt Elemente, bis die <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A>\-Eigenschaft true ist.  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 Ein vollständiges Beispiel finden Sie unter [Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Zeitgesteuerte Blockierungsvorgänge  
 In zeitgesteuerten <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>\- und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>\-Blockierungsvorgängen in begrenzten Auflistungen versucht die Methode, ein Element hinzuzufügen oder zu entfernen.  Ist ein Element verfügbar, wird es in die Variable eingefügt, die durch einen Verweis übergeben wurde, und von der Methode wird "true" zurückgegeben.  Wird nach einem angegebenen Timeout kein Element abgerufen, wird von der Methode "false" zurückgegeben.  Vom Thread können dann vor dem erneuten Zugriff auf die Auflistung andere wichtige Aufgaben erledigt werden.  Ein Beispiel für den zeitgesteuerten Zugriff auf Blockierungen finden Sie im zweiten Beispiel unter [Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Abbrechen von Vorgängen für das Hinzufügen und Entfernen  
 Vorgänge für das Hinzufügen und Entfernen werden in der Regel in einer Schleife ausgeführt.  Sie können eine Schleife abbrechen, indem Sie ein <xref:System.Threading.CancellationToken> an die <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>\- oder <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>\-Methode übergeben und dann den Wert der <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>\-Eigenschaft des Tokens in jeder Iteration überprüfen.  Ist für den Wert "true" festgelegt, muss von Ihnen auf die Abbruchanforderung reagiert werden. Bereinigen Sie hierzu alle Ressourcen, und beenden Sie die Schleife.  Das folgende Beispiel zeigt eine Überladung von <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>, an die ein Abbruchtoken übergeben wird, und den Code, in dem das Token verwendet wird:  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 Ein Beispiel für das Hinzufügen von Unterstützung für Abbruchvorgänge finden Sie im zweiten Beispiel in [Gewusst wie: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Angeben des Auflistungstyps  
 Beim Erstellen einer <xref:System.Collections.Concurrent.BlockingCollection%601> kann nicht nur die begrenzte Kapazität, sondern auch der zu verwendende Auflistungstyp angegeben werden.  Sie können z. B. ein <xref:System.Collections.Concurrent.ConcurrentQueue%601> für ein FIFO\-Verhalten \(First\-In\-First\-Out\) oder ein <xref:System.Collections.Concurrent.ConcurrentStack%601> für ein LIFO\-Verhalten \(Last\-In\-First\-Out\) angeben.  Sie können jede Auflistungsklasse verwenden, von der die <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>\-Schnittstelle implementiert wird.  Der standardmäßige Auflistungstyp für <xref:System.Collections.Concurrent.BlockingCollection%601> ist <xref:System.Collections.Concurrent.ConcurrentQueue%601>.  Das folgende Codebeispiel veranschaulicht, wie eine <xref:System.Collections.Concurrent.BlockingCollection%601> von Zeichenfolgen mit einer Kapazität von 1000 erstellt wird, die eine <xref:System.Collections.Concurrent.ConcurrentBag%601> verwendet:  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Begrenzungs\- und Blockadefunktionen zu einer Auflistung](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md).  
  
## IEnumerable\-Unterstützung  
 <xref:System.Collections.Concurrent.BlockingCollection%601> stellt eine <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>\-Methode bereit, die Consumern die Verwendung von `foreach` \(`For Each` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) ermöglicht, um so lange Elemente zu entfernen, bis die Auflistung abgeschlossen ist, d. h., bis sie leer ist und keine Elemente mehr hinzugefügt werden.  Weitere Informationen finden Sie unter [Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).  
  
## Verwenden vieler BlockingCollections als eine einzelne Auflistung  
 Für Szenarien, in denen von einem Consumer Elemente aus mehreren Auflistungen gleichzeitig entnommen werden müssen, können Sie Arrays von <xref:System.Collections.Concurrent.BlockingCollection%601> erstellen und statische Methoden, wie <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> oder <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A> verwenden, von denen für beliebige Auflistungen im Array Elemente entfernt bzw. hinzugefügt werden können.  Wird eine Auflistung blockiert, wird von der Methode so lange weitergesucht, bis eine Auflistung gefunden wird, von der der Vorgang ausgeführt werden kann.  Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von Arrays mit blockierenden Auflistungen in einer Pipeline](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md).  
  
## Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Auflistungen und Datenstrukturen](../../../../docs/standard/collections/index.md)   
 [Threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)