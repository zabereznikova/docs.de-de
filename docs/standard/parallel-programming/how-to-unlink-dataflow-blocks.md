---
title: "Gewusst wie: Verknüpfungen für Datenflussblöcke aufheben"
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
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41f1b83fab6ff44e69ac2f010f70e6e254341f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-unlink-dataflow-blocks"></a>Gewusst wie: Verknüpfungen für Datenflussblöcke aufheben
Dieses Dokument beschreibt, wie Verknüpfung zwischen einen Datenfluss Zielblock und der zugehörigen Quelle aufgelöst wird.  
  
> [!TIP]
>  Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten. Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt drei <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> Objekte, die jeweils die Aufrufe der `TrySolution` Methode, um einen Wert zu berechnen. Dieses Beispiel benötigen Sie nur das Ergebnis aus dem ersten Aufruf `TrySolution` um den Vorgang abzuschließen.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Empfangen Sie den Wert aus dem ersten <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> Objekt, das abgeschlossen ist, in diesem Beispiel definiert die `ReceiveFromAny(T)` Methode. Die `ReceiveFromAny(T)` Methode nimmt ein Array aus <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> Objekte und verknüpft Sie jedes dieser Objekte zu einer <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> Objekt. Bei Verwendung der <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> verknüpft einen quelldatenflussblock mit einem Zielblock, der die Quelle Nachrichten an das Ziel weitergegeben, sobald Daten verfügbar werden. Da die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> Klasse akzeptiert nur die erste Nachricht, die sie bereitgestellt werden, die `ReceiveFromAny(T)` Methode erzeugt das Ergebnis durch Aufrufen der <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> Methode. Die erste Nachricht, die angeboten wird hierdurch die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> Objekt. Der <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> Methode verfügt über eine überladene Version, die akzeptiert eine <xref:System.Boolean> Parameter `unlinkAfterOne` , wenn er auf festgelegt ist `True`, weist den Quellblock an das Ziel aufheben, nachdem das Ziel eine Nachricht aus der Quelle empfangen hat. Es ist wichtig für die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> -Objekt, dessen Quellen aufheben können, da die Beziehung zwischen dem Array von Quellen und die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> Objekt ist nicht mehr erforderlich ist, nach der <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> -Objekt eine Nachricht empfängt.  
  
 So aktivieren Sie die übrigen Aufrufe `TrySolution` , endet, wenn eine von ihnen einen Wert berechnet die `TrySolution` -Methode übernimmt ein <xref:System.Threading.CancellationToken> -Objekt, das nach dem Aufruf von abgebrochen wird `ReceiveFromAny(T)` zurückgegeben. Die <xref:System.Threading.SpinWait.SpinUntil%2A> Methode gibt zurück, wenn dies <xref:System.Threading.CancellationToken> -Objekt abgebrochen wird.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
