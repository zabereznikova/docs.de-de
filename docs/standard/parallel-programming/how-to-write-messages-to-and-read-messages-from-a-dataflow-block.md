---
title: 'Gewusst wie: Meldungen in einen Datenflussblock schreiben und Meldungen daraus lesen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
ms.openlocfilehash: 917892e16a3517800953437f2fce877a57a64575
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290706"
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a>Gewusst wie: Meldungen in einen Datenflussblock schreiben und Meldungen daraus lesen
In diesem Dokument wird beschrieben, wie die TPL-Datenflussbibliothek verwendet wird, um Nachrichten in einen Datenflussblock zu schreiben und aus einem Datenflussblock zu lesen. Die TPL-Datenflussbibliothek bietet synchrone und asynchrone Methoden zum Schreiben von Nachrichten an einen Datenflussblock und zum Lesen von Nachrichten aus einem Datenflussblock. In diesem Dokument wird die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType>-Klasse verwendet. Die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Klasse puffert Nachrichten und fungiert als Nachrichtenquelle und als Nachrichtenziel.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a>Synchrones Schreiben in einen und Lesen aus einem Datenflussblock  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A>-Methode zum Schreiben in einen <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Datenflussblock und die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>-Methode zum Lesen aus demselben Objekt verwendet.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 Sie können auch die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>-Methode zum Lesen aus einem Datenflussblock einsetzen, wie im folgenden Beispiel gezeigt. Der aktuelle Thread wird von der <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>-Methode nicht blockiert, und sie ist nützlich, wenn Sie gelegentlich Daten abrufen.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Da die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A>-Methode synchron arbeitet, erhält das <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Objekt in den vorherigen Beispielen alle Daten, bevor in der zweiten Schleife Daten gelesen werden. Im folgenden Beispiel wird das erste Beispiel erweitert, indem <xref:System.Threading.Tasks.Parallel.Invoke%2A> verwendet wird, um gleichzeitig aus dem Nachrichtenblock zu lesen und in ihn zu schreiben. Da durch <xref:System.Threading.Tasks.Parallel.Invoke%2A> Aktionen gleichzeitig ausgeführt werden, werden die Werte nicht in einer bestimmten Reihenfolge in das <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Objekt geschrieben.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a>Asynchrones Schreiben in einen und Lesen aus einem Datenflussblock  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A>-Methode zum asynchronen Schreiben in ein <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Objekt und die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A>-Methode zum asynchronen Lesen aus demselben Objekt verwendet. Dieses Beispiel verwendet die Operatoren [async](../../csharp/language-reference/keywords/async.md) und [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) und [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic) für asynchrones Senden von Daten an und Lesen von Daten aus dem Zielblock. Die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A>-Methode ist nützlich, wenn Sie einem Datenflussblock ermöglichen müssen, Nachrichten zurückzustellen. Die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A>-Methode ist nützlich, wenn Sie Daten verarbeiten möchten, sobald diese verfügbar sind. Weitere Informationen, wie Nachrichten zwischen Nachrichtenblöcken weitergegeben werden, finden Sie im Abschnitt über die Nachrichtenübergabe in [Datenfluss](dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel enthält den vollständigen Code für dieses Dokument.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="next-steps"></a>Nächste Schritte  
 In diesem Beispiel wird veranschaulicht, wie direkt aus einem Nachrichtenblock gelesen und in ihn geschrieben wird. Sie können Datenflussblöcke auch so verbinden, dass sie *Pipelines* (lineare Sequenzen von Datenflussblöcken) oder *Netzwerke* (Diagramme von Datenflussblöcken) bilden. In einer Pipeline oder einem Netzwerk geben Quellen asynchron Daten an Ziele weiter, sobald diese Daten verfügbar werden. Ein Beispiel für die Erstellung einer einfachen Datenflusspipeline finden Sie unter [Walkthrough: Creating a Dataflow Pipeline (Exemplarische Vorgehensweise: Erstellen einer Datenflusspipeline)](walkthrough-creating-a-dataflow-pipeline.md). Ein Beispiel für die Erstellung eines komplexeren Datenflussnetzwerks finden Sie unter [Walkthrough: Using Dataflow in a Windows Forms Application (Exemplarische Vorgehensweise: Datenfluss in einer Windows Forms-Anwendung verwenden)](walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Dataflow (Datenfluss)](dataflow-task-parallel-library.md)
