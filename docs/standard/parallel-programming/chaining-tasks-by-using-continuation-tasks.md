---
title: Verketten von Tasks mithilfe von Fortsetzungstasks
description: Erfahren Sie, wie Sie in .NET Tasks mithilfe von Fortsetzungstasks verketten. Ein Fortsetzungstask ist ein asynchroner Task, der von einem anderen Task aufgerufen wird.
ms.date: 07/20/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, continuations
ms.assetid: 0b45e9a2-de28-46ce-8212-1817280ed42d
ms.openlocfilehash: 132518b9d8d22efecfcf3ed14e8b5969aa768cd4
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024588"
---
# <a name="chaining-tasks-using-continuation-tasks"></a>Verketten von Tasks mithilfe von Fortsetzungstasks

Bei der asynchronen Programmierung ruft ein asynchroner Vorgang nach seinem Abschluss häufig einen zweiten Vorgang auf. Fortsetzungen ermöglichen es nachfolgenden Vorgängen, die Ergebnisse des ersten Vorgangs zu nutzen. In der Vergangenheit wurden für diese Fortsetzungen vor allem Rückrufmethoden genutzt. In der Task Parallel Library wird die gleiche Funktionalität durch _Fortsetzungsaufgaben_bereitgestellt. Ein Fortsetzungstask (auch kurz als Fortsetzung bezeichnet) ist ein asynchroner Task, der von einem anderen Task, dem _Vorgänger_, nach dessen Beendigung aufgerufen wird.

Fortsetzungen können relativ einfach eingesetzt werden, sind dabei jedoch sehr leistungsstark und flexibel. Sie haben unter anderem folgende Möglichkeiten:

- Übergeben von Daten vom Vorgänger an die Fortsetzung
- Angeben der präzisen Bedingungen, unter denen die Fortsetzung aufgerufen bzw. nicht aufgerufen wird
- Abbrechen einer Fortsetzung vor dem Starten oder kooperativ während ihrer Ausführung
- Bereitstellen von Hinweisen zur Planung der Fortsetzung
- Aufrufen mehrerer Fortsetzungen durch den gleichen Vorgänger
- Aufrufen einer Fortsetzung, wenn alle Vorgänger abgeschlossen werden oder einer von mehreren Vorgängern abgeschlossen wird
- Verketten von Fortsetzungen der Reihe nach auf eine beliebige Länge
- Beheben von durch den Vorgänger ausgelösten Ausnahmen mithilfe einer Fortsetzung

## <a name="about-continuations"></a>Über Fortsetzungen

Eine Fortsetzung ist eine Aufgabe, die im <xref:System.Threading.Tasks.TaskStatus.WaitingForActivation> -Zustand erstellt wird. Sie wird automatisch aktiviert, wenn ihre Vorgängeraufgabe bzw. -aufgaben abgeschlossen wird bzw. werden. Das Aufrufen von <xref:System.Threading.Tasks.Task.Start%2A?displayProperty=nameWithType> für eine Fortsetzung in Benutzercode löst eine <xref:System.InvalidOperationException?displayProperty=nameWithType> -Ausnahme aus.

Eine Fortsetzung ist selbst ein <xref:System.Threading.Tasks.Task> und blockiert nicht den Thread, in dem sie gestartet wird. Rufen Sie die <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> -Methode auf, um den Thread bis zum Abschluss der Fortsetzungsaufgabe zu blockieren.

## <a name="create-a-continuation-for-a-single-antecedent"></a>Erstellen einer Fortsetzung für einen einzelnen Vorgänger

Sie erstellen eine Fortsetzung, die durch Aufrufen der Methode <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> ausgeführt wird, wenn ihr Vorgänger abgeschlossen wurde. Im folgenden Beispiel ist das grundlegende Muster dargestellt (aus Gründen der Übersichtlichkeit wird die Ausnahmebehandlung ausgelassen). Es führt eine Vorgängeraufgabe `taskA`aus, der ein <xref:System.DayOfWeek> -Objekt zurückgibt, der den Namen des aktuellen Wochentags angibt. Nach Abschluss des Vorgängers wird der Fortsetzungsaufgabe `continuation` der Vorgänger übergeben; sie zeigt dann eine Zeichenfolge an, die dessen Ergebnis beinhaltet.

