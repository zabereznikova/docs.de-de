---
title: Empfohlene Vorgehensweisen für die Zuverlässigkeit
ms.date: 03/30/2017
helpviewer_keywords:
- marking locks
- rebooting databases
- denial of service attacks
- back-out code
- SQL Server [.NET Framework], reliability
- synchronization, reliability
- single-threaded COM components
- slow leaks
- suspending threads
- asynchronous exception handling
- leaked resources [.NET Framework]
- unmanaged memory
- memory, reliability
- threading [.NET Framework], reliability
- process-wide domain shared states
- shared states
- SafeHandle class, reliability
- reliability contracts [.NET Framework]
- cleanup operations
- constrained execution regions
- CERs
- finalizers, reliability
- reliability [.NET Framework]
- blocks, reliability
- finally clauses
- cross-application domain shared states
- catch blocks
- identifying locks
- writing reliable code
- impersonation
- GC.KeepAlive method
- managed threading
- locks, reliability
- STA-dependent features
- fibers
ms.assetid: cf624c1f-c160-46a1-bb2b-213587688da7
ms.openlocfilehash: bd51ea1b79ac1dbd89a862f3961cc8508a87f301
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715980"
---
# <a name="reliability-best-practices"></a>Empfohlene Vorgehensweisen für die Zuverlässigkeit

Die folgenden Zuverlässigkeitsregeln sind auf SQL Server ausgerichtet, jedoch gelten sie auch für jede hostbasierte Serveranwendung. Es ist äußerst wichtig, dass es bei Servern wie SQL Server zu keinem Ressourcenverlust kommt und dass diese nicht zum Absturz gebracht werden.  Dies kann jedoch nicht erreicht werden, indem Zurücksetzungscode für jede Methode geschrieben wird, die den Zustand eines Objekts ändert.  Das Ziel ist nicht, 100 Prozent zuverlässigen verwalteten Code zu schreiben, der mit Zurücksetzungscode nach Fehlern an einer beliebigen Stelle wiederhergestellt wird.  Das wäre eine schwierige Aufgabe mit wenig Aussicht auf Erfolg.  Die Common Language Runtime (CLR) kann keine ausreichend starken Garantien für verwalteten Code bereitstellen, um das Schreiben von perfektem Code möglich zu machen.  Beachten Sie, dass SQL Server im Gegensatz zu ASP.NET nur einen Prozess verwendet, der nicht wiederverwendet werden kann, ohne dass eine Datenbank für eine unzumutbar lange Zeit außer Betrieb genommen wird.

Mit diesen schwächeren Garantien und der Ausführung in einem einzelnen Prozess basiert die Zuverlässigkeit auf dem Beenden von Threads oder ggf. dem Wiederverwenden von Anwendungsdomänen sowie dem Ergreifen von Vorsichtsmaßnahmen, um sicherzustellen, dass Betriebssystemressourcen wie Handles oder Arbeitsspeicher nicht verloren gehen.  Selbst mit dieser einfacheren Zuverlässigkeitseinschränkung bestehen immer noch erhebliche Zuverlässigkeitsanforderungen:

- Betriebssystemressourcen dürfen niemals verloren gehen.

- Alle verwalteten Sperren für die CLR müssen identifiziert werden.

- Ein anwendungsdomänenübergreifender freigegebener Zustand darf niemals unterbrochen werden, damit das Wiederverwenden von <xref:System.AppDomain> reibungslos funktioniert.

Obwohl es theoretisch möglich ist, verwalteten Code zu schreiben, um <xref:System.Threading.ThreadAbortException>-, <xref:System.StackOverflowException>- und <xref:System.OutOfMemoryException>-Ausnahmen zu behandeln, kann von Entwicklern nicht erwartet werden, derart stabilen Code für die gesamte Anwendung schreiben.  Aus diesem Grund führen Out-of-band-Ausnahmen dazu, dass der ausführende Thread beendet wird. Wenn der beendete Thread einen Freigabezustand geändert hat, was dadurch ermittelt werden kann, ob im Thread eine Sperre enthalten ist, wird <xref:System.AppDomain> nicht geladen.  Wenn eine Methode, die einen freigegebenen Zustand ändert, beendet wird, ist der Zustand inkonsistent, da es nicht möglich ist, verlässlichen Zurücksetzungscode zu schreiben, um den Freigabezustand zu aktualisieren.

In der Version 2.0 von .NET Framework ist SQL Server der einzige Host, der Zuverlässigkeit erfordert.  Wenn Ihre Assembly auf SQL Server ausgeführt wird, sollten Sie Zuverlässigkeit für jeden Teil dieser Assembly gewährleisten, selbst wenn bestimmte Funktionen vorhanden sind, die bei der Ausführung in der Datenbank deaktiviert werden.  Dies ist erforderlich, da die Codeanalyse-Engine Code auf Assemblyebene untersucht und nicht von deaktiviertem Code unterscheiden kann. Eine andere Überlegung bei der SQL Server-Programmierung ist, dass SQL Server alles in einem Prozess ausführt. Außerdem wird die <xref:System.AppDomain>-Wiederverwendung zur Bereinigung aller Ressourcen wie Arbeitsspeicher und Betriebssystemhandles verwendet.

Sie können sich nicht auf Finalizer, Destruktoren oder `try/finally`-Blöcke für Zurücksetzungscode verlassen. Diese können unterbrochen oder nicht aufgerufen werden.

Asynchrone Ausnahmen wie <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> und <xref:System.OutOfMemoryException> können an unerwarteten Stellen und prinzipiell in jeder Computeranweisung auftreten.

Bei verwalteten Threads handelt es sich nicht notwendigerweise um Win32-Threads in SQL. Es kann sich auch um Fibers handeln.

Ein prozess- oder anwendungsdomänenübergreifender veränderlicher Freigabezustand lässt sich nur mit großem Aufwand sicher verändern und sollte wenn möglich vermieden werden.

Probleme aufgrund von nicht ausreichendem Arbeitsspeicher sind in SQL Server nicht selten.

