---
title: 'Gewusst wie: Meldungen in einen Datenflussblock schreiben und Meldungen daraus lesen'
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
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf609a8c350a44fc802cce0ec10693431bbf4f42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a>Gewusst wie: Meldungen in einen Datenflussblock schreiben und Meldungen daraus lesen
In diesem Dokument wird beschrieben, wie die TPL-Datenflussbibliothek verwendet wird, um Nachrichten in einen Datenflussblock zu schreiben und aus einem Datenflussblock zu lesen. Die TPL-Datenflussbibliothek bietet synchrone und asynchrone Methoden zum Schreiben von Nachrichten an einen Datenflussblock und zum Lesen von Nachrichten aus einem Datenflussblock. Dieses Dokument verwendet die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> Klasse. Die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> Klasse puffert Nachrichten und verhält sich als Nachrichtenquelle und als Ziel der Nachricht.  
  
> [!TIP]
>  Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten. Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a>Synchrones Schreiben in einen und Lesen aus einem Datenflussblock  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> Methode zum Schreiben einer <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> Datenflussblock und die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> Methode aus dem gleichen Objekt gelesen.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 Sie können auch die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> Methode zum Lesen aus einem Datenflussblock, wie im folgenden Beispiel gezeigt. Die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> Methode blockiert den aktuellen Thread nicht und ist nützlich, wenn Sie gelegentlich Daten abzurufen.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Da die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> Methode agiert synchron, die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> Objekt in den vorherigen Beispielen empfängt alle Daten, bevor die zweite Schleife Daten liest. Das folgende Beispiel erweitert das erste Beispiel mit <xref:System.Threading.Tasks.Parallel.Invoke%2A> zum Lesen und Schreiben an den Nachrichtenblock gleichzeitig. Da <xref:System.Threading.Tasks.Parallel.Invoke%2A> Aktionen gleichzeitig werden die Werte nicht geschrieben die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> Objekt in einer bestimmten Reihenfolge.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a>Asynchrones Schreiben in einen und Lesen aus einem Datenflussblock  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> Methode zum asynchronen Schreiben in eine <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> Objekt und die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> Methode asynchron aus dem gleichen Objekt gelesen. Dieses Beispiel verwendet die Operatoren [async](~/docs/csharp/language-reference/keywords/async.md) und [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) und [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic) für asynchrones Senden von Daten an und Lesen von Daten aus dem Zielblock. Die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> Methode ist nützlich, wenn einen Datenflussblock Verschieben von Nachrichten aktiviert werden müssen. Die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> Methode ist nützlich, wenn Sie möchten auf Daten angewendet werden soll, wenn diese Daten verfügbar werden. Weitere Informationen, wie Nachrichten zwischen Nachrichtenblöcken weitergegeben werden, finden Sie im Abschnitt über die Nachrichtenübergabe in [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel enthält den vollständigen Code für dieses Dokument.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DataflowReadWrite.cs` (`DataflowReadWrite.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**  
  
## <a name="next-steps"></a>Nächste Schritte  
 In diesem Beispiel wird veranschaulicht, wie direkt aus einem Nachrichtenblock gelesen und in ihn geschrieben wird. Sie können Datenflussblöcke auch so verbinden, dass sie *Pipelines* (lineare Sequenzen von Datenflussblöcken) oder *Netzwerke* (Diagramme von Datenflussblöcken) bilden. In einer Pipeline oder einem Netzwerk geben Quellen asynchron Daten an Ziele weiter, sobald diese Daten verfügbar werden. Ein Beispiel für die Erstellung einer einfachen Datenflusspipeline finden Sie unter [Walkthrough: Creating a Dataflow Pipeline (Exemplarische Vorgehensweise: Erstellen einer Datenflusspipeline)](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md). Ein Beispiel für die Erstellung eines komplexeren Datenflussnetzwerks finden Sie unter [Walkthrough: Using Dataflow in a Windows Forms Application (Exemplarische Vorgehensweise: Datenfluss in einer Windows Forms-Anwendung verwenden)](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
