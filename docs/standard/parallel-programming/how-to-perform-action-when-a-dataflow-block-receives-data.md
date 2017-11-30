---
title: "Gewusst wie: Eine Aktion ausführen, wenn ein Datenflussblock Daten empfängt"
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
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d049d20f5e685096a72857cd18a89688633883c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a>Gewusst wie: Eine Aktion ausführen, wenn ein Datenflussblock Daten empfängt
*Ausführungsdatenflussblock*-Typen rufen einen vom Benutzer bereitgestellten Delegaten auf, wenn sie Daten empfangen. Die <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, und <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> Klassen sind ausführungsdatenflussblocktypen. Können Sie die `delegate` Schlüsselwort (`Sub` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), <xref:System.Action%601>, <xref:System.Func%602>, oder einen Lambda-Ausdruck, wenn Sie eine Arbeitsfunktion so ein ausführungsdatenflussblock bereitstellen. Dieses Dokument beschreibt, wie <xref:System.Func%602> und Lambda-Ausdrücke zum Ausführen der Aktion in ausführungsblöcke.  
  
> [!TIP]
>  Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten. Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Datenfluss verwendet, um eine Datei von einem Datenträger zu lesen und die Anzahl der Bytes in dieser Datei zu berechnen, die gleich 0 sind. Er verwendet <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> zum Lesen der Datei, und berechnen Sie die Anzahl von 0 (null) Bytes und <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> die Anzahl von NULL Bytes auf der Konsole ausgegeben. Die <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> Objekt gibt an, eine <xref:System.Func%602> -Objekt, Arbeitsvorgänge auszuführen, wenn die Blöcke Daten empfangen. Die <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> Objekt verwendet einen Lambda-Ausdruck, um die Anzahl von 0 (null) Bytes, die gelesen werden, an die Konsole zu drucken.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Obwohl Sie einen Lambda-Ausdruck auf bereitstellen, können eine <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> -Objekt, in diesem Beispiel verwendet <xref:System.Func%602> mit anderen Code verwenden, kann die `CountBytes` Methode. Die <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> Objekt verwendet einen Lambda-Ausdruck aus, da die Arbeit ausgeführt werden, bezieht sich auf diese Aufgabe und wahrscheinlich nicht von anderem Code hilfreich sein. Weitere Informationen zur Funktionsweise von Lambda-Ausdrücken in der Task Parallel Library finden Sie unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 Im Abschnitt Zusammenfassung von delegieren Typen in der [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) Dokument enthält eine Zusammenfassung der Delegattypen, die Sie bereitstellen können <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, und <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> Objekte. In der Tabelle wird auch angegeben, ob der Delegattyp synchron oder asynchron arbeitet.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DataflowExecutionBlocks.cs` (`DataflowExecutionBlocks.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Dieses Beispiel enthält einen Delegaten vom Typ <xref:System.Func%602> auf die <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> Objekt, das die Aufgabe von der Datenflussblock synchron auszuführen. Um den Datenflussblock über asynchron Verhalten zu aktivieren, geben Sie einen Delegaten vom Typ <xref:System.Func%601> an den Datenflussblock. Wenn ein Datenflussblock asynchron verhält, ist die Aufgabe, die den Datenflussblock über vollständige nur, wenn das zurückgegebene <xref:System.Threading.Tasks.Task%601> -Objekt abgeschlossen ist. Das folgende Beispiel ändert die `CountBytes`-Methode und verwendet die Operatoren [async](~/docs/csharp/language-reference/keywords/async.md) und [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) und [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), um asynchron die Gesamtzahl der Bytes in der bereitgestellten Datei zu berechnen, die 0 (null) sind. Die <xref:System.IO.FileStream.ReadAsync%2A> Methode Datei Lesevorgänge ist asynchron.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 Sie können auch asynchrone Lambda-Ausdrücke verwenden, um eine Aktion in einem Ausführungsdatenflussblock auszuführen. Im folgende Beispiel ändert die <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> -Objekt, das im vorherigen Beispiel verwendet wird, sodass einen Lambda-Ausdruck verwendet, die Aufgaben asynchron auszuführen.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
