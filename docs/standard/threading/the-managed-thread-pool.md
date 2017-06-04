---
title: "The Managed Thread Pool | Microsoft Docs"
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
  - "thread pooling [.NET Framework]"
  - "thread pools [.NET Framework]"
  - "threading [.NET Framework], thread pool"
  - "threading [.NET Framework], pooling"
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
caps.latest.revision: 24
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 24
---
# The Managed Thread Pool
Die <xref:System.Threading.ThreadPool>\-Klasse stellt einer Anwendung einen Pool von Arbeitsthreads bereit, die vom System verwaltet werden und Ihnen die Möglichkeit bieten, sich mehr auf Anwendungsaufgaben als auf die Threadverwaltung zu konzentrieren.  Für kurze Aufgaben, bei denen Hintergrundverarbeitung erforderlich ist, bietet sich der verwaltete Threadpool als einfache Lösung für den Umgang mit mehreren Threads an.  Zum Beispiel können Sie, beginnend mit [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], <xref:System.Threading.Tasks.Task>\- und <xref:System.Threading.Tasks.Task%601>\-Objekte erstellen, die asynchrone Aufgaben in Threads im Threadpool ausführen.  
  
> [!NOTE]
>  In [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)] wurde der Durchsatz des Threadpools in drei wichtigen Bereichen, die in früheren Versionen von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] als Engpässe galten, deutlich gesteigert: Einfügen von Aufgaben in die Warteschlange, Weiterleitung von Threads im Threadpool und Weiterleitung von E\/A\-Abschlussthreads.  Zur Verwendung dieser Funktionen sollte die Anwendung für [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] oder höher ausgelegt sein.  
  
 In .NET Framework 2.0 steht für Hintergrundaufgaben, die mit der Benutzeroberfläche interagieren, auch die <xref:System.ComponentModel.BackgroundWorker>\-Klasse zur Verfügung, die mithilfe von Ereignissen kommuniziert, die für den Benutzeroberflächenthread ausgelöst werden.  
  
 Threadpoolthreads werden in .NET Framework zu verschiedenen Zwecken eingesetzt, z. B. für asynchrone E\/A\-Komplettierung, Timerrückrufe, registrierte Wartevorgänge, asynchrone Methodenaufrufe mithilfe von Delegaten und <xref:System.Net>\-Socketverbindungen.  
  
## Gründe, die gegen die Verwendung von Threadpools sprechen  
 In einigen Szenarien ist die Erstellung und Verwaltung eigener Threads der Verwendung von Threadpoolthreads vorzuziehen:  
  
-   Sie benötigen einen Vordergrundthread.  
  
-   Sie benötigen einen Thread mit einer bestimmten Priorität.  
  
-   Es gibt Aufgaben, die den Thread über einen längeren Zeitraum blockieren.  Da die Anzahl der Threads im Threadpool begrenzt ist, kann eine hohe Anzahl blockierter Threadpoolthreads das Starten von Aufgaben verhindern.  
  
-   Sie müssen Threads in ein Singlethread\-Apartment einfügen.  Alle <xref:System.Threading.ThreadPool>\-Threads befinden sich im Multithread\-Apartment.  
  
-   Dem Thread muss eine stabile Identität zugeordnet werden, oder ein Thread soll einer Aufgabe zugeordnet werden.  
  
## Eigenschaften von Threadpools  
 Threadpoolthreads sind Hintergrundthreads.  Siehe [Foreground and Background Threads](../../../docs/standard/threading/foreground-and-background-threads.md).  Jeder Thread verwendet die standardmäßige Stapelgröße, wird mit Standardpriorität ausgeführt und befindet sich im Multithread\-Apartment.  
  
 Pro Prozess gibt es nur einen Threadpool.  
  
### Ausnahmen in Threadpoolthreads  
 Nicht behandelte Ausnahmen in Threadpoolthreads beenden den Prozess.  Für diese Regel gelten jedoch die folgenden drei Ausnahmen:  
  
-   In einem Threadpoolthread wird eine <xref:System.Threading.ThreadAbortException> ausgelöst, da <xref:System.Threading.Thread.Abort%2A> aufgerufen wurde.  
  
-   In einem Threadpoolthread wird eine <xref:System.AppDomainUnloadedException> ausgelöst, da die Anwendungsdomäne entladen wird.  
  
