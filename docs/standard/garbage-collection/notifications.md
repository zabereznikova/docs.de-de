---
title: Garbage Collection-Benachrichtigungen
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
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a>Garbage Collection-Benachrichtigungen
Es gibt Situationen, in denen eine vollständige Garbagecollection (d. h. eine Collection der Generation 2) von der common Language Runtime Leistung beeinträchtigen kann. Dies kann ein Problem vor allem mit Servern, die große Mengen von Anforderungen zu verarbeiten; In diesem Fall kann eine lange Garbagecollection einen Anforderungstimeout verursachen. Um zu verhindern, dass eine vollständige Auflistung von im Rahmen eines kritischen Zeitraums aufgetreten sind, können Sie benachrichtigt werden, dass eine vollständige Garbagecollection nähert sich dem und anschließend ergreifen, um die arbeitsauslastung mit einer anderen Serverinstanz umleiten. Sie können auch eine Sammlung selbst auslösen, vorausgesetzt, dass die aktuelle Serverinstanz keine Anforderungen zu verarbeiten muss.  
  
 Die <xref:System.GC.RegisterForFullGCNotification%2A> Methode registriert für eine Benachrichtigung ausgelöst werden, wenn die Common Language Runtime ermittelt, dass eine vollständige Garbagecollection ansteht. Es gibt zwei Komponenten für diese Benachrichtigung: Wenn die vollständige Garbagecollection ansteht und wann die vollständige Garbagecollection abgeschlossen wurde.  
  
> [!WARNING]
>  Nur blockierende Garbage Collection auslösen Benachrichtigungen. Wenn die [ \<GcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) Konfigurationselement aktiviert ist, löst die Garbage Collection im Hintergrund keine Benachrichtigungen.  
  
 Um zu bestimmen, wann eine Benachrichtigung ausgelöst wurde, verwenden die <xref:System.GC.WaitForFullGCApproach%2A> und <xref:System.GC.WaitForFullGCComplete%2A> Methoden. In der Regel verwenden Sie diese Methoden in einer `while` Schleife, um fortlaufend abzurufen eine <xref:System.GCNotificationStatus> -Enumeration, der den Status der Benachrichtigung angezeigt. Wenn dieser Wert ist <xref:System.GCNotificationStatus.Succeeded>, können Sie wie folgt vorgehen:  
  
-   Als Antwort auf eine Benachrichtigung erhalten, mit der <xref:System.GC.WaitForFullGCApproach%2A> -Methode, können Sie die arbeitsauslastung umleiten und möglicherweise eine Collection selbst auslösen.  
  
-   Als Antwort auf eine Benachrichtigung erhalten, mit der <xref:System.GC.WaitForFullGCComplete%2A> -Methode, Sie können die aktuellen Serverinstanz, die zur Verarbeitung von Anforderungen erneut verfügbar machen. Sie können auch Informationen sammeln. Beispielsweise können Sie die <xref:System.GC.CollectionCount%2A> Methode, um die Anzahl der Sammlungen erfassen.  
  
 Die <xref:System.GC.WaitForFullGCApproach%2A> und <xref:System.GC.WaitForFullGCComplete%2A> Methoden sind für die Zusammenarbeit konzipiert. Mit einem anderen Zeichen ohne kann zu unbestimmte Ergebnissen führen.  
  
## <a name="full-garbage-collection"></a>Vollständige Garbagecollection  
 Die Common Language Runtime führt eine vollständige Garbagecollection dazu, dass eine der folgenden Szenarien zutrifft:  
  
-   Genügend Arbeitsspeicher hat in Generation 2 verursacht die nächste Collection der Generation 2 höher gestuft wurden.  
  
-   Genügend Arbeitsspeicher hat in den großen Objektheap, sodass die nächste Collection der Generation 2 höher gestuft wurden.  
  
-   Eine Auflistung der Generation 1 ist eine Auflistung der Generation 2 aufgrund anderer Faktoren eskaliert.  
  
 Die Schwellenwerte, die Sie, in angeben der <xref:System.GC.RegisterForFullGCNotification%2A> Methode anwenden, um die ersten beiden Szenarien. Allerdings im ersten Szenario erhalten nicht immer Sie die Benachrichtigung über die Zeit, die proportional zu den Ihnen angegebenen Schwellenwerte für gibt es zwei Gründe:  
  
-   Die Common Language Runtime wird jede kleine objektzuordnung (zur Verbesserung der Leistung) nicht überprüft werden.  
  
-   Nur dann höher stufen Generation 1 Sammlungen Speicher in Generation 2.  
  
 Das dritte Szenario trägt auch zur Ungewissheit wann die Benachrichtigung erhält. Obwohl dies keine Garantie dafür ist, beweist es werden eine gute Möglichkeit, die Auswirkungen einer ungünstigen vollständige Garbagecollection verringern, indem Sie die Anforderungen während dieser Zeit umleiten oder ratenbasierte die Auflistung selbst wenn es besser untergebracht werden kann.  
  
