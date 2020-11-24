---
title: Übersicht über Synchronisierungsprimitive
description: Erfahren Sie mehr über .NET-Threadsynchronisierungsprimitive zum Synchronisieren des Zugriffs auf eine freigegebene Ressource oder die Steuerthreadinteraktion.
ms.date: 10/01/2018
helpviewer_keywords:
- synchronization, threads
- threading [.NET],synchronizing threads
- managed threading
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
ms.openlocfilehash: 9dfaaa6050cc6e9a6b86f991aa6d2ce2a815959a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819655"
---
# <a name="overview-of-synchronization-primitives"></a>Übersicht über Synchronisierungsprimitive

.NET bietet eine Reihe von Typen, mit denen Sie den Zugriff auf eine freigegebene Ressource synchronisieren oder die Threadinteraktion koordinieren können.

> [!IMPORTANT]
> Verwenden Sie die gleiche Synchronisierungsprimitivinstanz, um den Zugriff einer freigegebenen Ressource zu schützen. Wenn Sie verschiedene Synchronisierungsprimitivinstanzen verwenden, um dieselbe Ressource zu schützen, umgehen Sie den Schutz, der von einem Synchronisierungsprimitive bereitgestellt wird.

## <a name="waithandle-class-and-lightweight-synchronization-types"></a>WaitHandle-Klasse und einfache Synchronisierungstypen

Von der <xref:System.Threading.WaitHandle?displayProperty=nameWithType>-Klasse werden mehrere .NET-Synchronisierungsprimitive abgeleitet, die ein natives Handle für die Betriebssystemsynchronisierung kapselt, und einen Signalmechanismus für die Threadinteraktion verwendet. Diese Klassen umfassen:

- <xref:System.Threading.Mutex?displayProperty=nameWithType> gewährt exklusiven Zugriff auf eine freigegebene Ressource. Der Zustand eines Mutex wird signalisiert, wenn er nicht in Besitz eines Threads ist.
- <xref:System.Threading.Semaphore?displayProperty=nameWithType> schränkt die Anzahl von Threads ein, die gleichzeitig auf eine freigegebene Ressource oder einen Pool von Ressourcen zugreifen können. Der Status eines Semaphors wird auf „signalisiert“ festgelegt, wenn die Anzahl größer als Null ist, bzw. wird auf „nicht signalisiert“ gesetzt, wenn die Anzahl Null ist.
- <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> stellt ein Threadsynchronisierungsereignis dar und kann sich entweder in einem signalisierten oder nicht signalisierten Zustand befinden.
- <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> wird aus <xref:System.Threading.EventWaitHandle> abgeleitet und wird nach der Freigabe eines einzelnen wartenden Threads automatisch in einen nicht signalisierten Zustand zurückgesetzt, wenn einen Signalisierung eintritt.
- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> wird aus <xref:System.Threading.EventWaitHandle> abgeleitet bleibt bei einer Signalisierung in einem signalisierten Zustand, bis die <xref:System.Threading.EventWaitHandle.Reset%2A>-Methode aufgerufen wird.

Da <xref:System.Threading.WaitHandle> aus <xref:System.MarshalByRefObject?displayProperty=nameWithType> abgeleitet wird, können diese Typen im .NET Framework verwendet werden, um die Aktivitäten von Threads über Anwendungsdomänengrenzen hinweg zu synchronisieren.

Im .NET Framework, in .NET Core und in .NET 5 oder höheren Versionen können einige dieser Typen benannte Systemsynchronisierungshandles darstellen, die im gesamten Betriebssystem sichtbar sind und die für die prozessübergreifende Synchronisierung verwendet werden können:

- <xref:System.Threading.Mutex>
- <xref:System.Threading.Semaphore> (unter Windows)
- <xref:System.Threading.EventWaitHandle> (unter Windows)

Weitere Informationen finden Sie in der Referenz für die <xref:System.Threading.WaitHandle>-API.

