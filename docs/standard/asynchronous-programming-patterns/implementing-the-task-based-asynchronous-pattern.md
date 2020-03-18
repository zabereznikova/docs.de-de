---
title: Implementieren des aufgabenbasierten asynchronen Entwurfsmusters
ms.date: 06/14/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: fab6bd41-91bd-44ad-86f9-d8319988aa78
ms.openlocfilehash: 6218aa1a7b813601e9b718abf862e20a7cbcd313
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124306"
---
# <a name="implementing-the-task-based-asynchronous-pattern"></a>Implementieren des aufgabenbasierten asynchronen Entwurfsmusters
Sie können das aufgabenbasierte asynchrone Muster (Task-based Asynchronous Pattern, TAP) auf drei Arten implementieren: mit C# und den Visual Basic-Compilern in Visual Studio, manuell oder mit einer Kombination von Compilermethoden und manuellen Methoden. In den folgenden Abschnitten wird jede dieser Methoden ausführlich erörtert. Mit dem TAP-Muster können sowohl rechnergebundene als auch E/A-gebundene asynchrone Vorgänge implementiert werden. Im Abschnitt [Workloads](#workloads) werden die einzelnen Vorgangstypen erläutert.

## <a name="generating-tap-methods"></a>Generieren von TAP-Methoden

### <a name="using-the-compilers"></a>Verwenden der Compiler
Ab .NET Framework 4.5 gilt jede Methode, die mit dem Schlüsselwort `async` (`Async` in Visual Basic) attributiert ist, als asynchrone Methode, und die C#- und Visual Basic-Compiler führen die erforderlichen Transformationen aus, um die Methode mithilfe der TAP-Methode als asynchrone Methode zu implementieren. Eine asynchrone Methode sollte entweder <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>- oder ein <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Objekt zurückgeben. Im letzteren Fall sollte der Text der Funktion einen `TResult`-Typ zurückgeben, und der Compiler stellt sicher, dass dieses Ergebnis durch das resultierende Taskobjekt verfügbar gemacht wird. Entsprechend werden alle Ausnahmen, die im Text der Methode nicht behandelt werden, zur Ausgabeaufgabe gemarshallt und führen dazu, dass die resultierende Aufgabe im Zustand <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> endet. Die Ausnahme ist, wenn eine <xref:System.OperationCanceledException> (oder abgeleitete Typen) nicht behandelt wird. In diesem Fall enden die resultierenden Aufgaben im Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType>.

### <a name="generating-tap-methods-manually"></a>Manuelles Generieren von TAP-Methoden
Sie können das TAP-Muster manuell implementieren, um eine bessere Kontrolle über die Implementierung zu haben. Der Compiler nutzt den öffentlichen Oberflächenbereich, der über den <xref:System.Threading.Tasks?displayProperty=nameWithType>-Namespace verfügbar gemacht wird, und unterstützende Typen im <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace. Wenn Sie das TAP selbst implementieren möchten, erstellen Sie ein <xref:System.Threading.Tasks.TaskCompletionSource%601>-Objekt, führen Sie den asynchronen Vorgang aus, und wenn er abgeschlossen wurde, rufen Sie die Methode <xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetException%2A> oder <xref:System.Threading.Tasks.TaskCompletionSource%601.SetCanceled%2A> oder die `Try`-Version einer dieser Methoden auf. Wenn Sie eine TAP-Methode manuell implementieren, müssen Sie sicherstellen, dass die resultierende Aufgabe abgeschlossen wird, wenn der dargestellte asynchrone Vorgang abgeschlossen wird. Beispiel:

