---
title: 'Gewusst wie: Verknüpfungen für Datenflussblöcke aufheben'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
ms.openlocfilehash: b49cfc9730ba154202baf15093a54ba3ce0e2a8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139296"
---
# <a name="how-to-unlink-dataflow-blocks"></a>Gewusst wie: Verknüpfungen für Datenflussblöcke aufheben
In diesem Dokument erfahren Sie, wie Sie eine Verknüpfung zwischen einen Zieldatenflussblock und der zugehörigen Quelle auflösen.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden drei <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>-Objekte erstellt, die jeweils die `TrySolution`-Methode aufrufen, um einen Wert zu berechnen. In diesem Beispiel wird nur das Ergebnis vom ersten Aufruf von `TrySolution` zum Beenden benötigt.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Um den Wert aus dem ersten <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>-Objekt zu erhalten, das beendet wird, wird in diesem Beispiel die `ReceiveFromAny(T)`-Methode definiert. Die `ReceiveFromAny(T)`-Methode akzeptiert ein Array aus <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>-Objekten und verknüpft jedes dieser Objekte mit einem <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>-Objekt. Wenn Sie die <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>-Methode aufrufen, um einen Quelldatenflussblock mit einem Zieldatenflussblock zu verknüpfen, überträgt der Quelldatenflussblock Daten an den Zielblock, sobald welche verfügbar sind. Da die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>-Klasse nur die erste angebotene Nachricht akzeptiert, erzeugt die `ReceiveFromAny(T)`-Methode ihr Ergebnis durch Aufrufen der <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>-Methode. Hierdurch wird die erste Nachricht erzeugt, die dem <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>-Objekt angeboten wird. Die <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>-Methode weist eine überladene Version auf, die ein <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions>-Objekt mit der Eigenschaft <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.MaxMessages> akzeptiert, wenn diese auf `1` festgelegt ist. Durch dieses Objekt wird der Quellblock angewiesen, die Verknüpfung mit dem Ziel zu lösen, nachdem das Ziel eine Nachricht von der Quelle erhalten hat. Es ist wichtig, dass das <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>-Objekt von seinen Quellen getrennt wird, da die Beziehung zwischen dem Array der Quellen und dem <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>-Objekt nicht mehr benötigt wird, nachdem das <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>-Objekt eine Nachricht erhalten hat.  
  
 Damit die verbleibenden Aufrufe von `TrySolution` beendet werden, sobald einer einen Wert zurückgegeben hat, übernimmt die `TrySolution`-Methode ein <xref:System.Threading.CancellationToken>-Objekt, das abgebrochen wird, nachdem der Aufruf von `ReceiveFromAny(T)` zurückgegeben wurde. Die <xref:System.Threading.SpinWait.SpinUntil%2A>-Methode gibt zurück, wann dieses <xref:System.Threading.CancellationToken>-Objekt abgebrochen wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
