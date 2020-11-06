---
title: Datensynchronisierung für Multithreading
description: Informationen zum Synchronisieren von Daten zum Multithreading in .NET Wählen Sie Strategien wie synchronisierte Coderegionen, die manuelle Synchronisierung oder synchronisierte Kontexte aus.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET], synchronizing threads
- managed threading
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
ms.openlocfilehash: 63ee85f3d8bab865ce34566ec381d23676b27991
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188587"
---
# <a name="synchronizing-data-for-multithreading"></a>Datensynchronisierung für Multithreading

Wenn mehrere Threads die Eigenschaften und Methoden eines einzelnen Objekts aufrufen können, ist es wichtig, dass diese Aufrufe synchronisiert werden. Andernfalls kann ein Thread möglicherweise die Aufgabe eines anderen Threads unterbrechen, und das Objekt bleibt womöglich in einem ungültigen Status zurück. Eine Klasse, deren Mitglieder vor solchen Unterbrechungen geschützt, wird threadsicher genannt.  
  
.NET stellt verschiedene Strategien zum Synchronisieren des Zugriffs auf Instanzmember und statische Member bereit:  
  
- Synchronisierte Codebereiche. Sie können die <xref:System.Threading.Monitor>-Klasse oder die Compilerunterstützung für diese Klasse zum Synchronisieren von einzig und allein dem Codeblock verwenden, der sie benötigt, wobei die Leistung verbessert wird.  
  
- Manuelle Synchronisierung Sie können die von der .NET-Klassenbibliothek bereitgestellten Synchronisierungsobjekte verwenden. Unter [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md) finden Sie weitere Informationen, darunter eine Beschreibung der <xref:System.Threading.Monitor>-Klasse.  
  
- Synchronisierte Kontexte. Sie können die <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>-Klasse nur im Zusammenhang mit .NET Framework- und Xamarin-Anwendungen verwenden, um eine einfache automatische Synchronisierung für <xref:System.ContextBoundObject>-Objekte zu ermöglichen.  
  
- Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace. Diese Klassen stellen integrierte synchronisierte Hinzufüge- und Entfernungsvorgänge bereit. Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../collections/thread-safe/index.md).  
  
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
 Die .NET-Klassenbibliothek stellt eine Reihe von Klassen zum Synchronisieren von Threads bereit. Weitere Informationen finden Sie unter [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md).  
  
## <a name="synchronized-code-regions"></a>Synchronisierte Codebereiche  
 Sie können die <xref:System.Threading.Monitor>-Klasse oder ein Compilerschlüsselwort zur Synchronisierung von Codeblöcken, Instanzmethoden und statischen Methoden verwenden. Es gibt keine Unterstützung für synchronisierte statische Felder.  
  
 Visual Basic und C# unterstützen das Markieren von Codeblöcken mit einem bestimmten Sprachschlüsselwort, der `lock`-Anweisung in C# oder der `SyncLock`-Anweisung in Visual Basic. Wenn der Code von einem Thread ausgeführt wird, wird versucht, die Sperre abzurufen. Wenn die Sperre bereits von einem anderen Thread abgerufen wurde, wird der Thread blockiert, bis die Sperre verfügbar ist. Wenn der Thread den synchronisierten Codeblock beendet, wird die Sperre aufgehoben, unabhängig davon, wie der Thread den Block beendet.  
  
> [!NOTE]
> Die `lock`- und `SyncLock`-Anweisung werden mit <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> und <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>implementiert, sodass andere Methoden von <xref:System.Threading.Monitor> in Verbindung mit ihnen im synchronisierten Bereich verwendet werden können.  
  
 Sie können eine Methode auch mit einem <xref:System.Runtime.CompilerServices.MethodImplAttribute>-Element mit dem Wert <xref:System.Runtime.CompilerServices.MethodImplOptions.Synchronized?displayProperty=nameWithType> versehen. Dies hat die gleiche Auswirkung wie die Verwendung von <xref:System.Threading.Monitor> oder von einem der Compilerschlüsselwörter zum Sperren des gesamten Texts der Methode.  
  
 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> kann verwendet werden, um einen Thread aus blockierten Vorgängen zu unterbrechen, wie z.B. das Warten auf Zugriff auf einen synchronisierten Codebereich. **Thread.Interrupt** dient außerdem zum Unterbrechen von Threads von Vorgängen wie <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> aus.  
  
> [!IMPORTANT]
> Sperren Sie nicht den Typ – d.h. `typeof(MyType)` in C#, `GetType(MyType)` in Visual Basic oder `MyType::typeid` in C++ – um die `static`-Methoden zu schützen (`Shared`-Methoden in Visual Basic). Verwenden Sie stattdessen ein privates statisches Objekt. Verwenden Sie auch nicht `this` in C# (`Me` in Visual Basic), um Instanzmethoden zu sperren. Verwenden Sie stattdessen ein privates Objekt. Eine Klasse oder Instanz kann von einem anderen Code als Ihrem eigenen gesperrt werden, was potenziell zu Deadlocks oder Leistungsproblemen führt.  
  
### <a name="compiler-support"></a>Compilerunterstützung  
 Visual Basic und C# unterstützen ein Sprachschlüsselwort, das <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> und <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> zum Sperren des Objekts verwendet. Visual Basic unterstützt die [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md)-Anweisung und C# unterstützt die [lock](../../csharp/language-reference/keywords/lock-statement.md)-Anweisung.  
  
 Wenn eine Ausnahme im Codeblock ausgelöst wird, wird in beiden Fällen die Sperre, die durch **lock** oder **SyncLock** erstellt wurde, automatisch aufgehoben. Die C#- und Visual Basic-Compiler geben einen **try**/**finally** -Block mit **Monitor.Enter** zu Beginn des Versuchs und **Monitor.Exit** im **finally** -Block aus. Wenn eine Ausnahme innerhalb eines **lock** - oder **SyncLock** -Blocks ausgelöst wird, wird der **finally** -Handler ausgeführt, damit Sie notwendige Bereinigungen ausführen können.  
  
## <a name="synchronized-context"></a>Synchronisierter Kontexte  

Ausschließlich in .NET Framework- und Xamarin-Anwendungen können Sie das <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>-Element für beliebige <xref:System.ContextBoundObject>-Elemente verwenden, um alle Instanzmethoden und -felder zu synchronisieren. Alle Objekte in der gleichen Kontextdomäne teilen die gleiche Sperre. Mehrere Threads können auf die Methoden und Felder zugreifen, jedoch ist nur ein einzelner Thread gleichzeitig zulässig.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>
- [Threads and Threading (Threads und Threading)](threads-and-threading.md)
- [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md)
- [SyncLock-Anweisung](../../visual-basic/language-reference/statements/synclock-statement.md)
- [lock-Anweisung](../../csharp/language-reference/keywords/lock-statement.md)
