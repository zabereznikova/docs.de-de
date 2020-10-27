---
title: Der verwaltete Threadpool
description: Erfahren Sie mehr über den .NET-Threadpool, der Arbeitsthreads im Hintergrund bereitstellt.
ms.date: 08/02/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- thread pooling [.NET]
- thread pools [.NET]
- threading [.NET], thread pool
- threading [.NET], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
ms.openlocfilehash: 2671ce7c9721b15de8a3805da27040e973a62804
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223797"
---
# <a name="the-managed-thread-pool"></a>Der verwaltete Threadpool

Die <xref:System.Threading.ThreadPool?displayProperty=nameWithType>-Klasse stellt einer Anwendung einen Pool von Arbeitsthreads bereit, die vom System verwaltet werden und Ihnen die Möglichkeit bieten, sich mehr auf Anwendungsaufgaben als auf die Threadverwaltung zu konzentrieren. Für kurze Aufgaben, bei denen Hintergrundverarbeitung erforderlich ist, bietet sich der verwaltete Threadpool als einfache Lösung für den Umgang mit mehreren Threads an. Die Verwendung des Threadpools ist ab Version 4 des Frameworks deutlich einfacher, da Sie <xref:System.Threading.Tasks.Task>- und <xref:System.Threading.Tasks.Task%601>-Objekte erstellen können, die asynchrone Aufgaben auf Threads aus dem Threadpool ausführen.  
  
Threadpoolthreads werden in .NET für viele Zwecke verwendet. Dazu gehören [Task Parallel Library](../parallel-programming/task-parallel-library-tpl.md)-Vorgänge (TPL), asynchrone E/A-Komplettierung, [Timerrückrufe](timers.md), registrierte Wartevorgänge, asynchrone Methodenaufrufe mithilfe von Delegaten und <xref:System.Net?displayProperty=nameWithType>-Socketverbindungen.  

## <a name="thread-pool-characteristics"></a>Eigenschaften von Threadpools

Threadpoolthreads sind [Hintergrundthreads](foreground-and-background-threads.md). Jeder Thread verwendet die standardmäßige Stapelgröße, wird mit Standardpriorität ausgeführt und befindet sich im Multithread-Apartment. Sobald ein Thread im Threadpool seine Aufgabe abgeschlossen hat, wird er an eine Warteschlange von Threads zurückgegeben. Ab diesem Zeitpunkt kann er wiederverwendet werden. Aufgrund der Wiederverwendung müssen Anwendungen nicht für jede Aufgabe einen neuen Threads erstellen.
  
Pro Prozess gibt es nur einen Threadpool.  
  
### <a name="exceptions-in-thread-pool-threads"></a>Ausnahmen in Threadpoolthreads

Nicht behandelte Ausnahmen in Threadpoolthreads beenden den Prozess. Für diese Regel gelten jedoch die folgenden drei Ausnahmen:  
  
- In einem Threadpoolthread wird eine <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType>-Ausnahme ausgelöst, da <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> aufgerufen wurde.  
- In einem Threadpoolthread wird eine <xref:System.AppDomainUnloadedException?displayProperty=nameWithType>-Ausnahme ausgelöst, da die Anwendungsdomäne entladen wird.  
- Der Prozess wurde durch die Common Language Runtime oder einen Hostprozess beendet.  
  
Weitere Informationen finden Sie unter [Ausnahmen in verwalteten Threads](exceptions-in-managed-threads.md).  
  
### <a name="maximum-number-of-thread-pool-threads"></a>Maximale Anzahl von Threads im Threadpool

Die Anzahl von Vorgängen, die im Threadpool angereiht werden kann, wird nur durch den verfügbaren Arbeitsspeicher beschränkt. Allerdings schränkt der Threadpool die Anzahl von Threads ein, die gleichzeitig im Prozess aktiv sein können. Wenn alle Threadpoolthreads aktiv sind, werden zusätzliche Arbeitselemente eingereiht, bis Threads verfügbar sind, um diese auszuführen. Ab .NET Framework 4 ist die Standardgröße des Threadpools für einen Prozess von mehreren Faktoren abhängig, z.B. von der Größe des virtuellen Adressraums. Ein Prozess kann die <xref:System.Threading.ThreadPool.GetMaxThreads%2A?displayProperty=nameWithType>-Methode aufrufen, um die Anzahl der Threads zu bestimmen.  
  
Sie können die maximale Anzahl von Threads mithilfe der <xref:System.Threading.ThreadPool.GetMaxThreads%2A?displayProperty=nameWithType>-Methode und der <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>-Methode steuern.  

> [!NOTE]
> Code, der die Common Language Runtime hostet, kann die Größe mithilfe der [`ICorThreadpool::CorSetMaxThreads`](../../framework/unmanaged-api/hosting/icorthreadpool-corsetmaxthreads-method.md)-Methode festlegen.  
  
### <a name="thread-pool-minimums"></a>Mindestwerte für den Threadpool

Der Threadpool stellt bei Bedarf neue Arbeitsthreads oder E/A-Abschlussthreads bereit, bis ein angegebener Mindestwert für jede Kategorie erreicht ist. Sie können die <xref:System.Threading.ThreadPool.GetMinThreads%2A?displayProperty=nameWithType>-Methode verwenden, um diese Mindestwerte abzurufen.  
  
