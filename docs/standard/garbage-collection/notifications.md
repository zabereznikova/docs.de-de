---
title: Garbage Collection-Benachrichtigungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
ms.openlocfilehash: d5646c4969c95350ab4cd63b16f6f99ffba3a4ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131533"
---
# <a name="garbage-collection-notifications"></a>Garbage Collection-Benachrichtigungen
Es gibt Situationen, in denen eine vollständige Garbage Collection (d.h. eine Garbage Collection der Generation 2) der Common Language Runtime die Leistung beeinträchtigen kann. Dies kann vor allem bei Servern, die eine hohe Zahl an Anforderungen verarbeiten, ein Problem sein; in diesem Fall kann eine lange Garbage Collection einen Anforderungstimeout verursachen. Um eine vollständige Garbage Collection im Rahmen eines kritischen Zeitraums zu verhindern, können Sie benachrichtigt werden, wenn eine vollständige Garbage Collection bevorsteht, und Maßnahmen ergreifen, um die Workload auf eine andere Serverinstanz umzuleiten. Sie können auch selbst eine Garbage Collection auslösen, vorausgesetzt, dass die aktuelle Serverinstanz keine Anforderungen verarbeiten muss.  
  
 Die <xref:System.GC.RegisterForFullGCNotification%2A>-Methode registriert, dass eine Benachrichtigung ausgelöst werden soll, wenn die Runtime erkennt, dass eine vollständige Garbage Collection ansteht. Diese Benachrichtigung besteht aus zwei Teilen: Der eine Teil wird gesendet, wenn die vollständige Garbage Collection ansteht, und der andere Teil, wenn die vollständige Garbage Collection abgeschlossen wurde.  
  
> [!WARNING]
> Nur blockierende Garbage Collections lösen Benachrichtigungen aus. Wenn das [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)-Konfigurationselement aktiviert ist, lösen Garbage Collections im Hintergrund keine Benachrichtigungen aus.  
  
 Um zu bestimmen, wann eine Benachrichtigung ausgelöst wurde, verwenden Sie die <xref:System.GC.WaitForFullGCApproach%2A>- und <xref:System.GC.WaitForFullGCComplete%2A>-Methode. In der Regel verwenden Sie diese Methoden in einer `while`-Schleife, um fortlaufend eine <xref:System.GCNotificationStatus>-Enumeration abzurufen, die den Status der Benachrichtigung anzeigt. Wenn dieser Wert <xref:System.GCNotificationStatus.Succeeded> ist, können Sie Folgendes tun:  
  
- Als Antwort auf eine mit der <xref:System.GC.WaitForFullGCApproach%2A>-Methode erhaltene Benachrichtigung können Sie die Workload umleiten und möglicherweise selbst eine Garbage Collection auslösen.  
  
- Als Antwort auf eine mit der <xref:System.GC.WaitForFullGCComplete%2A>-Methode erhaltene Benachrichtigung können Sie die aktuelle Serverinstanz erneut zur Verarbeitung von Anforderungen verfügbar machen. Sie können auch Informationen sammeln. Beispielsweise können Sie mit der <xref:System.GC.CollectionCount%2A>-Methode die Anzahl der Sammlungen erfassen.  
  
 Die <xref:System.GC.WaitForFullGCApproach%2A>- und <xref:System.GC.WaitForFullGCComplete%2A>-Methode sind für die Zusammenarbeit konzipiert. Die Verwendung der einen ohne die andere kann zu unvorhersehbaren Ergebnissen führen.  
  
## <a name="full-garbage-collection"></a>Vollständige Garbage Collection  
 Die Runtime löst eine vollständige Garbage Collection aus, wenn eines der folgenden Szenarien zutrifft:  
  
- Genügend Arbeitsspeicher wurde in Generation 2 heraufgestuft, um die nächste Generation 2-Garbage Collection auszulösen.  
  
- Genügend Arbeitsspeicher wurde in den großen Objektheap heraufgestuft, um die nächste Generation 2-Garbage Collection auszulösen.  
  
- Eine Generation 1-Garbage Collection wird aufgrund anderer Faktoren zu einer Generation 2-Garbage Collection eskaliert.  
  
 Die Schwellenwerte, die Sie in der <xref:System.GC.RegisterForFullGCNotification%2A>-Methode angeben, gelten für die ersten beiden Szenarien. Allerdings erhalten Sie im ersten Szenario die Benachrichtigung nicht immer genau dann, wenn die von Ihnen angegebenen Schwellenwerte auftreten. Dafür gibt es zwei Gründe:  
  
- Die Runtime überprüft (leistungsbedingt) nicht jede kleine Objektzuordnung.  
  
- Nur Generation 1-Garbage Collections stufen Arbeitsspeicher in Generation 2 herauf.  
  
 Das dritte Szenario trägt auch zur Ungewissheit bei, wann Sie die Benachrichtigung erhalten. Obwohl dies keine Garantie ist, ist es eine gute Möglichkeit, die Auswirkungen einer ungünstigen vollständigen Garbage Collection zu verringern, indem Sie die Anforderungen während dieser Zeit umleiten oder die Garbage Collection zu einem günstigeren Zeitpunkt selbst auslösen.  
  
