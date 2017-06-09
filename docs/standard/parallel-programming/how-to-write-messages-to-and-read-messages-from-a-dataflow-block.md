---
title: "How to: Write Messages to and Read Messages from a Dataflow Block | Microsoft Docs"
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
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, reading and writing messages"
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Write Messages to and Read Messages from a Dataflow Block
In diesem Dokument wird beschrieben, wie die TPL\-Datenfluss\-Bibliothek verwendet, um Nachrichten an und wird von einem Datenflussblock zu schreiben.  Die TPL\-Datenfluss\-Bibliothek stellt die synchronen und asynchronen Methoden zum Schreiben von Meldungen zu und Lesen von Meldungen aus einem Datenflussblock bereit.  In diesem Dokument wird die Klasse <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=fullName>.  Die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>\-Klasse puffert Meldungen und verhält sich als Meldungsquelle und als Meldungsziel.  
  
> [!TIP]
>  Die TPL\-Datenflussbibliothek \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\-Namespace\) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.  Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>\-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet\-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow`\-Paket.  
  
## Schreiben in und Lesen einer Datenfluss\-Block synchron  
 Im folgenden Beispiel verwendet die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A>\-Methode, um zu einem <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> Datenflussblock und der <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>\-Methode das Lesen aus dem gleichen Objekt zu schreiben.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 Sie können die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>\-Methode auch verwenden, um von einem Datenflussblock, wie im folgenden Beispiel dargestellt zu lesen.  Die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>\-Methode blockiert nicht den aktuellen Thread und ist hilfreich, wenn Sie gelegentlich für Daten abrufen.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Da die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A>\-Methode synchron ausführt, empfängt das <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>\-Objekt in den vorherigen Beispielen alle Daten, bevor die zweite Schleife Daten liest.  Im folgenden Beispiel erweitert das erste Beispiel, indem es <xref:System.Threading.Tasks.Parallel.Invoke%2A> verwendet, um aus dem gelesen und an den Nachrichtenblock gleichzeitig zu schreiben.  Da Aktionen <xref:System.Threading.Tasks.Parallel.Invoke%2A> gleichzeitig ausführt, werden die Werte nicht an <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>\-Objekt in einer bestimmten Reihenfolge geschrieben.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## Schreiben in und Lesen einer Datenfluss\-Block asynchron  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> methode, um ein Objekt und die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> methode lesenden desselben asynchron asynchron zu schreiben <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>\-Objekt.  Dieses Beispiel verwendet die unter [asynchron](../Topic/async%20\(C%23%20Reference\).md) und [Sie erwarten](../Topic/await%20\(C%23%20Reference\).md)\-Operatoren \([Asynchrone](../Topic/Async%20\(Visual%20Basic\).md) und [Rechnen Sie](../Topic/Await%20Operator%20\(Visual%20Basic\).md) in Visual Basic\) können Daten an und statt vom Zielblock asynchron zu senden.  Die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> methode ist hilfreich, wenn Sie einen Datenflussblock aktivieren müssen, um Nachrichten zu verschieben.  Die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> methode ist hilfreich, wenn Sie auf Daten angewendet werden möchten, wann diese Daten verfügbar werden.  Weitere Informationen dazu, wie Nachrichten mithilfe Meldungsblöcken weitergeben, finden Sie im Abschnitt Meldungsübergabe in [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## Ein vollständiges Beispiel  
 Das folgende Beispiel enthält den vollständigen Code für dieses Dokument.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei, die `DataflowReadWrite.cs` \(`DataflowReadWrite.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) trägt, und dann ausgeführt wird den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**  
  
## Nächste Schritte  
 Dieses Beispiel zeigt, wie aus liest und an einen Nachrichtenblock direkt schreibt.  Sie können Datenflussblöcke an Formularpipelines, die lineare Sequenzen von Datenflussblöcken sind, oder *Netzwerken* herstellen, die Diagramme aus Datenflussblöcken sind.  In einer Pipeline oder einem Netzwerk geben Quellen asynchron Daten an Ziele weiter, sobald diese Daten verfügbar werden.  Ein Beispiel für die Erstellung einer Basistextur Datenflusspipeline, finden Sie unter [Walkthrough: Creating a Dataflow Pipeline](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md).  Ein Beispiel erstellt das ein komplexeres Datenflussnetzwerk, finden Sie unter [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## Siehe auch  
 [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)