---
title: 'Gewusst wie: JoinBlock zum Lesen aus mehreren Quellen verwenden'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
ms.openlocfilehash: cd2f5c65f45d83ef23643dcc747a748bb8ba89d9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290823"
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a>Gewusst wie: JoinBlock zum Lesen aus mehreren Quellen verwenden
In diesem Dokument erfahren Sie, wie Sie mithilfe der <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>-Klasse einen Vorgang ausführen, wenn Daten aus mehreren Quellen verfügbar sind. Zudem wird der nicht gierige Modus veranschaulicht, durch den mehrere Gruppierungsblöcke eine Datenquelle effizienter gemeinsam verwenden können.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden drei Ressourcentypen (`NetworkResource`, `FileResource` und `MemoryResource`) definiert und Vorgänge ausführt, sobald Ressourcen verfügbar werden. Für dieses Bespiel wird ein Paar aus `NetworkResource` und `MemoryResource` benötigt, um den ersten Vorgang auszuführen, und ein Paar aus `FileResource` und `MemoryResource`, um den zweiten Vorgang auszuführen. Damit diese Vorgänge ausgeführt werden, wenn alle erforderlichen Ressourcen verfügbar sind, wird in diesem Beispiel die <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>-Klasse verwendet. Wenn ein <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>-Objekt Daten aus allen Ressourcen empfängt, gibt es diese an das Ziel weiter, d.h. in diesem Beispiel an das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt. Beide <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>-Objekte lesen aus dem freigegebenen Pool von `MemoryResource`-Objekten.  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 Für eine effiziente Nutzung des freigegebenen Pools von `MemoryResource`-Objekten wird in diesem Beispiel ein <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions>-Objekt angegeben, für das die <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A>-Eigenschaft auf `False` festgelegt ist. Auf diese Weise werden <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>-Objekte erzeugt, die im nicht gierigen Modus agieren. Ein nicht gieriger Gruppierungsblock stellt alle eingehenden Nachrichten zurück, bis eine aus jeder Quelle verfügbar ist. Wenn eine der zurückgestellten Nachrichten durch einen anderen Block akzeptiert wurde, wird der Prozess durch den Gruppierungsblock neu gestartet. Der nicht gierige Modus bietet die Möglichkeit, dass Gruppierungsblöcke, die mindestens einen Quellblock gemeinsam nutzen, weiter abgearbeitet werden, während andere Blöcke auf Daten warten. Wenn in diesem Beispiel ein `MemoryResource`-Objekt zum `memoryResources`-Pool hinzugefügt wird, kann der erste Gruppierungsblock zum Empfangen der zweiten Datenquelle weiter ausgeführt werden. Wenn in diesem Beispiel der gierige Modus (also der Standardmodus) verwendet wird, könnte ein Gruppierungsblock das `MemoryResource`-Objekt akzeptieren und warten, bis die zweite Ressource verfügbar ist. Wenn der andere Gruppierungsblock jedoch seine zweite Datenquelle zur Verfügung hat, kann er keinen Fortschritt machen, da das `MemoryResource`-Objekt vom anderen Gruppierungsblock akzeptiert wurde.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Verwendung von nicht gierigen Gruppierungen kann Ihnen auch dabei helfen, einen Deadlock in Ihrer Anwendung zu vermeiden. In einer Softwareanwendung kommt es zu einem *Deadlock*, wenn zwei oder mehr Prozesse jeweils eine Ressource halten und gegenseitig darauf warten, dass ein anderer Prozess eine andere Ressource freigibt. Betrachten Sie eine Anwendung, die zwei <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>-Objekte definiert. Beide Objekte lesen jeweils Daten aus zwei gemeinsam genutzten Quellblöcken. Wenn ein Gruppierungsblock im gierigen Modus aus der ersten Quelle und der zweite Gruppierungsblock aus der zweiten Quelle liest, könnte die Anwendung blockieren, weil beide Gruppierungsblöcke gegenseitig darauf warten, dass der andere seine Ressource freigibt. Im nicht gierigen Modus liest jeder Gruppierungsblock nur dann aus seinen Quellen, wenn alle Daten verfügbar sind und somit das Risiko eines Deadlocks ausgeschlossen ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Dataflow (Datenfluss)](dataflow-task-parallel-library.md)