Einfache Synchronisierungstypen basieren nicht auf zugrunde liegende Betriebssystemhandles und bieten in der Regel eine bessere Leistung. Allerdings können sie nicht für die prozessübergreifende Synchronisierung verwendet werden. Verwenden Sie diese Typen für die Threadsynchronisierung innerhalb einer Anwendung.

Einige dieser Typen stellen Alternativen zu den aus <xref:System.Threading.WaitHandle> abgeleiteten Typen dar. Beispielsweise ist <xref:System.Threading.SemaphoreSlim> eine einfache Alternative zu <xref:System.Threading.Semaphore>.

## <a name="synchronization-of-access-to-a-shared-resource"></a>Synchronisieren des Zugriffs auf eine freigegebene Ressource

.NET stellt eine Reihe von Synchronisierungsprimitiven zum Steuern des Zugriffs auf eine freigegebene Ressource von mehreren Threads bereit.

### <a name="monitor-class"></a>Monitor-Klasse

Die <xref:System.Threading.Monitor?displayProperty=nameWithType>-Klasse gewährt den gegenseitig exklusiven Zugriff auf eine freigegebene Ressource, indem sie eine Sperre für das Objekt, das die Ressource identifiziert, abruft oder aufhebt. Während eine Sperre aufrechterhalten wird, kann der Thread, der die Sperre aufrechterhält, die Sperre abrufen und aufheben. Für jeden anderen Thread wird das Abrufen der Sperre blockiert, und die <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>-Methode wartet auf die Aufhebung. Die <xref:System.Threading.Monitor.Enter%2A>-Methode ruft eine freigegebene Sperre ab. Sie können die <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>-Methode auch verwenden, um die Zeitspanne anzugeben, in der ein Thread versucht, eine Sperre abzurufen. Da die <xref:System.Threading.Monitor>-Klasse Threadaffinität hat, muss der Thread, der eine Sperre erhalten hat, die Sperre durch Aufruf der <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>-Methode freigeben.

Sie können die Interaktion von Threads, die eine Sperre für dasselbe Objekt erhalten, mit den Methoden <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> und <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> koordinieren.

Weitere Informationen finden Sie in der Referenz für die <xref:System.Threading.Monitor>-API.

> [!NOTE]
> Verwenden Sie die [lock](../../csharp/language-reference/keywords/lock-statement.md)-Anweisung in C# und die [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md)-Anweisung in Visual Basic, um den Zugriff auf eine freigegebene Ressource zu synchronisieren, anstatt die <xref:System.Threading.Monitor>-Klasse direkt zu verwenden. Die Anweisungen werden mithilfe der <xref:System.Threading.Monitor.Enter%2A>- und <xref:System.Threading.Monitor.Exit%2A>-Methoden implementiert und verwenden den `try…finally`-Block, um sicherzustellen, dass die erhaltene Sperre aufgehoben wird.

### <a name="mutex-class"></a>Mutex-Klasse

Die <xref:System.Threading.Mutex?displayProperty=nameWithType>-Klasse gewährt wie <xref:System.Threading.Monitor> exklusiven Zugriff auf eine freigegebene Ressource. Verwenden Sie eine der [Mutex.WaitOne](<xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>)-Methodenüberladungen, um den Besitz eines Mutex anzufordern. Wie <xref:System.Threading.Monitor> hat auch <xref:System.Threading.Mutex> Threadaffinität und der Thread, der eine Mutex erworben hat, muss diesen durch den Aufruf der <xref:System.Threading.Mutex.ReleaseMutex%2A?displayProperty=nameWithType>-Methode freigeben.