Wenn in SQL Server gehostete Bibliotheken ihren Freigabezustand nicht ordnungsgemäß aktualisieren, ist die Wahrscheinlichkeit hoch, dass der Code nicht wiederhergestellt wird, bis die Datenbank neu gestartet wird.  Zudem ist es in einigen Extremfällen möglich, dass dadurch beim SQL Server-Prozess ein Fehler auftritt, wodurch die Datenbank neu gestartet wird.  Ein Neustart der Datenbank kann zum Absturz einer Website führen oder sich auf Unternehmensvorgänge auswirken, wobei die Verfügbarkeit beeinträchtigt wird.  Ein langsamer Verlust von Betriebssystemressourcen wie Arbeitsspeicher oder Handles kann dazu führen, dass beim Server ein Fehler auftritt, wobei Handles ohne Möglichkeit zur Wiederherstellung zugewiesen werden. Möglicherweise kann auch die Leistung des Servers langsam abnehmen, wobei die Verfügbarkeit der Anwendung eines Kunden reduziert wird.  Natürlich sollen diese Szenarios vermieden werden.

## <a name="best-practice-rules"></a>Best Practices-Regeln

In der Einführung wurde der Fokus darauf gelegt, auf welche Fehler im Code Review für den verwalteten Code, der auf dem Server ausgeführt wird, geprüft werden muss, um die Stabilität und Zuverlässigkeit des Frameworks zu verbessern. All diese Überprüfungen werden allgemein empfohlen und sind auf einem Server ein absolutes Muss.

Bei einem Deadlock oder einer Ressourceneinschränkung bricht SQL Server einen Thread ab oder entfernt eine <xref:System.AppDomain>.  In diesem Fall wird nur Zurücksetzungscode in einem eingeschränkten Ausführungsbereich (CER) garantiert ausgeführt.

### <a name="use-safehandle-to-avoid-resource-leaks"></a>Verwenden von SafeHandle zur Vermeidung von Ressourcenverlusten

Falls <xref:System.AppDomain> entladen wird, können Sie sich nicht auf die Ausführung von `finally`-Blöcken oder Finalizern verlassen. Daher ist es wichtig, den Zugriff auf alle Betriebssystemressourcen über die <xref:System.Runtime.InteropServices.SafeHandle>-Klasse anstatt über <xref:System.IntPtr>, <xref:System.Runtime.InteropServices.HandleRef> oder ähnliche Klassen zu abstrahieren. Dies ermöglicht der CLR, die von Ihnen verwendeten Handles selbst im Fall des Entfernens von <xref:System.AppDomain> nachzuverfolgen und zu schließen.  <xref:System.Runtime.InteropServices.SafeHandle> verwendet ein Objekt der Klasse CriticalFinalizerObject als Finalizer, der von der CLR immer ausgeführt wird.

Das Betriebssystemhandle wird vom Moment seiner Erstellung in einem SafeHandle bis zu dem Moment gespeichert, in dem es freigegeben wird.  Es gibt kein Zeitfenster, in dem eine <xref:System.Threading.ThreadAbortException> den Verlust eines Handles verursachen kann.  Darüber hinaus führt der Plattformaufruf eine Verweiszählung des Handles aus, was eine genaue Nachverfolgung der Lebenszeit des Handles ermöglicht. Hierdurch wird ein Sicherheitsproblem mit einer Racebedingung zwischen `Dispose` und einer Methode verhindert, die das Handle momentan verwendet.

Die meisten Klassen, die derzeit über einen Finalizer zum einfachen Bereinigen eines Betriebssystemhandles verfügen, werden den Finalizer nicht mehr benötigen. Stattdessen wird sich der Finalizer in der abgeleiteten <xref:System.Runtime.InteropServices.SafeHandle>-Klasse befinden.

Beachten Sie, dass <xref:System.Runtime.InteropServices.SafeHandle> kein Ersatz für <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> ist.  Es bestehen immer noch potenzielle Vorteile im Hinblick auf Ressourcenkonflikte und Leistung gegenüber dem expliziten Löschen von Betriebssystemressourcen.  Beachten Sie aber, dass `finally`-Blöcke, die Ressourcen explizit löschen, möglicherweise nicht vollständig ausgeführt werden.

<xref:System.Runtime.InteropServices.SafeHandle> ermöglicht es Ihnen, Ihre eigene <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Methode zu implementieren, die Anweisungen zum Freigeben des Handles ausführt. Beispiele für derartige Anweisungen sind das Übergeben des Zustands an eine Routine zur Freigabe von Betriebssystemhandles oder das Freigeben von mehreren Handles in einer Schleife.  Die CLR garantiert, dass diese Methode ausgeführt wird.  Es liegt in der Verantwortung des Erstellers der <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Implementierung, sicherzustellen, dass das Handle in allen Fällen freigegeben wird. Wird dies nicht sichergestellt, geht das Handle verloren, was oft dazu führt, dass native Ressourcen verloren gehen, die dem Handle zugewiesen sind. Daher ist es wichtig, abgeleitete <xref:System.Runtime.InteropServices.SafeHandle>-Klassen so zu strukturieren, dass die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Implementierung nicht die Zuordnung von Ressourcen erfordert, die zum Zeitpunkt des Aufrufs möglicherweise nicht verfügbar sind. Beachten Sie, dass es zulässig ist, Methoden aufzurufen, die möglicherweise innerhalb der Implementierung von <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> fehlschlagen, vorausgesetzt, Ihr Code kann mit solchen Fehlern umgehen und die Vereinbarung zum Freigeben des nativen Handles erfüllen. Für das Debuggen verfügt <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> über einen Rückgabewert vom Typ <xref:System.Boolean>, der auf `false` gesetzt werden kann, wenn ein schwerwiegender Fehler auftritt, der die Freigabe der Ressource verhindert. Auf diese Weise wird der MDA [releaseHandleFailed](../debug-trace-profile/releasehandlefailed-mda.md) aktiviert, um im aktivierten Zustand bei der Identifizierung des Problems zu helfen. Er wirkt sich auf keine andere Weise auf die Laufzeit aus. <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> wird nicht erneut für die dieselbe Ressource aufgerufen, und daher geht das Handle verloren.

<xref:System.Runtime.InteropServices.SafeHandle> ist in bestimmten Kontexten nicht geeignet.  Da die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Methode in einem <xref:System.GC>-Finalizerthread ausgeführt werden kann, sollten alle Handles, die in einem bestimmten Thread freigegeben werden müssen, nicht in eine <xref:System.Runtime.InteropServices.SafeHandle>-Klasse eingebunden sein.