> [!NOTE]
> Wenn die Anforderungen niedrig sind, kann die tatsächliche Anzahl der Threads im Threadpool unterhalb der Mindestwerte liegen.  
  
Wenn ein Minimum erreicht wird, kann der Threadpool weitere Threads erstellen oder warten, bis einige Aufgaben abgeschlossen sind. Ab .NET Framework 4 erstellt und zerstört der Threadpool Arbeitsthreads, um den Durchsatz zu optimieren. Der Durchsatz ist als die Anzahl der Aufgaben definiert, die pro Zeiteinheit abgeschlossen werden. Bei zu wenigen Threads werden die verfügbaren Ressourcen möglicherweise nicht optimal genutzt, wohingegen bei zu vielen Threads Ressourcenkonflikte auftreten können.  
  
> [!CAUTION]
> Sie können die <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>-Methode verwenden, um die Mindestanzahl an Threads im Leerlauf zu erhöhen. Allerdings kann ein unnötiges Erhöhen dieses Wertes zu Leistungsproblemen führen. Wenn zu viele Aufgaben gleichzeitig gestartet werden, werden möglicherweise alle Aufgaben zu langsam ausgeführt. In den meisten Fällen erreicht der Threadpool mit dem eigenen Algorithmus für die Zuordnung von Threads eine bessere Leistung.  

## <a name="using-the-thread-pool"></a>Verwenden des Threadpools

Ab .NET Framework 4 kann der Threadpool am einfachsten über die [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) verwendet werden. Standardmäßig verwenden TPL-Typen wie <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> Threadpoolthreads, um Aufgaben auszuführen.

Sie können den Threadpool auch verwenden, indem Sie in verwaltetem Code <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> aufrufen (oder [`ICorThreadpool::CorQueueUserWorkItem`](../../framework/unmanaged-api/hosting/icorthreadpool-corqueueuserworkitem-method.md) in nicht verwaltetem Code) und einen <xref:System.Threading.WaitCallback?displayProperty=nameWithType>-Delegaten übergeben, der die Methode darstellt, die die Aufgabe ausführt.

Eine andere Möglichkeit, den Threadpool zu verwenden, ist, Arbeitselemente, die mit einem Wartevorgang verknüpft sind, mit der <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType>-Methode in die Warteschlange zu stellen und ein <xref:System.Threading.WaitHandle?displayProperty=nameWithType> zu übergeben, das bei einer Signalisierung oder einem Timeout die Methode aufruft, die vom <xref:System.Threading.WaitOrTimerCallback?displayProperty=nameWithType>-Delegaten dargestellt wird. Threadpoolthreads werden zum Aufrufen von Rückrufmethoden verwendet.  

Beispiele finden Sie auf den referenzierten API-Seiten.
  
## <a name="skipping-security-checks"></a>Überspringen der Sicherheitsüberprüfungen

Der Threadpool stellt auch die <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType>-Methode und die <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType>-Methode bereit. Verwenden Sie diese Methoden nur, wenn Sie sicher sind, dass der Stapel des Aufrufers irrelevant für die Sicherheitsüberprüfungen ist, die während der Ausführung der in der Warteschlange stehenden Aufgabe stattfinden. <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> und <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> erfassen beide den Stapel des Aufrufers, der mit dem Stapel des Threadpoolthreads zusammengeführt wird, wenn der Thread beginnt, eine Aufgabe auszuführen. Wenn eine Sicherheitsüberprüfung erforderlich ist, muss der gesamte Stapel überprüft werden. Obwohl die Überprüfung Sicherheit gewährleistet, wird dadurch auch die Leistung beeinträchtigt.  

## <a name="when-not-to-use-thread-pool-threads"></a>Gründe, die gegen die Verwendung von Threadpools sprechen

In einigen Szenarios ist die Erstellung und Verwaltung eigener Threads der Verwendung von Threadpoolthreads vorzuziehen:  
  
- Sie benötigen einen Vordergrundthread.  
- Sie benötigen einen Thread mit einer bestimmten Priorität.  
- Es gibt Aufgaben, die den Thread über einen längeren Zeitraum blockieren. Da die Anzahl der Threads im Threadpool begrenzt ist, kann eine hohe Anzahl blockierter Threadpoolthreads das Starten von Aufgaben verhindern.  
- Sie müssen Threads in ein Singlethread-Apartment einfügen. Alle <xref:System.Threading.ThreadPool>-Threads befinden sich im Multithread-Apartment.  
- Dem Thread muss eine stabile Identität zugeordnet werden, oder ein Thread soll einer Aufgabe zugeordnet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)
- [Gewusst wie: Zurückgeben eines Werts aus einer Aufgabe](../parallel-programming/how-to-return-a-value-from-a-task.md)
- [Threading Objects and Features (Threadingobjekte und -funktionen)](threading-objects-and-features.md)
- [Threads and Threading (Threads und Threading)](threads-and-threading.md)
- [Asynchronous File I/O](../io/asynchronous-file-i-o.md)
- [Timer](timers.md)
