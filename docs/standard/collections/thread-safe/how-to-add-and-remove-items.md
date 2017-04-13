---
title: "Gewusst wie: Hinzuf&#252;gen und Entfernen von Elementen aus einem ConcurrentDictionary | Microsoft Docs"
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
  - "threadsichere Auflistungen, gleichzeitiges Wörterbuch"
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Hinzuf&#252;gen und Entfernen von Elementen aus einem ConcurrentDictionary
In diesem Beispiel wird gezeigt, wie Elemente einem <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>\-Objekt hinzugefügt werden bzw. wie sie daraus abgerufen, darin aktualisiert und daraus entfernt werden.  Diese Auflistungsklasse ist eine threadsichere Implementierung.  Es wird empfohlen, die Klasse immer zu verwenden, wenn mehrere Threads möglicherweise gleichzeitig versuchen, auf die Elemente zuzugreifen.  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> stellt mehrere Hilfsmethoden bereit, durch die es unnötig wird, zuerst mit dem Code zu überprüfen, ob ein Schlüssel vorhanden ist, bevor versucht wird, Daten hinzuzufügen oder zu entfernen.  In der folgenden Tabelle werden diese Hilfsmethoden aufgeführt, und es wird beschrieben, wann sie verwendet werden sollen.  
  
|Methode|Verwendung:|  
|-------------|-----------------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|Sie möchten einen neuen Wert für einen angegebenen Schlüssel hinzufügen und bei Vorhandensein des Schlüssels den Wert ersetzen.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|Sie möchten den vorhandenen Wert für einen angegebenen Schlüssel abrufen und bei Nichtvorhandensein des Schlüssels möchten Sie ein Schlüssel\-Wert\-Paar angeben.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A>|Sie möchten ein Schlüssel\-Wert\-Paar hinzufügen, abrufen, aktualisieren oder entfernen, und bei Vorhandensein des Schlüssels oder bei Fehlschlagen des Versuchs aus einem anderen Grund alternative Aktionen ausführen.|  
  
## Beispiel  
 Im folgenden Beispiel werden einem <xref:System.Collections.Concurrent.ConcurrentDictionary%602>\-Objekt mithilfe von zwei <xref:System.Threading.Tasks.Task>\-Instanzen gleichzeitig einige Elemente hinzugefügt. Anschließend wird der gesamte Inhalt ausgegeben, um anzuzeigen, dass die Elemente hinzugefügt wurden.  Im Beispiel wird auch gezeigt, wie <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>\-Methoden verwendet, um der Auflistung Elemente hinzuzufügen, zu aktualisieren und abzurufen.  
  
 [!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
 [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> ist für Multithreadszenarien vorgesehen.  Sie müssen keine Sperren im Code verwenden, um der Auflistung Elemente hinzuzufügen oder daraus zu entfernen.  Es ist immer jedoch möglich, dass ein Thread einen Wert abruft und dass ein anderer Thread umgehend die Auflistung aktualisiert, indem dem gleichen Schlüssel ein neuer Wert zugewiesen wird.  
  
 Obwohl darüber hinaus alle Methoden von <xref:System.Collections.Concurrent.ConcurrentDictionary%602> threadsicher sind, sind nicht alle Methoden unteilbar, insbesondere <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.  Der an diese Methoden übergebene Benutzerdelegat wird außerhalb der internen Sperre des Wörterbuchs aufgerufen. \(Hierdurch soll verhindert werden, dass unbekannter Code alle Threads blockiert.\) Aus diesem Grund ist es möglich, dass diese Abfolge von Ereignissen eintritt:  
  
 1\) ThreadA ruft <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> auf, findet kein Element und erstellt ein neues hinzuzufügendes Element, indem der valueFactory\-Delegat aufgerufen wird.  
  
 2\) ThreadB ruft gleichzeitig <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> auf, der zugehörige valueFactory\-Delegat wird aufgerufen, und die interne Sperre wird vor ThreadA erreicht. Daher wird dem Wörterbuch das neue Schlüssel\-Wert\-Paar hinzugefügt.  
  
 3\) Der Benutzerdelegat von ThreadA wird abgeschlossen, und der Thread erreicht die Sperre. Jedoch scheint das neue Element bereits vorhanden zu sein.  
  
 4\) ThreadA führt "Get" aus und gibt die Daten zurück, die zuvor durch ThreadB hinzugefügt wurden.  
  
 Daher ist nicht sichergestellt, dass die von <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> zurückgegebenen Daten mit den Daten identisch sind, die von valueFactory des Threads erstellt wurden.  Eine ähnliche Abfolge von Ereignissen kann eintreten, wenn <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> aufgerufen wird.  
  
## Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)