Runtime Callable Wrapper (RCWs) können durch die CLR ohne zusätzlichen Code bereinigt werden.  Bei Code, der den Plattformaufruf verwendet und ein COM-Objekt als `IUnknown*` oder <xref:System.IntPtr> behandelt, muss der Code so umgeschrieben werden, dass er einen RCW verwendet.  <xref:System.Runtime.InteropServices.SafeHandle> ist für dieses Szenario möglicherweise nicht geeignet, da die Möglichkeit besteht, dass eine nicht verwaltete Freigabemethode einen Rückruf für den verwalteten Code ausführt.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Verwenden Sie <xref:System.Runtime.InteropServices.SafeHandle>, um Betriebssystemressourcen zu kapseln. Verwenden Sie nicht <xref:System.Runtime.InteropServices.HandleRef> oder Felder vom Typ <xref:System.IntPtr>.

### <a name="ensure-finalizers-do-not-have-to-run-to-prevent-leaking-operating-system-resources"></a>Stellen Sie sicher, dass Finalizer nicht ausgeführt werden müssen, um das Verlust von Betriebssystemressourcen zu verhindern.

Überprüfen Sie Ihre Finalizer sorgfältig, um sicherzustellen, dass eine wichtige Betriebssystemressource auch dann nicht verloren geht, wenn sie nicht ausgeführt werden.  Im Gegensatz zum normalen Entladen von <xref:System.AppDomain> werden Objekte während des unvorhergesehen Entladens von <xref:System.AppDomain> nicht finalisiert, wenn die Anwendung in einem stabilen Zustand ausgeführt wird oder wenn ein Server wie SQL Server heruntergefahren wird.  Stellen Sie sicher, dass Ressourcen im Fall eines plötzlichen Entladens nicht verloren gehen, da die korrekte Ausführung der Anwendung nicht garantiert werden kann, die Integrität des Servers jedoch erhalten werden muss, indem Ressourcen nicht verloren gehen.  Verwenden Sie <xref:System.Runtime.InteropServices.SafeHandle>, um Betriebssystemressourcen freizugeben.

### <a name="ensure-that-finally-clauses-do-not-have-to-run-to-prevent-leaking-operating-system-resources"></a>Stellen Sie sicher, dass keine Klauseln ausgeführt werden müssen, um das Verlust von Betriebssystemressourcen zu verhindern.

Für `finally`-Klauseln besteht keine Garantie, dass diese außerhalb von CERs ausgeführt werden, weshalb Bibliotheksentwickler sich nicht auf Code innerhalb eines `finally`-Blocks verlassen dürfen, um nicht verwaltete Ressourcen freizugeben.  Die empfohlene Lösung ist die Verwendung von <xref:System.Runtime.InteropServices.SafeHandle>.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Verwenden Sie <xref:System.Runtime.InteropServices.SafeHandle> anstatt `Finalize` zum Bereinigen von Betriebssystemressourcen. Verwenden Sie nicht <xref:System.IntPtr>, sondern <xref:System.Runtime.InteropServices.SafeHandle> zum Kapseln von Ressourcen. Wenn die finally-Klausel ausgeführt werden muss, platzieren Sie diese in einer CER.

### <a name="all-locks-should-go-through-existing-managed-locking-code"></a>Alle Sperren sollten vorhandenen verwalteten Sperr Code durchlaufen.

Der CLR muss bekannt sein, wann der Code gesperrt ist. So kann sichergestellt werden, dass die CLR die <xref:System.AppDomain> löscht, anstatt einfach den Thread abzubrechen.  Das Abbrechen des Threads könnte gefährlich sein, da die durch den Thread verarbeiteten Daten in einem inkonsistenten Zustand verbleiben könnten. Daher muss die gesamte <xref:System.AppDomain>-Klasse wiederverwendet werden.  Die Konsequenzen eines Fehlers beim Identifizieren einer Sperre können Deadlocks oder falsche Ergebnisse sein. Verwenden Sie die Methoden <xref:System.Threading.Thread.BeginCriticalRegion%2A> und <xref:System.Threading.Thread.EndCriticalRegion%2A>, um Sperrbereiche zu identifizieren.  Erstere sind statisch, befinden sich in der <xref:System.Threading.Thread>-Klasse und können nur auf den aktuellen Thread angewendet werden. Diese Methoden helfen dabei, zu verhindern, dass ein Thread die Sperrenanzahl eines anderen Threads bearbeitet.

In <xref:System.Threading.Monitor.Enter%2A> und <xref:System.Threading.Monitor.Exit%2A> ist diese CLR-Benachrichtigung integriert. Daher wird deren Verwendung und die Verwendung der [lock-Anweisung](../../csharp/language-reference/keywords/lock-statement.md) empfohlen, die diese Methoden verwendet.

Andere Sperrmechanismen wie Spinlocks und <xref:System.Threading.AutoResetEvent> müssen diese Methoden aufrufen, um die CLR darüber zu benachrichtigen, dass auf einen kritischen Bereich zugegriffen wird.  Diese Methoden verwenden keine Sperren. Sie informieren die CLR darüber, dass Code in einem kritischen Bereich ausgeführt wird und dass der Abbruch des Threads zu einem inkonsistenten Freigabezustand führen könnte.  Wenn Sie einen eigenen Sperrentyp wie z.B. eine benutzerdefinierte <xref:System.Threading.ReaderWriterLock>-Klasse definiert haben, verwenden Sie diese Methoden zur Berechnung der Sperrenanzahl.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Markieren und identifizieren Sie alle Sperren mithilfe von <xref:System.Threading.Thread.BeginCriticalRegion%2A> und <xref:System.Threading.Thread.EndCriticalRegion%2A>. Verwenden Sie nicht <xref:System.Threading.Interlocked.CompareExchange%2A>, <xref:System.Threading.Interlocked.Increment%2A> und <xref:System.Threading.Interlocked.Decrement%2A> in einer Schleife.  Führen Sie keinen Plattformaufruf der Win32-Varianten dieser Methoden aus.  Verwenden Sie <xref:System.Threading.Thread.Sleep%2A> nicht in einer Schleife.  Verwenden Sie keine flüchtigen Felder (volatile-Felder).

### <a name="cleanup-code-must-be-in-a-finally-or-a-catch-block-not-following-a-catch"></a>Der Bereinigungs Code muss sich in einem-Block oder einem catch-Block befinden, nicht nach einem catch

