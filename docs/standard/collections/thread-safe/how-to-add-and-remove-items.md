---
title: "Gewusst wie: Hinzufügen und Entfernen von Elementen aus einem ConcurrentDictionary | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, concurrent dictionary
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9d20d75b2492c214305c07a5e19941cd91b66f67
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a>Gewusst wie: Hinzufügen und Entfernen von Elementen aus einem ConcurrentDictionary
Dieses Beispiel zeigt das Hinzufügen, Abrufen, Aktualisieren und Entfernen von Elementen einer <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>-Sammlung. Diese Auflistungsklasse ist eine threadsichere Implementierung. Es empfiehlt sich, diese Klasse immer dann zu verwenden, wenn möglicherweise mehrere Threads gleichzeitig versuchen, auf Elemente zuzugreifen.  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> bietet verschiedene praktische Methoden, mit denen der Code nicht mehr zuerst prüfen muss, ob ein Schlüssel vorhanden ist, bevor versucht wird, Daten hinzuzufügen oder zu entfernen. Die folgende Tabelle führt diese praktischen Methoden auf und beschreibt ihre Verwendung.  
  
|Methode|Wenn folgende Bedingungen vorliegen|  
|------------|---------------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|Sie möchten einen neuen Wert für einen angegebenen Schlüssel hinzufügen und, wenn der Schlüssel bereits vorhanden ist, den Wert ersetzen.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|Sie möchten den vorhandenen Wert für einen angegebenen Schlüssel abrufen und, wenn der Schlüssel nicht vorhanden ist, ein Schlüssel-Wert-Paar angeben.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A>|Sie möchten ein Schlüssel-Wert-Paar hinzufügen, abrufen, aktualisieren oder entfernen und, wenn der Schlüssel bereits vorhanden ist oder der Versuch aus einem anderen Grund fehlschlägt, eine alternative Aktion durchführen.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Instanzen von <xref:System.Threading.Tasks.Task> verwendet, um <xref:System.Collections.Concurrent.ConcurrentDictionary%602> parallel einige Elemente hinzuzufügen und dann den gesamten Inhalt auszugeben, um zu zeigen, dass die Elemente erfolgreich hinzugefügt wurden. Das Beispiel zeigt auch die Verwendung der Methoden <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> zum Hinzufügen, Aktualisieren und Abrufen von Elementen zur, in der bzw. aus der Sammlung.  
  
 [!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
 [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> ist für Multithreadszenarien vorgesehen. Sie müssen keine Sperren in Ihrem Code verwenden, um Elemente zur Auflistung hinzuzufügen oder daraus zu entfernen. Es ist jedoch immer möglich, dass ein Thread einen Wert abruft und ein anderer Thread durch Zuweisen eines neuen Werts zum gleichen Schlüssel die Auflistung unmittelbar danach aktualisiert.  
  
 Außerdem sind, obwohl alle Methoden von <xref:System.Collections.Concurrent.ConcurrentDictionary%602> threadsicher sind, nicht alle Methoden atomisch, insbesondere <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>. Der an diese Methoden übergebene Benutzerdelegat wird außerhalb der internen Sperre des Wörterbuchs aufgerufen. (Dies erfolgt, um zu verhindern, dass unbekannter Code alle Threads blockiert.) Daher ist es möglich, dass die folgende Ereignissequenz eintritt:  
  
 1\) threadA ruft <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> auf, findet kein Element und erstellt ein neues Element zum Hinzufügen durch Aufrufen des valueFactory-Delegaten.  
  
 2\) threadB ruft parallel <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> auf, dessen valueFactory-Delegat wird aufgerufen und erreicht die interne Sperre vor threadA, daher wird dem Wörterbuch sein neues Schlüssel/Wert-Paar hinzugefügt.  
  
 3\) Der Benutzerdelegat von threadA wird fertiggestellt, und der Thread erreicht die Sperre, stellt jetzt aber fest, dass das Element bereits vorhanden ist.  
  
 4\) threadA führt einen „Get“ aus und gibt die Daten zurück, die zuvor von threadB hinzugefügt worden waren.  
  
 Daher lässt sich nicht sicherstellen, dass die von <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> zurückgegebenen Daten die gleichen Daten sind, die von der valueFactory des Threads erstellt wurden. Eine ähnliche Abfolge der Ereignisse kann auch beim Aufruf von <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> eintreten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)