[!code-csharp[Conceptual.TAP_Patterns#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#1)]
[!code-vb[Conceptual.TAP_Patterns#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#1)]

### <a name="hybrid-approach"></a>Hybrider Ansatz
 Möglicherweise finden Sie es sinnvoll, das TAP-Muster manuell zu implementieren, die Kernlogik für die Implementierung jedoch an den Compiler zu delegieren. Sie können den hybriden Ansatz beispielsweise verwenden, wenn Sie Argumente außerhalb einer vom Compiler generierten asynchronen Methode überprüfen möchten, damit die Ausnahmen zum direkten Aufrufer der Methode überwechseln können, anstatt durch das Objekt <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> verfügbar gemacht zu werden:

 [!code-csharp[Conceptual.TAP_Patterns#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#2)]
 [!code-vb[Conceptual.TAP_Patterns#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#2)]

 Eine solche Delegierung ist auch sinnvoll, wenn Sie eine Beschleunigungsoptimierung implementieren und eine zwischengespeicherte Aufgabe zurückgeben möchten.

## <a name="workloads"></a>Arbeitslasten
Sowohl rechnergebundene als auch E/A-gebundene asynchrone Vorgänge können als TAP-Methoden implementiert werden. Wenn sie jedoch aus einer Bibliothek öffentlich verfügbar gemacht werden, sollten TAP-Methoden nur für Arbeitslasten bereitgestellt werden, die E/A-gebundene Vorgänge enthalten (sie können auch Berechnungen enthalten, jedoch nicht ausschließlich). Wenn eine Methode ausschließlich rechnergebunden ist, sollte sie nur als synchrone Implementierung verfügbar gemacht werden. Der verwendende Code kann dann entscheiden, ob ein Aufruf dieser synchronen Methode durch einen Task umschlossen werden soll, um die Arbeit in einen anderen Thread auszulagern oder Parallelität zu erreichen. Wenn eine Methode dagegen E/A-gebunden ist, sollte sie ausschließlich als asynchrone Implementierung verfügbar gemacht werden.

### <a name="compute-bound-tasks"></a>Rechnergebundene Tasks
Die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse ist perfekt zur Darstellung von rechenintensiven Vorgängen geeignet. Standardmäßig nutzt sie spezielle Unterstützung innerhalb der <xref:System.Threading.ThreadPool>-Klasse, um die effiziente Ausführung bereitzustellen, und bietet auch bedeutende Kontrolle darüber, wann, wo und wie asynchrone Berechnungen durchgeführt werden.

Sie können rechnergebundene Aufgaben auf die folgenden Arten generieren:

- Im .NET Framework 4 verwenden Sie die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>-Methode, die einen asynchron ausgeführten Delegaten (in der Regel einen <xref:System.Action%601> oder einen <xref:System.Func%601>) akzeptiert. Wenn Sie einen <xref:System.Action%601>-Delegaten bereitstellen, gibt die Methode ein <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekt zurück, das die asynchrone Ausführung dieses Delegaten darstellt. Wenn Sie einen <xref:System.Func%601>-Delegaten bereitstellen, gibt die Methode ein <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Objekt zurück. Überladungen der <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>-Methode akzeptieren ein Abbruchtoken (<xref:System.Threading.CancellationToken>), Aufgabenerstellungsoptionen (<xref:System.Threading.Tasks.TaskCreationOptions>) und einen Aufgabenplaner (<xref:System.Threading.Tasks.TaskScheduler>), die alle eine präzisere Steuerung der Planung und Ausführung der Aufgabe ermöglichen. Eine Factoryinstanz für den aktuellen Aufgabenplaner ist als statische Eigenschaft (<xref:System.Threading.Tasks.Task.Factory%2A>) der <xref:System.Threading.Tasks.Task>-Klasse verfügbar, z. B. `Task.Factory.StartNew(…)`.

- Verwenden Sie in .NET Framework 4.5 und höheren Versionen (einschließlich .NET Core und .NET Standard) die statische Methode <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> als Verknüpfung mit <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>. Sie können <xref:System.Threading.Tasks.Task.Run%2A> verwenden, um problemlos eine rechnergebundene Aufgabe zu starten, die auf den Threadpool abzielt. In .NET Framework 4.5 und höheren Versionen ist dies der bevorzugte Mechanismus zum Starten eines rechnergebundenen Tasks. Verwenden Sie `StartNew` nur dann direkt, wenn Sie eine präzisere Kontrolle über den Task haben möchten.

- Verwenden Sie die Konstruktoren des Typs `Task` oder der Methode `Start`, wenn Sie die Aufgabe separat generieren und planen möchten. Öffentliche Methoden dürfen nur Aufgaben zurückgeben, die bereits gestartet wurden.

- Verwenden Sie die Überladungen der <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>-Methode. Diese Methode erstellt eine neue Aufgabe, die geplant wird, wenn eine andere Aufgabe abgeschlossen wurde. Einige der <xref:System.Threading.Tasks.Task.ContinueWith%2A>-Überladungen akzeptieren ein Abbruchtoken, Fortsetzungsmöglichkeiten und einen Aufgabenplaner für eine bessere Steuerung der Planung und Ausführung der Fortsetzungsaufgabe.

- Verwenden Sie die <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>-Methode und die <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A?displayProperty=nameWithType>-Methode. Diese Methoden erstellen eine neue Aufgabe, die geplant wird, wenn eine oder alle Aufgaben in einem bereitgestellten Satz von Aufgaben abgeschlossen sind. Außerdem stellen diese Methoden Überladungen bereit, um die Planung und die Ausführung dieser Tasks zu steuern.

In rechnergebundenen Aufgaben kann das System die Ausführung einer geplanten Aufgabe verhindern, wenn es vor Start der Aufgabe eine Abbruchanforderung empfängt. Wenn Sie also ein Abbruchtoken (<xref:System.Threading.CancellationToken>- Objekt) bereitstellen, können Sie dieses Token an den asynchronen Code übergeben, der das Token überwacht. Sie können das Token auch an eine der zuvor erwähnten Methoden wie `StartNew` oder `Run` bereitstellen, damit die Laufzeit der `Task` auch das Token überwachen kann.

Betrachten Sie beispielsweise eine asynchrone Methode, die ein Bild rendert. Der Text der Aufgabe kann das Abbruchtoken abrufen, sodass während des Renderns die Ausführung des Codes vorzeitig beendet werden kann, falls eine Abbruchanforderung empfangen wird. Zudem sollten Sie den Renderingvorgang verhindern, wenn die Abbruchsanforderung eintrifft, bevor das Rendering beginnt:

[!code-csharp[Conceptual.TAP_Patterns#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#3)]
[!code-vb[Conceptual.TAP_Patterns#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#3)]

Rechnergebundene Aufgaben werden im Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled> beendet, wenn mindestens eine der folgenden Bedingungen erfüllt ist:

- Eine Abbruchanforderung geht über das <xref:System.Threading.CancellationToken>-Objekt ein, das als Argument an die Erstellungsmethode bereitgestellt wird (beispielsweise, `StartNew` oder `Run`), bevor die Aufgabe zum Zustand <xref:System.Threading.Tasks.TaskStatus.Running> übergeht.

- Eine <xref:System.OperationCanceledException>-Ausnahme wird im Text einer solchen Aufgabe nicht behandelt, diese Ausnahme enthält das gleiche <xref:System.Threading.CancellationToken>, das an die Aufgabe übergeben wird und dieses Token stellt dar, dass der Abbruch angefordert wird.

Wenn im Text der Aufgabe eine weitere Ausnahme nicht behandelt wird, wird diese im Zustand <xref:System.Threading.Tasks.TaskStatus.Faulted> beendet, und jeder Versuch, auf die Aufgabe zu warten oder auf ihr Ergebnis zuzugreifen, löst eine Ausnahme aus.

### <a name="io-bound-tasks"></a>E/A-gebundene Tasks
Um eine Aufgabe zu erstellen, die nicht vollständig in einem Thread ausgeführt werden sollen, wird der <xref:System.Threading.Tasks.TaskCompletionSource%601>-Typ verwendet. Dieser Typ macht eine <xref:System.Threading.Tasks.TaskCompletionSource%601.Task%2A>-Eigenschaft verfügbar, die eine zugeordnete <xref:System.Threading.Tasks.Task%601>-Instanz zurückgibt. Der Lebenszyklus dieser Aufgabe wird durch <xref:System.Threading.Tasks.TaskCompletionSource%601>-Methoden wie <xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetException%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetCanceled%2A> und ihre `TrySet` Varianten gesteuert.

Nehmen wir beispielsweise an, dass Sie eine Aufgabe erstellen möchten, die nach einem bestimmten Zeitraum abgeschlossen wird. Beispielsweise könnten Sie eine Aktivität in der Benutzeroberfläche verzögern. Die <xref:System.Threading.Timer?displayProperty=nameWithType>-Klasse ermöglicht es bereits, einen Delegaten nach einem angegebenen Zeitraum asynchron aufzurufen, und mit <xref:System.Threading.Tasks.TaskCompletionSource%601> lässt sich eine <xref:System.Threading.Tasks.Task%601>-Front für den Timer erstellen, wie im folgenden Beispiel:

[!code-csharp[Conceptual.TAP_Patterns#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#4)]
[!code-vb[Conceptual.TAP_Patterns#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#4)]

Ab .NET Framework 4.5 wird zu diesem Zweck die Methode <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> bereitgestellt, und Sie können sie in einer anderen asynchronen Methode verwenden, um beispielsweise eine asynchrone Abrufschleife zu implementieren:

[!code-csharp[Conceptual.TAP_Patterns#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#5)]
[!code-vb[Conceptual.TAP_Patterns#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#5)]

Die <xref:System.Threading.Tasks.TaskCompletionSource%601>-Klasse hat keine nicht generische Entsprechung. <xref:System.Threading.Tasks.Task%601> wird jedoch von <xref:System.Threading.Tasks.Task> abgeleitet, sodass das generische <xref:System.Threading.Tasks.TaskCompletionSource%601>-Objekt für Ein-/Ausgabe-gebundene Methoden verwendet werden kann, die einfach eine Aufgabe zurückgeben. Um dies zu erreichen, können Sie eine Quelle mit einem Dummy-`TResult` (<xref:System.Boolean>) verwenden. Das ist eine gute Standardmöglichkeit, aber wenn Sie darüber besorgt sind, dass der Benutzer der <xref:System.Threading.Tasks.Task> sie in eine <xref:System.Threading.Tasks.Task%601> umwandeln wird, können Sie stattdessen einen privaten `TResult`-Typ verwenden). Beispielsweise wurde die zuvor gezeigte `Delay`-Methode entwickelt, um die aktuelle Zeit zusammen mit dem resultierenden Offset (`Task<DateTimeOffset>`) zurückzugeben. Wenn ein solcher Ergebniswert nicht erforderlich ist, kann die Methode stattdessen wie folgt codiert werden (beachten Sie die Änderung des Rückgabetyps und die Änderung des Arguments in <xref:System.Threading.Tasks.TaskCompletionSource%601.TrySetResult%2A>):

[!code-csharp[Conceptual.TAP_Patterns#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#6)]
[!code-vb[Conceptual.TAP_Patterns#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#6)]

### <a name="mixed-compute-bound-and-io-bound-tasks"></a>Tasks, die sowohl rechnergebunden als auch E/A-gebunden sind
Asynchrone Methoden sind nicht auf ausschließlich rechnergebundene oder ausschließlich E/A-gebundene Vorgänge beschränkt, sondern können eine Mischung aus beiden Vorgangsarten darstellen. Tatsächlich werden mehrere asynchrone Operationen häufig zu größeren Mischvorgängen kombiniert. Die bereits gezeigte `RenderAsync`-Methode hat beispielsweise einen rechenintensiven Vorgang ausgeführt, um ein Bild auf Grundlage von eingegebenen `imageData` zu rendern. Die `imageData` können aus einem Webdienst stammen, auf den asynchron zugegriffen wird:

[!code-csharp[Conceptual.TAP_Patterns#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#7)]
[!code-vb[Conceptual.TAP_Patterns#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#7)]

Dieses Beispiel zeigt auch, wie ein einzelnes Abbruchstoken nacheinander in mehreren asynchronen Vorgängen verwendet werden kann. Weitere Informationen finden Sie im Abschnitt zur Verwendung von Abbruchtokens unter [Verwenden des aufgabenbasierten asynchronen Musters](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

## <a name="see-also"></a>Weitere Informationen

- [Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)
- [Nutzen des aufgabenbasierten asynchronen Musters](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)
- [Interoperabilität mit anderen asynchronen Mustern und Typen](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
