---
title: Aufgabenbasiertes asynchrones Programmieren – .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallelism, task
ms.assetid: 458b5e69-5210-45e5-bc44-3888f86abd6f
ms.openlocfilehash: 51292d977f2be87cec7c3481f5004fe5fe756224
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74204545"
---
# <a name="task-based-asynchronous-programming"></a>Aufgabenbasiertes asynchrones Programmieren

Die Task Parallel Library (TPL) basiert auf dem Konzept einer *Aufgabe*, die einen asynchronen Vorgang darstellt. In einigen Dingen ist eine Aufgabe vergleichbar mit einer <xref:System.Threading.ThreadPool>, weist jedoch eine höhere Abstraktionsebene auf. Der Begriff *Aufgabenparallelität* bezeichnet eine oder mehrere eigenständige Aufgaben, die gleichzeitig ausgeführt werden. Aufgaben bieten zwei Hauptvorteile:

- Effiziente und skalierbare Verwendung von Systemressourcen.

     Aufgaben werden im Hintergrund in <xref:System.Threading.ThreadPool> eingereicht, der mit Algorithmen verbessert wurde, durch die die Anzahl von Threads bestimmt und angepasst wird und die einen Lastenausgleich verfügbar machen, der den Durchsatz maximiert. Aufgaben sind hierdurch relativ einfach strukturiert, und Sie können für eine differenzierte Parallelität viele Aufgaben erstellen.

- Stärker programmgesteuerte Kontrolle als bei Threads oder Arbeitselementen.

     Aufgaben und das diese umgebende Framework stellen einen umfangreichen Satz von APIs bereit, die Warten, Abbruch, Fortsetzungen, robuste Ausnahmebehandlung, detaillierte Zustandsangaben, benutzerdefinierte Planung und Vieles mehr unterstützen.

Aus diesen Gründen ist TPL in .NET Framework die bevorzugte API zum Schreiben von asynchronem, parallelem und Multithreadcode.

## <a name="creating-and-running-tasks-implicitly"></a>Implizites Erstellen und Ausführen von Aufgaben

Die <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>-Methode bietet eine einfache Möglichkeit, eine beliebige Anzahl willkürlicher Anweisungen gleichzeitig auszuführen. Sie müssen nur einen <xref:System.Action>-Delegaten für jede Arbeitsaufgabe übergeben. Die einfachste Möglichkeit, diese Delegaten zu erstellen, sind Lambdaausdrücke. Der Lambdaausdruck kann entweder eine benannte Methode aufrufen oder den Code inline bereitstellen. Im folgenden Beispiel wird ein grundlegender <xref:System.Threading.Tasks.Parallel.Invoke%2A>-Aufruf dargestellt, der zwei Aufgaben erstellt und startet, die gleichzeitig ausgeführt werden. Die erste Aufgabe wird durch einen Lambda-Ausdruck dargestellt, der die `DoSomeWork`-Methode aufruft, und die zweite Aufgabe wird durch einen Lambda-Ausdruck dargestellt, der die `DoSomeOtherWork`-Methode aufruft.

> [!NOTE]
> Diese Dokumentation definiert Delegaten in TPL mithilfe von Lambdaausdrücken. Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