## <a name="notification-threshold-parameters"></a>Schwellenwertparameter für die Benachrichtigung  
 Die <xref:System.GC.RegisterForFullGCNotification%2A>-Methode verfügt über zwei Parameter zur Angabe der Schwellenwerte der Objekte der Generation 2 und des großen Objektheaps. Wenn diese Werte erfüllt sind, sollte eine Garbage Collection-Benachrichtigung ausgelöst werden. In der folgenden Tabelle werden diese Parameter beschrieben.  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Eine Zahl zwischen 1 und 99, die auf der Grundlage der in Generation 2 heraufgestuften Objekte angibt, wann die Benachrichtigung ausgelöst werden soll.|  
|`largeObjectHeapThreshold`|Eine Zahl zwischen 1 und 99, die auf der Grundlage der dem großen Objektheap zugeordneten Objekte angibt, wann die Benachrichtigung ausgelöst werden soll.|  
  
 Wenn Sie einen zu hohen Wert angeben, besteht eine hohe Wahrscheinlichkeit, dass Sie eine Benachrichtigung erhalten, aber die Wartezeit vor dem Auslösen der Garbage Collection durch die Runtime könnte zu lang sein. Wenn Sie eine Garbage Collection selbst auslösen, können Sie vielleicht mehr Objekte freigegeben, als wenn die Runtime die Garbage Collection auslösen würde.  
  
 Wenn Sie einen zu niedrigen Wert angeben, könnte die Runtime die Garbage Collection auslösen, bevor Sie benachrichtigt werden können.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>BESCHREIBUNG  
 Im folgenden Beispiel verarbeitet eine Gruppe von Servern eingehende Webanforderungen. Um die Workload der Verarbeitung von Anforderungen zu simulieren, werden Bytearrays einer <xref:System.Collections.Generic.List%601>-Sammlung hinzugefügt. Jeder Server wird für eine Garbage Collection-Benachrichtigung registriert und startet dann einen Thread auf der `WaitForFullGCProc`-Benutzermethode, um kontinuierlich die <xref:System.GCNotificationStatus> -Enumeration zu überwachen, die von der <xref:System.GC.WaitForFullGCApproach%2A>- und <xref:System.GC.WaitForFullGCComplete%2A>-Methode zurückgegeben wird.  
  
 Die <xref:System.GC.WaitForFullGCApproach%2A>- und <xref:System.GC.WaitForFullGCComplete%2A>-Methode rufen ihre jeweiligen Benutzermethoden zur Ereignisbehandlung auf, wenn eine Benachrichtigung ausgelöst wird:  
  
- `OnFullGCApproachNotify`  
  
     Diese Methode ruft die `RedirectRequests`-Benutzermethode auf, die den Server, der Anforderungen in die Warteschlange setzt, anweist, das Senden von Anforderungen an den Server anzuhalten. Dies wird durch Festlegen der Variablen auf Klassenebene `bAllocate` auf `false` simuliert, sodass keine weiteren Objekte zugewiesen werden.  
  
     Als Nächstes wird die `FinishExistingRequests`-Benutzermethode aufgerufen, um die Verarbeitung der ausstehenden Serveranforderungen zu beenden. Dies wird durch Löschen der <xref:System.Collections.Generic.List%601>-Sammlung simuliert.  
  
     Zum Schluss wird eine Garbage Collection ausgelöst, da die Arbeitslast gering ist.  
  
- `OnFullGCCompleteNotify`  
  
     Diese Methode ruft die Benutzermethode `AcceptRequests` auf, um das Akzeptieren von Anforderungen fortzusetzen, da der Server nicht mehr für eine vollständige Garbage Collection anfällig ist. Diese Aktion wird durch Festlegung der `bAllocate`-Variablen auf `true` simuliert, sodass das Hinzufügen von Objekten zur <xref:System.Collections.Generic.List%601>-Sammlung fortgesetzt werden kann.  
  
 Der folgende Code enthält die `Main`-Methode des Beispiels.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 Der folgende Code enthält die `WaitForFullGCProc`-Benutzermethode, die eine kontinuierliche while-Schleife zum Überprüfen auf Garbage Collection-Benachrichtigungen enthält.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 Der folgende Code enthält die `OnFullGCApproachNotify`-Methode gemäß Aufruf durch die  
  
 `WaitForFullGCProc` -Methode.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 Der folgende Code enthält die `OnFullGCApproachComplete`-Methode gemäß Aufruf durch die  
  
 `WaitForFullGCProc` -Methode.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 Der folgende Code enthält die Benutzermethoden, die durch die `OnFullGCApproachNotify`- und `OnFullGCCompleteNotify`-Methode aufgerufen werden. Die Benutzermethoden leiten Anforderungen um, schließen vorhandene Anforderungen ab und setzen dann Anforderungen fort, nachdem eine vollständige Garbage Collection aufgetreten ist.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 Das gesamte Codebeispiel lautet wie folgt:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