Bereinigungscode darf nie auf einen `catch`-Block folgen. Er sollte sich in einem `finally`-Block oder im `catch`-Block selbst befinden. Dies entspricht der üblichen Vorgehensweise. Ein `finally`-Block wird allgemein bevorzugt, da er den gleichen Code ausführt, wenn eine Ausnahme ausgelöst wird und wenn der Code am Ende des `try`-Blocks normal aufgerufen wird.  Wenn eine unerwartete Ausnahme ausgelöst wird, z.B. eine <xref:System.Threading.ThreadAbortException>, wird der Bereinigungscode nicht ausgeführt.  Nicht verwaltete Ressourcen, die Sie in einem `finally`-Block bereinigen würden, sollten idealerweise in einem Objekt der <xref:System.Runtime.InteropServices.SafeHandle>-Klasse gekapselt sein, um Verluste zu vermeiden.  Beachten Sie, dass das C#-Schlüsselwort `using` effektiv verwendet werden kann, um Objekte einschließlich Handles zu löschen.

Obwohl die Wiederverwendung von <xref:System.AppDomain> Ressourcen im Finalizerthread bereinigen kann, ist es dennoch wichtig, Bereinigungscode an der richtigen Stelle zu platzieren. Wenn ein Thread eine asynchrone Ausnahme empfängt, ohne eine Sperre zu verwenden, sollten Sie beachten, dass die CLR versucht, den Thread selbst zu beenden, ohne <xref:System.AppDomain> wiederherstellen zu müssen.  Indem sichergestellt wird, dass Ressourcen besser früh als spät bereinigt werden, können mehr Ressourcen verfügbar gemacht und die Lebensdauer besser verwaltet werden. Wenn Sie einen Handle nicht explizit für eine Datei in einem Fehlercodepfad schließen, warten Sie darauf, dass der <xref:System.Runtime.InteropServices.SafeHandle>-Finalizer ihn bereinigt. Wenn Ihr Code das nächste Mal ausgeführt wird, tritt möglicherweise ein Fehler beim dem Versuch auf, auf dieselbe Datei zuzugreifen, falls der Finalizer nicht bereits ausgeführt wurde.  Aus diesem Grund hilft das Sicherstellen, dass Bereinigungscode vorhanden ist und korrekt funktioniert, dabei, dass die Wiederherstellung nach Fehlern besser und schneller erfolgt, obwohl es nicht unbedingt erforderlich ist.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Bereinigungscode nach einem `catch`-Block muss sich in einem `finally`-Block befinden. Platzieren Sie Aufrufe zum Löschen in einem finally-Block. `catch`-Blöcke sollten abschließend Ausnahmen auslösen bzw. neu auslösen. Es werden Ausnahmen auftreten, z.B. Code, der ermittelt, ob eine Netzwerkverbindung eingerichtet werden kann, wobei Sie eine große Anzahl von Ausnahmen erhalten könnten. Dennoch sollte jeder Code, der das Abfangen einer Reihe von Ausnahmen unter normalen Bedingungen erfordert, darauf hinweisen, dass der Code getestet werden sollte, um herauszufinden, ob er erfolgreich sein wird.

### <a name="process-wide-mutable-shared-state-between-application-domains-should-be-eliminated-or-use-a-constrained-execution-region"></a>Prozess weiter änderbarer Freigabe Zustand zwischen Anwendungs Domänen muss entfernt werden, oder es sollte ein eingeschränkter Ausführungs Bereich verwendet werden.

Wie in der Einleitung beschrieben, kann es sehr schwierig sein, verwalteten Code zu schreiben, der den prozessübergreifenden veränderbaren Freigabezustand zwischen Anwendungsdomänen auf verlässliche Weise überwacht.  Ein prozessübergreifender veränderbarer Freigabezustand ist jede Art von Datenstruktur zwischen Anwendungsdomänen, entweder in Win32-Code, innerhalb der CLR oder in verwaltetem Code, der Remoting verwendet.  Ein veränderbarer Freigabezustand ist sehr schwer in verwaltetem Code zu schreiben, und jeder statische Freigabezustand sollte nur mit großer Vorsicht erfolgen.  Wenn es in Ihrem Fall zu einem prozessübergreifenden oder computerübergreifenden Freigabezustand kommt, suchen Sie nach einer Möglichkeit, diesen zu beseitigen, oder schützen Sie den Freigabezustand mithilfe eines eingeschränkten Ausführungsbereichs.  Beachten Sie, dass jede Bibliothek mit Freigabezustand, der nicht identifiziert und korrigiert ist, dazu führen könnte, dass ein Host wie SQL Server abstürzt, der ein korrektes Entladen von <xref:System.AppDomain> erfordert.

Wenn in Code ein COM-Objekt verwendet wird, vermeiden Sie, dieses COM-Objekt zwischen Anwendungsdomänen freizugeben.

### <a name="locks-do-not-work-process-wide-or-between-application-domains"></a>Sperren funktionieren nicht Prozess weit oder zwischen Anwendungs Domänen.

In der Vergangenheit wurden <xref:System.Threading.Monitor.Enter%2A> und die [lock-Anweisung](../../csharp/language-reference/keywords/lock-statement.md) dazu verwendet, Sperren für den globalen Prozess zu erstellen.  Dies ist beispielsweise beim Sperren von agilen <xref:System.AppDomain>-Klassen wie <xref:System.Type>-Instanzen von nicht freigegebenen Assemblys, <xref:System.Threading.Thread>-Objekten, internalisierten Zeichenfolgen und einigen Zeichenfolgen der Fall, die mithilfe von Remoting zwischen Anwendungsdomänen freigegeben sind.  Diese Sperren sind nicht mehr prozessübergreifend.  Überprüfen Sie, ob der Code innerhalb der Sperre eine externe, persistente Ressource wie eine Datei auf einem Datenträger oder möglicherweise eine Datenbank verwendet, um eine prozessübergreifende Sperre zwischen Anwendungsdomänen zu identifizieren.

