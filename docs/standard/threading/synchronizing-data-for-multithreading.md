---
title: "Synchronizing Data for Multithreading | Microsoft Docs"
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
  - "synchronization, threads"
  - "threading [.NET Framework], synchronizing threads"
  - "managed threading"
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Synchronizing Data for Multithreading
Wenn mehrere Threads die Eigenschaften und Methoden eines einzelnen Objekts aufrufen können, müssen diese Aufrufe synchronisiert werden.  Andernfalls kann es vorkommen, dass ein Thread die Aktionen eines anderen Threads unterbricht und dadurch einen unzulässigen Zustand für das Objekt verursacht.  Eine Klasse, deren Member vor derartigen Unterbrechungen geschützt sind, wird als threadsicher bezeichnet.  
  
 Die Common Language\-Infrastruktur stellt verschiedene Strategien bereit, um den Zugriff auf Instanzmember und statische Member zu synchronisieren:  
  
-   Synchronisierte Codebereiche.  Durch die <xref:System.Threading.Monitor>\-Klasse oder die Compilerunterstützung für diese Klasse werden nur die erforderlichen Codeblöcke synchronisiert, wodurch die Leistung gesteigert wird.  
  
-   Manuelle Synchronisierung.   Sie können die von der .NET Framework\-Klassenbibliothek bereitgestellten Synchronisierungsobjekte verwenden.  Weitere Informationen finden Sie unter [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md). In diesem Thema wird auch die <xref:System.Threading.Monitor>\-Klasse behandelt.  
  
-   Synchronisierte Kontexte.  Durch <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> wird eine einfache, automatische Synchronisierung von <xref:System.ContextBoundObject>\-Objekten ermöglicht.  
  
-   Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=fullName>\-Namespace.  Diese Klassen stellen integrierte synchronisierte Vorgänge zum Hinzufügen und Entfernen bereit.  Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md).  
  
 Von der Common Language Runtime wird ein Threadmodell bereitgestellt, in dem Klassen verschiedenen Kategorien zugeordnet werden, die je nach Anforderung auf verschiedene Weise synchronisiert werden können.  In der folgenden Tabelle wird gezeigt, welche Synchronisierung bei Feldern und Methoden der jeweiligen Synchronisierungskategorie unterstützt wird.  
  
|Kategorie \(Category\)|Globale Felder|Statische Felder|Statische Methoden|Instanzfelder|Instanzmethoden|Spezifische Codeblöcke|  
|----------------------------|--------------------|----------------------|------------------------|-------------------|---------------------|----------------------------|  
|Keine Synchronisierung|nein|nein|nein|nein|nein|nein|  
|Synchronisierter Kontext|nein|nein|nein|ja|ja|nein|  
|Synchronisierte Codebereiche|nein|nein|Nur wenn markiert|nein|Nur wenn markiert|Nur wenn markiert|  
|Manuelle Synchronisierung|Manuell|Manuell|Manuell|Manuell|Manuell|Manuell|  
  
## Keine Synchronisierung  
 Dies ist die Standardeinstellung für Objekte.  Jeder beliebige Thread kann jederzeit auf alle Methoden oder Felder zugreifen.  Es sollte jedoch nur jeweils ein Thread auf diese Objekte zugreifen.  
  
## Manuelle Synchronisierung  
 Die .NET Framework\-Klassenbibliothek stellt eine Reihe von Klassen zum Synchronisieren von Threads bereit.  Siehe [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## Synchronisierte Codebereiche  
 Durch die <xref:System.Threading.Monitor>\-Klasse oder ein Compilerschlüsselwort können Codeblöcke, Instanzmethoden und statische Methoden synchronisiert werden.  Synchronisierte statische Felder werden nicht unterstützt.  
  
 Visual Basic und C\# unterstützen das Markieren von Codeblöcken mit einem bestimmten Sprachschlüsselwort, der `lock`\-Anweisung in C\# oder der `SyncLock`\-Anweisung in Visual Basic.  Wenn der Code von einem Thread ausgeführt wird, wird versucht, die Sperre zu übernehmen.  Wenn bereits ein anderer Thread die Sperre übernommen hat, wird der Thread blockiert, bis die Sperre verfügbar ist.  Wenn der Thread den synchronisierten Codeblock beendet, wird die Sperre freigegeben, unabhängig davon, wie der Thread den Block beendet.  
  
> [!NOTE]
>  Die `lock`\- und `SyncLock`\-Anweisungen werden mit <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName> und <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName> implementiert, sodass andere Methoden von <xref:System.Threading.Monitor> zusammen mit ihnen im synchronisierten Bereich verwendet werden können.  
  
 Sie können eine Methode auch mit **MethodImplAttribute**  und **MethodImplOptions.Synchronized** ergänzen. Das hat denselben Effekt wie **Monitor** oder eines der Compilerschlüsselwörter, um den gesamten Methodentext zu sperren.  
  
 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> kann verwendet werden, um einen Thread aus blockierten Vorgängen herauszulösen, z. B. bei Wartezeiten während des Zugriffs auf einen synchronisierten Codebereich.  **Thread.Interrupt** wird auch zum Befreien von Threads aus Vorgängen wie <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> verwendet.  
  
> [!IMPORTANT]
>  Sperren Sie nicht den Typ \(`typeof(MyType)` in C\#, `GetType(MyType)` in Visual Basic oder `MyType::typeid` in C\+\+\), um `static`\-Methoden zu schützen \(`Shared`\-Methoden in Visual Basic\).  Verwenden Sie stattdessen ein privates statisches Objekt.  Genauso sollten Sie `this` in C\# \(`Me` in Visual Basic\) nicht zum Sperren von Instanzmethoden verwenden.  Verwenden Sie stattdessen ein privates Objekt.  Eine Klasse oder Instanz kann von fremdem Code gesperrt werden, der Deadlocks oder Leistungseinbußen verursachen kann.  
  
### Compilerunterstützung  
 Sowohl Visual Basic als auch C\# unterstützen ein Sprachschlüsselwort, das das Objekt mit <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName> und <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName> sperrt.  Visual Basic unterstützt die [SyncLock](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md)\-Anweisung, C\# die [lock](../Topic/lock%20Statement%20\(C%23%20Reference\).md)\-Anweisung.  
  
 In beiden Fällen wird eine Ausnahme im Codeblock ausgelöst. Die durch **lock** oder **SyncLock** erlangte Sperre wird automatisch freigegeben.  Die Compiler von C\# und Visual Basic geben einen **try**\/**finally**\-Block aus, wobei **Monitor.Enter** am Anfang des **try**\-Blocks und **Monitor.Exit** im **finally**\-Block enthalten ist.  Wenn innerhalb des **lock**\- oder **SyncLock**\-Blocks eine Ausnahme ausgelöst wird, wird die Bereinigung durch den **finally**\-Handler ermöglicht.  
  
## Synchronisierter Kontext  
 Durch Anwendung von **SynchronizationAttribute** auf ein beliebiges **ContextBoundObject** können alle Instanzmethoden und \-felder synchronisiert werden.  Alle Objekte derselben Kontextdomäne nutzen dieselbe Sperre.  Mehrere Threads können auf die Methoden und Felder zugreifen, jedoch immer nur ein einzelner Thread gleichzeitig.  
  
## Siehe auch  
 <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)   
 [SyncLock Statement](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md)   
 [lock\-Anweisung](../Topic/lock%20Statement%20\(C%23%20Reference\).md)