Im Gegensatz zu <xref:System.Threading.Monitor> kann die <xref:System.Threading.Mutex>-Klasse für die prozessübergreifende Synchronisierung verwendet werden. Verwenden Sie dazu einen benannten Mutex, der im gesamten Betriebssystem sichtbar ist. Verwenden Sie zum Erstellen einer benannten Mutexinstanz einen [Mutex-Konstruktor](<xref:System.Threading.Mutex.%23ctor%2A>), der einen Namen angibt. Sie können auch die <xref:System.Threading.Mutex.OpenExisting%2A?displayProperty=nameWithType>-Methode aufrufen, um ein vorhandenes benanntes Systemmutex zu öffnen.
  
Weitere Informationen finden Sie im Artikel [Mutexe](mutexes.md) und in der Referenz zur <xref:System.Threading.Mutex>-API.

### <a name="spinlock-structure"></a>SpinLock-Struktur

Die <xref:System.Threading.SpinLock?displayProperty=nameWithType>-Struktur gewährt wie <xref:System.Threading.Monitor> exklusiven Zugriff auf eine freigegebene Ressource, basierend auf der Verfügbarkeit einer Sperre. Wenn <xref:System.Threading.SpinLock> versucht, eine nicht verfügbare Sperre zu erhalten, wartet sie in einer Schleife und überprüft wiederholt, ob die Sperre verfügbar ist.

Weitere Informationen zu den Vor- und Nachteilen der Verwendung von SpinLock finden Sie im [SpinLock](spinlock.md)-Artikel und in der Referenz zur <xref:System.Threading.SpinLock>-API.

### <a name="readerwriterlockslim-class"></a>ReaderWriterLockSlim-Klasse

Die <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType>-Klasse gewährt exklusiven Schreibzugriff auf eine freigegebene Ressource und ermöglicht es mehreren Threads, gleichzeitig zum Lesen auf die Ressource zuzugreifen. Möglicherweise möchten Sie <xref:System.Threading.ReaderWriterLockSlim> verwenden, um den Zugriff auf eine freigegebene Datenstruktur zu synchronisieren, die threadsichere Lesevorgänge unterstützt, aber exklusiven Zugriff für die Durchführung von Schreibvorgängen benötigt. Wenn ein Thread exklusiven Zugriff anfordert (z.B. durch Aufrufen der <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A?displayProperty=nameWithType>-Methode), werden nachfolgende Writeranforderungen blockiert, bis alle vorhandenen Reader die Sperre beendet haben und der Writer die Sperre aktiviert und beendet hat.
  
Weitere Informationen finden Sie in der Referenz für die <xref:System.Threading.ReaderWriterLockSlim>-API.

### <a name="semaphore-and-semaphoreslim-classes"></a>Semaphore- und SemaphoreSlim-Klassen

Die <xref:System.Threading.Semaphore?displayProperty=nameWithType>- und <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>-Klassen schränken die Anzahl von Threads ein, die gleichzeitig auf eine freigegebene Ressource oder einen Pool von Ressourcen zugreifen können. Zusätzliche Threads, die die Ressource anfordern, warten, bis ein Thread das Semaphor freigibt. Da das Semaphor keine Threadaffinität hat, kann ein Thread das Semaphor erhalten und ein anderer kann es freigeben.

<xref:System.Threading.SemaphoreSlim> ist eine einfache Alternative zu <xref:System.Threading.Semaphore> und kann nur für die Synchronisierung innerhalb einer einzelnen Prozessgrenze verwendet werden.

Unter Windows können Sie <xref:System.Threading.Semaphore> für die prozessübergreifende Synchronisierung verwenden. Erstellen Sie dafür eine <xref:System.Threading.Semaphore>-Instanz, die ein benanntes Systemsemaphor darstellt, indem Sie einen der [Semaphorskonstruktoren](<xref:System.Threading.Semaphore.%23ctor%2A>) verwenden, die einen Namen oder die <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType>-Methode angeben. <xref:System.Threading.SemaphoreSlim> unterstützt keine benannten Systemsemaphoren.

