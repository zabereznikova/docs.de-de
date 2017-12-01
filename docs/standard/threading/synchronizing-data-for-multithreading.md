---
title: "Datensynchronisierung für Multithreading"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- synchronization, threads
- threading [.NET Framework], synchronizing threads
- managed threading
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a17eba2f930fda06d643d78c73c117e89ae86928
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="synchronizing-data-for-multithreading"></a>Datensynchronisierung für Multithreading
Wenn mehrere Threads die Eigenschaften und Methoden eines einzelnen Objekts aufrufen können, ist es wichtig, dass diese Aufrufe synchronisiert werden. Andernfalls kann ein Thread möglicherweise die Aufgabe eines anderen Threads unterbrechen, und das Objekt bleibt womöglich in einem ungültigen Status zurück. Eine Klasse, deren Mitglieder vor solchen Unterbrechungen geschützt, wird threadsicher genannt.  
  
 Die Common Language Infrastructure stellt verschiedene Strategien zum Synchronisieren des Zugriffs auf Instanzmember und statische Member bereit:  
  
-   Synchronisierte Codebereiche. Sie können die <xref:System.Threading.Monitor> Klasse oder Compiler-Unterstützung für diese Klasse nur der Code blockieren, die synchronisiert benötigt, Verbessern der Leistung.  
  
-   Manuelle Synchronisierung Sie können die von der .NET Framework-Klassenbibliothek bereitgestellten Synchronisierungsobjekte verwenden. Finden Sie unter [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md), einschließlich eine Erläuterung der <xref:System.Threading.Monitor> Klasse.  
  
-   Synchronisierte Kontexte. Sie können die <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> zum Aktivieren von einfachen, automatische Synchronisierung von <xref:System.ContextBoundObject> Objekte.  
  
-   Auflistungsklassen, die der <xref:System.Collections.Concurrent?displayProperty=nameWithType> Namespace. Diese Klassen stellen integrierte synchronisierte Hinzufüge- und Entfernungsvorgänge bereit. Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md).  
  
 Die Common Language Runtime stellt ein Threadmodell bereit, bei dem Klassen in verschiedene Kategorien fallen, die je nach den Anforderungen in einer Vielzahl von Möglichkeiten synchronisiert werden können. Die folgende Tabelle zeigt, welche Synchronisierungsunterstützung für Felder und Methoden mit einer angegebenen Synchronisierungskategorie vorhanden sind.  
  
|Kategorie|Globale Felder|Statische Felder|Statische Methoden|Instanzfelder|Instanzmethoden|Spezifische Codeblöcke|  
|--------------|-------------------|-------------------|--------------------|---------------------|----------------------|--------------------------|  
|Keine Synchronisierung|Nein|Nein|Nein|Nein|Nein|Nein|  
|Synchronisierter Kontexte|Nein|Nein|Nein|Ja|Ja|Nein|  
|Synchronisierte Codebereiche|Nein|Nein|Nur wenn markiert|Nein|Nur wenn markiert|Nur wenn markiert|  
|Manuelle Synchronisierung|Manuell|Manuell|Manuell|Manuell|Manuell|Manuell|  
  
## <a name="no-synchronization"></a>Keine Synchronisierung  
 Dies ist die Standardeinstellung für Objekte. Jeder Thread kann jederzeit auf alle Methoden oder Felder zugreifen. Es sollte jedoch nur ein Thread nach dem anderen auf diese Objekte zugreifen.  
  