Beachten Sie, dass die Verwendung einer Sperre innerhalb einer <xref:System.AppDomain>-Klasse Probleme verursachen kann, falls der geschützte Code eine externe Ressource verwendet, da dieser Code gleichzeitig in mehreren Anwendungsdomänen ausgeführt werden könnte.  Dies kann zum Problem werden, wenn in eine Protokolldatei geschrieben oder für den gesamten Prozess eine Bindung an einen Socket erfolgt.  Diese Änderungen bedeuten, dass bis auf die Verwendung einer benannten <xref:System.Threading.Mutex>- oder <xref:System.Threading.Semaphore>-Instanz keine einfache Möglichkeit besteht, verwalteten Code zu verwenden, um eine prozessglobale Sperre abzurufen.  Erstellen Sie Code, der nicht gleichzeitig in zwei Anwendungsdomänen ausgeführt wird, oder verwenden Sie die <xref:System.Threading.Mutex>- oder <xref:System.Threading.Semaphore>-Klassen.  Wenn vorhandener Code nicht geändert werden kann, verwenden Sie nicht ein benanntes Win32-Mutexobjekt für diese Synchronisierung, da das Ausführen im Fibermodus bedeutet, dass Sie nicht garantieren können, dass der gleiche Betriebssystemthread ein Mutex abrufen und freigeben wird.  Sie müssen die verwaltete <xref:System.Threading.Mutex>-Klasse oder eine benannte <xref:System.Threading.ManualResetEvent>-, <xref:System.Threading.AutoResetEvent>- oder <xref:System.Threading.Semaphore>-Instanz verwenden, um die Codesperre so zu synchronisieren, dass die CLR die Sperre beachtet, anstatt diese mithilfe von nicht verwaltetem Code zu synchronisieren.

#### <a name="avoid-locktypeofmytype"></a>Vermeiden Sie lock(typeof(MyType))

Private und öffentliche <xref:System.Type>-Objekte in freigegebenen Assemblys, bei denen nur eine Kopie des Codes zwischen allen Anwendungsdomänen freigegeben wird, stellen ebenfalls Probleme dar.  Für freigegebene Assemblys ist nur eine Instanz einer <xref:System.Type>-Klasse pro Prozess vorhanden. Dies bedeutet, dass mehrere Anwendungsdomänen genau dieselbe <xref:System.Type>-Instanz freigeben.  Durch eine Sperre für eine <xref:System.Type>-Instanz wird nicht nur die <xref:System.AppDomain>, sondern der gesamte Prozess beeinflusst.  Wenn eine <xref:System.AppDomain> ein <xref:System.Type>-Objekt sperrt, wird der Thread unvermittelt unterbrochen, und die Sperre wird nicht aufgehoben.  Diese Sperre kann dann bei anderen Anwendungsdomänen zu einem Deadlock führen.

Eine gute Möglichkeit zur Verwendung von Sperren in statischen Methoden besteht darin, ein statisches internes Synchronisierungsobjekt zum Code hinzuzufügen.  Dieses kann im Klassenkonstruktor initialisiert werden, wenn ein solcher vorhanden ist. Andernfalls kann das Objekt wie folgt initialisiert werden:

```csharp
private static Object s_InternalSyncObject;
private static Object InternalSyncObject
{
    get
    {
        if (s_InternalSyncObject == null)
        {
            Object o = new Object();
            Interlocked.CompareExchange(
                ref s_InternalSyncObject, o, null);
        }
        return s_InternalSyncObject;
    }
}
```

Wenn anschließend eine Sperre verwendet wird, verwenden Sie die `InternalSyncObject`-Eigenschaft, um ein Objekt zu erhalten, auf das die Sperre angewendet werden kann.  Sie müssen die Eigenschaft nicht verwenden, wenn Sie das interne Synchronisierungsobjekt im Klassenkonstruktor initialisiert haben.  Der zur Sperrung verwendete Initialisierungscode, der zwei Kontrollstrukturen zur Prüfung enthält, sollte wie im folgenden Beispiel aussehen:

```csharp
public static MyClass SingletonProperty
{
    get
    {
        if (s_SingletonProperty == null)
        {
            lock(InternalSyncObject)
            {
                // Do not use lock(typeof(MyClass))
                if (s_SingletonProperty == null)
                {
                    MyClass tmp = new MyClass(…);
                    // Do all initialization before publishing
                    s_SingletonProperty = tmp;
                }
            }
        }
        return s_SingletonProperty;
    }
}
```

#### <a name="a-note-about-lockthis"></a>Hinweis zu Lock (this)

Es ist im Allgemeinen zulässig, ein einzelnes Objekt zu sperren, auf das öffentlich zugegriffen werden kann.  Wenn das Objekt jedoch ein Singleton-Objekt ist, das bei einem gesamten Subsystem zu einem Deadlock führen kann, empfiehlt sich ebenfalls das obige Entwurfsmuster.  Das Sperren des <xref:System.Security.SecurityManager>-Objekts kann z.B. zu einem Deadlock in der <xref:System.AppDomain> führen, wodurch die gesamte <xref:System.AppDomain> unbrauchbar wird. Es wird daher empfohlen, ein als öffentlich deklariertes Objekt dieses Typs nicht zu sperren.  Eine Sperre einer einzelnen Auflistung oder eines einzelnen Arrays sollte jedoch in der Regel kein Problem darstellen.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Sperren Sie keine Typen, die möglicherweise über Anwendungsdomänen hinweg verwendet werden oder über eine starke Objektidentität verfügen. Rufen Sie nicht <xref:System.Threading.Monitor.Enter%2A> für Objekte der Klassen <xref:System.Type>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.PropertyInfo>, <xref:System.String>, <xref:System.ValueType>, <xref:System.Threading.Thread> oder für Objekte auf, die von <xref:System.MarshalByRefObject> abgeleitet werden.

### <a name="remove-gckeepalive-calls"></a>Entfernen Sie GC. KeepAlive-Aufrufe

In vorhandenem Code wird in vielen Fällen die <xref:System.GC.KeepAlive%2A>-Methode entweder nicht verwendet, obwohl dies erforderlich wäre, oder sie wird falsch angewendet.  Nach der Konvertierung in <xref:System.Runtime.InteropServices.SafeHandle> müssen Klassen nicht <xref:System.GC.KeepAlive%2A> aufrufen. Die Voraussetzung dafür ist, dass sie auf <xref:System.Runtime.InteropServices.SafeHandle> anstelle eines Finalizers zurückgreifen, um die Betriebssystemhandles zu finalisieren.  Der Leistungsabfall, der durch das anhaltende Aufrufen von <xref:System.GC.KeepAlive%2A> zustande kommt, ist unerheblich. Durch den Eindruck, dass ein Aufruf von <xref:System.GC.KeepAlive%2A> erforderlich oder ausreichend ist, um ein Problem mit der Lebensdauer zu lösen, das möglicherweise nicht mehr vorhanden ist, wird die Verwaltung des Codes jedoch erschwert.  Beim Verwenden der Runtime Callable Wrapper (RCWs) von COM-Interop muss <xref:System.GC.KeepAlive%2A> allerdings dennoch im Code vorhanden sein.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Entfernen Sie <xref:System.GC.KeepAlive%2A>.