[!code-csharp[TPL#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#21)]
[!code-vb[TPL#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#21)]

> [!NOTE]
> Die Anzahl von <xref:System.Threading.Tasks.Task>-Instanzen, die im Hintergrund von <xref:System.Threading.Tasks.Parallel.Invoke%2A> erstellt werden, ist nicht notwendigerweise mit der Anzahl der bereitgestellten Delegaten identisch. Die TPL kann verschiedene Optimierungen einsetzen, besonders bei einer großen Anzahl von Delegaten.

Weitere Informationen finden Sie unter [Gewusst wie: Ausführen von parallelen Aufgaben mithilfe von Parallel.Invoke](../../../docs/standard/parallel-programming/how-to-use-parallel-invoke-to-execute-parallel-operations.md).

Wenn Sie die Aufgabenausführung präziser steuern oder einen Wert aus der Aufgabe zurückgeben möchten, müssen Sie expliziter mit <xref:System.Threading.Tasks.Task>-Objekten arbeiten.

## <a name="creating-and-running-tasks-explicitly"></a>Explizites Erstellen und Ausführen von Aufgaben

Eine Aufgabe, die keinen Wert zurückgibt, wird durch die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse dargestellt. Eine Aufgabe, die einen Wert zurückgibt, wird durch die <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Klasse dargestellt, die von <xref:System.Threading.Tasks.Task> erbt. Das Aufgabenobjekt verarbeitet die Infrastrukturdetails und stellt Methoden sowie Eigenschaften bereit, auf die während der gesamten Lebensdauer der Aufgabe vom aufrufenden Thread aus zugegriffen werden kann. Sie können beispielsweise jederzeit auf die <xref:System.Threading.Tasks.Task.Status%2A>-Eigenschaft einer Aufgabe zugreifen, um zu ermitteln, ob die Ausführung gestartet, abgeschlossen oder abgebrochen wurde bzw. ob eine Ausnahme ausgelöst wurde. Der Status wird durch eine <xref:System.Threading.Tasks.TaskStatus>-Enumeration dargestellt.

Wenn Sie eine Aufgabe erstellen, weisen Sie dieser einen Benutzerdelegaten zu, der den von der Aufgabe ausgeführten Code kapselt. Der Delegat kann als benannter Delegat, als anonyme Methode oder als Lambda-Ausdruck angegeben werden. Lambdaausdrücke können einen Aufruf einer benannten Methode enthalten, wie im folgenden Beispiel gezeigt. Beachten Sie, dass im Beispiel ein Aufruf der <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>-Methode enthalten ist, um sicherzustellen, dass die Aufgabe abgeschlossen ist, ehe die Konsolenmodusanwendung beendet wird.

[!code-csharp[TPL_TaskIntro#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/lambda1.cs#1)]
[!code-vb[TPL_TaskIntro#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/lambda1.vb#1)]

Sie können auch die <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>-Methoden verwenden, um eine Aufgabe in einem Vorgang zu erstellen und zu starten. Zum Verwalten der Aufgabe verwenden die <xref:System.Threading.Tasks.Task.Run%2A>-Methoden den Standardaufgabenplaner, unabhängig von dem Aufgabenplaner, der dem aktuellen Thread zugewiesen ist. Wenn eine präzisere Steuerung der Erstellung und Planung von Aufgaben nicht erforderlich ist, sollten diese vorzugsweise mit den <xref:System.Threading.Tasks.Task.Run%2A>-Methoden erstellt und gestartet werden.

[!code-csharp[TPL_TaskIntro#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/run1.cs#2)]
[!code-vb[TPL_TaskIntro#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/run1.vb#2)]

Sie können auch die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>-Methode verwenden, um eine Aufgabe in einem Schritt zu erstellen und zu starten. Verwenden Sie diese Methode, wenn Erstellung und Planung nicht getrennt werden müssen, zusätzliche Aufgabenerstellungsoptionen oder die Nutzung eines bestimmten Planers erforderlich sind oder der Aufgabe zusätzliche Zustände übergeben werden müssen, die über deren <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType>-Eigenschaft abgerufen werden können, wie im folgenden Beispiel dargestellt.

[!code-csharp[TPL_TaskIntro#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/asyncstate.cs#23)]
[!code-vb[TPL_TaskIntro#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/asyncstate.vb#23)]

<xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> machen jeweils eine statische <xref:System.Threading.Tasks.Task.Factory%2A>-Eigenschaft verfügbar, von der eine Standardinstanz von <xref:System.Threading.Tasks.TaskFactory> zurückgegeben wird, sodass Sie die Methode als `Task.Factory.StartNew()` aufrufen können. Darüber hinaus verfügen die Aufgaben im Beispiel, da sie vom <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Typ sind, jeweils über eine öffentliche <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>-Eigenschaft, die das Ergebnis der Berechnung enthält. Die Aufgaben werden asynchron ausgeführt und können in einer beliebigen Reihenfolge abgeschlossen werden. Wenn auf die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft zugegriffen wird, ehe die Berechnung beendet wurde, sperrt die Eigenschaft den aufrufenden Thread, bis der Wert verfügbar ist.

[!code-csharp[TPL_TaskIntro#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/result1.cs#4)]
[!code-vb[TPL_TaskIntro#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/result1.vb#4)]

Weitere Informationen finden Sie unter [Gewusst wie: Zurückgeben eines Werts aus einer Aufgabe](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md).

Wenn Sie einen Lambdaausdruck verwenden, um einen Delegaten zu erstellen, haben Sie Zugriff auf alle Variablen, die an dieser Stelle im Quellcode sichtbar sind. In einigen Fällen jedoch, insbesondere in Schleifen, wird die Variable nicht wie erwartet vom Lambda-Ausdruck erfasst. Es wird nur der endgültige Wert erfasst, und nicht der nach jeder Iteration geänderte Wert. Das Problem wird anhand des folgenden Beispiels veranschaulicht. Es wird ein Schleifenzähler an den Lambda-Ausdruck übergeben, wodurch ein `CustomData`-Objekt instanziiert wird und der Schleifenzähler als Objektbezeichner verwendet. Die Ausgabe im Beispiel zeigt, dass jedes `CustomData`-Objekt einen identischen Bezeichner hat.

[!code-csharp[TPL_TaskIntro#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/iteration1b.cs#22)]
[!code-vb[TPL_TaskIntro#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/iteration1b.vb#22)]

Sie können auf den Wert jeder Iteration zugreifen, indem Sie für die Aufgabe über ihren Konstruktor ein Zustandsobjekt bereitstellen. Im folgenden Beispiel wird das vorhergehende Beispiel geändert, indem der Schleifenzähler beim Erstellen des `CustomData`-Objekts verwendet wird, das wiederum an den Lambda-Ausdruck übergeben wird.  Wie die Ausgabe im Beispiel zeigt, weist jedes `CustomData`-Objekt jetzt einen eindeutigen Bezeichner basierend auf den Wert des Schleifenzählers zum Zeitpunkt der Instanziierung des Objekts auf.

[!code-csharp[TPL_TaskIntro#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/iteration1a.cs#21)]
[!code-vb[TPL_TaskIntro#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/iteration1a.vb#21)]

Dieser Zustand wird als Argument an den Aufgabendelegaten übergeben, und mit der <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType>-Eigenschaft kann über das Aufgabenobjekt auf den Zustand zugegriffen werden.  Das folgende Beispiel zeigt eine Abwandlung des vorherigen Beispiels. Es verwendet die <xref:System.Threading.Tasks.Task.AsyncState%2A>-Eigenschaft, um Informationen zu den `CustomData`-Objekten anzuzeigen, die an den Lambdaausdruck übergeben wurden.

[!code-csharp[TPL_TaskIntro#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/asyncstate.cs#23)]
[!code-vb[TPL_TaskIntro#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/asyncstate.vb#23)]

## <a name="task-id"></a>Aufgaben-ID

Jeder Aufgabe wird eine ganzzahlige ID zugeordnet, durch die diese in einer Anwendungsdomäne eindeutig identifiziert wird und auf die mit der <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=nameWithType>-Eigenschaft zugegriffen werden kann. Die ID vereinfacht das Anzeigen von Aufgabeninformationen in den Fenstern **Parallele Stapel** und **Parallele Aufgaben** des Visual Studio-Debuggers. Die ID wird verzögert erzeugt, d. h., sie wird erst nach einer entsprechenden Anforderung erstellt. Eine Aufgabe kann daher bei jeder Programmausführung eine andere ID aufweisen. Weitere Informationen zum Anzeigen von Aufgaben-IDs im Debugger finden Sie unter [Verwenden des Fensters „Aufgaben“](/visualstudio/debugger/using-the-tasks-window) und [Verwenden des Fensters „Parallele Stapel“](/visualstudio/debugger/using-the-parallel-stacks-window).

## <a name="task-creation-options"></a>Aufgabenerstellungsoptionen

Die meisten APIs, die Aufgaben erstellen, stellen Überladungen bereit, die einen <xref:System.Threading.Tasks.TaskCreationOptions>-Parameter akzeptieren. Durch Angabe einer dieser Optionen teilen Sie dem Aufgabenplaner mit, wie die Aufgabe im Threadpool geplant werden soll. In der folgenden Tabelle sind die verschiedenen Aufgabenerstellungsoptionen aufgeführt.

|<xref:System.Threading.Tasks.TaskCreationOptions>-Parameterwert|Beschreibung|
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|
|<xref:System.Threading.Tasks.TaskCreationOptions.None>|Dies ist die Standardoption, wenn keine Option angegeben wurde. Der Planer verwendet zum Planen der Aufgabe seine Standardheuristik.|
|<xref:System.Threading.Tasks.TaskCreationOptions.PreferFairness>|Gibt an, dass die Aufgabe so geplant werden soll, dass früher erstellte Aufgaben mit großer Wahrscheinlichkeit auch früher ausgeführt werden als Aufgaben, die später erstellt wurden.|
|<xref:System.Threading.Tasks.TaskCreationOptions.LongRunning>|Gibt an, dass die Aufgabe einen Vorgang mit langer Laufzeit darstellt.|
|<xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>|Gibt an, dass eine Aufgabe als angefügtes untergeordnetes Element der aktuellen Aufgabe erstellt werden soll (sofern vorhanden). Weitere Informationen finden Sie unter [Attached and Detached Child Tasks (Angefügte und getrennte untergeordnete Aufgaben)](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md).|
|<xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach>|Gibt an, dass beim Angeben der `AttachedToParent`-Option durch eine innere Aufgabe diese Aufgabe nicht zu einer angefügten untergeordneten Aufgabe wird.|
|<xref:System.Threading.Tasks.TaskCreationOptions.HideScheduler>|Gibt an, dass der Taskplaner für Aufgaben, die über das Aufrufen von Methoden wie <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> oder <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> aus einer bestimmten Aufgabe erstellt werden, der Standardplaner ist und nicht der Planer, mit dem diese Aufgabe ausgeführt wird.|

Die Optionen können mit einer bitweisen **OR**-Operation kombiniert werden. Im folgenden Beispiel wird eine Aufgabe veranschaulicht, die über die <xref:System.Threading.Tasks.TaskCreationOptions.LongRunning>-Option und die <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness>-Option verfügt.

[!code-csharp[TPL_TaskIntro#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#03)]
[!code-vb[TPL_TaskIntro#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#03)]

## <a name="tasks-threads-and-culture"></a>Aufgaben, Threads und Kultur

Jeder Thread hat eine zugeordnete Kultur und Benutzeroberflächenkultur, die durch die <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>- bzw. die <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft definiert ist. Die Kultur eines Threads wird in Vorgängen wie Formatieren, Analysieren, Sortieren und Zeichenfolgenvergleich verwendet. Die Benutzeroberflächenkultur eines Threads wird für Nachschlagen in Ressourcen verwendet. Normalerweise sind die Standardkultur und -benutzeroberflächenkultur eines Threads durch die Systemkultur definiert, es sei denn, Sie legen eine Standardkultur für alle Threads in einer Anwendungsdomäne mit der <xref:System.Globalization.CultureInfo.DefaultThreadCurrentCulture%2A?displayProperty=nameWithType>- und der <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft fest. Wenn Sie die Kultur eines Threads explizit festlegen und einen neuen Thread starten, erbt der neue Thread nicht die Kultur des aufrufenden Threads, sondern die Standardkultur des Systems wird als seine Kultur verwendet. Im aufgabenbasierten Programmiermodell für Anwendungen, die gezielt Versionen von .NET Framework vor .NET Framework 4.6 verwenden, wird so vorgegangen.

> [!IMPORTANT]
> Beachten Sie, dass die Kultur des aufrufenden Threads (als Bestandteil des Kontexts einer Aufgabe) für Anwendungen gilt, die *gezielt* .NET Framework 4.6 verwenden, und nicht für Anwendungen, deren *Ausführung unter* .NET Framework 4.6 erfolgt. Sie können beim Erstellen Ihres Projekts in Visual Studio eine bestimmte Version von .NET Framework als Ziel angeben, indem Sie diese Version aus der Dropdownliste am oberen Rand des Dialogfelds **Neues Projekt** auswählen; außerhalb von Visual Studio können Sie das <xref:System.Runtime.Versioning.TargetFrameworkAttribute>-Attribut verwenden. Bei Anwendungen, die gezielt Versionen von .NET Framework vor .NET Framework 4.6 verwenden oder auf keine bestimmte Version von .NET Framework ausgerichtet sind, wird die Kultur einer Aufgabe weiterhin durch die Kultur des Threads bestimmt, über den sie ausgeführt werden.

Beginnend mit Anwendungen, die gezielt .NET Framework 4.6 verwenden, erbt jede Aufgabe die Kultur des aufrufenden Threads. Das gilt selbst dann, wenn die Aufgabe asynchron über einen Threadpoolthread ausgeführt wird.

Das folgende Beispiel bietet eine einfache Veranschaulichung. In dem Beispiel wird das Attribut <xref:System.Runtime.Versioning.TargetFrameworkAttribute> verwendet, um gezielt .NET Framework 4.6 zu verwenden, und die aktuelle Kultur der Anwendung wird entweder in Französisch (Frankreich) oder, wenn Französisch (Frankreich) bereits die aktuelle Kultur ist, in Englisch (USA) geändert. Anschließend wird der Delegat `formatDelegate` aufgerufen, der einige Zahlen zurückgibt, die als Währungswerte in der neuen Kultur formatiert sind. Beachten Sie, dass der Delegat unabhängig davon, ob er als Aufgabe synchron oder asynchron ausgeführt wird, das erwartete Ergebnis zurückgibt, weil die asynchrone Aufgabe die Kultur des aufrufenden Threads erbt.

[!code-csharp[System.Globalization.CultureInfo.Class.Async#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.cultureinfo.class.async/cs/asyncculture1.cs#5)]
[!code-vb[System.Globalization.CultureInfo.Class.Async#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.cultureinfo.class.async/vb/asyncculture1.vb#5)]

Wenn Sie Visual Studio verwenden, können Sie das <xref:System.Runtime.Versioning.TargetFrameworkAttribute>-Attribut weglassen und stattdessen beim Erstellen des Projekts im Dialogfeld **Neues Projekt** .NET Framework 4.6 als Ziel auswählen.

Wenn die Ausgabe das Verhalten von Apps widerspiegeln soll, die gezielt .NET Framework-Versionen vor .NET Framework 4.6 verwenden, entfernen Sie das Attribut <xref:System.Runtime.Versioning.TargetFrameworkAttribute> aus dem Quellcode. Die Ausgabe entspricht den Formatierungskonventionen der Standardsystemkultur, nicht der Kultur des aufrufenden Threads.

Weitere Informationen zu asynchronen Aufgaben und Kultur, finden Sie im Thema <xref:System.Globalization.CultureInfo> im Abschnitt "Kultur und asynchrone aufgabenbasierte Vorgänge".

## <a name="creating-task-continuations"></a>Erstellen von Aufgabenfortsetzungen

Mithilfe der Methoden <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> können Sie eine Aufgabe angeben, die gestartet werden soll, wenn die *Vorgängeraufgabe* abgeschlossen wurde. An den Delegaten der Fortsetzungsaufgabe wird ein Verweis auf die vorherige Aufgabe übergeben, damit dieser den Status der vorherigen Aufgabe überprüfen kann und durch Abruf des Werts der <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>-Eigenschaft die Ausgabe der vorherigen Aufgabe als Eingabe für die Fortsetzung verwenden kann.

Im folgenden Beispiel wird die `getData`-Aufgabe durch einen Aufruf der <xref:System.Threading.Tasks.TaskFactory.StartNew%60%601%28System.Func%7B%60%600%7D%29?displayProperty=nameWithType>-Methode gestartet. Die `processData`-Aufgabe wird automatisch gestartet, wenn `getData` endet, und `displayData` wird gestartet, wenn `processData` endet. `getData` erzeugt ein Ganzzahlarray, auf das über die `processData`-Aufgabe durch die `getData`-Eigenschaft der <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>-Aufgabe zugegriffen werden kann. Die `processData` Aufgabe verarbeitet das Array und gibt ein Ergebnis zurück, dessen Typ vom Rückgabetyp des Lambda-Ausdrucks abgeleitet wird, der an die <xref:System.Threading.Tasks.Task%601.ContinueWith%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%600%7D%2C%60%600%7D%29?displayProperty=nameWithType>-Methode übergeben wurde. Die `displayData`-Aufgabe wird automatisch ausgeführt, wenn  `processData` endet und das <xref:System.Tuple%603>-Objekt, das durch den `processData`-Lambda-Ausdruck zurückgegeben wurde, über die `displayData`-Eigenschaft der `processData`-Aufgabe für die  <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>-Aufgabe zugänglich ist. Die `displayData`-Aufgabe nutzt das Ergebnis der `processData`-Aufgabe und erzeugt ein Ergebnis, dessen Typ auf ähnliche Weise abgeleitet wird und das dem Programm in der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft zur Verfügung gestellt wird.

[!code-csharp[TPL_TaskIntro#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/continuations1.cs#5)]
[!code-vb[TPL_TaskIntro#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/continuations1.vb#5)]

Da <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> eine Instanzmethode ist, können Sie die Methodenaufrufe verketten, anstatt ein <xref:System.Threading.Tasks.Task%601>-Objekt für jede Vorgängeraufgabe zu instanziieren. Das folgende Beispiel entspricht funktionell dem vorherigen Beispiel, verkettet aber die Aufrufe der <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>-Methode. Beachten Sie, dass das <xref:System.Threading.Tasks.Task%601>-Objekt, das durch die Kette von Methodenaufrufen zurückgegeben wird, die endgültige Fortsetzungsaufgabe ist.

[!code-csharp[TPL_TaskIntro#24](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/continuations2.cs#24)]
[!code-vb[TPL_TaskIntro#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/continuations2.vb#24)]

Die <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>-Methode und die <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A>-Methode ermöglichen es Ihnen, die Ausführung von mehreren Aufgaben fortzusetzen.

Weitere Informationen finden Sie unter [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).

## <a name="creating-detached-child-tasks"></a>Erstellen von getrennten untergeordneten Aufgaben

Wenn durch Benutzercode, der in einer Aufgabe ausgeführt wird, eine neue Aufgabe ohne Angabe der <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>-Option erstellt wird, ist die neue Aufgabe auf keine besondere Weise mit der übergeordneten Aufgabe synchronisiert. Dieser Typ einer nicht synchronisierten Aufgabe wird als *getrennte geschachtelte Aufgabe* oder *getrennte untergeordnete Aufgabe* bezeichnet. Im folgenden Beispiel wird eine Aufgabe dargestellt, die eine getrennte untergeordnete Aufgabe erstellt.

[!code-csharp[TPL_TaskIntro#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#07)]
[!code-vb[TPL_TaskIntro#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#07)]

Beachten Sie, dass die übergeordnete Aufgabe nicht auf den Abschluss der getrennten untergeordneten Aufgabe wartet.

## <a name="creating-child-tasks"></a>Erstellen von untergeordneten Aufgaben

Wenn durch Benutzercode, der in einer Aufgabe ausgeführt wird, eine Aufgabe mit der <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>-Option erstellt wird, wird die neue Aufgabe als *angefügte untergeordnete Aufgabe* der übergeordneten Aufgabe bezeichnet. Mithilfe der <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>-Option können Sie eine strukturierte Aufgabenparallelität angeben, da die übergeordnete Aufgabe implizit auf den Abschluss aller angefügten untergeordneten Aufgaben wartet. Im folgenden Beispiel wird eine übergeordnete Aufgabe dargestellt, die zehn angefügte untergeordnete Aufgaben erstellt. Beachten Sie, dass, obwohl das Beispiel die <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>-Methode aufruft, um auf den Abschluss der übergeordneten Aufgabe zu warten, nicht explizit auf den Abschluss der angefügten untergeordneten Aufgabe gewartet werden muss.

[!code-csharp[TPL_TaskIntro#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/child1.cs#8)]
[!code-vb[TPL_TaskIntro#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/child1.vb#8)]

Durch das Angeben der <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>-Option für eine übergeordnete Aufgabe kann das Anfügen anderer Aufgaben an die übergeordnete Aufgabe verhindert werden. Weitere Informationen finden Sie unter [Attached and Detached Child Tasks (Angefügte und getrennte untergeordnete Aufgaben)](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md).

## <a name="waiting-for-tasks-to-finish"></a>Warten auf die Beendigung von Aufgaben

Der <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Typ und der <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Typ bieten mehrere Überladungen der <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>-Methode, die das Warten auf den Abschluss einer Aufgabe ermöglichen. Außerdem können Sie mittels Überladungen der statischen <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>-Methode und der <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType>-Methode auf den Abschluss einer bestimmten oder aller Aufgaben in einem Array warten.

In der Regel wird aus einem der folgenden Gründe auf den Abschluss einer Aufgabe gewartet:

- Der Hauptthread hängt von dem Endergebnis ab, das von einer Aufgabe berechnet wird.

- Sie müssen Ausnahmen behandeln, die möglicherweise von der Aufgabe ausgelöst werden.

- Die Anwendung wird möglicherweise beendet, ehe die Ausführung aller Aufgaben abgeschlossen ist. Beispielsweise werden Konsolenanwendungen beendet, sobald der synchrone Code in `Main` (dem Anwendungseinstiegspunkt) ausgeführt wurde.

Im folgenden Beispiel wird das grundlegende Muster dargestellt, das keine Ausnahmebehandlung beinhaltet.

[!code-csharp[TPL_TaskIntro#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#06)]
[!code-vb[TPL_TaskIntro#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#06)]

Ein Beispiel, in dem die Behandlung von Ausnahmen veranschaulicht wird, finden Sie unter [Ausnahmebehandlung](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).

Bei einigen Überladungen können Sie einen Timeout angeben, während andere ein zusätzliches <xref:System.Threading.CancellationToken> als Eingabeparameter nutzen, sodass der Wartevorgang selbst entweder programmgesteuert oder als Reaktion auf eine Benutzereingabe abgebrochen werden kann.

Beim Warten auf eine Aufgabe wird implizit auf alle untergeordneten Elemente dieser Aufgabe gewartet, die mit der <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType>-Option erstellt wurden. <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> wird sofort zurückgegeben, wenn die Aufgabe bereits abgeschlossen wurde. Alle von einer Aufgabe ausgelöste Ausnahmen werden von einer <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>-Methode ausgelöst, auch wenn die <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>-Methode nach Abschluss der Aufgabe aufgerufen wurde.

## <a name="composing-tasks"></a>Verfassen von Aufgaben

Die Klassen <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> bieten mehrere Methoden zur einfacheren Erstellung mehrerer Aufgaben, um allgemeine Muster zu implementieren und die in C#, Visual Basic sowie F# bereitgestellten asynchronen Sprachfeatures besser einzusetzen. In diesem Abschnitt werden die Methoden <xref:System.Threading.Tasks.Task.WhenAll%2A>, <xref:System.Threading.Tasks.Task.WhenAny%2A>, <xref:System.Threading.Tasks.Task.Delay%2A> und <xref:System.Threading.Tasks.Task.FromResult%2A> beschrieben.

### <a name="taskwhenall"></a>Task.WhenAll

Die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>-Methode wartet asynchron auf den Abschluss mehrerer <xref:System.Threading.Tasks.Task>-Objekte oder <xref:System.Threading.Tasks.Task%601>-Objekte. Die Methode stellt überladene Versionen zum Warten auf nicht einheitliche Sätze von Aufgaben bereit. Beispielsweise kann in einem Methodenaufruf auf den Abschluss mehrerer <xref:System.Threading.Tasks.Task>-Objekte und <xref:System.Threading.Tasks.Task%601>-Objekte gewartet werden.

### <a name="taskwhenany"></a>Task.WhenAny

Die <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>-Methode wartet asynchron auf den Abschluss eines von mehreren <xref:System.Threading.Tasks.Task>-Objekten oder <xref:System.Threading.Tasks.Task%601>-Objekten. Wie die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>-Methode stellt auch diese Methode überladene Versionen bereit, mit denen auf nicht einheitliche Sätze von Aufgaben gewartet werden kann. Die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode ist insbesondere in folgenden Szenarien nützlich.

- Redundante Vorgänge. Betrachten Sie einen Algorithmus oder einen Vorgang, der auf verschiedene Weise ausgeführt werden kann. Sie können die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode verwenden, um den Vorgang auszuwählen, der zuerst beendet wird, und dann die verbleibenden Vorgänge abzubrechen.

- Überlappende Vorgänge. Sie können mehrere Vorgänge starten, die alle beendet werden müssen, und die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode verwenden, um Ergebnisse zu verarbeiten, wenn jeder Vorgang beendet wird. Nachdem ein Vorgang beendet wurde, können Sie eine oder mehrere weitere Aufgaben starten.

- Eingeschränkte Vorgänge. Sie können die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode verwenden, um das vorherige Szenario zu erweitern, indem Sie die Anzahl der gleichzeitigen Vorgänge einschränken.

- Abgelaufene Vorgänge. Sie können die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode verwenden, um eine Auswahl zwischen einer oder mehreren Aufgaben und einer anderen Aufgabe zu treffen, die nach einem bestimmten Zeitpunkt abgeschlossen wird, z. B. die von der <xref:System.Threading.Tasks.Task.Delay%2A>-Methode zurückgegebene Aufgabe. Die <xref:System.Threading.Tasks.Task.Delay%2A>-Methode wird im folgenden Abschnitt beschrieben.

### <a name="taskdelay"></a>Task.Delay

Die <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>-Methode generiert <xref:System.Threading.Tasks.Task>-Objekt, das nach dem angegebenen Zeitraum abgeschlossen wird. Mithilfe dieser Methode können Sie Schleifen erstellen, die gelegentlich Daten abrufen, Timeouts einfügen, die Verarbeitung von Benutzereingaben für einen vorab festgelegten Zeitraum verzögern usw.

### <a name="tasktfromresult"></a>Task(T).FromResult

Mit der <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType>-Methode, können Sie ein <xref:System.Threading.Tasks.Task%601>-Objekt erstellen, das ein vorberechnetes Ergebnis enthält. Diese Methode ist nützlich, wenn Sie einen asynchronen Vorgang ausführen, der ein <xref:System.Threading.Tasks.Task%601>-Objekt zurückgibt, und das Ergebnis dieses <xref:System.Threading.Tasks.Task%601>-Objekts bereits berechnet wurde. Ein Beispiel, in dem <xref:System.Threading.Tasks.Task.FromResult%2A> verwendet wird, um die Ergebnisse asynchroner Downloadvorgänge abzurufen, die in einem Cache gespeichert sind, finden Sie unter [Gewusst wie: Erstellen von vorberechneten Aufgaben](../../../docs/standard/parallel-programming/how-to-create-pre-computed-tasks.md).

## <a name="handling-exceptions-in-tasks"></a>Behandeln von Ausnahmen in Aufgaben

Wenn eine Aufgabe eine oder mehrere Ausnahmen auslöst, werden die Ausnahmen in eine <xref:System.AggregateException>-Ausnahme eingeschlossen. Diese Ausnahme wird an den Thread zurückgegeben, der mit der Aufgabe verbunden ist. In der Regel ist dies der Thread, der auf den Abschluss der Aufgabe wartet oder der Thread, der auf die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft zugreift. Dieses Verhalten trägt dazu bei, dass die .NET Framework-Richtlinie umgesetzt wird, der zufolge alle Ausnahmefehler standardmäßig zu einem Beenden des Prozesses führen. Der aufrufende Code kann die Ausnahmen behandeln, indem er Folgendes in einem `try`/`catch`-Block verwendet:

- Die <xref:System.Threading.Tasks.Task.Wait%2A> -Methode

- Die <xref:System.Threading.Tasks.Task.WaitAll%2A> -Methode

- Die <xref:System.Threading.Tasks.Task.WaitAny%2A> -Methode

- Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft.

Der Verbindungsthread kann Ausnahmen ebenfalls behandeln, indem er auf die <xref:System.Threading.Tasks.Task.Exception%2A>-Eigenschaft zugreift, bevor die Aufgabe der Garbage Collection zugeordnet wird. Durch den Zugriff auf diese Eigenschaft verhindern Sie, dass der Ausnahmefehler das Ausnahmeweitergabe-Verhalten auslöst, durch das der Prozess beim Abschluss des Objekts beendet wird.

Weitere Informationen zu Ausnahmen und Aufgaben finden Sie unter [Ausnahmebehandlung](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).

## <a name="canceling-tasks"></a>Abbrechen von Aufgaben

Die <xref:System.Threading.Tasks.Task>-Klasse unterstützt einen kooperativen Abbruch und ist vollständig in die <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>-Klasse und die <xref:System.Threading.CancellationToken?displayProperty=nameWithType>-Klasse integriert, die in .NET Framework 4 eingeführt wurden. Viele Konstruktoren in der <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse verwenden ein <xref:System.Threading.CancellationToken>-Objekt als Eingabeparameter. Viele der <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>- und <xref:System.Threading.Tasks.Task.Run%2A>-Überladungen enthalten auch einen <xref:System.Threading.CancellationToken>-Parameter.

Mit der <xref:System.Threading.CancellationTokenSource>-Klasse können Sie das Token erstellen und die Abbruchanforderung zu einem späteren Zeitpunkt ausgeben. Übergeben Sie das Token als Argument an <xref:System.Threading.Tasks.Task>, und verweisen Sie in dem Benutzerdelegaten, der auf eine Abbruchanforderung reagiert, auf das gleiche Token.

Weitere Informationen finden Sie unter [Aufgabenabbruch](../../../docs/standard/parallel-programming/task-cancellation.md) und [Gewusst wie: Abbrechen eine Aufgabe und der zugehörigen untergeordneten Aufgaben](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).

## <a name="the-taskfactory-class"></a>Die TaskFactory-Klasse

Die <xref:System.Threading.Tasks.TaskFactory>-Klasse stellt statische Methoden bereit, die einige allgemeine Muster zum Erstellen und Starten von Aufgaben und Fortsetzungsaufgaben kapseln.

- Das bekannteste Muster ist <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>, durch das in einer Anweisung eine Aufgabe erstellt und gestartet wird.

- Wenn Sie Fortsetzungsaufgaben aus mehreren Vorgängern erstellen, verwenden Sie die <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>-Methode oder die <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A>-Methode oder die äquivalenten Methoden in der <xref:System.Threading.Tasks.Task%601>-Klasse. Weitere Informationen finden Sie unter [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).

- Um die `BeginX`-Methode und `EndX`-Methode des asynchronen Programmiermodells in einer <xref:System.Threading.Tasks.Task>-Instanz oder <xref:System.Threading.Tasks.Task%601>-Instanz zu kapseln, verwenden Sie die <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>-Methoden. Weitere Informationen finden Sie unter [TPL und herkömmliche asynchrone .NET Framework-Programmierung](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md).

Auf die standardmäßige <xref:System.Threading.Tasks.TaskFactory> kann als statische Eigenschaft in der <xref:System.Threading.Tasks.Task>-Klasse oder <xref:System.Threading.Tasks.Task%601>-Klasse zugegriffen werden. Sie können eine <xref:System.Threading.Tasks.TaskFactory> auch direkt instanziieren und verschiedene Optionen angeben, einschließlich <xref:System.Threading.CancellationToken>, <xref:System.Threading.Tasks.TaskCreationOptions>, <xref:System.Threading.Tasks.TaskContinuationOptions> oder <xref:System.Threading.Tasks.TaskScheduler>. Die beim Erstellen der Aufgabenfactory angegebenen Optionen werden auf alle Aufgaben angewendet, die von dieser erstellt werden, außer Sie erstellen <xref:System.Threading.Tasks.Task> mit der <xref:System.Threading.Tasks.TaskCreationOptions>-Enumeration. In diesem Fall werden die Optionen der Aufgabenfactory mit den Optionen der Aufgabe überschrieben.

## <a name="tasks-without-delegates"></a>Aufgaben ohne Delegaten

In einigen Fällen können Sie mithilfe einer <xref:System.Threading.Tasks.Task> einen asynchronen Vorgang kapseln, der nicht von Ihrem Benutzerdelegaten, sondern von einer externen Komponente durchgeführt wird. Wenn der Vorgang auf dem Begin/End-Muster des asynchronen Programmiermodells basiert, können Sie die <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>-Methoden verwenden. Wenn das nicht der Fall ist, können Sie den Vorgang mithilfe des <xref:System.Threading.Tasks.TaskCompletionSource%601>-Objekts in eine Aufgabe einschließen und dadurch bestimmte Vorteile der <xref:System.Threading.Tasks.Task>-Programmierbarkeit erhalten, z. B. Unterstützung von Ausnahmeweitergabe und Fortsetzungen. Weitere Informationen finden Sie unter <xref:System.Threading.Tasks.TaskCompletionSource%601>.

## <a name="custom-schedulers"></a>Benutzerdefinierte Planer

Die meisten Anwendungs- oder Bibliotheksentwickler machen sich keine Gedanken über den für die Ausführung der Aufgabe verwendeten Prozessor, über die Synchronisierung der Arbeit mit anderen Aufgaben oder die Planung im <xref:System.Threading.ThreadPool?displayProperty=nameWithType>. Die einzige Voraussetzung für sie ist eine möglichst effiziente Ausführung auf dem Hostcomputer. Wenn Sie eine präzisere Steuerung der Planungsdetails benötigen, können Sie in der Task Parallel Library bestimmte Einstellungen im Standardaufgabenplaner konfigurieren und sogar einen benutzerdefinierten Planer angeben. Weitere Informationen finden Sie unter <xref:System.Threading.Tasks.TaskScheduler>.

## <a name="related-data-structures"></a>Verwandte Datenstrukturen

Die TPL beinhaltet zahlreiche neue öffentliche Typen, die sowohl in parallelen, als auch in sequenziellen Szenarios hilfreich sind. Hierzu zählen mehrere threadsichere, schnelle und skalierbare Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace sowie mehrere neue Synchronisierungstypen, z. B. <xref:System.Threading.Semaphore?displayProperty=nameWithType> und <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, die für bestimmte Arten von Arbeitslasten effizienter als ihre Vorgänger sind. Andere neue Typen in .NET Framework 4, z. B. <xref:System.Threading.Barrier?displayProperty=nameWithType> und <xref:System.Threading.SpinLock?displayProperty=nameWithType>, stellen Funktionalität bereit, die in früheren Releases nicht verfügbar war. Weitere Informationen finden Sie unter [Datenstrukturen für die parallele Programmierung](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md).

## <a name="custom-task-types"></a>Benutzerdefinierte Aufgabentypen

Es wird empfohlen, nicht von <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> oder <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> zu erben. Stattdessen sollten Sie die <xref:System.Threading.Tasks.Task.AsyncState%2A>-Eigenschaft verwenden, um einem <xref:System.Threading.Tasks.Task>-Objekt oder einem <xref:System.Threading.Tasks.Task%601>-Objekt zusätzliche Daten oder einen zusätzlichen Zustand zuzuordnen. Sie können auch Erweiterungsmethoden verwenden, um die Funktionen der <xref:System.Threading.Tasks.Task>-Klasse und der <xref:System.Threading.Tasks.Task%601>-Klasse zu erweitern. Weitere Informationen zu Erweiterungsmethoden finden Sie unter [Erweiterungsmethoden](../../csharp/programming-guide/classes-and-structs/extension-methods.md) und [Erweiterungsmethoden](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).

Wenn Sie von <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> erben müssen, können Sie nicht <xref:System.Threading.Tasks.Task.Run%2A> oder die Klassen <xref:System.Threading.Tasks.TaskFactory?displayProperty=nameWithType>, <xref:System.Threading.Tasks.TaskFactory%601?displayProperty=nameWithType> oder <xref:System.Threading.Tasks.TaskCompletionSource%601?displayProperty=nameWithType> zum Erstellen von Instanzen des benutzerdefinierten Aufgabentyps verwenden, da von diesen Mechanismen nur <xref:System.Threading.Tasks.Task>- und <xref:System.Threading.Tasks.Task%601>-Objekte erstellt werden. Außerdem können Sie nicht die von <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.TaskFactory> und <xref:System.Threading.Tasks.TaskFactory%601> bereitgestellten Aufgabenfortsetzungsmechanismen verwenden, um Instanzen des benutzerdefinierten Aufgabentyps zu erstellen, da mit diesen Mechanismen ebenfalls nur <xref:System.Threading.Tasks.Task>-Objekte und <xref:System.Threading.Tasks.Task%601>-Objekte erstellt werden.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-|-|
|[Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)|Beschreibt die Funktionsweise von Fortsetzungen.|
|[Angefügte und getrennte untergeordnete Aufgaben](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)|Beschreibt den Unterschied zwischen angefügten und getrennten untergeordneten Aufgaben.|
|[Aufgabenabbruch](../../../docs/standard/parallel-programming/task-cancellation.md)|Beschreibt die integrierte Abbruchunterstützung des <xref:System.Threading.Tasks.Task>-Objekts.|
|[Ausnahmebehandlung](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md)|Beschreibt die Behandlung von Ausnahmen in gleichzeitigen Threads.|
|[Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von Parallel.Invoke](../../../docs/standard/parallel-programming/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Beschreibt die Verwendung von <xref:System.Threading.Tasks.Parallel.Invoke%2A>.|
|[Gewusst wie: Zurückgeben eines Werts aus einer Aufgabe](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)|Beschreibt, wie in Aufgaben Werte zurückgegeben werden.|
|[Gewusst wie: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)|Beschreibt, wie Aufgaben abgebrochen werden.|
|[Gewusst wie: Erstellen von vorberechneten Aufgaben](../../../docs/standard/parallel-programming/how-to-create-pre-computed-tasks.md)|Beschreibt, wie mithilfe der <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType>-Methode die Ergebnisse asynchroner Downloadvorgänge aus einem Cache abgerufen werden können.|
|[Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben](../../../docs/standard/parallel-programming/how-to-traverse-a-binary-tree-with-parallel-tasks.md)|Beschreibt, wie Aufgaben zum Traversieren einer binären Struktur verwendet werden.|
|[Gewusst wie: Entpacken einer geschachtelten Aufgabe](../../../docs/standard/parallel-programming/how-to-unwrap-a-nested-task.md)|Veranschaulicht die Verwendung der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>-Erweiterungsmethode.|
|[Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)|Beschreibt, wie Sie mithilfe von <xref:System.Threading.Tasks.Parallel.For%2A> und <xref:System.Threading.Tasks.Parallel.ForEach%2A> parallele Schleifen für Daten erstellen.|
|[Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)|Der Knoten auf oberster Ebene für die parallele .NET Framework-Programmierung.|

## <a name="see-also"></a>Weitere Informationen

- [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
- [Beispiele für die parallele Programmierung mit .NET Framework](https://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
