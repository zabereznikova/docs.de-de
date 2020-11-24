---
title: 'Vorgehensweise: Schreiben und Lesen von Nachrichten in einem Datenflussblock'
ms.date: 09/10/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
ms.openlocfilehash: be0e78989105cc59bd041ceb8c6f31073a702f83
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820786"
---
# <a name="how-to-write-and-read-messages-from-a-dataflow-block"></a>Vorgehensweise: Schreiben und Lesen von Nachrichten in einem Datenflussblock

In diesem Artikel wird beschrieben, wie die Task Parallel Library-Datenflussbibliothek (TPL) verwendet wird, um Nachrichten in einen Datenflussblock zu schreiben und aus einem Datenflussblock zu lesen. Die TPL-Datenflussbibliothek bietet synchrone und asynchrone Methoden zum Schreiben von Nachrichten an einen Datenflussblock und zum Lesen von Nachrichten aus einem Datenflussblock. In diesem Artikel wird die Verwendung der <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType>-Klasse veranschaulicht. Die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Klasse puffert Nachrichten und fungiert sowohl als Nachrichtenquelle als auch als Nachrichtenziel.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-and-reading-synchronously"></a>Synchrones Schreiben und Lesen

Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A>-Methode zum Schreiben in einen <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Datenflussblock und die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>-Methode zum Lesen aus demselben Objekt verwendet.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="2":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="2":::

Sie können auch die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>-Methode zum Lesen aus einem Datenflussblock einsetzen, wie im folgenden Beispiel gezeigt. Der aktuelle Thread wird von der <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>-Methode nicht blockiert, und sie ist nützlich, wenn Sie gelegentlich Daten abrufen.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="3":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="3":::

Da die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A>-Methode synchron arbeitet, erhält das <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Objekt in den vorherigen Beispielen alle Daten, bevor in der zweiten Schleife Daten gelesen werden. Im folgenden Beispiel wird das erste Beispiel erweitert, indem <xref:System.Threading.Tasks.Task.WhenAll(System.Threading.Tasks.Task[])?displayProperty=nameWithType> verwendet wird, um gleichzeitig aus dem Nachrichtenblock zu lesen und in ihn zu schreiben. Da durch <xref:System.Threading.Tasks.Task.WhenAll%2A> Aktionen gleichzeitig ausgeführt werden, werden die Werte nicht in einer bestimmten Reihenfolge in das <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Objekt geschrieben.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="4":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="4":::

## <a name="writing-and-reading-asynchronously"></a>Asynchrones Schreiben und Lesen

Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A>-Methode zum asynchronen Schreiben in ein <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Objekt und die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A>-Methode zum asynchronen Lesen aus demselben Objekt verwendet. Dieses Beispiel verwendet die Operatoren [async](../../csharp/language-reference/keywords/async.md) und [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) und [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic) für asynchrones Senden von Daten an und Lesen von Daten aus dem Zielblock. Die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A>-Methode ist nützlich, wenn Sie einem Datenflussblock ermöglichen müssen, Nachrichten zurückzustellen. Die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A>-Methode ist nützlich, wenn Sie Daten verarbeiten möchten, sobald diese verfügbar sind. Weitere Informationen, wie Nachrichten zwischen Nachrichtenblöcken weitergegeben werden, finden Sie im Abschnitt über die Nachrichtenübergabe in [Datenfluss](dataflow-task-parallel-library.md).

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="5":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="5":::

## <a name="a-complete-example"></a>Vollständiges Beispiel

Das folgende Beispiel zeigt den gesamten Code für diesen Artikel.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="1":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="1":::

## <a name="next-steps"></a>Nächste Schritte

In diesem Beispiel wird veranschaulicht, wie direkt aus einem Nachrichtenblock gelesen und in ihn geschrieben wird. Sie können Datenflussblöcke auch so verbinden, dass sie *Pipelines* (lineare Sequenzen von Datenflussblöcken) oder *Netzwerke* (Diagramme von Datenflussblöcken) bilden. In einer Pipeline oder einem Netzwerk geben Quellen asynchron Daten an Ziele weiter, sobald diese Daten verfügbar werden. Ein Beispiel für die Erstellung einer einfachen Datenflusspipeline finden Sie unter [Walkthrough: Creating a Dataflow Pipeline (Exemplarische Vorgehensweise: Erstellen einer Datenflusspipeline)](walkthrough-creating-a-dataflow-pipeline.md). Ein Beispiel für die Erstellung eines komplexeren Datenflussnetzwerks finden Sie unter [Walkthrough: Using Dataflow in a Windows Forms Application (Exemplarische Vorgehensweise: Datenfluss in einer Windows Forms-Anwendung verwenden)](walkthrough-using-dataflow-in-a-windows-forms-application.md).

## <a name="see-also"></a>Weitere Informationen

- [Datenfluss (Task Parallel Library)](dataflow-task-parallel-library.md)