### <a name="use-the-hostprotection-attribute"></a>Verwenden des HostProtection-Attributs

Das <xref:System.Security.Permissions.HostProtectionAttribute> (HPA) stellt deklarative Sicherheitsaktionen zur Festlegung von Hostschutzanforderungen zur Verfügung. Auf diese Weise kann sogar vom Host verhindert werden, dass in voll vertrauenswürdigem Code Methoden aufgerufen werden, die für einen bestimmten Host wie <xref:System.Environment.Exit%2A> oder <xref:System.Windows.Forms.MessageBox.Show%2A> für SQL Server ungeeignet sind.

Das HPA wirkt sich nur auf nicht verwaltete Anwendungen aus, die die Common Language Runtime hosten und den Hostschutz implementieren. Ein Beispiel ist SQL Server. Die Anwendung der Sicherheitsaktion führt basierend auf den Hostressourcen, die von der Klasse oder Methode verfügbar gemacht werden, zur Erstellung eines Linkaufrufs. Wenn der Code in einer Clientanwendung oder auf einem Server ausgeführt wird, der nicht Teil eines geschützten Hostbereichs ist, „verschwindet“ das Attribut. Es wird also nicht erkannt und daher nicht angewendet.

> [!IMPORTANT]
> Der Zweck dieses Attributs besteht darin, hostspezifische Richtlinien für Programmiermodelle durchzusetzen. Ein erzwungenes Sicherheitsverhalten ist jedoch nicht das Ziel.  Obwohl ein Linkaufruf verwendet wird, um auf Übereinstimmung mit den Programmiermodellanforderungen zu prüfen, ist das <xref:System.Security.Permissions.HostProtectionAttribute> keine Sicherheitsberechtigung.

Wenn für den Host keine Programmiermodellanforderungen vorliegen, kommt es nicht zu einem Linkaufruf.

Das Attribut identifiziert Folgendes:

- Methoden oder Klassen, die nicht mit dem Programmiermodell des Hosts kompatibel sind, jedoch abgesehen davon keine negativen Auswirkungen haben.

- Methoden oder Klassen, die nicht mit dem Programmiermodell des Hosts kompatibel sind und zur Destabilisierung von serververwaltetem Benutzercode führen können.

- Methoden oder Klassen, die nicht mit dem Programmiermodell des Hosts kompatibel sind und zur Destabilisierung des Serverprozesses selbst führen können.

> [!NOTE]
> Wenn Sie eine Klassenbibliothek erstellen, die von Anwendungen aufgerufen werden soll, die in einer geschützten Hostumgebung ausgeführt werden können, sollten Sie dieses Attribut auf Member anwenden, die <xref:System.Security.Permissions.HostProtectionResource>-Kategorien verfügbar machen. Die Verwendung von Membern der .NET Framework-Klassenbibliothek mit diesem Attribut führt nur dazu, dass die unmittelbar aufrufende Methode überprüft wird.  Auch der Bibliotheksmember muss auf gleiche Weise seine aufrufende Methode überprüfen.

Weitere Informationen zu HPA finden Sie unter <xref:System.Security.Permissions.HostProtectionAttribute>.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Alle Methoden, in denen Synchronisierung oder Threading zur Anwendung kommt, müssen für SQL Server mit dem HPA identifiziert werden. Dies gilt auch für Methoden, die Zustände freigeben, synchronisiert werden oder externe Prozesse verwalten. Zu den <xref:System.Security.Permissions.HostProtectionResource>-Werten, die sich auf SQL Server auswirken, gehören <xref:System.Security.Permissions.HostProtectionResource.SharedState>, <xref:System.Security.Permissions.HostProtectionResource.Synchronization> und <xref:System.Security.Permissions.HostProtectionResource.ExternalProcessMgmt>. Von einem HPA sollten nicht nur Methoden identifiziert werden, die Ressourcen verwenden, die sich auf SQL auswirken. Vielmehr sollten alle Methoden, die eine <xref:System.Security.Permissions.HostProtectionResource> verfügbar machen, von diesem Attribut identifiziert werden.

### <a name="do-not-block-indefinitely-in-unmanaged-code"></a>Nicht unbegrenzt in nicht verwaltetem Code blockieren

Blockierungen in nicht verwaltetem Code anstatt in verwaltetem Code können zu einem Denial-of-Service-Angriff führen, da die CLR nicht in der Lage ist, den Thread abzubrechen.  Durch einen blockierten Thread wird – zumindest bei Verzicht auf unsichere Vorgänge – die CLR daran gehindert, die <xref:System.AppDomain> zu entladen.  Die Blockierung mithilfe eines Windows-Synchronisierungs primitiven ist ein eindeutiger Beispiel dafür, was wir nicht zulassen können.  Die Blockierung in einem Aufruf von `ReadFile` für einen Socket sollte nach Möglichkeit vermieden werden – im Idealfall sollte die Windows-API einen Mechanismus für einen Vorgang wie diesen bereitstellen, um ein Timeout zu erzielen.

Jede Methode, die in nativem Code aufgerufen wird, sollte idealerweise einen Win32-Aufruf mit einem angemessenen, zeitlich begrenzten Timeout verwenden.  Wenn der Benutzer ein Timeout festlegen darf, sollte dieses nur dann zeitlich unbegrenzt sein dürfen, falls der Benutzer über bestimmte Sicherheitsberechtigungen verfügt.  Wenn eine Methode länger als ca. 10 Sekunden blockiert wird, benötigen Sie entweder eine Version, die Timeouts unterstützt, oder zusätzliche CLR-Unterstützung.

