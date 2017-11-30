---
title: 'Gewusst wie: JoinBlock zum Lesen aus mehreren Quellen verwenden'
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
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41445e4874b94809840ecf9ebda6f27ccc955c9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a>Gewusst wie: JoinBlock zum Lesen aus mehreren Quellen verwenden
Dieses Dokument erläutert die Verwendung der <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> Klasse, um einen Vorgang auszuführen, wenn Daten aus mehreren Quellen verfügbar sind. Es wird veranschaulicht, wie nicht gierigen Modus zu verwenden, um mehrere gruppierungsblöcke eine Datenquelle effizienter gemeinsam verwenden können.  
  
> [!TIP]
>  Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten. Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert drei Ressourcentypen, `NetworkResource`, `FileResource`, und `MemoryResource`, und Vorgänge ausführt, wenn Ressourcen verfügbar werden. Dieses Beispiel benötigen Sie ein `NetworkResource` und `MemoryResource` Paar, um den ersten Vorgang auszuführen und ein `FileResource` und `MemoryResource` Paar, um den zweiten Vorgang auszuführen. Damit kann diese Vorgänge auftreten, wenn alle erforderliche Ressourcen verfügbar sind, in diesem Beispiel verwendet die <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> Klasse. Wenn eine <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> Objekt empfängt Daten aus allen Quellen, die es überträgt diese Daten an das Ziel, die in diesem Beispiel wird ein <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> Objekt. Beide <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> Objekte zu lesen, aus einem freigegebenen Pool `MemoryResource` Objekte.  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 So aktivieren Sie die effiziente Verwendung von dem freigegebenen Pool mit `MemoryResource` Objekte in diesem Beispiel wird eine <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> Objekt mit der <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> -Eigenschaft auf festgelegt `False` erstellen <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> Objekte, die im nicht gierigen Modus bearbeiten. Ein nicht gieriger Join-Block zurück alle eingehenden Nachrichten, bis eine aus der jeweiligen Quelle verfügbar ist. Wenn eine der zurückgestellten Nachrichten durch einen anderen Block akzeptiert wurden, wird der gruppierungsblock des Prozesses neu gestartet. Nicht gieriger Modus ermöglicht gruppierungsblöcke, die gemeinsam eine oder mehrere Quellblöcke Fortschritte machen, wie die anderen Blöcken auf die Daten warten. In diesem Beispiel wenn eine `MemoryResource` Objekt hinzugefügt wird die `memoryResources` pool, den ersten Join Block, um die zweite Datenquelle empfangen kann Fortschritt vornehmen. Wenn in diesem Beispiel gierigen Modus verwenden würden, also standardmäßig eine gruppierungsblock dauern die `MemoryResource` Objekt, und warten Sie, bis die zweite Ressource verfügbar wird. Jedoch, wenn der andere gruppierungsblock die zweite Datenquelle verfügt, kann nicht erleichtern Fortschritt da die `MemoryResource` Objekt von der anderen gruppierungsblock vorgenommen wurde.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Verwendung des nicht gierigen Joins hilft auch Deadlocks in der Anwendung zu vermeiden. In einer softwareanwendung *Deadlock* tritt auf, wenn mindestens zwei Prozesse jeweils über eine Ressource und warten Sie, sich gegenseitig einem anderen Prozess eine weitere Ressource freigegeben. Betrachten Sie eine Anwendung, die zwei definiert <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> Objekte. Beide Objekte Lesen von Daten aus zwei freigegebenen Quellblöcke. Im gierigen Modus Wenn ein Join-Block aus der ersten Quelle gelesen und der zweite gruppierungsblock aus der zweiten Quelle liest die Anwendung ein Deadlock auftreten kann, da beide Blöcke gegenseitig join warten, bis die andere die Ressource freigegeben. Im nicht gierigen Modus jedes Join-Block Lesevorgänge aus Quellen nur, wenn alle Daten verfügbar ist und daher das Risiko von Deadlocks wird entfernt.  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
