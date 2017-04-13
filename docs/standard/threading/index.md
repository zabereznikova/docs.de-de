---
title: "Managed Threading | Microsoft Docs"
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
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Managed Threading
Unabhängig davon, ob eine Anwendung für einen Computer mit einem oder mehreren Prozessoren entwickelt wurde, sollte sie optimal auf die Interaktion mit einem Benutzer ansprechen, auch wenn sie gerade mit anderen Aufgaben befasst ist.  Die Verwendung verschiedener Ausführungsthreads stellt eine der effektivsten Möglichkeiten dar, eine Anwendung entsprechend reaktionsschnell zu gestalten und gleichzeitig den Prozessor zwischen Benutzerereignissen oder sogar währenddessen zu nutzen.  In diesem Abschnitt werden die grundlegenden Threadingkonzepte eingeführt und insbesondere verwaltete Threadingkonzepte und die Verwendung von verwaltetem Threading ausführlich behandelt.  
  
> [!NOTE]
>  Beginnend mit [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] wird die Multithread\-Programmierung durch die <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>\-Klasse und die <xref:System.Threading.Tasks.Task?displayProperty=fullName>\-Klasse, [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), neue parallele Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=fullName>\-Namespace und ein neues Programmierungsmodell erheblich vereinfacht, das auf dem Konzept von Aufgaben und nicht auf Threads basiert.  Weitere Informationen finden Sie unter [Parallel Programming](../../../docs/standard/parallel-programming/index.md).  
  
## In diesem Abschnitt  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)  
 Enthält eine Übersicht über das verwaltete Threading und erläutert, in welchen Fällen mehrere Threads verwendet werden.  
  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 Erklärt das Erstellen, Starten, Anhalten, Fortsetzen und Abbrechen von Threads.  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Behandelt Synchronisierungsstufen, die Vermeidung von Deadlock\- und Racebedingungen, Einzel\- und Multiprozessorcomputer und weitere Threadingprobleme.  
  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)  
 Beschreibt die verwalteten Klassen, mit denen Sie Threadingaktivitäten sowie die Daten von Objekten, auf die in verschiedenen Threads zugegriffen wird, synchronisieren können und bietet eine Übersicht über Threadpoolthreads.  
  
## Referenz  
 <xref:System.Threading>  
 Enthält Klassen zum Verwenden und dem Synchronisieren von verwalteten Threads.  
  
 <xref:System.Collections.Concurrent>  
 Enthält Auflistungsklassen, die sicher mit mehreren Threads verwendet werden können.  
  
 <xref:System.Threading.Tasks>  
 Enthält Klassen zum Erstellen und Planen von parallelen Verarbeitungsaufgaben.  
  
## Verwandte Abschnitte  
 [Anwendungsdomänen](../../../docs/framework/app-domains/application-domains.md)  
 Übersicht über Anwendungsdomänen und deren Verwendung durch die Common Language\-Infrastruktur.  
  
 [Asynchrone Datei\-E\/A](../../../docs/standard/io/asynchrone-datei-e-a.md)  
 Beschreibt die Leistungsvorteile und den grundlegenden Ablauf der asynchronen E\/A.  
  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 Übersicht über asynchrones Programmieren.  
  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Erläutert das Aufrufen von Methoden für Threadpoolthreads mithilfe der integrierten Features von Delegaten.  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 Beschreibt die parallelen Programmierbibliotheken, die die Verwendung mehrerer Threads in Anwendungen vereinfachen.  
  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 Beschreibt ein System zum parallelen Ausführen von Abfragen, um mehrere Prozessoren zu nutzen.