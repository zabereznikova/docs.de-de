---
title: Asynchrone Rückgabetypen (C#)
description: Hier erhalten Sie Informationen zu Rückgabetypen, die asynchrone Methoden in C# aufweisen können, und Sie sehen Codebeispiele für die einzelnen Typen und weitere Ressourcen.
ms.date: 08/19/2020
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
ms.openlocfilehash: 71e560ed8ee0cae14da396e5ea2f3ab29611ebab
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811495"
---
# <a name="async-return-types-c"></a>Asynchrone Rückgabetypen (C#)

Asynchrone Methoden können folgende Rückgabetypen haben:

- <xref:System.Threading.Tasks.Task> für eine asynchrone Methode, die einen Vorgang ausführt, aber keinen Wert zurückgibt.
- <xref:System.Threading.Tasks.Task%601> für eine asynchrone Methode, die einen Wert zurückgibt.
- `void` für einen Ereignishandler.
- Ab C# 7.0: jeder Typ, der über eine zugängliche `GetAwaiter`-Methode verfügt. Das von der `GetAwaiter`-Methode zurückgegebene Objekt muss die <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType>-Schnittstelle implementieren.
- Ab C# 8.0 <xref:System.Collections.Generic.IAsyncEnumerable%601> für eine asynchrone Methode, die einen *asynchronen Datenstrom* zurückgibt.

Weitere Informationen über async-Methoden finden Sie unter [Asynchrone Programmierung mit async und await (C#)](./index.md).

Es gibt auch einige weitere Typen, die spezifisch für Windows-Workloads gelten:

- <xref:System.Windows.Threading.DispatcherOperation> für asynchrone Vorgänge, die auf Windows beschränkt sind
- <xref:Windows.Foundation.IAsyncAction> für asynchrone Aktionen in UWP, die keinen Wert zurückgeben
- <xref:Windows.Foundation.IAsyncActionWithProgress%601> für asynchrone Aktionen in UWP, die den Fortschritt melden, aber keinen Wert zurückgeben
- <xref:Windows.Foundation.IAsyncOperation%601> für asynchrone Vorgänge in UWP, die einen Wert zurückgeben
- <xref:Windows.Foundation.IAsyncOperationWithProgress%602> für asynchrone Vorgänge in UWP, die den Fortschritt melden und einen Wert zurückgeben

## <a name="task-return-type"></a>Task-Rückgabetyp

Asynchrone Methoden, die keine `return`-Anweisung enthalten oder eine `return`-Anweisung enthalten, die keinen Operanden zurückgibt, haben normalerweise einen Rückgabetyp von <xref:System.Threading.Tasks.Task>. Solche Methoden geben `void` zurück, wenn sie synchron ausgeführt werden. Wenn Sie einen <xref:System.Threading.Tasks.Task>-Rückgabetyp für eine asynchrone Methode verwenden, kann ein aufrufende Methode einen `await`-Operator verwenden, um den Abschluss des Aufrufers anzuhalten, bis die aufgerufene asynchrone Methode beendet ist.

Im folgenden Beispiel enthält die `WaitAndApologizeAsync`-Methode keine `return`-Anweisung, weshalb die Methode ein <xref:System.Threading.Tasks.Task>-Objekt zurückgibt. Durch Rückgabe von `Task` wird ermöglicht, dass `WaitAndApologizeAsync` erwartet wird. Der Typ <xref:System.Threading.Tasks.Task> enthält keine `Result`-Eigenschaft, da er nicht über einen Rückgabewert verfügt.

:::code language="csharp" source="snippets/async-return-types/async-returns2.cs" id="TaskReturn":::

`WaitAndApologizeAsync` wird erwartet, indem eine „await“-Anweisung anstelle eines „await“-Ausdrucks verwendet wird, ähnlich der Aufrufanweisung einer Methode, die „void“ zurückgibt. Die Anwendung eines Erwartungsoperators erzeugt in diesem Fall keinen Wert. Eine Erläuterung der Begriffe Anweisung und Ausdruck finden Sie in der folgenden Tabelle:

| Art von „await“ | Beispiel                                      | type                                   |
|------------|----------------------------------------------|----------------------------------------|
| -Anweisung.  | `await SomeTaskMethodAsync()`                | <xref:System.Threading.Tasks.Task>     |
| Ausdruck | `T result = await SomeTaskMethodAsync<T>();` | <xref:System.Threading.Tasks.Task%601> |

Sie können den `WaitAndApologizeAsync`-Aufruf eines await-Operators von der Anwendung trennen (dies wird im folgenden Code veranschaulicht). Beachten Sie jedoch, dass `Task` über keine `Result`-Eigenschaft verfügt und dass kein Wert erzeugt wird, wenn ein Erwartungsoperator auf `Task` angewendet wird.

Der folgende Code trennt Aufrufe der Methode `WaitAndApologizeAsync` vom Erwarten der Aufgabe, die die Methode zurückgibt.

:::code language="csharp" source="snippets/async-return-types/async-returns2a.cs" id="AwaitTask":::

## <a name="tasktresult-return-type"></a>Task-Rückgabetyp \<TResult\>

Der Rückgabetyp <xref:System.Threading.Tasks.Task%601> wird für eine asynchrone Methode verwendet, die eine [return](../../../language-reference/keywords/return.md)-Anweisung enthält, in der der Operand `TResult` lautet.

Im folgenden Beispiel enthält die `GetLeisureHoursAsync`-Methode eine `return`-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund muss die Methodendeklaration den Rückgabetyp `Task<int>` haben. Die asynchrone Methode <xref:System.Threading.Tasks.Task.FromResult%2A> ist ein Platzhalter für einen Vorgang, der einen <xref:System.DateTime.DayOfWeek>-Wert zurückgibt.

:::code language="csharp" source="snippets/async-return-types/async-returns1.cs" id="LeisureHours":::

Wenn `GetLeisureHoursAsync` aus einem „await“-Ausdruck in der Methode `ShowTodaysInfo` aufgerufen wird, ruft der „await“-Ausdruck den ganzzahligen Wert ab (der Wert von `GetLeisureHours`), der in der Aufgabe gespeichert wird, die von der Methode `leisureHours` zurückgegeben wird. Weitere Informationen zu await-Ausdrücken finden Sie unter [await](../../../language-reference/operators/await.md).

Wie `await` das Ergebnis aus einem `Task<T>` abruft, lässt sich besser erkennen, wenn Sie den Aufruf von `GetLeisureHoursAsync` von der Anwendung von `await` trennen, wie der folgende Code zeigt. Ein Aufruf der `GetLeisureHoursAsync`-Methode, die nicht sofort eine Antwort erwartet, gibt ein `Task<int>` zurück, wie Sie es von der Deklaration der Methode erwarten. Die Aufgabe wird im Beispiel der `getLeisureHoursTask`-Variablen zugewiesen. Da `getLeisureHoursTask` eine <xref:System.Threading.Tasks.Task%601> ist, enthält es eine <xref:System.Threading.Tasks.Task%601.Result>-Eigenschaft des Typs `TResult`. In diesem Fall stellt `TResult` einen Integertyp dar. Wenn `await` auf `getLeisureHoursTask` angewendet wird, wertet der „await“-Ausdruck den Inhalt der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A> von `getLeisureHoursTask` aus. Der Wert wird der `ret`-Variablen zugewiesen.

> [!IMPORTANT]
> Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft ist eine Blocking-Eigenschaft. Wenn Sie darauf zuzugreifen versuchen, bevor seine Aufgabe beendet ist, wird der momentan aktive Thread blockiert, bis die Aufgabe abgeschlossen und der Wert verfügbar ist. In den meisten Fällen sollten Sie auf den Wert zugreifen, indem Sie `await` verwenden, anstatt direkt auf die Eigenschaft zuzugreifen.
>
> Im vorherigen Beispiel wurde der Wert der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft abgerufen, um den Hauptthread zu blockieren, damit die `Main`-Methode `message` an die Konsole ausgeben konnte, bevor die Anwendung beendet wurde.

:::code language="csharp" source="snippets/async-return-types/async-returns1a.cs" id="StoreTask":::

## <a name="void-return-type"></a>Rückgabetyp „Void“

Der Rückgabetyp `void` wird in asynchronen Ereignishandlern verwendet, die den Rückgabetyp `void` erfordern. Für andere Methoden als Ereignishandler, die keinen Wert zurückgeben, sollten Sie stattdessen <xref:System.Threading.Tasks.Task> zurückgeben, da eine asynchrone Methode, die `void` zurückgibt, nicht erwartet werden kann. Jeder Aufrufer einer solchen Methode muss bis zum Abschluss ausgeführt werden, ohne darauf zu warten, dass die aufgerufene asynchrone Methode abgeschlossen wird. Der Aufrufer muss von allen Werten oder Ausnahmen unabhängig sein, die von der asynchronen Methode generiert werden.

Der Aufrufer einer asynchronen Methode, die „void“ zurückgibt, kann von der Methode ausgelöste Ausnahmen nicht behandeln, und solche Ausnahmefehler können möglicherweise zu Fehlern in der Anwendung führen. Wenn eine Methode, die <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt, eine Ausnahme auslöst, wird die Ausnahme im zurückgegebenen Task gespeichert. Die Ausnahme wird erneut ausgelöst, wenn auf den Task gewartet wird. Stellen Sie daher sicher, dass jede asynchrone Methode, die eine Ausnahme erstellen kann, über den Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> verfügt und die Aufrufe der Methode erwartet werden.

Weitere Informationen zum Auffangen von Ausnahmen in asynchronen Methoden finden Sie im Abschnitt [Ausnahmen in async-Methoden](../../../language-reference/keywords/try-catch.md#exceptions-in-async-methods) des Artikels [try-catch (C#-Referenz)](../../../language-reference/keywords/try-catch.md).

Im folgenden Beispiel wird das Verhalten eines asynchronen Ereignishandlers dargestellt. Im Beispielcode muss ein asynchroner Ereignishandler dem Hauptthread mitteilen, dass er abgeschlossen wurde. Anschließend kann der Hauptthread darauf warten, dass ein asynchroner Ereignishandler abgeschlossen wird, bevor das Programm beendet wird.

:::code language="csharp" source="snippets/async-return-types/async-returns3.cs":::

## <a name="generalized-async-return-types-and-valuetasktresult"></a>Generalisierte asynchrone Rückgabetypen und ValueTask\<TResult\>

Ab C# 7.0 kann eine asynchrone Methode jeden Typ zurückgeben, der über eine zugängliche `GetAwaiter`-Methode verfügt.

Da es sich bei <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> um Verweistypen handelt, kann bei der Speicherbelegung in leistungskritischen Pfaden, besonders bei Zuordnungen in engen Schleifen, die Leistung beeinträchtigt werden. Die Unterstützung für generalisierte Rückgabetypen bedeutet, dass Sie einen einfachen Werttyp statt eines Verweistypen zurückgeben können, um zusätzliche Speicherbelegungen zu vermeiden.

.NET stellt die Struktur <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> als einfache Implementierung eines generalisierten Werts bereit, der eine Aufgabe zurückgibt. Sie müssen das NuGet-Paket `System.Threading.Tasks.Extensions` zu Ihrem Projekt hinzufügen, um den Typ <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> zu verwenden. Im folgenden Beispiel wird die Struktur <xref:System.Threading.Tasks.ValueTask%601> verwendet, um den Wert von zwei Würfelvorgängen abzurufen.

:::code language="csharp" source="snippets/async-return-types/async-valuetask.cs":::

## <a name="async-streams-with-iasyncenumerablet"></a>Asynchrone Datenströme mit IAsyncEnumerable\<T\>

Ab C# 8.0 kann eine asynchrone Methode einen *asynchronen Datenstrom* zurückgeben, der durch <xref:System.Collections.Generic.IAsyncEnumerable%601> dargestellt wird. Ein asynchroner Datenstrom bietet eine Möglichkeit zur Aufzählung von Elementen, die aus einem Datenstrom gelesen wurden, wenn die Elemente mit wiederholten asynchronen Aufrufen in Blöcken generiert werden. Das folgende Beispiel zeigt eine asynchrone Methode, die einen asynchronen Datenstrom generiert:

:::code language="csharp" source="snippets/async-return-types/AsyncStreams.cs" id="GenerateAsyncStream":::

Das oben gezeigte Beispiel liest asynchron Zeilen aus einer Zeichenfolge. Sobald eine Zeile gelesen wurde, zählt der Code jedes Wort in der Zeichenfolge auf. Aufrufen zählen die einzelnen Wörter mit der `await foreach`-Anweisung auf. Die Methode wartet, wenn sie die nächste Zeile aus der Quellzeichenfolge asynchron lesen muss.

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Verarbeiten asynchroner Aufgaben nach Abschluss](start-multiple-async-tasks-and-process-them-as-they-complete.md)
- [Asynchrone Programmierung mit Async und Await (C#)](index.md)
- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
