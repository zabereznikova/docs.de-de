---
title: 'Gewusst wie: Implementieren eines Producer-Consumer-Musters'
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e47355ceebaa00a8a688dc56bfd9e647da79ded2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>Gewusst wie: Implementieren eines Producer-Consumer-Musters
Dieses Dokument beschreibt, wie die TPL-Datenflussbibliothek verwendet wird, um ein Producer-Consumer-Muster zu implementieren. Bei diesem Muster sendet der *Producer* Nachrichten an einen Nachrichtenblock, während der *Consumer* Nachrichten aus diesem Block ausliest.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein grundlegendes Producer-Consumer-Modell, das Datenfluss verwendet. Die `Produce`-Methode schreibt Arrays, die zufällige Datenbytes enthalten, in ein <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType>-Objekt, und die `Consume`-Methode liest Bytes aus einem <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>-Objekt. Da Sie sich mit den Schnittstellen <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> und <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> befassen, anstatt mit ihren abgeleiteten Typen, können Sie wiederverwendbaren Code schreiben und diesen auf eine Vielzahl von Datenflussblock-Typen anwenden. In diesem Beispiel wird die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Klasse verwendet. Da die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>-Klasse sowohl als Quell- als auch als Zielblock fungiert, können der Producer und der Consumer ein freigegebenes Objekt zum Übertragen von Daten verwenden.  
  
 Die `Produce`-Methode ruft die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A>-Methode in einer Schleife auf, um die Daten synchron in den Zielblock zu schreiben. Nachdem die `Produce`-Methode alle Daten in den Zielblock geschrieben hat, ruft sie die <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A>-Methode auf, um anzugeben, dass der Block niemals über zusätzliche Daten verfügen wird. Die `Consume`-Methode verwendet die Operatoren [async](~/docs/csharp/language-reference/keywords/async.md) und [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) und [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic) zur asynchronen Berechnung der Gesamtzahl von Bytes, die vom <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>-Objekt empfangen werden. Für die Asynchronität ruft die `Consume`-Methode die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>-Methode auf, um eine Benachrichtigung zu erhalten, wenn der Quellblock über Daten verfügt und wenn dem Quellblock niemals zusätzliche Daten zur Verfügung stehen werden.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei namens `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` für Visual Basic) ein, und führen Sie dann den folgenden Befehl in einem Eingabeaufforderungsfenster von Visual Studio aus:  
  
 Visual C#  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 Visual Basic  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 In diesem Beispiel wird nur ein Consumer verwendet, um die Quelldaten zu verarbeiten. Wenn Sie in Ihrer Anwendung über mehrere Consumer verfügen, verwenden Sie die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>-Methode, um wie im folgenden Beispiel Daten aus dem Quellblock zu lesen.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 Die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>-Methode gibt `False` zurück, wenn keine Daten verfügbar sind. Wenn mehrere Consumer gleichzeitig auf den Quellblock zugreifen müssen, gewährleistet dieser Mechanismus, dass Daten nach dem Aufruf von <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> weiterhin verfügbar sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