## <a name="manual-synchronization"></a>Manuelle Synchronisierung  
 Die .NET Framework-Klassenbibliothek stellt eine Reihe von Klassen zum Synchronisieren von Threads bereit. Weitere Informationen finden Sie unter [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## <a name="synchronized-code-regions"></a>Synchronisierte Codebereiche  
 Sie können die <xref:System.Threading.Monitor> Klasse oder ein Compilerschlüsselwort Codeblöcke, Instanzmethoden und statischen Methoden zu synchronisieren. Es gibt keine Unterstützung für synchronisierte statische Felder.  
  
 Visual Basic und C# unterstützen das Markieren von Codeblöcken mit einem bestimmten Sprachschlüsselwort, der `lock`-Anweisung in C# oder der `SyncLock`-Anweisung in Visual Basic. Wenn der Code von einem Thread ausgeführt wird, wird versucht, die Sperre abzurufen. Wenn die Sperre bereits von einem anderen Thread abgerufen wurde, wird der Thread blockiert, bis die Sperre verfügbar ist. Wenn der Thread den synchronisierten Codeblock beendet, wird die Sperre aufgehoben, unabhängig davon, wie der Thread den Block beendet.  
  
> [!NOTE]
>  Die `lock` und `SyncLock` Anweisungen werden mit implementiert <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> und <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>, sodass andere Methoden des <xref:System.Threading.Monitor> kann in Verbindung mit ihnen in der synchronisierten Bereich verwendet werden.  
  
 Sie können ein Methode auch mit einem **MethodImplAttribute** and **MethodImplOptions.Synchronized** verzieren, was die gleiche Auswirkung hat, wie **Monitor** oder ein anderes Compilerschlüsselwort zu verwenden, um den gesamten Rumpf der Methode zu sperren.  
  
 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>kann verwendet werden, um einen Thread aus blockierenden Vorgänge wie das Warten auf den Zugriff auf einen synchronisierten Codebereich. **Thread.Interrupt** dient außerdem zum Unterbrechen von Threads aus, wie z. B. <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Sperren Sie nicht den Typ – d.h. `typeof(MyType)` in C#, `GetType(MyType)` in Visual Basic oder `MyType::typeid` in C++ – um die `static`-Methoden zu schützen (`Shared`-Methoden in Visual Basic). Verwenden Sie stattdessen ein privates statisches Objekt. Verwenden Sie auch nicht `this` in C# (`Me` in Visual Basic), um Instanzmethoden zu sperren. Verwenden Sie stattdessen ein privates Objekt. Eine Klasse oder Instanz kann von einem anderen Code als Ihrem eigenen gesperrt werden, was potenziell zu Deadlocks oder Leistungsproblemen führt.  
  
### <a name="compiler-support"></a>Compilerunterstützung  
 Visual Basic- und c# unterstützt ein Schlüsselwort, das verwendet <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> und <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> auf Sperrung des Objekts. Visual Basic unterstützt die [SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md)-Anweisung und C# unterstützt die [lock](~/docs/csharp/language-reference/keywords/lock-statement.md)-Anweisung.  
  
 Wenn eine Ausnahme im Codeblock ausgelöst wird, wird in beiden Fällen die Sperre, die durch **lock** oder **SyncLock** erstellt wurde, automatisch aufgehoben. Die C#- und Visual Basic-Compiler geben einen **try**/**finally**-Block mit **Monitor.Enter** zu Beginn des Versuchs und **Monitor.Exit** im **finally**-Block aus. Wenn eine Ausnahme innerhalb eines **lock**- oder **SyncLock**-Blocks ausgelöst wird, wird der **finally**-Handler ausgeführt, damit Sie notwendige Bereinigungen ausführen können.  
  
## <a name="synchronized-context"></a>Synchronisierter Kontexte  
 Können Sie das **SynchronizationAttribute** auf **ContextBoundObject** verwenden, um alle Instanzmethoden und Felder zu synchronisieren Alle Objekte in der gleichen Kontextdomäne teilen die gleiche Sperre. Mehrere Threads können auf die Methoden und Felder zugreifen, jedoch ist nur ein einzelner Thread gleichzeitig zulässig.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>  
 [Threads and Threading (Threads und Threading)](../../../docs/standard/threading/threads-and-threading.md)  
 [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 [SyncLock-Anweisung](~/docs/visual-basic/language-reference/statements/synclock-statement.md)  
 [lock-Anweisung](~/docs/csharp/language-reference/keywords/lock-statement.md)