Weitere Informationen finden Sie im Artikel [Semaphore und SemaphoreSlim](semaphore-and-semaphoreslim.md) und in der Referenz zur <xref:System.Threading.Semaphore>- oder <xref:System.Threading.SemaphoreSlim>-API.

## <a name="thread-interaction-or-signaling"></a>Threadinteraktionen oder -signalisierung

Threadinteraktionen (oder Threadsignalisierung) bedeutet, dass ein Thread zum Fortsetzen des Vorgangs auf eine Benachrichtigung oder ein Signal von einem oder mehreren Threads warten muss. Wenn beispielsweise Thread A die <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>-Methode von Thread B aufruft, wird Thread A blockiert, bis Thread B abgeschlossen ist. Die im vorhergehenden Abschnitt beschriebenen Synchronisierungsprimitive bieten einen anderen Mechanismus für die Signalisierung: Durch die Freigabe einer Sperre benachrichtigt ein Thread einen anderen Thread, dass er durch den Erhalt der Sperre fortgesetzt werden kann.

Dieser Abschnitt beschreibt zusätzliche Signalisierungskonstrukte, die von .NET bereitgestellt werden.

### <a name="eventwaithandle-autoresetevent-manualresetevent-and-manualreseteventslim-classes"></a>EventWaitHandle-, AutoResetEvent-, ManualResetEvent- und ManualResetEventSlim-Klassen

Die <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>-Klasse stellt ein Threadsynchronisierungsereignis dar.

Ein Synchronisierungsereignis kann entweder in einem nicht signalisierten oder signalisierten Zustand sein. Wenn der Zustand eines Ereignisses nicht signalisiert ist, wird ein Thread, der die <xref:System.Threading.WaitHandle.WaitOne%2A?>-Überladung des Ereignisses aufruft, blockiert, bis ein Ereignis signalisiert wird. Die <xref:System.Threading.EventWaitHandle.Set%2A?displayProperty=nameWithType> Methode legt den Zustand eines Ereignisses auf „signalisiert“ fest.

Das Verhalten einer signalisierten <xref:System.Threading.EventWaitHandle> hängt von den Zurücksetzmodus ab:

- Eine mit der <xref:System.Threading.EventWaitHandle>-Flag erstellten <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> wird nach der Freigabe eines einzelnen wartenden Threads automatisch zurückgesetzt. Es ist wie ein Drehkreuz, das bei jeder Signalisierung nur einen Thread durchlässt. Die <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>-Klasse, die von <xref:System.Threading.EventWaitHandle> abgeleitet wird, stellt dieses Verhalten dar.
- Eine mit der <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType>-Flag erstellte <xref:System.Threading.EventWaitHandle.Reset%2A> bleibt so lange ein Signal, bis die <xref:System.Threading.EventWaitHandle>-Methode aufgerufen wird. Es ist wie ein Tor, das bis zum Signal geschlossen wird und dann offen bleibt, bis es jemand schließt. Die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse, die von <xref:System.Threading.EventWaitHandle> abgeleitet wird, stellt dieses Verhalten dar. Die <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>-Klasse ist eine einfache Alternative zu <xref:System.Threading.ManualResetEvent>.

Unter Windows können Sie <xref:System.Threading.EventWaitHandle> für die prozessübergreifende Synchronisierung verwenden. Erstellen Sie dafür eine <xref:System.Threading.EventWaitHandle>-Instanz, die ein benanntes Systemsynchronisierungsereignis darstellt, indem Sie einen der [EventWaitHandle-Konstruktoren](<xref:System.Threading.EventWaitHandle.%23ctor%2A>) verwenden, die einen Namen oder die <xref:System.Threading.EventWaitHandle.OpenExisting%2A?displayProperty=nameWithType>-Methode angeben.

Weitere Informationen finden Sie im Artikel [EventWaitHandle](eventwaithandle.md). Die API-Referenz finden Sie unter <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.AutoResetEvent>, <xref:System.Threading.ManualResetEvent> und <xref:System.Threading.ManualResetEventSlim>.

