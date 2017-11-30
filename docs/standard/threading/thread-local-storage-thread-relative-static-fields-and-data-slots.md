---
title: 'Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39dd80d378171563f2aadadaa146278e8a417d32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots
Sie können lokale Threadspeicher (TLS) zum Speichern von Daten verwenden, die für einen Thread und die Anwendung eindeutig ist. .NET Framework bietet zwei Möglichkeiten zur Verwendung verwaltet TLS: threadbezogene statische Felder und Datenslots.  
  
-   Verwenden Sie threadbezogene statische Felder (threadbezogene `Shared` Felder in Visual Basic), wenn Sie Ihre Bedürfnisse exakt zum Zeitpunkt der Kompilierung erwarten können. Threadbezogene statische Felder bieten die beste Leistung. Außerdem können Sie die Vorteile der typüberprüfung zur Kompilierzeit.  
  
-   Verwenden Sie Datenslots aus, wenn die tatsächlichen Anforderungen nur zur Laufzeit ermittelt werden können. Datenslots sind langsamer und umständlicher als threadbezogene statische Felder verwenden, und Daten werden als Typ gespeichert <xref:System.Object>, sodass Sie es in den richtigen Typ umwandeln müssen, bevor Sie ihn verwenden.  
  
 Verwenden Sie in nicht verwalteten C++ `TlsAlloc` Slots dynamisch zuordnen und `__declspec(thread)` zu deklarieren, dass eine Variable in threadbezogene Speicher zugewiesen werden soll. Threadbezogene statische Felder und Datenslots stellen die verwaltete Version dieses Verhaltens bereit.  
  
 In der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], können Sie die <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> Klasse threadlokale Objekte zu erstellen, der verzögert initialisiert werden, wenn das Objekt zuerst genutzt wird. Weitere Informationen finden Sie unter [Verzögerte Initialisierung](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="uniqueness-of-data-in-managed-tls"></a>Eindeutigkeit der Daten im verwalteten TLS  
 Sowohl bei Verwendung von threadbezogene statische Felder oder Datenslots sind Daten in verwalteten TLS für die Kombination von Threads und eine Anwendungsdomäne eindeutig.  
  
-   Innerhalb einer Anwendungsdomäne kann nicht nur ein Thread Daten aus einem anderen Thread ändern, selbst wenn beide Threads das gleiche Feld oder Slot verwenden.  
  
-   Wenn ein Thread das gleiche Feld oder den Slot aus mehreren Anwendungsdomänen zugreift, wird in jeder Anwendungsdomäne ein separater Wert beibehalten.  
  
 Z. B. wenn ein Thread legt der Wert eines statischen Felds threadbezogene geht in einer anderen Anwendungsdomäne und ruft dann den Wert des Felds ab, der in der zweiten Anwendungsdomäne abgerufene Wert unterscheidet sich von den Wert in der ersten Anwendungsdomäne. Ein neuer Wert für das Feld in der zweiten Anwendungsdomäne festgelegt wirkt sich nicht auf den Wert des Felds in der ersten Anwendungsdomäne aus.  
  
 Wenn ein Thread die gleichen benannten Datenslot in zwei unterschiedlichen Anwendungsdomänen abruft, bleiben die Daten in der ersten Anwendungsdomäne auf ähnliche Weise, unabhängig von den Daten in der zweiten Anwendungsdomäne.  
  
## <a name="thread-relative-static-fields"></a>Threadbezogene statische Felder  
 Wenn Sie wissen, dass es sich bei ein Teil der Daten immer für eine Anwendungsdomäne Kombination aus "und" Thread eindeutig ist, gelten die <xref:System.ThreadStaticAttribute> -Attribut auf das statische Feld. Verwenden Sie das Feld wie jedes andere statische Feld verwenden. Die Daten in das Feld ist nur für jeden Thread, der verwendet wird.  
  
 Threadbezogene statische Felder Geben Sie eine bessere Leistung als Datenslots und haben den Vorteil, dass typüberprüfung zur Kompilierzeit.  
  
 Denken Sie daran, dass die Klasse Konstruktorcode auf dem ersten Thread im ersten Kontext ausgeführt wird, die auf das Feld zugreift. In allen anderen Threads oder Kontexten in der gleichen Anwendungsdomäne werden die Felder auf initialisiert `null` (`Nothing` in Visual Basic) Wenn sie Verweistypen sind, oder an Standardeinstellung Werte hat, wenn sie sind Werttypen. Aus diesem Grund sollten Sie nicht auf Klassenkonstruktoren threadbezogene statische Felder initialisieren verlassen. Stattdessen vermeiden Sie beim Initialisieren des threadbezogene statische Felder und wird davon ausgegangen, dass sie mit initialisiert werden `null` (`Nothing`) oder mit ihren Standardwerten.  
  
## <a name="data-slots"></a>Datenslots  
 .NET Framework bietet dynamische Datenslots, die eine Kombination aus Thread und Anwendungsdomäne eindeutig sind. Es gibt zwei Arten von Datenslots: benannte und nicht benannte Slots. Beide implementiert werden, mithilfe der <xref:System.LocalDataStoreSlot> Struktur.  
  
-   Um einen benannten Datenslot zu erstellen, verwenden Sie die <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> oder <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType> Methode. Um einen Verweis auf einen vorhandenen benannten Slot zu erhalten, übergeben Sie den Namen in der <xref:System.Threading.Thread.GetNamedDataSlot%2A> Methode.  
  
-   Um einen unbenannten Datenslot zu erstellen, verwenden Sie die <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType> Methode.  
  
 Verwenden Sie für benannte und Steckplätze unbenannte, die <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> Methoden festlegen und Abrufen der Informationen im Slot. Hierbei handelt es sich um statische Methoden, die immer auf die Daten für den Thread, der derzeit diese ausgeführt wird.  
  
 Benannte Slots ist besonders angenehm beim, da das Einschubfach abgerufen werden können, bei Bedarf durch übergeben den Namen in der <xref:System.Threading.Thread.GetNamedDataSlot%2A> -Methode, statt einen Verweis auf einen unbenannten Slot beizubehalten. Allerdings möglicherweise einer anderen Komponente verwendet den gleichen Namen für den Speicher threadbezogene und ein Thread führt Code aus der Komponente und die andere Komponente, die zwei Komponenten gegenseitig Daten beschädigt werden. (Dieses Szenario wird davon ausgegangen, dass beide Komponenten in der gleichen Anwendungsdomäne ausgeführt werden und sie nicht entwickelt werden, um dieselben Daten verwenden.)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ContextStaticAttribute>  
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>  
 <xref:System.ThreadStaticAttribute>  
 <xref:System.Runtime.Remoting.Messaging.CallContext>  
 [Threading](../../../docs/standard/threading/index.md)
