---
title: 'Gewusst wie: Implementieren eines Producer-Consumer-Musters'
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
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1aba08e8364d8a21f70ab480d58041115a4849e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>Gewusst wie: Implementieren eines Producer-Consumer-Musters
Dieses Dokument beschreibt, wie die TPL-Datenflussbibliothek verwendet wird, um ein Producer-Consumer-Muster zu implementieren. Bei diesem Muster sendet der *Producer* Nachrichten an einen Nachrichtenblock, während der *Consumer* Nachrichten aus diesem Block ausliest.  
  
> [!TIP]
>  Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten. Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein grundlegendes Producer-Consumer-Modell, das Datenfluss verwendet. Die `Produce` Methode schreibt Arrays, zufälligen Bytes der Daten enthalten, ein <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> Objekt und die `Consume` Methode liest Bytes aus einer <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> Objekt. Ebenenfunktion auf die <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> und <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> Schnittstellen und keine deren abgeleiteten Typen können wieder verwendbaren Code schreiben, der fungieren kann auf einer Vielzahl von datenflussblocktypen. Dieses Beispiel verwendet die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> Klasse. Da die <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> blockieren-Klasse fungiert als Quelle und als Zielblock, der Producer und Consumer können ein freigegebenes Objekt zum Übertragen von Daten.  
  
 Die `Produce` Methodenaufrufe der <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> Methode in einer Schleife, um die Daten synchron an den Zielblock zu schreiben. Nach der `Produce` Methode schreibt alle Daten auf den Zielblock, ruft er die <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> Methode, um anzugeben, dass der Block keine zusätzliche Daten verfügbar muss. Die `Consume` -Methode verwendet die [Async](~/docs/csharp/language-reference/keywords/async.md) und ["await"](~/docs/csharp/language-reference/keywords/await.md) Operatoren ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) und ["await"](~/docs/visual-basic/language-reference/operators/await-operator.md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), Die Gesamtanzahl der Bytes, die von empfangen werden asynchron zu berechnen der <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> Objekt. Asynchron, fungieren die `Consume` Methodenaufrufe der <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> Methode, um eine Benachrichtigung erhalten, wenn der Quellblock hat Daten verfügbar sind und wenn Quellblock nie zusätzliche Daten zur Verfügung haben.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 In diesem Beispiel wird nur ein Consumer verwendet, um die Quelldaten zu verarbeiten. Wenn Sie mehrere Consumer in Ihrer Anwendung verfügen, verwenden die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> Methode zum Lesen von Daten aus dem Quellblock, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 Die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> -Methode zurückkehrt `False` Wenn keine Daten verfügbar ist. Wenn mehrere Consumer Quellblock gleichzeitig zugreifen müssen, dieser Mechanismus gewährleistet ist, dass Daten immer noch verfügbar, nach dem Aufruf von sind <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
