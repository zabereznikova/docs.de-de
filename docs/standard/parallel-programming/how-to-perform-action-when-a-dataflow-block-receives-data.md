---
title: 'Gewusst wie: Eine Aktion ausführen, wenn ein Datenflussblock Daten empfängt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
ms.openlocfilehash: 3a709e40908afcbd1a228aab00fe36be43097826
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825727"
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a>Gewusst wie: Eine Aktion ausführen, wenn ein Datenflussblock Daten empfängt
*Ausführungsdatenflussblock*-Typen rufen einen vom Benutzer bereitgestellten Delegaten auf, wenn sie Daten empfangen. Die Klassen <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> sind Typen von Ausführungsdatenflussblöcken. Sie können das Schlüsselwort `delegate` (`Sub` in Visual Basic), <xref:System.Action%601>, <xref:System.Func%602> oder einen Lambdaausdruck verwenden, wenn Sie eine Arbeitsfunktion für einen Ausführungsdatenflussblock bereitstellen. In diesem Dokument wird beschrieben, wie <xref:System.Func%602> und Lambdaausdrücke verwendet werden, um Aktionen in Ausführungsblöcken auszuführen.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Datenfluss verwendet, um eine Datei von einem Datenträger zu lesen und die Anzahl der Bytes in dieser Datei zu berechnen, die gleich 0 sind. Zum Lesen der Datei und berechnen der Anzahl von 0 (null) Bytes wird <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> verwendet, und <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> dient dazu, die Anzahl von 0 Bytes auf der Konsole auszugegeben. Das <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>-Objekt legt ein <xref:System.Func%602>-Objekt fest, um Arbeitsvorgänge auszuführen, wenn die Blöcke Daten empfangen. Das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt gibt mithilfe eines Lambdaausdrucks die Anzahl der gelesenen 0 Bytes auf der Konsole aus.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Obwohl Sie für ein <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>-Objekt einen Lambdaausdruck bereitstellen können, wird in diesem Beispiel <xref:System.Func%602> verwendet, damit anderer Code die `CountBytes`-Methode anwenden kann. Das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt verwendet einen Lambdaausdruck, da die auszuführende Arbeit für diesen Task spezifisch und mit anderem Code wahrscheinlich nicht hilfreich ist. Weitere Informationen zur Funktionsweise von Lambda-Ausdrücken in der Task Parallel Library finden Sie unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](lambda-expressions-in-plinq-and-tpl.md).  
  
 Der Abschnitt mit der Übersicht über die Delegattypen im Dokument [Datenfluss](dataflow-task-parallel-library.md) fasst die Delegattypen zusammen, die Sie für die Objekte <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> und <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> zur Verfügung stellen können. In der Tabelle wird auch angegeben, ob der Delegattyp synchron oder asynchron arbeitet.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Dieses Beispiel enthält einen Delegaten vom Typ <xref:System.Func%602> für das <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>-Objekt, um den Task des Datenflussblocks synchron auszuführen. Damit das asynchrone Verhalten des Datenflussblocks aktiviert wird, stellen Sie einen Delegaten vom Typ <xref:System.Func%601> für den Datenflussblock bereit. Wenn sich ein Datenflussblock asynchron verhält, ist der Task des Datenflussblocks nur dann abgeschlossen, wenn das zurückgegebene <xref:System.Threading.Tasks.Task%601>-Objekt beendet wird. Das folgende Beispiel ändert die `CountBytes`-Methode und verwendet die Operatoren [async](../../csharp/language-reference/keywords/async.md) und [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) und [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic), um die Gesamtzahl der Bytes in der bereitgestellten Datei asynchron zu berechnen, die 0 (null) sind. Die <xref:System.IO.FileStream.ReadAsync%2A>-Methode führt asynchrone Dateilesevorgänge aus.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 Sie können auch asynchrone Lambda-Ausdrücke verwenden, um eine Aktion in einem Ausführungsdatenflussblock auszuführen. Das folgende Beispiel ändert das im vorherigen Beispiel verwendete <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>-Objekt, sodass die Arbeit mithilfe eines Lambdaausdrucks asynchron ausgeführt wird.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Dataflow (Datenfluss)](dataflow-task-parallel-library.md)
