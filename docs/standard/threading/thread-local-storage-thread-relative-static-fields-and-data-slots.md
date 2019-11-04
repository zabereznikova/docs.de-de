---
title: 'Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
ms.openlocfilehash: b5a7c4b78f8599f64aa11f1c98c033866e582933
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127521"
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots
Sie können verwalteten lokalen Threadspeicher (TLS, Thread Local Storage) zum Speichern von Daten verwenden, die für einen Thread und die Anwendungsdomäne eindeutig sind. .NET Framework bietet zwei Möglichkeiten zur Verwendung von verwaltetem TLS: threadbezogene statische Felder und Datenslots.  
  
- Verwenden Sie threadbezogene statische Felder (threadbezogene `Shared`-Felder in Visual Basic), wenn Sie Ihre Anforderungen zum Zeitpunkt der Kompilierung exakt bestimmen können. Threadbezogene statische Felder bieten die beste Leistung. Außerdem bieten sie Ihnen die Vorteile der Typüberprüfung zur Kompilierzeit.  
  
- Verwenden Sie Datenslots, wenn die tatsächlichen Anforderungen voraussichtlich nur zur Laufzeit ermittelt werden können. Datenslots sind langsamer und umständlicher zu verwenden als threadbezogene statische Felder, und Daten werden als Typ <xref:System.Object> gespeichert, sodass Sie sie in den richtigen Typ umwandeln müssen, bevor Sie sie verwenden.  
  
 Ordnen Sie Slots in nicht verwaltetem C++ mit `TlsAlloc` dynamisch zu, und deklarieren Sie mit `__declspec(thread)`, dass eine Variable in threadbezogenem Speicher zugewiesen werden soll. Threadbezogene statische Felder und Datenslots stellen die verwaltete Version dieses Verhaltens bereit.  
  
 In .NET Framework 4 können Sie mit der <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>-Klasse threadlokale Objekte erstellen, die verzögert initialisiert werden, wenn das Objekt zuerst genutzt wird. Weitere Informationen finden Sie unter [Verzögerte Initialisierung](../../../docs/framework/performance/lazy-initialization.md).  
  
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
 .NET Framework bietet dynamische Datenslots, die für eine Kombination aus Thread und Anwendungsdomäne eindeutig sind. Es gibt zwei Arten von Datenslots: benannte und nicht benannte Slots. Beide werden mithilfe der <xref:System.LocalDataStoreSlot>-Struktur implementiert.  
  
- Erstellen Sie einen benannten Datenslot mit der <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType>- oder <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>-Methode. Um einen Verweis auf einen vorhandenen benannten Slot abzurufen, übergeben Sie seinen Namen der <xref:System.Threading.Thread.GetNamedDataSlot%2A>-Methode.  
  
- Erstellen Sie einen unbenannten Datenslot mit der <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType>-Methode.  
  
 Verwenden Sie für benannte und unbenannte Slots die <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType>- und <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType>-Methode zum Festlegen und Abrufen der Daten im Slot. Hierbei handelt es sich um statische Methoden, die immer für den Thread, der sie derzeit ausführt, auf die Daten angewendet werden.  
  
 Benannte Slots sind praktisch, da Sie den Slot bei Bedarf abrufen können, indem Sie seinen Namen der <xref:System.Threading.Thread.GetNamedDataSlot%2A>-Methode übergeben, statt einen Verweis auf einen unbenannten Slot beizubehalten. Wenn allerdings eine andere Komponente denselben Namen für ihren threadbezogenen Speicher verwendet, und ein Thread sowohl Code aus Ihrer Komponente als auch der anderen ausführt, könnten die zwei Komponenten sich gegenseitig ihre Daten beschädigen. (Dieses Szenario setzt voraus, dass beide Komponenten in derselben Anwendungsdomäne ausgeführt werden und nicht zur gemeinsamen Nutzung derselben Daten konzipiert sind.)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ContextStaticAttribute>
- <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>
- <xref:System.ThreadStaticAttribute>
- <xref:System.Runtime.Remoting.Messaging.CallContext>
- [Threading](../../../docs/standard/threading/index.md)