Hier finden Sie einige Beispiele für problematische APIs.  Sowohl anonyme als auch benannte Pipes können ohne Timeout erstellt werden. Im Code muss allerdings sichergestellt werden, dass nie `CreateNamedPipe` oder `WaitNamedPipe` mit NMPWAIT_WAIT_FOREVER aufgerufen werden.  Darüber hinaus kommt es möglicherweise auch dann zu unerwarteten Blockierungen, wenn ein Timeout angegeben wird.  Der Aufruf von `WriteFile` in einer anonymen Pipe wird blockiert, bis der Schreibvorgang für alle Bytes beendet ist. Wenn sich im Puffer ungelesene Daten befinden, wird der `WriteFile`-Aufruf blockiert, bis der Reader Speicherplatz im Puffer der Pipe freigegeben hat.  Für Sockets sollte immer eine API verwendet werden, die einen Timeoutmechanismus unterstützt.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Eine Blockierung ohne Timeout ist in nicht verwaltetem Code ein Denial-of-Service-Angriff. Führen Sie keine Plattformaufrufe von `WaitForSingleObject`, `WaitForSingleObjectEx`, `WaitForMultipleObjects`, `MsgWaitForMultipleObjects` und `MsgWaitForMultipleObjectsEx` aus.  Verwenden Sie nicht NMPWAIT_WAIT_FOREVER.

### <a name="identify-any-sta-dependent-features"></a>Identifizieren Sie alle STA-abhängigen Features.

Identifizieren Sie Code, der COM-Single-Threaded-Apartments (STAs) verwendet.  STAs sind für den SQL Server-Prozess deaktiviert.  Von `CoInitialize` abhänge Funktionen wie z.B. Leistungsindikatoren oder die Zwischenablage müssen in SQL Server deaktiviert werden.

### <a name="ensure-finalizers-are-free-of-synchronization-problems"></a>Sicherstellen, dass Finalizer keine Synchronisierungs Probleme aufweisen

Es besteht die Möglichkeit, dass in zukünftigen Versionen von .NET Framework mehrere Finalizer-Threads vorhanden sind. Das bedeutet, dass Finalizer für verschiedene Instanzen desselben Typs gleichzeitig ausgeführt werden.  Finalizer müssen nicht völlig threadsicher sein, da der Garbage Collector garantiert, dass ein Finalizer für eine vorhandene Objektinstanz in nur einem Thread ausgeführt wird.  Finalizer müssen jedoch so programmiert werden, dass Racebedingungen und Deadlocks vermieden werden, wenn Finalizer gleichzeitig für unterschiedliche Objektinstanzen ausgeführt werden.  Wenn beispielsweise beim Schreiben in eine Protokolldatei ein externer Zustand in einem Finalizer verwendet wird, müssen Threadingprobleme behandelt werden.  Verlassen Sie sich bei der Gewährleistung von Threadsicherheit nicht auf die Finalisierung. Verwenden Sie außerdem keinen verwalteten oder nativen threadlokalen Speicher zum Speichern eines Zustands im Finalizer-Thread.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

In Finalizern dürfen keine Synchronisierungsprobleme auftreten. Verwenden Sie keinen statischen veränderlichen Zustand in einem Finalizer.

### <a name="avoid-unmanaged-memory-if-possible"></a>Vermeiden Sie nach Möglichkeit nicht verwalteten Speicher.

Nicht verwalteter Speicher kann ebenso wie ein Betriebssystemhandle verloren gehen. Verwenden Sie daher falls möglich Arbeitsspeicher auf dem Stapel mit [stackalloc](../../csharp/language-reference/operators/stackalloc.md) oder ein fixiertes verwaltetes Objekt wie die [fixed-Anweisung](../../csharp/language-reference/keywords/fixed-statement.md) oder einen <xref:System.Runtime.InteropServices.GCHandle> mithilfe von „byte[]“. Der <xref:System.GC> gibt diese Ressourcen abschließend frei. Wenn Sie jedoch nicht verwalteten Speicher zuordnen müssen, sollten Sie eine Klasse verwenden, die von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitet wird, um den Code für die Speicherbelegung zu umschließen.

Beachten Sie, dass <xref:System.Runtime.InteropServices.SafeHandle> in mindestens einem Fall nicht verwendet werden sollte. Bei COM-Methodenaufrufen, die Speicher belegen oder freigeben, ist es üblich, dass eine DLL zunächst Speicher über `CoTaskMemAlloc` belegt und eine andere DLL anschließend diesen Speicher mit `CoTaskMemFree` freigibt.  Die Verwendung eines <xref:System.Runtime.InteropServices.SafeHandle>-Objekts wäre hier nicht sinnvoll, da dieses versuchen würde, die Lebensdauer des nicht verwalteten Speichers mit der Lebensdauer von <xref:System.Runtime.InteropServices.SafeHandle> zu verknüpfen, anstatt zuzulassen, dass die andere DLL die Lebensdauer des Arbeitsspeichers verwaltet.

### <a name="review-all-uses-of-catchexception"></a>Alle Verwendungszwecke von catch (Exception) überprüfen

In catch-Blöcken zum Abfangen aller Ausnahmen anstatt einer bestimmten Ausnahme werden nun auch asynchrone Ausnahmen abgefangen. Überprüfen Sie jeden catch(Exception)-Block, und achten Sie darauf, dass keine wichtigen Ressourcen freigeben werden oder Zurücksetzungscode übersprungen wird. Suchen Sie außerdem nach potenziell fehlerhaftem Verhalten innerhalb des catch-Blocks selbst für die Behandlung der Ausnahmen <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> oder <xref:System.OutOfMemoryException>.  Beachten Sie, dass im Code möglicherweise Annahmen protokolliert oder getroffen werden, dass bestimmte Ausnahmen sichtbar sind oder eine Ausnahme aus genau einem Grund aufgetreten ist.  Diese Annahmen müssen möglicherweise aktualisiert werden, um <xref:System.Threading.ThreadAbortException> einzuschließen.

