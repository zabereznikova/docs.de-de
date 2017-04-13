---
title: "Gewusst wie: Hinzuf&#252;gen von Begrenzungs- und Blockadefunktionen zu einer Auflistung | Microsoft Docs"
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
  - "threadsichere Auflistungen, benutzerdefinierte blockierende Auflistungen"
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Hinzuf&#252;gen von Begrenzungs- und Blockadefunktionen zu einer Auflistung
In diesem Beispiel wird gezeigt, wie Begrenzungs\- und Blockadefunktionen durch Implementieren der <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName>\-Schnittstelle in der Klasse hinzugefügt werden. Zudem wird erläutert, wie eine Klasseninstanz als interner Speichermechanismus für ein <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>\-Objekt verwendet wird.  Weitere Informationen zu Begrenzungen und Blockierung finden Sie unter [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
## Beispiel  
 Die benutzerdefinierte Auflistungsklasse ist eine grundlegende Prioritätswarteschlange, in der die Prioritätsstufen als Array von <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>\-Objekten dargestellt werden.  Es wird keine zusätzliche Sortierung innerhalb jeder Warteschlange ausgeführt.  
  
 Im Clientcode werden drei Aufgaben gestartet.  In der ersten Aufgabe werden nur Tastaturbefehle abgefragt, um während der Ausführung den Vorgang an einer beliebigen Stelle abbrechen zu können.  Die zweite Aufgabe ist der Producerthread. Dabei werden der Blockierungsauflistung neue Elemente hinzugefügt, und jedes Element erhält auf Grundlage eines Zufallswerts eine Priorität.  In der dritten Aufgabe werden Elemente aus der Auflistung entfernt, sobald sie verfügbar sind.  
  
 Sie können das Verhalten der Anwendung anpassen, indem Sie die Ausführung eines der Threads im Vergleich zum anderen Thread beschleunigen.  Wenn der Producer schneller ausgeführt wird, sehen Sie die Begrenzungsfunktion, während durch die Blockierungsauflistung das Hinzufügen von Elementen verhindert wird, wenn sie bereits die Anzahl der im Konstruktor angegebenen Elemente enthält.  Wenn der Consumer schneller ausgeführt wird, sehen Sie die Blockierungsfunktion, während der Consumer auf das Hinzufügen eines neuen Elements wartet.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 In der Standardeinstellung ist der Speicher für ein <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>\-Objekt <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.  
  
## Siehe auch  
 [Threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)