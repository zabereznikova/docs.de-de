---
title: Asynchrone Rückgabetypen (C#)
ms.date: 04/14/2020
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
ms.openlocfilehash: 73a6e1924652c8635377547e2faddc864ac5540a
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389135"
---
# <a name="async-return-types-c"></a>Asynchrone Rückgabetypen (C#)

Asynchrone Methoden können folgende Rückgabetypen haben:

- <xref:System.Threading.Tasks.Task%601> für eine asynchrone Methode, die einen Wert zurückgibt.
- <xref:System.Threading.Tasks.Task> für eine asynchrone Methode, die einen Vorgang ausführt, aber keinen Wert zurückgibt.
- `void` für einen Ereignishandler.
- Ab C# 7.0: jeder Typ, der über eine zugängliche `GetAwaiter`-Methode verfügt. Das von der `GetAwaiter`-Methode zurückgegebene Objekt muss die <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType>-Schnittstelle implementieren.
- Ab C# 8.0 <xref:System.Collections.Generic.IAsyncEnumerable%601> für eine asynchrone Methode, die einen *asynchronen Datenstrom* zurückgibt.

Weitere Informationen über die Methode „Async“ finden Sie unter [Asynchronous Programming with async and await (C#) (Asynchrone Programmierung mit Async und Await (C#))](./index.md).  
  
## <a name="tasktresult-return-type"></a>Rückgabetyp „Task\<TResult\>“  
Der Rückgabetyp <xref:System.Threading.Tasks.Task%601> wird für eine asynchrone Methode verwendet, die eine [return](../../../language-reference/keywords/return.md)-Anweisung (C#) enthält, in der der Operand `TResult` lautet.  
  
Im folgenden Beispiel enthält die asynchrone `GetLeisureHours`-Methode eine `return`-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund muss die Methodendeklaration den Rückgabetyp `Task<int>` haben.  Die asynchrone Methode <xref:System.Threading.Tasks.Task.FromResult%2A> ist ein Platzhalter für einen Vorgang, der eine Zeichenfolge zurückgibt.
  
:::code language="csharp" source="./snippets/async-returns1.cs" id="SnippetFirstExample":::

Wenn `GetLeisureHours` aus einem „await“-Ausdruck in der Methode `ShowTodaysInfo` aufgerufen wird, ruft der „await“-Ausdruck den ganzzahligen Wert ab (der Wert von `GetLeisureHours`), der in der Aufgabe gespeichert wird, die von der Methode `leisureHours` zurückgegeben wird. Weitere Informationen zu await-Ausdrücken finden Sie unter [await](../../../language-reference/operators/await.md).  
  
Wie `await` das Ergebnis aus einem `Task<T>` abruft, lässt sich besser erkennen, wenn Sie den Aufruf von `GetLeisureHours` von der Anwendung von `await` trennen, wie der folgende Code zeigt. Ein Aufruf der `GetLeisureHours`-Methode, die nicht sofort eine Antwort erwartet, gibt ein `Task<int>` zurück, wie Sie es von der Deklaration der Methode erwarten. Die Aufgabe wird im Beispiel der `integerTask`-Variablen zugewiesen. Da `integerTask` eine <xref:System.Threading.Tasks.Task%601> ist, enthält es eine <xref:System.Threading.Tasks.Task%601.Result>-Eigenschaft des Typs `TResult`. In diesem Fall stellt `TResult` einen Integertyp dar. Wenn `await` auf `integerTask` angewendet wird, wertet der „await“-Ausdruck den Inhalt der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A> von `integerTask` aus. Der Wert wird der `ret`-Variablen zugewiesen.  
  
> [!IMPORTANT]
> Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft ist eine Blocking-Eigenschaft. Wenn Sie darauf zuzugreifen versuchen, bevor seine Aufgabe beendet ist, wird der momentan aktive Thread blockiert, bis die Aufgabe abgeschlossen und der Wert verfügbar ist. In den meisten Fällen sollten Sie auf den Wert zugreifen, indem Sie `await` verwenden, anstatt direkt auf die Eigenschaft zuzugreifen. <br/> Im vorherigen Beispiel wurde der Wert der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A> abgerufen, um den Hauptthread zu blockieren, sodass die Methode `ShowTodaysInfo` die Ausführung beenden konnte, bevor die Anwendung beendet wurde.  

:::code language="csharp" source="./snippets/async-returns1a.cs" id="SnippetSecondVersion":::

## <a name="task-return-type"></a>Rückgabetyp „Task“  
Asynchrone Methoden, die keine `return`-Anweisung enthalten oder eine `return`-Anweisung enthalten, die keinen Operanden zurückgibt, haben normalerweise einen Rückgabetyp von <xref:System.Threading.Tasks.Task>. Solche Methoden geben `void` zurück, wenn sie synchron ausgeführt werden. Wenn Sie einen <xref:System.Threading.Tasks.Task>-Rückgabetyp für eine asynchrone Methode verwenden, kann ein aufrufende Methode einen `await`-Operator verwenden, um den Abschluss des Aufrufers anzuhalten, bis die aufgerufene asynchrone Methode beendet ist.  
  
Im folgenden Beispiel enthält die asynchrone Methode `WaitAndApologize` keine `return`-Anweisung, daher gibt die Methode ein <xref:System.Threading.Tasks.Task>-Objekt zurück. Durch Rückgabe von `Task` wird ermöglicht, dass `WaitAndApologize` erwartet wird. Der Typ <xref:System.Threading.Tasks.Task> enthält keine `Result`-Eigenschaft, da er nicht über einen Rückgabewert verfügt.  

:::code language="csharp" source="./snippets/async-returns2.cs" id="SnippetTaskReturn":::

`WaitAndApologize` wird erwartet, indem eine „await“-Anweisung anstelle eines „await“-Ausdrucks verwendet wird, ähnlich der Aufrufanweisung einer Methode, die „void“ zurückgibt. Die Anwendung eines Erwartungsoperators erzeugt in diesem Fall keinen Wert.  
  
Wie im vorherigen Beispiel <xref:System.Threading.Tasks.Task%601> können Sie den Aufruf von `WaitAndApologize` mit einem Erwartungsoperator trennen, wie der folgende Code zeigt. Beachten Sie jedoch, dass `Task` über keine `Result`-Eigenschaft verfügt und dass kein Wert erzeugt wird, wenn ein Erwartungsoperator auf `Task` angewendet wird.  
  
Der folgende Code trennt Aufrufe der Methode `WaitAndApologize` vom Erwarten der Aufgabe, die die Methode zurückgibt.  

:::code language="csharp" source="./snippets/async-returns2a.cs" id="SnippetAwaitTask":::

## <a name="void-return-type"></a>Rückgabetyp „Void“

Der Rückgabetyp `void` wird in asynchronen Ereignishandlern verwendet, die den Rückgabetyp `void` erfordern. Für andere Methoden als Ereignishandler, die keinen Wert zurückgeben, sollten Sie stattdessen <xref:System.Threading.Tasks.Task> zurückgeben, da eine asynchrone Methode, die `void` zurückgibt, nicht erwartet werden kann. Jeder Aufrufer einer solchen Methode muss bis zum Abschluss ausgeführt werden, ohne darauf zu warten, dass die aufgerufene asynchrone Methode abgeschlossen wird. Der Aufrufer muss von allen Werten oder Ausnahmen unabhängig sein, die von der asynchronen Methode generiert werden.  
  
Der Aufrufer einer asynchronen Methode, die „void“ zurückgibt, kann von der Methode ausgelöste Ausnahmen nicht behandeln, und solche Ausnahmefehler können möglicherweise zu Fehlern in der Anwendung führen. Wenn eine Methode, die <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt, eine Ausnahme auslöst, wird die Ausnahme im zurückgegebenen Task gespeichert. Die Ausnahme wird erneut ausgelöst, wenn auf den Task gewartet wird. Stellen Sie daher sicher, dass jede asynchrone Methode, die eine Ausnahme erstellen kann, über den Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> verfügt und die Aufrufe der Methode erwartet werden.  
  
Weitere Informationen zum Auffangen von Ausnahmen in asynchronen Methoden finden Sie im Abschnitt [Ausnahmen in Asynch-Methoden](../../../language-reference/keywords/try-catch.md#exceptions-in-async-methods) des Artikels [try-catch (C#-Referenz)](../../../language-reference/keywords/try-catch.md).  
  
Im folgenden Beispiel wird das Verhalten eines asynchronen Ereignishandlers dargestellt. Im Beispielcode muss ein asynchroner Ereignishandler dem Hauptthread mitteilen, dass er abgeschlossen wurde. Anschließend kann der Hauptthread darauf warten, dass ein asynchroner Ereignishandler abgeschlossen wird, bevor das Programm beendet wird.

:::code language="csharp" source="./snippets/async-returns3.cs":::

## <a name="generalized-async-return-types-and-valuetasktresult"></a>Generalisierte asynchrone Rückgabetypen und ValueTask\<TResult\>

Ab C# 7.0 kann eine asynchrone Methode jeden Typ zurückgeben, der über eine zugängliche `GetAwaiter`-Methode verfügt.

Da es sich bei <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> um Verweistypen handelt, kann bei der Speicherbelegung in leistungskritischen Pfaden, besonders bei Zuordnungen in engen Schleifen, die Leistung beeinträchtigt werden. Die Unterstützung für generalisierte Rückgabetypen bedeutet, dass Sie einen einfachen Werttyp statt eines Verweistypen zurückgeben können, um zusätzliche Speicherbelegungen zu vermeiden.

.NET stellt die Struktur <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> als einfache Implementierung eines generalisierten Werts bereit, der eine Aufgabe zurückgibt. Sie müssen das NuGet-Paket `System.Threading.Tasks.Extensions` zu Ihrem Projekt hinzufügen, um den Typ <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> zu verwenden. Im folgenden Beispiel wird die Struktur <xref:System.Threading.Tasks.ValueTask%601> verwendet, um den Wert von zwei Würfelvorgängen abzurufen.
  
:::code language="csharp" source="./snippets/async-valuetask.cs":::

## <a name="async-streams-with-iasyncenumerablet"></a>Asynchrone Datenströme mit IAsyncEnumerable\<T\>

Ab C# 8.0 kann eine asynchrone Methode einen *asynchronen Datenstrom* zurückgeben, der durch <xref:System.Collections.Generic.IAsyncEnumerable%601> dargestellt wird. Ein asynchroner Datenstrom bietet eine Möglichkeit zur Aufzählung von Elementen, die aus einem Datenstrom gelesen wurden, wenn die Elemente mit wiederholten asynchronen Aufrufen in Blöcken generiert werden. Das folgende Beispiel zeigt eine asynchrone Methode, die einen asynchronen Datenstrom generiert:

:::code language="csharp" source="./snippets/AsyncStreams.cs" id="SnippetGenerateAsyncStream":::

Das oben gezeigte Beispiel liest asynchron Zeilen aus einer Zeichenfolge. Sobald eine Zeile gelesen wurde, zählt der Code jedes Wort in der Zeichenfolge auf. Aufrufen zählen die einzelnen Wörter mit der `await foreach`-Anweisung auf. Die Methode wartet, wenn sie die nächste Zeile aus der Quellzeichenfolge asynchron lesen muss.

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Ablaufsteuerung in asynchronen Programmen (C#)](./control-flow-in-async-programs.md)
- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
