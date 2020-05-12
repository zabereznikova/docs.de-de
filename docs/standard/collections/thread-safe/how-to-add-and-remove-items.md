---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einer ConcurrentDictionary-Klasse'
ms.date: 05/04/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, concurrent dictionary
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
ms.openlocfilehash: 6e5204c5a71232ef9d1a050891e7fe6d92c375f2
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796118"
---
# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a>Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einer ConcurrentDictionary-Klasse

Dieses Beispiel zeigt, wie Elemente hinzugefügt, abgerufen, aktualisiert und von einer <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType> entfernt werden. Diese Auflistungsklasse ist eine threadsichere Implementierung. Es empfiehlt sich, diese Klasse immer dann zu verwenden, wenn möglicherweise mehrere Threads gleichzeitig versuchen, auf Elemente zuzugreifen.

<xref:System.Collections.Concurrent.ConcurrentDictionary%602> bietet verschiedene praktische Methoden, mit denen der Code nicht mehr zuerst prüfen muss, ob ein Schlüssel vorhanden ist, bevor versucht wird, Daten hinzuzufügen oder zu entfernen. Die folgende Tabelle führt diese praktischen Methoden auf und beschreibt ihre Verwendung.

| Methode | Wenn folgende Bedingungen vorliegen |
|--|--|
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> | Sie möchten einen neuen Wert für einen angegebenen Schlüssel hinzufügen und, wenn der Schlüssel bereits vorhanden ist, den Wert ersetzen. |
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> | Sie möchten den vorhandenen Wert für einen angegebenen Schlüssel abrufen und, wenn der Schlüssel nicht vorhanden ist, ein Schlüssel-Wert-Paar angeben. |
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A> | Sie möchten ein Schlüssel-Wert-Paar hinzufügen, abrufen, aktualisieren oder entfernen und, wenn der Schlüssel bereits vorhanden ist oder der Versuch aus einem anderen Grund fehlschlägt, eine alternative Aktion durchführen. |

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Instanzen von <xref:System.Threading.Tasks.Task> verwendet, um <xref:System.Collections.Concurrent.ConcurrentDictionary%602> parallel einige Elemente hinzuzufügen und dann den gesamten Inhalt auszugeben, um zu zeigen, dass die Elemente erfolgreich hinzugefügt wurden. Das Beispiel zeigt auch, wie die Methoden <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> zum Hinzufügen, Aktualisieren und Abrufen von Elementen aus der Auflistung verwendet werden.

[!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
[!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]

<xref:System.Collections.Concurrent.ConcurrentDictionary%602> wurde für Multithread-Szenarios entworfen. Sie müssen keine Sperren in Ihrem Code verwenden, um Elemente zur Auflistung hinzuzufügen oder daraus zu entfernen. Es ist jedoch immer möglich, dass ein Thread einen Wert abruft und ein anderer Thread durch Zuweisen eines neuen Werts zum gleichen Schlüssel die Auflistung unmittelbar danach aktualisiert.

Darüber hinaus sind zwar alle Methoden von <xref:System.Collections.Concurrent.ConcurrentDictionary%602> threadsicher, aber nicht alle Methoden sind atomisch – insbesondere <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>. Der an diese Methoden übergebene Benutzerdelegat wird außerhalb der internen Sperre des Wörterbuchs aufgerufen (um unbekannten Code davon abzuhalten, alle Threads zu blockieren). Daher ist es möglich, dass die folgende Ereignissequenz eintritt:

1. _threadA_ ruft <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> auf, findet kein Element und erstellt ein neues hinzuzufügendes Element durch Aufrufen des `valueFactory`-Delegaten.

1. _threadB_ ruft <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> gleichzeitig auf, der zugehörige `valueFactory`-Delegat wird aufgerufen und erreicht die interne Sperre vor _threadA_. Daher wird das neue Schlüssel-Wert-Paar dieses Threads zum Wörterbuch hinzugefügt.

1. Der Benutzerdelegat von _threadA_ wird fertiggestellt, und der Thread erreicht die Sperre, stellt jetzt aber fest, dass das Element bereits vorhanden ist.

1. _threadA_ führt eine Get-Aktion aus und gibt die Daten zurück, die zuvor von _threadB_ hinzugefügt wurden.

Daher ist nicht garantiert, dass die von <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> zurückgegebenen Daten die gleichen Daten sind, die von `valueFactory` des Threads erstellt wurden. Eine ähnliche Abfolge von Ereignissen kann eintreten, wenn <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> aufgerufen wird.

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Threadsichere Sammlungen](../../../../docs/standard/collections/thread-safe/index.md)
