---
title: "How to: Implement a Producer-Consumer Dataflow Pattern | Microsoft Docs"
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
  - "TPL dataflow library, implementing producer-consumer pattern"
  - "Task Parallel Library, dataflows"
  - "producer-consumer patterns, implementing [TPL]"
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Implement a Producer-Consumer Dataflow Pattern
In diesem Dokument wird beschrieben, wie die TPL\-Datenfluss\-Bibliothek verwendet, um ein Producer\-Consumer\-Musters zu implementieren.  Bei diesem Muster sendet der *Producer* Nachrichten an einen Nachrichtenblock, während der *Consumer* Nachrichten aus diesem Block ausliest.  
  
> [!TIP]
>  Die TPL\-Datenflussbibliothek \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\-Namespace\) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.  Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>\-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet\-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow`\-Paket.  
  
## Beispiel  
 Das folgende Beispiel zeigt ein einfaches Producer\-Consumer\-Modell Datenfluss, das verwendet.  Die `Produce`\-Methode schreibt Arrays, die zufällige Bytes Daten zu einem Objekt enthalten <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=fullName> und die `Consume`\-Methode Bytes eines <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=fullName>\-Objekt.  Wenn Sie nach den <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> und <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>\-Schnittstellen, anstatt auf ihre abgeleiteten Typen angewendet werden, können Sie wiederverwendbaren Code schreiben, der nach einer Vielzahl von Datenflussblockstypen angewendet werden kann.  Dieses Beispiel verwendet die Klasse <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>.  Da die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>\-Klasse als Quell\- sowie als Zielblock auftritt, können Producer und Consumer ein freigegebenes Objekt für Datenübertragung verwenden.  
  
 Die `Produce`\-Methode die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A>\-Methode in einer Schleife, um Daten dem Zielblock synchron zu schreiben.  Nachdem die `Produce`\-Methode alle Daten dem Zielblock schreibt, wird die Methode <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> auf, um anzugeben, dass der Block die niemals zusätzlichen Daten verfügt.  Die `Consume`\-Methode verwendet die [asynchron](../Topic/async%20\(C%23%20Reference\).md) und [Sie erwarten](../Topic/await%20\(C%23%20Reference\).md)\-Operatoren \([Asynchrone](../Topic/Async%20\(Visual%20Basic\).md) und [Rechnen Sie](../Topic/Await%20Operator%20\(Visual%20Basic\).md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) Um die Gesamtzahl von Bytes asynchron berechnet, die vom <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>\-Objekt empfangen werden.  So asynchron sich, die `Consume`\-Methode die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> methode, um eine Benachrichtigung zu empfangen, wenn die Quell\- die Daten enthält, die verfügbaren und der Quell\- nie die zusätzlichen Daten verfügt.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei, die `DataflowProducerConsumer.cs` \(`DataflowProducerConsumer.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) trägt, und dann ausgeführt wird den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## Robuste Programmierung  
 Dieses Beispiel verwendet nur einen Consumer, um die Quelldaten zu verarbeiten.  Wenn mehrere Consumer in der Anwendung befindet, verwenden Sie die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>\-Methode, um Daten vom Quellblock, wie im folgenden Beispiel dargestellt zu lesen.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 Die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>\-Methode gibt `False` zurück, wenn keine Daten verfügbar sind.  Wenn passieren, müssen Consumer auf den Quell\- gleichzeitig zugreifen, Gewährleistungen diesem Mechanismus, dass Daten nach dem Aufruf von <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> weiterhin verfügbar sind.  
  
## Siehe auch  
 [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)