Sie sollten alle Stellen, an denen Ausnahmen jeden Typs abgefangen werden, so ändern, dass ein erwarteter Ausnahmetyp abgefangen wird. Ein Beispiel ist eine <xref:System.FormatException>, die bei einer Methode zur Formatierung von Zeichenfolgen auftritt.  Auf diese Weise wird verhindert, dass der catch-Block bei unerwarteten Ausnahmen ausgeführt wird. Außerdem wird sichergestellt, dass Fehler nicht durch das Abfangen unerwarteter Ausnahmen maskiert werden.  Allgemein gilt, dass Sie nie eine Ausnahme in Bibliothekscode behandeln dürfen. Code, in dem Sie eine Ausnahme abfangen müssen, kann auf einen Entwurfsfehler im abgerufenen Code hindeuten.  In einigen Fällen empfiehlt es sich, eine Ausnahme abzufangen und einen anderen Ausnahmetyp auszulösen, um mehr Daten bereitzustellen.  Verwenden Sie in diesem Fall geschachtelte Ausnahmen, da so die tatsächliche Ursache des Fehlers in der <xref:System.Exception.InnerException%2A>-Eigenschaft der neuen Ausnahme gespeichert wird.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Prüfen Sie in verwaltetem Code alle catch-Blöcke, die alle Objekte oder Ausnahmen abfangen.  In C#bedeutet dies, dass sowohl `catch` {} als auch `catch(Exception)` {}gekennzeichnet werden.  Sie sollten entweder einen ganz bestimmten Ausnahmetyp verwenden oder den Code prüfen, um sicherzustellen, dass es beim Abfangen unerwarteter Ausnahmetypen nicht zu Fehlern kommt.

### <a name="do-not-assume-a-managed-thread-is-a-win32-thread--it-is-a-fiber"></a>Gehen Sie nicht davon aus, dass ein verwalteter Thread ein Win32-Thread ist – er ist eine Fiber.

Die Verwendung von verwaltetem threadlokalen Speicher ist möglich. Sie können jedoch keinen nicht verwalteten threadlokalen Speicher verwenden oder davon ausgehen, dass der Code erneut im aktuellen Betriebssystemthread ausgeführt wird. Ändern Sie keine Einstellungen wie das Threadgebietsschema. Verwenden Sie zum Abruf der Methoden `InitializeCriticalSection` oder `CreateMutex` keinen Plattformaufruf, da diese darauf angewiesen sind, dass der gesperrte Betriebssystemthread wieder entsperrt wird. Da dies bei der Verwendung von Fibern nicht der Fall ist, können kritische Abschnitte in Win32 und Mutex-Verfahren nicht direkt in SQL verwendet werden.  Beachten Sie, dass die verwaltete <xref:System.Threading.Mutex>-Klasse keine Probleme hinsichtlich der Threadaffinität behandelt.

Sie können den Zustand eines verwalteten <xref:System.Threading.Thread>-Objekts größtenteils sicher nutzen und dabei beispielsweise verwalteten threadlokalen Speicher und die aktuelle Benutzeroberflächenkultur des Threads verwenden. Sie können auch das <xref:System.ThreadStaticAttribute> verwenden, wodurch nur der aktuell verwaltete Thread auf den Wert einer vorhandenen statischen Variable zugreifen kann. Dies ist eine alternative Methode zur Verwendung threadlokalen Speichers in einer Fiber in der CLR. Aus Gründen, die mit dem Programmiermodell zusammenhängen, können Sie die aktuelle Kultur eines Threads nicht ändern, wenn dieser in SQL ausgeführt wird.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

SQL Server wird im Fibermodus ausgeführt. Verwenden Sie keinen threadlokalen Speicher. Führen Sie außerdem keine Plattformaufrufe von `TlsAlloc`, `TlsFree`, `TlsGetValue` und `TlsSetValue.` aus.

### <a name="let-sql-server-handle-impersonation"></a>SQL Server Handle für den Identitätswechsel

Da der Identitätswechsel auf der Threadebene ausgeführt wird und SQL im Fibermodus ausgeführt werden kann, sollte es in verwaltetem Code zu keinem Identitätswechsel von Benutzern und zu keinem Aufruf von `RevertToSelf` kommen.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Überlassen Sie den Identitätswechsel SQL Server. Verwenden Sie nicht `RevertToSelf`, `ImpersonateAnonymousToken`, `DdeImpersonateClient`, `ImpersonateDdeClientWindow`, `ImpersonateLoggedOnUser`, `ImpersonateNamedPipeClient`, `ImpersonateSelf`, `RpcImpersonateClient`, `RpcRevertToSelf`, `RpcRevertToSelfEx` oder `SetThreadToken`.

### <a name="do-not-call-threadsuspend"></a>Thread:: Suspend nicht anrufen

Einen Thread anzuhalten scheint ein unproblematischer Vorgang zu sein. Es kann dabei jedoch zu Deadlocks kommen.  Wenn ein Thread, der eine Sperre verwendet, von einem zweiten Thread angehalten wird und dieser denselben Bereich sperrt, tritt ein Deadlock auf.  <xref:System.Threading.Thread.Suspend%2A> kann aktuell die Sicherheit, das Laden von Klassen, Remoting und Reflektion beeinträchtigen.

#### <a name="code-analysis-rule"></a>Code Analyse Regel

Rufen Sie <xref:System.Threading.Thread.Suspend%2A> nicht auf. Verwenden Sie stattdessen eine richtige Synchronisierungsprimitive wie ein <xref:System.Threading.Semaphore> oder <xref:System.Threading.ManualResetEvent>.

### <a name="protect-critical-operations-with-constrained-execution-regions-and-reliability-contracts"></a>Schützen Sie kritische Vorgänge mit eingeschränkten Ausführungs Bereichen und Zuverlässigkeits Verträgen.

Stellen Sie bei der Ausführung eines komplexen Vorgangs, der einen freigegebenen Zustand aktualisiert oder der deterministisch entweder vollständig gelingt oder fehlschlägt, sicher, dass dieser von einem eingeschränkten Ausführungsbereich (CER) geschützt ist. Auf diese Weise wird garantiert, dass der Code immer und sogar dann ausgeführt wird, wenn ein Thread unerwartet abgebrochen oder <xref:System.AppDomain> unvorhergesehen entladen wird.

Ein CER ist ein besonderer `try/finally`-Block, dem ein Aufruf der Methode <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> vorangestellt wird.

Hierdurch wird der Just-In-Time-Compiler angewiesen, den gesamten Code im finally-Block vorzubereiten, bevor der `try`-Block ausgeführt wird. So wird sichergestellt, dass der Code im finally-Block erstellt wird und in allen Fällen ausführbar ist. Es ist nicht ungewöhnlich, dass in einem CER ein leerer `try`-Block verwendet wird. Die Verwendung eines CER schützt vor asynchronen Threadabbrüchen und Ausnahmen bei unzureichendem Speicherplatz. Unter <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> finden Sie einen CER, der zusätzlich Stapelüberläufe in überaus komplexem Code behandelt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.ConstrainedExecution>
- [SQL Server-Programmierung und Hostschutzattribute](sql-server-programming-and-host-protection-attributes.md)