-   Der Prozess wurde durch die Common Language Runtime oder einen Hostprozess beendet.  
  
 Weitere Informationen finden Sie unter [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  In den .NET Framework\-Versionen 1.0 und 1.1 erfasst die Common Language Runtime automatisch nicht behandelte Ausnahmen in Threadpoolthreads.  Dies kann den Anwendungszustand beschädigen und dazu führen, dass die Anwendung nicht mehr reagiert. Das Debuggen kann erhebliche Schwierigkeiten bereiten.  
  
### Maximale Anzahl von Threads im Threadpool  
 Die Anzahl von Vorgängen, die für den Threadpool in die Warteschlange aufgenommen werden, ist zwar nur durch den verfügbaren Speicher begrenzt, der Threadpool kann jedoch nur eine bestimmte Anzahl von Threads enthalten, die gleichzeitig im Prozess aktiv sind.  Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ist die Standardgröße des Threadpools für einen Prozess von mehreren Faktoren abhängig, z. B. von der Größe des virtuellen Adressraums.  Ein Prozess kann die <xref:System.Threading.ThreadPool.GetMaxThreads%2A>\-Methode aufrufen, um die Anzahl der Threads zu bestimmen.  
  
 Sie können die maximale Anzahl von Threads mithilfe der <xref:System.Threading.ThreadPool.GetMaxThreads%2A>\-Methode und der <xref:System.Threading.ThreadPool.SetMaxThreads%2A>\-Methode steuern.  
  
> [!NOTE]
>  In den .NET Framework\-Versionen 1.0 und 1.1 kann die Größe des Threadpools nicht über verwalteten Code festgelegt werden.  Code, der die Common Language Runtime hostet, kann die Größe anhand von `CorSetMaxThreads` festlegen, das in mscoree.h definiert wird.  
  
### Threadpoolmindestwerte  
 Der Threadpool stellt bei Bedarf neue Arbeitsthreads oder E\/A\-Abschlussthreads bereit, bis ein angegebener Mindestwert für jede Kategorie erreicht ist.  Sie können die <xref:System.Threading.ThreadPool.GetMinThreads%2A>\-Methode verwenden, um diese Mindestwerte abzurufen.  
  
> [!NOTE]
>  Wenn die Anforderungen niedrig sind, kann die tatsächliche Anzahl der Threads im Threadpool unterhalb der Mindestwerte liegen.  
  
 Wenn ein Minimum erreicht wird, kann der Threadpool weitere Threads erstellen oder warten, bis einige Aufgaben abgeschlossen sind.  Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] erstellt und zerstört der Threadpool Arbeitsthreads, um den Durchsatz zu optimieren. Der Durchsatz ist als die Anzahl der Aufgaben definiert, die pro Zeiteinheit abgeschlossen werden.  Bei zu wenigen Threads werden die verfügbaren Ressourcen möglicherweise nicht optimal genutzt, wohingegen bei zu vielen Threads Ressourcenkonflikte auftreten können.  
  
> [!CAUTION]
>  Sie können die <xref:System.Threading.ThreadPool.SetMinThreads%2A>\-Methode verwenden, um die Mindestanzahl an Threads im Leerlauf zu erhöhen.  Allerdings kann ein unnötiges Erhöhen dieses Wertes zu Leistungsproblemen führen.  Wenn zu viele Aufgaben gleichzeitig gestartet werden, werden möglicherweise alle Aufgaben zu langsam ausgeführt.  In den meisten Fällen erreicht der Threadpool mit dem eigenen Algorithmus für die Zuordnung von Threads eine bessere Leistung.  
  
## Überschreiben von Sicherheitsüberprüfungen  
 Der Threadpool stellt auch die <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=fullName>\-Methode und die <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=fullName>\-Methode bereit.  Verwenden Sie diese Methoden nur, wenn Sie sicher sind, dass der Stapel des Aufrufers irrelevant für die Sicherheitsüberprüfungen ist, die während der Ausführung der in der Warteschlange stehenden Aufgabe stattfinden.  <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>und <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> erfassen beide den Stapel des Aufrufers, der mit dem Stapel des Threadpoolthreads zusammengeführt wird, wenn der Thread beginnt, eine Aufgabe auszuführen.  Wenn eine Sicherheitsüberprüfung erforderlich ist, muss der gesamte Stapel überprüft werden.  Obwohl die Überprüfung Sicherheit gewährleistet, wird dadurch auch die Leistung beeinträchtigt.  
  