## <a name="notification-threshold-parameters"></a>Benachrichtigung Schwellenwert-Parameter  
 Die <xref:System.GC.RegisterForFullGCNotification%2A> -Methode verfügt über zwei Parameter, die Schwellenwerte der Objekte der Generation 2 und den großen Objektheap anzugeben. Wenn diese Werte erfüllt sind, sollte eine Garbage Collection-Benachrichtigung ausgelöst werden. In der folgenden Tabelle werden diese Parameter beschrieben.  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Eine Zahl zwischen 1 und 99, die angibt, wann die Benachrichtigung ausgelöst werden soll, basierend auf die Objekte in Generation 2 höher gestuft.|  
|`largeObjectHeapThreshold`|Eine Zahl zwischen 1 und 99, die angibt, wann die Benachrichtigung ausgelöst werden soll, basierend auf den Objekten, die in den großen Objektheap zugeordnet sind.|  
  
 Wenn Sie einen Wert, der zu hoch ist angeben, besteht eine hohe Wahrscheinlichkeit, dass Sie eine Benachrichtigung erhalten, aber möglicherweise zu langen Zeitraum warten, bevor die Laufzeit führt dazu, eine Auflistung dass. Wenn Sie eine Sammlung selbst auslösen, können Sie mehr Objekte als potenziell freigegeben werden würden, wenn die Laufzeit führt dazu, die Auflistung dass freigeben.  
  
 Wenn Sie einen Wert, der zu niedrig ist angeben, verursachen die Laufzeit die Auflistung vor mussten Sie ausreichend lange, um benachrichtigt zu werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel eine Gruppe von Servern-Dienst eingehende webanforderungen. Um die Arbeitslast der Verarbeitung von Anforderungen zu simulieren, Byte-Arrays hinzugefügt werden eine <xref:System.Collections.Generic.List%601> Auflistung. Jeder Server für eine Garbage Collection-Benachrichtigung registriert, und klicken Sie dann auf startet einen Thread der `WaitForFullGCProc` Benutzermethode überwachen kontinuierlich die <xref:System.GCNotificationStatus> -Enumeration, die von zurückgegeben wird die <xref:System.GC.WaitForFullGCApproach%2A> und die <xref:System.GC.WaitForFullGCComplete%2A> Methoden.  
  
 Die <xref:System.GC.WaitForFullGCApproach%2A> und <xref:System.GC.WaitForFullGCComplete%2A> Methoden aufrufen ihrer jeweiligen Benutzer Ereignisbehandlungsmethoden aus, wenn eine Benachrichtigung ausgelöst wird:  
  
-   `OnFullGCApproachNotify`  
  
     Diese Methode ruft die `RedirectRequests` Benutzermethode, den die Anforderung queuing-Server zum Senden von anhalten angewiesen wird, fordert für den Server. Dies wird durch Festlegen der Variablen auf Klassenebene simuliert `bAllocate` auf `false` so, dass keine weiteren Objekte zugewiesen werden.  
  
     Als Nächstes wird die `FinishExistingRequests` Benutzermethode wird aufgerufen, um die ausstehende Serveranfragen Verarbeitung beenden. Dadurch wird simuliert, durch Deaktivieren der <xref:System.Collections.Generic.List%601> Auflistung.  
  
     Zum Schluss wird eine Garbagecollection ausgelöst, da die Arbeitslast gering ist.  
  
-   `OnFullGCCompleteNotify`  
  
     Diese Methode ruft die Benutzermethode `AcceptRequests` Anforderungen akzeptieren, da der Server nicht mehr anfällig für eine vollständige Garbagecollection werden fortgesetzt. Dadurch wird simuliert, indem die `bAllocate` Variable `true` , damit der hinzuzufügenden Objekte fortgesetzt werden können die <xref:System.Collections.Generic.List%601> Auflistung.  
  
 Der folgende Code enthält die `Main` Methode des Beispiels.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 Der folgende Code enthält die `WaitForFullGCProc` Benutzermethode, die eine kontinuierliche while-Schleife zu suchende Garbage Collection-Benachrichtigungen enthält.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 Der folgende Code enthält die `OnFullGCApproachNotify` Methode, wie aus einem der  
  
 `WaitForFullGCProc`-Methode.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 Der folgende Code enthält die `OnFullGCApproachComplete` Methode, wie aus einem der  
  
 `WaitForFullGCProc`-Methode.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 Der folgende Code enthält die Benutzermethoden, die aufgerufen werden, aus der `OnFullGCApproachNotify` und `OnFullGCCompleteNotify` Methoden. Die Benutzermethoden an Anforderungen umgeleitet werden, vorhandene Anforderungen abgeschlossen und Anforderungen dann fortgesetzt, nachdem eine vollständige Garbagecollection aufgetreten ist.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 Das gesamte Codebeispiel lautet wie folgt:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
