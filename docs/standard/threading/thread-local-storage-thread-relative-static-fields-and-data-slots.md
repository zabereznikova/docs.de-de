---
title: 'Lokaler Threadspeicher: Threadbezogene statische Felder und Datenslots'
ms.date: 03/30/2017
helpviewer_keywords:
- threading [.NET], local storage
- threading [.NET], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
ms.openlocfilehash: c9ea2939dcff321a1d4e24e7a97c056c016e5fdc
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819629"
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>Lokaler Threadspeicher: Threadbezogene statische Felder und Datenslots

Sie können verwalteten threadlokalen Speicher (TLS, Thread Local Storage) zum Speichern von Daten verwenden, die für einen Thread und eine Anwendungsdomäne eindeutig sind. .NET bietet zwei Möglichkeiten zur Verwendung von verwaltetem TLS: threadbezogene statische Felder und Datenslots.  
  
- Verwenden Sie threadbezogene statische Felder (threadbezogene `Shared`-Felder in Visual Basic), wenn Sie Ihre Anforderungen zum Zeitpunkt der Kompilierung exakt bestimmen können. Threadbezogene statische Felder bieten die beste Leistung. Außerdem bieten sie Ihnen die Vorteile der Typüberprüfung zur Kompilierzeit.  
  
- Verwenden Sie Datenslots, wenn die tatsächlichen Anforderungen voraussichtlich nur zur Laufzeit ermittelt werden können. Datenslots sind langsamer und umständlicher zu verwenden als threadbezogene statische Felder, und Daten werden als Typ <xref:System.Object> gespeichert, sodass Sie sie in den richtigen Typ umwandeln müssen, bevor Sie sie verwenden.  
  
 Ordnen Sie Slots in nicht verwaltetem C++ mit `TlsAlloc` dynamisch zu, und deklarieren Sie mit `__declspec(thread)`, dass eine Variable in threadbezogenem Speicher zugewiesen werden soll. Threadbezogene statische Felder und Datenslots stellen die verwaltete Version dieses Verhaltens bereit.  
  
Sie können mit der <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>-Klasse threadlokale Objekte erstellen, die verzögert initialisiert werden, wenn das Objekt zum ersten Mal verwendet wird. Weitere Informationen finden Sie unter [Verzögerte Initialisierung](../../framework/performance/lazy-initialization.md).  
  
## <a name="uniqueness-of-data-in-managed-tls"></a>Eindeutigkeit der Daten im verwalteten TLS  
 Ob Sie threadbezogene statische Felder oder Datenslots verwenden, Daten in verwaltetem TLS sind für die Kombination von Thread und Anwendungsdomäne eindeutig.  
  
- Innerhalb einer Anwendungsdomäne kann ein Thread Daten aus einem anderen Thread auch dann nicht ändern, wenn beide Threads dasselbe Feld oder denselben Slot verwenden.  
  
- Wenn ein Thread von mehreren Anwendungsdomänen aus auf dasselbe Feld oder denselben Slot zugreift, wird in jeder Anwendungsdomäne ein separater Wert beibehalten.  
  
 Wenn ein Thread z.B. den Wert eines threadbezogenen statischen Felds festlegt, in eine andere Anwendungsdomäne eintritt und dann den Wert des Felds abruft, unterscheidet sich der in der zweiten Anwendungsdomäne abgerufene Wert von dem Wert in der ersten Anwendungsdomäne. Das Festlegen eines neuen Werts für das Feld in der zweiten Anwendungsdomäne wirkt sich nicht auf den Wert des Felds in der ersten Anwendungsdomäne aus.  
  
 Auch wenn ein Thread denselben benannten Datenslot in zwei unterschiedlichen Anwendungsdomänen abruft, bleiben die Daten in der ersten Anwendungsdomäne unabhängig von den Daten in der zweiten Anwendungsdomäne.  
  
## <a name="thread-relative-static-fields"></a>Threadbezogene statische Felder  
 Wenn Sie wissen, dass ein Datenstück für eine Kombination aus Thread und Anwendungsdomäne immer eindeutig ist, wenden Sie das <xref:System.ThreadStaticAttribute>-Attribut auf das statische Feld an. Verwenden Sie das Feld wie jedes andere statische Feld. Die Daten im Feld sind für jeden Thread eindeutig, der sie verwendet.  
  
 Threadbezogene statische Felder bieten bessere Leistung als Datenslots und haben den Vorteil der Typüberprüfung zur Kompilierzeit.  
  
 Denken Sie daran, dass Klassenkonstruktorcode auf dem ersten Thread im ersten Kontext ausgeführt wird, der auf das Feld zugreift. In allen anderen Threads oder Kontexten in derselben Anwendungsdomäne werden die Felder mit `null` (`Nothing` in Visual Basic) initialisiert, wenn sie Verweistypen sind, oder mit ihren Standardwerten, wenn sie Werttypen sind. Aus diesem Grund sollten Sie sich beim Initialisieren threadbezogener statischer Felder nicht auf Klassenkonstruktoren verlassen. Vermeiden Sie stattdessen das Initialisieren threadbezogener statischer Felder, und setzen Sie voraus, dass sie mit `null` (`Nothing`) oder ihren Standardwerten initialisiert werden.  
  
## <a name="data-slots"></a>Datenslots  

.NET stellt dynamische Datenslots bereit, die für eine Kombination aus Thread und Anwendungsdomäne eindeutig sind. Es gibt zwei Arten von Datenslots: benannte und nicht benannte Slots. Beide werden mithilfe der <xref:System.LocalDataStoreSlot>-Struktur implementiert.  
  
- Erstellen Sie einen benannten Datenslot mit der <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType>- oder <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>-Methode. Um einen Verweis auf einen vorhandenen benannten Slot abzurufen, übergeben Sie seinen Namen der <xref:System.Threading.Thread.GetNamedDataSlot%2A>-Methode.  
  
- Erstellen Sie einen unbenannten Datenslot mit der <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType>-Methode.  
  
 Verwenden Sie für benannte und unbenannte Slots die <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType>- und <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType>-Methode zum Festlegen und Abrufen der Daten im Slot. Hierbei handelt es sich um statische Methoden, die immer für den Thread, der sie derzeit ausführt, auf die Daten angewendet werden.  
  
 Benannte Slots sind praktisch, da Sie den Slot bei Bedarf abrufen können, indem Sie seinen Namen der <xref:System.Threading.Thread.GetNamedDataSlot%2A>-Methode übergeben, statt einen Verweis auf einen unbenannten Slot beizubehalten. Wenn allerdings eine andere Komponente denselben Namen für ihren threadbezogenen Speicher verwendet, und ein Thread sowohl Code aus Ihrer Komponente als auch der anderen ausführt, könnten die zwei Komponenten sich gegenseitig ihre Daten beschädigen. (Dieses Szenario setzt voraus, dass beide Komponenten in derselben Anwendungsdomäne ausgeführt werden und nicht zur gemeinsamen Nutzung derselben Daten konzipiert sind.)  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ContextStaticAttribute>
- <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>
- <xref:System.ThreadStaticAttribute>
- <xref:System.Runtime.Remoting.Messaging.CallContext>
- [Threading](index.md)