### <a name="countdownevent-class"></a>CountdownEvent-Klasse

Die <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>-Klasse stellt ein Ereignis dar, das festgelegt wird, wenn die Anzahl null ist. Wenn <xref:System.Threading.CountdownEvent.CurrentCount?displayProperty=nameWithType> größer als Null ist, wird ein Thread, der <xref:System.Threading.CountdownEvent.Wait%2A?displayProperty=nameWithType> abruft, blockiert. Rufen Sie <xref:System.Threading.CountdownEvent.Signal%2A?displayProperty=nameWithType> auf, um die Anzahl eines Ereignisses zu verringern.

Im Gegensatz zu <xref:System.Threading.ManualResetEvent> oder <xref:System.Threading.ManualResetEventSlim>, mit denen Sie mehrere Threads mit einem Signal von einem Thread entsperren können, können Sie mit <xref:System.Threading.CountdownEvent> einen oder mehrere Threads mit Signalen von mehreren Threads entsperren.

Weitere Informationen finden Sie im Artikel [CountdownEvent](countdownevent.md) und in der Referenz zur <xref:System.Threading.CountdownEvent>-API.

### <a name="barrier-class"></a>Barrier-Klasse

Die <xref:System.Threading.Barrier?displayProperty=nameWithType> Klasse stellt eine Barriere zur Threadausführung dar. Ein Thread, der die <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType>-Methode aufruft, signalisiert, dass er die Barriere erreicht hat und wartet, bis andere teilnehmenden Threads die Barriere erreichen. Wenn alle teilnehmenden Threads die Barriere erreichen, werden sie weiter ausgeführt, und die Barriere wird zurückgesetzt und kann wieder verwendet werden.

Sie können <xref:System.Threading.Barrier> verwenden, wenn ein oder mehrere Threads die Ergebnisse anderer Threads benötigen, bevor Sie mit der nächsten Berechnungsphase fortfahren.

Weitere Informationen finden Sie im Artikel [Barriere](barrier.md) und in der Referenz zur <xref:System.Threading.Barrier>-API.

## <a name="interlocked-class"></a>Interlocked-Klasse

Die <xref:System.Threading.Interlocked?displayProperty=nameWithType>-Klasse stellt statische Methoden zur Verfügung, die einfache atomare Operationen an einer Variablen durchführen. Diese atomaren Operationen umfassen Addition, Inkrementieren und Dekrementieren, Austausch, bedingter Austausch je nach Vergleich und Lesevorgänge für einen 64-Bit-Ganzzahlenwert.

Weitere Informationen finden Sie in der Referenz für die <xref:System.Threading.Interlocked>-API.

## <a name="spinwait-structure"></a>SpinWait-Struktur

Die <xref:System.Threading.SpinWait?displayProperty=nameWithType>-Struktur stellt Unterstützung für Spin-basierte Wartevorgänge bereit. Sie können die Struktur verwenden, wenn ein Thread warten muss, bis ein Ereignis signalisiert oder eine Bedingung erfüllt wird, außer wenn die tatsächliche Wartezeit voraussichtlich kürzer als die erforderliche Wartezeit beim Verwenden eines Wait-Handles oder einer anderen Blockierung des Threads ist. Mithilfe von <xref:System.Threading.SpinWait> können Sie einen kurzen Wartezeitraum angeben und danach nur dann auslösen (z. B. durch Warten oder Ruhezustand), wenn die Bedingung nicht in der angegebenen Zeit erfüllt wurde.

Weitere Informationen finden Sie im Artikel [SpinWait](spinwait.md) und in der Referenz zur <xref:System.Threading.SpinWait>-API.

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Threadsichere Sammlungen](../collections/thread-safe/index.md)
- [Threadingobjekte und -funktionen](threading-objects-and-features.md)