> [!NOTE]
> Die C#-Beispiele in diesem Artikel verwenden den `async`-Modifizierer und die `Main`-Methode. Dieses Feature ist in C# 7.1 und höher verfügbar. In älteren Versionen wird beim Kompilieren des Beispielcodes [`CS5001`](../../csharp/misc/cs5001.md) generiert. Sie müssen deshalb als Sprachversion C# 7.1 oder höher verwenden. Im Artikel [Auswählen der C#-Sprachversion](../../csharp/language-reference/configure-language-version.md) erfahren Sie, wie Sie die Sprachversion konfigurieren können.

:::code language="csharp" source="snippets/cs/simple1.cs":::

[!code-vb[TPL_Continuations#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/simple1.vb#1)]

## <a name="create-a-continuation-for-multiple-antecedents"></a>Erstellen einer Fortsetzung für mehrere Vorgänger

Sie können auch eine Fortsetzung erstellen, die ausgeführt wird, wenn beliebige oder alle Aufgaben einer Gruppe abgeschlossen wurden. Zum Ausführen einer Fortsetzung nach dem Abschluss aller Vorgängeraufgaben rufen Sie die statische (`Shared` in Visual Basic) <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> -Methode oder die <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> -Instanzmethode auf. Zum Ausführen einer Fortsetzung nach dem Abschluss einer beliebigen Vorgängeraufgabe rufen Sie die statische (`Shared` in Visual Basic) <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> -Methode oder die <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A?displayProperty=nameWithType> -Instanzmethode auf.

Beachten Sie, dass Aufrufe der <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> - und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> -Überladungen den aufrufenden Thread nicht blockieren. Allerdings rufen Sie in der Regel alle Methoden außer <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAll%28System.Threading.Tasks.Task%5B%5D%29?displayProperty=nameWithType> auf, um die zurückgegebene <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>-Eigenschaft abzurufen, die den aufrufenden Thread blockiert.

Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> -Methode aufgerufen, um eine Fortsetzungsaufgabe zu erstellen, die die Ergebnisse ihrer zehn Vorgängeraufgaben wiedergibt. Jede Vorgängeraufgabe errechnet das Quadrat eines Indexwerts aus dem Bereich von 1 bis 10. Wenn die Vorgänger erfolgreich ausgeführt werden (also ihre <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> -Eigenschaft <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType>ist), stellt die <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> -Eigenschaft der Fortsetzung ein Array der <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> -Werte dar, die von den einzelnen Vorgängern zurückgegeben wurden. Im Beispiel werden sie addiert, um die Summe der Quadrate für alle Zahlen zwischen eins und zehn zu berechnen.

:::code language="csharp" source="snippets/cs/whenall1.cs":::

[!code-vb[TPL_Continuations#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/whenall1.vb#5)]

## <a name="continuation-options"></a>Fortsetzungsoptionen

Wenn Sie eine Fortsetzung einer einzelnen Aufgabe erstellen, können Sie eine <xref:System.Threading.Tasks.Task.ContinueWith%2A> -Überladung erstellen, die einen <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> -Enumerationswert annimmt, um die Bedingungen anzugeben, unter denen die Vorgängeraufgabe die Fortsetzung startet. Sie können beispielsweise angeben, dass die Fortsetzung nur ausgeführt werden soll, wenn der Vorgänger erfolgreich abgeschlossen wird, oder nur, wenn er in einem Fehlerzustand abgeschlossen wird. Wenn die Bedingung zu dem Zeitpunkt, zu dem der Vorgänger bereit ist, die Fortsetzung aufzurufen, nicht erfüllt ist, geht die Fortsetzung direkt in den Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> über und kann anschließend nicht mehr gestartet werden.

Eine Reihe von Fortsetzungsmethoden für mehrere Aufgaben, wie etwa Überladungen der Methode <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> , beinhalten außerdem einen Parameter <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> . Allerdings ist nur eine Teilmenge aller Elemente der <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> -Enumeration gültig. Sie können <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> -Werte angeben, die Entsprechungen in der <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=nameWithType> -Enumeration aufweisen, wie etwa <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType>, <xref:System.Threading.Tasks.TaskContinuationOptions.LongRunning?displayProperty=nameWithType>und <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness?displayProperty=nameWithType>. Wenn Sie für eine Fortsetzung mit mehreren Aufgaben die `NotOn` -Option oder die `OnlyOn` -Option angeben, wird zur Laufzeit eine <xref:System.ArgumentOutOfRangeException> -Ausnahme ausgelöst.

Weitere Informationen zu den Optionen für die Fortsetzung von Aufgaben finden Sie im Thema <xref:System.Threading.Tasks.TaskContinuationOptions> .

## <a name="pass-data-to-a-continuation"></a>Übergeben von Daten an eine Fortsetzung

Die Methode <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> übergibt einen Verweis auf den Vorgänger als Argument an den Benutzerstellvertreter der Fortsetzung. Wenn es sich beim dem Vorgänger um ein <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> -Objekt handelt und die Aufgabe bis zum Abschluss ausgeführt wurde, kann die Fortsetzung auf die <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> -Eigenschaft der Aufgabe zugreifen.

Die <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> -Eigenschaft ist bis zum Abschluss der Aufgabe blockiert. Wenn die Aufgabe jedoch abgebrochen oder als fehlerhaft gekennzeichnet wurde, wird beim Versuch, auf die <xref:System.Threading.Tasks.Task%601.Result%2A> -Eigenschaft zuzugreifen, eine <xref:System.AggregateException> -Ausnahme ausgegeben. Sie können dieses Problem vermeiden, indem Sie die <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnRanToCompletion> -Option wie im folgenden Beispiel gezeigt angeben.

:::code language="csharp" source="snippets/cs/result1.cs":::

[!code-vb[TPL_Continuations#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result1.vb#2)]

Wenn die Fortsetzung auch dann ausgeführt werden soll, wenn der Vorgänger nicht erfolgreich bis zum Abschluss ausgeführt wurde, müssen Sie Vorkehrungen gegen diese Ausnahme treffen. Ein Ansatz besteht darin, die Eigenschaft <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> des Vorgängers zu prüfen und den Zugriff auf die Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A> nur zu versuchen, wenn der Zustand nicht <xref:System.Threading.Tasks.TaskStatus.Faulted> oder <xref:System.Threading.Tasks.TaskStatus.Canceled>ist. Sie können jedoch auch die <xref:System.Threading.Tasks.Task.Exception%2A> -Eigenschaft des Vorgängers überprüfen. Weitere Informationen finden Sie unter [Ausnahmebehandlung (Task Parallel Library)](exception-handling-task-parallel-library.md). Im folgenden Beispiel wird das vorhergehende Beispiel verändert, und der Zugriff auf die Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> des Vorgängers erfolgt nur, wenn dessen Zustand <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType>ist.

:::code language="csharp" source="snippets/cs/result2.cs":::

[!code-vb[TPL_Continuations#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result2.vb#7)]

## <a name="cancel-a-continuation"></a>Abbrechen einer Fortsetzung

Die <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> -Eigenschaft einer Fortsetzung wird in den folgenden Situationen auf <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> festgelegt:

- Sie löst als Antwort auf eine Abbruchanforderung eine <xref:System.OperationCanceledException> -Ausnahme aus. Wenn die Ausnahme das gleiche Token enthält, das an die Fortsetzung übergeben wurde, wird dies als Bestätigung des kooperativen Abbruchs interpretiert, wie dies bei allen Aufgaben der Fall ist.
- Der Fortsetzung wird ein <xref:System.Threading.CancellationToken?displayProperty=nameWithType> übergeben, dessen <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> -Eigenschaft auf `true`festgelegt ist. In diesem Fall wird die Fortsetzung nicht gestartet und geht in den Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> über.
- Die Fortsetzung wird nie ausgeführt, das die von ihrem <xref:System.Threading.Tasks.TaskContinuationOptions> -Argument festgelegte Bedingung nicht erfüllt wurde. Wenn beispielsweise ein Vorgänger in einen <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> -Zustand übergeht, wird seine Fortsetzung, der die Option <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnFaulted?displayProperty=nameWithType> übergeben wurde, nicht ausgeführt, sondern geht stattdessen in den <xref:System.Threading.Tasks.TaskStatus.Canceled> -Zustand über.

Wenn eine Aufgabe und die zugehörige Fortsetzung zwei Teile des gleichen logischen Vorgangs sind, können Sie das gleiche Abbruchtoken an beide Aufgaben übergeben, wie im folgenden Beispiel gezeigt. Es besteht aus einem Vorgänger, der eine Liste mit ganzen Zahlen erstellt, die durch 33 teilbar sind und übergibt sie an die Fortsetzung. Die Fortsetzung zeigt ihrerseits die Liste an. Sowohl der Vorgänger als auch die Fortsetzung werden regelmäßig in zufälligen Intervallen angehalten. Darüber hinaus wird ein <xref:System.Threading.Timer?displayProperty=nameWithType> -Objekt verwendet, um die Methode `Elapsed` nach einem fünf Sekunden betragenden Timeoutintervall auszuführen. In diesem Beispiel wird die <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> -Methode aufgerufen, die bewirkt, dass die aktuell ausgeführte Aufgabe die <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A?displayProperty=nameWithType> -Methode aufruft. Ob die Methode <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> während der Ausführung des Vorgängers oder seiner Fortsetzung aufgerufen wird, hängt von der Dauer der zufällig generierten Pausen ab. Wenn der Vorgänger abgebrochen wurde, wird die Fortsetzung nicht gestartet. Wenn der Vorgänger nicht abgebrochen wird, kann das Token trotzdem zum Abbrechen der Fortsetzung verwendet werden.

:::code language="csharp" source="snippets/cs/cancellation1.cs":::

[!code-vb[TPL_Continuations#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation1.vb#3)]

Ferner können Sie die Ausführung einer Fortsetzung verhindern, wenn deren Vorgänger abgebrochen wird, ohne der Fortsetzung durch Angeben der Option <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled?displayProperty=nameWithType> beim Erstellen der Fortsetzung ein Abbruchtoken zu übergeben. Im Folgenden finden Sie ein einfaches Beispiel.

:::code language="csharp" source="snippets/cs/cancellation2.cs":::

[!code-vb[TPL_Continuations#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation2.vb#8)]

Nachdem eine Fortsetzung in den Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled> übergegangen ist, wirkt sich dies möglicherweise auf nachfolgende Fortsetzungen aus. Dies ist abhängig von den <xref:System.Threading.Tasks.TaskContinuationOptions> , die für die Fortsetzungen angegeben wurden.

Fortsetzungen, die verworfen wurden, werden nicht gestartet.

## <a name="continuations-and-child-tasks"></a>Fortsetzungen und untergeordnete Tasks

Eine Fortsetzung wird erst ausgeführt, wenn der Vorgänger und all zugehörigen untergeordneten Aufgaben abgeschlossen wurden. Die Fortsetzung wartet jedoch nicht, bis getrennte untergeordnete Aufgaben beendet wurden. Die beiden folgenden Beispiele veranschaulichen untergeordnete Aufgaben, die an einen Vorgänger, der eine Fortsetzung erstellt, angefügt und von ihm getrennt werden. Im folgenden Beispiel wird die Fortsetzung nur ausgeführt, wenn alle untergeordneten Aufgaben abgeschlossen wurden und die mehrfache Ausführung des Beispiels stets die gleiche Ausgabe erzeugt. Der Vorgänger im Beispiel wird durch Aufrufen der Methode <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> gestartet. Daher erstellt die Methode <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> standardmäßig eine übergeordnete Aufgabe, deren Standardoption zur Aufgabenerstellung <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> ist.

:::code language="csharp" source="snippets/cs/attached1.cs":::

[!code-vb[TPL_Continuations#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/attached1.vb#9)]

Wenn jedoch untergeordnete Aufgaben vom Vorgänger getrennt werden, wird die Fortsetzung ausgeführt, sobald der Vorgänger abgeschlossen wurde, unabhängig vom Zustand der untergeordneten Aufgaben. Daher können mehrfache Ausführungen des folgenden Beispiels veränderliche Ausgaben erzeugen, die davon abhängen, wie der Taskplaner die einzelnen untergeordneten Aufgaben verarbeitet hat.

:::code language="csharp" source="snippets/cs/detached1.cs":::

[!code-vb[TPL_Continuations#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/detached1.vb#10)]

Der Endstatus der Vorgängeraufgabe hängt vom Endstatus aller zugehörigen untergeordneten Aufgaben ab. Der Status getrennter untergeordneter Aufgaben wirkt sich nicht auf das übergeordnete Element aus. Weitere Informationen finden Sie unter [Angefügte und getrennte untergeordnete Aufgaben](attached-and-detached-child-tasks.md).

## <a name="associate-state-with-continuations"></a>Zuordnen eines Zustands zu Fortsetzungen

Sie können einer Aufgabenfortsetzung einen die oft ausgegebene Befehlszeilen  Zustand zuordnen. Die <xref:System.Threading.Tasks.Task.ContinueWith%2A> -Methode stellt überladene Versionen bereit, von denen jede einen <xref:System.Object> -Wert annimmt, der den Zustand der Fortsetzung darstellt. Sie können später mit der <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType> -Eigenschaft auf dieses Zustandsobjekt zugreifen. Das Zustandsobjekt ist `null` , wenn kein Wert angegeben wird.

Der Fortsetzungszustand ist bei der Verwendung der TPL nützlich, wenn Sie vorhandenen Code konvertieren, der das [Asynchrone Programmiermodell (APM)](../asynchronous-programming-patterns/asynchronous-programming-model-apm.md) verwendet. Im APM stellen Sie in der Regel den Objektzustand in der **Begin**_Method_-Methode bereit und greifen später mithilfe der <xref:System.IAsyncResult.AsyncState%2A?displayProperty=nameWithType>-Eigenschaft auf diesen Zustand zu. Mithilfe der <xref:System.Threading.Tasks.Task.ContinueWith%2A> -Methode können Sie diesen Zustand beibehalten, wenn Sie Code konvertieren, der das APM zur Verwendung der TPL verwendet.

Der Fortsetzungszustand kann außerdem hilfreich sein, wenn Sie mit <xref:System.Threading.Tasks.Task>-Objekten im Visual Studio-Debugger arbeiten. Beispielsweise wird im Fenster **Parallele Aufgaben** in der Spalte **Aufgabe** die Zeichenfolgendarstellung des Zustandsobjekts für jede Aufgabe angezeigt. Weitere Informationen zum Fenster **Parallele Aufgaben** finden Sie unter [Verwenden des Fensters „Aufgaben“](/visualstudio/debugger/using-the-tasks-window).

Im folgenden Beispiel wird die Verwendung eines Fortsetzungszustands gezeigt. Es erstellt eine Kette von Fortsetzungsaufgaben. Jede Aufgabe stellt die aktuelle Uhrzeit, ein <xref:System.DateTime> -Objekt, für den `state` -Parameter der <xref:System.Threading.Tasks.Task.ContinueWith%2A> -Methode bereit. Jedes <xref:System.DateTime> -Objekt stellt die Erstellungszeit der Fortsetzungsaufgabe dar. Jede Aufgabe erzeugt als Ergebnis ein zweites <xref:System.DateTime> -Objekt, das die Beendigungszeit der Aufgabe darstellt. Nach der Beendigung aller Aufgaben zeigt dieses Beispiel die Erstellungszeit und die Beendigungszeit jeder Fortsetzungsaufgabe an.

:::code language="csharp" source="snippets/cs/continuationstate.cs":::

[!code-vb[TPL_ContinuationState#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuationstate/vb/continuationstate.vb#1)]

## <a name="continuations-that-return-task-types"></a>Fortsetzungen, die Tasktypen zurückgeben

Zuweilen ist es erforderlich, eine Fortsetzung zu verketten, die einen <xref:System.Threading.Tasks.Task>-Typ zurückgibt. Diese werden als geschachtelte Tasks bezeichnet und kommen recht häufig vor. Wenn ein übergeordneter Task <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> aufruft und eine `continuationFunction` angibt, die einen Task zurückgibt, rufen Sie <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> auf, um einen Proxytask zu erstellen, der den asynchronen Vorgang von `<Task<Task<T>>>` oder `Task(Of Task(Of T))` (Visual Basic) repräsentiert.

Das folgende Beispiel zeigt, wie Fortsetzungen verwendet werden, die zusätzliche Funktionen umschließen, die Tasks zurückgeben. Die Umschließung jeder Fortsetzung kann aufgehoben werden, um den inneren Task verfügbar zu machen, der umschlossen war.

:::code language="csharp" source="snippets/cs/unwrap.cs":::
:::code language="vb" source="snippets/vb/unwrap.vb":::

Weitere Informationen zur Verwendung von <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> finden Sie unter [Gewusst wie: Entpacken einer geschachtelten Aufgabe](how-to-unwrap-a-nested-task.md).

## <a name="handle-exceptions-thrown-from-continuations"></a>Behandeln von durch Fortsetzungen ausgelösten Ausnahmen

Eine Vorgänger-Fortsetzung-Beziehung ist keine Beziehung zwischen übergeordneten und untergeordneten Elementen. Durch Fortsetzungen ausgelöste Ausnahmen werden nicht an den Vorgänger weitergegeben. Behandeln Sie Ausnahmen, die von Fortsetzungen ausgelöst wurden, daher wie bei allen anderen Aufgaben (siehe unten):

- Verwenden Sie die Methode <xref:System.Threading.Tasks.Task.Wait%2A>, <xref:System.Threading.Tasks.Task.WaitAll%2A>oder <xref:System.Threading.Tasks.Task.WaitAny%2A> bzw. die generische Entsprechung, um auf die Fortsetzung zu warten. Sie können in der gleichen `try` -Anweisung auf einen Vorgänger und seine Fortsetzungen warten, wie im folgenden Beispiel gezeigt.

:::code language="csharp" source="snippets/cs/exception1.cs":::

[!code-vb[TPL_Continuations#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception1.vb#6)]

- Sie können eine zweite Fortsetzung verwenden, um die <xref:System.Threading.Tasks.Task.Exception%2A> -Eigenschaft der ersten Fortsetzung zu beachten. In folgenden Beispiel versucht eine Aufgabe, aus einer nicht vorhandenen Datei zu lesen. In einem solchen Fall zeigt die Fortsetzung Informationen über die Ausnahme in der vorhergehenden Aufgabe an.

:::code language="csharp" source="snippets/cs/exception2.cs" id="example":::

[!code-vb[TPL_Continuations#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#4)]

Da die Ausführung mit der Option <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnFaulted?displayProperty=nameWithType> erfolgt ist, wird die Fortsetzung nur ausgeführt, wenn im Vorgänger eine Ausnahme auftritt, daher kann sie davon ausgehen, dass die Eigenschaft <xref:System.Threading.Tasks.Task.Exception%2A> des Vorgängers nicht `null`ist. Wenn die Fortsetzung unabhängig davon ausgeführt wird, ob im Vorgänger eine Ausnahme ausgelöst wurde, muss entsprechend eine Prüfung darauf erfolgen, dass die Eigenschaft <xref:System.Threading.Tasks.Task.Exception%2A> des Vorgängers nicht `null` ist, bevor versucht wird, die Ausnahme zu behandeln, wie im folgenden Beispiel dargestellt.

:::code language="csharp" source="snippets/cs/exception2.cs" id="exception":::

[!code-vb[TPL_Continuations#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#11)]

Weitere Informationen finden Sie unter [Ausnahmebehandlung (Task Parallel Library)](exception-handling-task-parallel-library.md).

- Wenn die Fortsetzung eine angefügte untergeordnete Aufgabe ist, die mit der <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType> -Option erstellt wurde, werden die zugehörigen Ausnahmen vom übergeordneten Element an den aufrufenden Thread zurückgegeben, wie dies auch bei allen anderen angefügten untergeordneten Elementen der Fall ist. Weitere Informationen finden Sie unter [Angefügte und getrennte untergeordnete Aufgaben](attached-and-detached-child-tasks.md).

## <a name="see-also"></a>Siehe auch

- [Task Parallel Library (TPL)](task-parallel-library-tpl.md)