## Verwenden des Threadpools  
 Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] kann der Threadpool am einfachsten über die [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) verwendet werden.  Standardmäßig verwenden parallele Bibliothekstypen wie <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> Threadpoolthreads, um Aufgaben auszuführen.  Sie können den Threadpool auch verwenden, indem Sie in verwaltetem Code <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName> aufrufen \(oder `CorQueueUserWorkItem` in nicht verwaltetem Code\) und einen <xref:System.Threading.WaitCallback>\-Delegaten übergeben, der die Methode darstellt, die die Aufgabe ausführt.  Eine andere Möglichkeit, den Threadpool zu verwenden, ist, Arbeitsaufgaben, die mit einem Wartevorgang verknüpft sind, mit der <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=fullName>\-Methode in die Warteschlange zu stellen und ein <xref:System.Threading.WaitHandle> zu übergeben, das bei einer Signalisierung oder einem Timeout die Methode aufruft, die vom <xref:System.Threading.WaitOrTimerCallback>\-Delegaten dargestellt wird.  Threadpoolthreads werden zum Aufrufen von Rückrufmethoden verwendet.  
  
## Threadpool\-Beispiele  
 Die Codebeispiele in diesem Abschnitt veranschaulichen den Threadpool bei Verwendung der <xref:System.Threading.Tasks.Task>\-Klasse, der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>\-Methode und der <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=fullName>\-Methode.  
  
-   [Ausführen von asynchronen Aufgaben mit der Task Parallel Library](#TaskParallelLibrary)  
  
-   [Asynchrones Ausführen von Code mit "QueueUserWorkItem"](#ExecuteCodeWithQUWI)  
  
-   [Bereitstellen von Aufgabendaten für "QueueUserWorkItem"](#TaskDataForQUWI)  
  
-   [Verwenden von RegisterWaitForSingleObject](#RegisterWaitForSingleObject)  
  
<a name="TaskParallelLibrary"></a>   
### Ausführen von asynchronen Aufgaben mit der Task Parallel Library  
 Im folgenden Beispiel wird veranschaulicht, wie mit einem Aufruf der <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName>\-Methode ein <xref:System.Threading.Tasks.Task>\-Objekt erstellt und verwendet wird.  Ein Beispiel, in dem die <xref:System.Threading.Tasks.Task%601>\-Klasse verwendet wird, um einen Wert aus einer asynchronen Aufgabe zurückzugeben, finden Sie unter [How to: Return a Value from a Task](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md).  
  
 [!code-csharp[System.Threading.Tasks.Task#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.task/cs/startnew.cs#01)]
 [!code-vb[System.Threading.Tasks.Task#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.task/vb/startnew.vb#01)]  
  
<a name="ExecuteCodeWithQUWI"></a>   
### Asynchrones Ausführen von Code mit "QueueUserWorkItem"  
 Im folgenden Beispiel wird mithilfe der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>\-Methode eine sehr einfache Aufgabe, die durch die `ThreadProc`\-Methode dargestellt wird, in die Warteschlange eingefügt.  
  
 [!code-cpp[Conceptual.ThreadPool#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.ThreadPool#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source1.cs#1)]
 [!code-vb[Conceptual.ThreadPool#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source1.vb#1)]  
  
<a name="TaskDataForQUWI"></a>   
### Bereitstellen von Aufgabendaten für "QueueUserWorkItem"  
 Im folgenden Codebeispiel wird eine Aufgabe mithilfe der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>\-Methode in die Warteschlange eingefügt, und es werden die Daten für die Aufgabe bereitgestellt.  
  
 [!code-cpp[Conceptual.ThreadPool#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.ThreadPool#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source2.cs#2)]
 [!code-vb[Conceptual.ThreadPool#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source2.vb#2)]  
  
<a name="RegisterWaitForSingleObject"></a>   
### Verwenden von RegisterWaitForSingleObject  
 Im folgenden Beispiel werden verschiedene Threadingfeatures dargestellt.  
  
-   Aufnehmen einer Aufgabe in die Warteschlange mithilfe der <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A>\-Methode zur Ausführung durch <xref:System.Threading.ThreadPool>\-Threads.  
  
-   Auslösen der Ausführung einer Aufgabe mithilfe von <xref:System.Threading.AutoResetEvent>.  Siehe [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
  
-   Behandeln von Timeouts und Signalen mit einem <xref:System.Threading.WaitOrTimerCallback>\-Delegaten  
  
-   Abbrechen einer in die Warteschlange eingefügten Aufgabe mithilfe von <xref:System.Threading.RegisteredWaitHandle>.  
  
 [!code-cpp[Conceptual.ThreadPool#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.ThreadPool#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source3.cs#3)]
 [!code-vb[Conceptual.ThreadPool#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source3.vb#3)]  
  
## Siehe auch  
 <xref:System.Threading.ThreadPool>   
 <xref:System.Threading.Tasks.Task>   
 <xref:System.Threading.Tasks.Task%601>   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [How to: Return a Value from a Task](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Asynchrone Datei\-E\/A](../../../docs/standard/io/asynchrone-datei-e-a.md)   
 [Timers](../../../docs/standard/threading/timers.md)