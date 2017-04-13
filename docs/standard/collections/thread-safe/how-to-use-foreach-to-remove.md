---
title: "Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach | Microsoft Docs"
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
  - "Threadsichere Auflistungen, Auflisten blockierender Auflistungen"
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Entfernen von Elementen in einer BlockingCollection mit ForEach
Neben dem Entnehmen von Elementen aus einer <xref:System.Collections.Concurrent.BlockingCollection%601> mit der <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A>\-Methode und der <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>\-Methode können Sie auch [foreach](../Topic/foreach,%20in%20\(C%23%20Reference\).md) \([For Each](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md) in Visual Basic\) verwenden, um Elemente zu entfernen, bis die Auflistung leer ist.  Dies wird als *mutierende Enumeration* oder *verbrauchende Enumeration* bezeichnet, da dieser Enumerator anders als eine typische `foreach`\-Schleife \(`For Each`\) durch das Entfernen von Elementen die Quellauflistung ändert.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie alle Elemente in einer <xref:System.Collections.Concurrent.BlockingCollection%601> mit einer `foreach`\-Schleife \(`For Each`\) entfernt werden.  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 In diesem Beispiel wird eine `foreach`\-Schleife mit der <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName>\-Methode im Consumerthread verwendet, durch die jedes Element aus der Auflistung entfernt wird, wenn es aufgelistet wird.  <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> begrenzt die maximale Anzahl gleichzeitiger Elemente in der Auflistung.  Wenn die Auflistung auf diese Weise aufgelistet wird, wird der Consumerthread blockiert, wenn keine Elemente verfügbar sind oder die Auflistung leer ist.  Die Blockierung ist in diesem Beispiel nicht von Bedeutung, da der Producerthread Elemente schneller hinzufügt, als sie abgerufen werden können.  
  
 Es gibt keine Garantie, dass die Elemente in der gleichen Reihenfolge aufgelistet werden, in der sie von den Producerthreads hinzugefügt werden.  
  
 Wenn Sie die Auflistung auflisten möchten, ohne sie zu ändern, verwenden Sie nur `foreach` \(`For Each`\) ohne die <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>\-Methode.  Beachten Sie, dass diese Art von Enumeration eine Momentaufnahme der Auflistung zu einem genauen Zeitpunkt darstellt.  Wenn andere Threads gleichzeitig Elemente hinzufügen oder entfernen, während Sie die Schleife ausführen, stellt die Schleife möglicherweise nicht den tatsächlichen Zustand der Auflistung dar.  
  
## Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Parallel Programming](../../../../docs/standard/parallel-programming/index.md)