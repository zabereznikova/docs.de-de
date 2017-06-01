---
title: "Thread Local Storage: Thread-Relative Static Fields and Data Slots | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "threading [.NET Framework], local storage"
  - "threading [.NET Framework], thread-relative static fields"
  - "local thread storage"
  - "TLS"
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Thread Local Storage: Thread-Relative Static Fields and Data Slots
Verwaltete lokale Threadspeicher \(TLS\) können zur Speicherung von Daten verwendet werden, die für einen Thread und eine Anwendungsdomäne eindeutig sind.  .NET Framework bietet zwei Möglichkeiten zur Verwendung verwalteter lokaler Threadspeicher: threadbezogene statische Felder und Datenslots.  
  
-   Verwenden Sie threadbezogene statische Felder \(threadbezogene `Shared`\-Felder in Visual Basic\), wenn Sie die Anforderungen zur Kompilierzeit genau einschätzen können.  Threadbezogene statische Felder bieten die beste Leistung.  Außerdem ermöglichen sie die Typüberprüfung zur Kompilierzeit.  
  
-   Verwenden Sie Datenslots, wenn Sie die tatsächlichen Anforderungen unter Umständen erst zur Laufzeit kennen.  Datenslots sind langsamer und umständlicher als threadbezogene statische Felder. Außerdem werden die Daten als <xref:System.Object>\-Typ gespeichert, sodass Sie sie vor der Verwendung in den richtigen Typ umwandeln müssen.  
  
 In nicht verwaltetem C\+\+ wird `TlsAlloc` verwendet, um Slots dynamisch zuzuweisen, und `__declspec(thread)`, um zu deklarieren, dass eine Variable in threadbezogenem Speicher zugewiesen werden soll.  Threadbezogene statische Felder und Datenslots stellen die verwaltete Version dieses Verhaltens bereit.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie threadlokale Objekte, die spät initialisiert werden, mithilfe der <xref:System.Threading.ThreadLocal%601?displayProperty=fullName>\-Klasse erstellen, sobald das Objekt erstmals genutzt wird.  Weitere Informationen finden Sie unter [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).  
  
## Eindeutigkeit der Daten im verwalteten TLS  
 Die Daten im verwalteten TLS sind für die Kombination aus Thread und Anwendungsdomäne eindeutig, und zwar unabhängig davon, ob Sie threadbezogene statische Felder oder Datenslots verwenden.  
  
-   Innerhalb einer Anwendungsdomäne kann ein Thread die Daten eines anderen Threads nicht ändern, auch wenn beide Threads das gleiche Feld oder den gleichen Slot verwenden.  
  
-   Wenn ein Thread aus mehreren Anwendungsdomänen auf das gleiche Feld oder den gleichen Slot zugreift, wird in jeder Anwendungsdomäne ein separater Wert beibehalten.  
  
 Wenn z. B. ein Thread den Wert eines threadbezogenen statischen Felds festlegt, in eine andere Anwendungsdomäne wechselt und anschließend den Wert des Felds abruft, unterscheidet sich der in der zweiten Anwendungsdomäne abgerufene Wert von dem Wert in der ersten Anwendungsdomäne.  Wenn für das Feld in der zweiten Anwendungsdomäne ein neuer Wert festgelegt wird, hat dies keine Auswirkungen auf den Wert des Felds in der ersten Anwendungsdomäne.  
  
 Ähnlich verhält es sich, wenn ein Thread den gleichen benannten Datenslot in zwei verschiedenen Anwendungsdomänen abruft: Die Daten in der ersten Anwendungsdomäne sind unabhängig von den Daten in der zweiten Anwendungsdomäne.  
  
## Threadbezogene statische Felder  
 Wenn Sie wissen, dass bestimmte Daten für eine Kombination aus Thread und Anwendungsdomäne stets eindeutig sind, wenden Sie das <xref:System.ThreadStaticAttribute>\-Attribut auf das statische Feld an.  Die Verwendung des Felds unterscheidet sich nicht von der eines anderen statischen Felds.  Die Daten im Feld sind für jeden Thread, der sie verwendet, eindeutig.  
  
 Threadbezogene statische Felder bieten eine bessere Leistung als Datenslots und ermöglichen zudem die Typüberprüfung zur Kompilierzeit.  
  
 Beachten Sie, dass jeder Klassenkonstruktorcode auf dem ersten Thread im ersten Kontext ausgeführt wird, der auf das Feld zugreift.  In allen anderen Threads oder Kontexten in der gleichen Anwendungsdomäne werden die Felder mit `null` \(`Nothing` in Visual Basic\) initialisiert, wenn sie Referenztypen sind, oder mit ihren Standardwerten, wenn es sich um Werttypen handelt.  Daher sollten Sie die Initialisierung threadbezogener statischer Felder nicht von Klassenkonstruktoren abhängig machen.  Stattdessen sollten Sie threadbezogene statische Felder nach Möglichkeit nicht initialisieren und davon ausgehen, dass sie mit `null` \(`Nothing`\) oder mit ihren Standardwerten initialisiert werden.  
  
## Datenslots  
 .NET Framework stellt dynamische Datenslots bereit, die für eine Kombination aus Thread und Anwendungsdomäne eindeutig sind.  Es gibt zwei Arten von Datenslots: benannte und nicht benannte.  Beide werden mit der <xref:System.LocalDataStoreSlot>\-Struktur implementiert.  
  
-   Um einen benannten Datenslot zu erstellen, verwenden Sie die <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=fullName>\-Methode oder die <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=fullName>\-Methode.  Zum Abrufen eines Verweises auf einen vorhandenen benannten Slot übergeben Sie seinen Namen an die <xref:System.Threading.Thread.GetNamedDataSlot%2A>\-Methode.  
  
-   Um einen unbenannten Datenslot zu erstellen, verwenden Sie die <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=fullName>\-Methode.  
  
 Verwenden Sie für benannte und unbenannte Datenslots die <xref:System.Threading.Thread.SetData%2A?displayProperty=fullName>\-Methode und die <xref:System.Threading.Thread.GetData%2A?displayProperty=fullName>\-Methode, um die Informationen im Slot festzulegen und abzurufen.  Hierbei handelt es sich um statische Methoden, die stets auf die Daten für den Thread angewendet werden, der sie zurzeit ausführt.  
  
 Benannte Slots können von Vorteil sein, da Sie den Slot bei Bedarf abrufen können, indem Sie seinen Namen an die <xref:System.Threading.Thread.GetNamedDataSlot%2A>\-Methode übergeben, anstatt einen Verweis auf einen unbenannten Slot beizubehalten.  Wenn jedoch eine andere Komponente den gleichen Namen für ihren threadbezogenen Speicher verwendet und ein Thread Code sowohl aus Ihrer Komponente als auch aus der anderen Komponente ausführt, können die beiden Komponenten die Daten der jeweils anderen Komponente beschädigen. \(In diesem Szenario wird davon ausgegangen, dass beide Komponenten in der gleichen Anwendungsdomäne ausgeführt werden und nicht zur Verwendung der gleichen Daten vorgesehen sind.\)  
  
## Siehe auch  
 <xref:System.ContextStaticAttribute>   
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=fullName>   
 <xref:System.ThreadStaticAttribute>   
 <xref:System.Runtime.Remoting.Messaging.CallContext>   
 [Threading](../../../docs/standard/threading/index.md)