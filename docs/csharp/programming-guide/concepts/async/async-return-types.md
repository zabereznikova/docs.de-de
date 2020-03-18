---
title: Asynchrone Rückgabetypen (C#)
ms.date: 05/29/2017
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
ms.openlocfilehash: 9926fea5308f9088ad924bcc98d8deed319c6300
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170038"
---
# <a name="async-return-types-c"></a>Asynchrone Rückgabetypen (C#)
Asynchrone Methoden können folgende Rückgabetypen haben:

- <xref:System.Threading.Tasks.Task%601> für eine asynchrone Methode, die einen Wert zurückgibt.

- <xref:System.Threading.Tasks.Task> für eine asynchrone Methode, die einen Vorgang ausführt, aber keinen Wert zurückgibt.

- `void` für einen Ereignishandler.

- Ab C# 7.0: jeder Typ, der über eine zugängliche `GetAwaiter`-Methode verfügt. Das von der `GetAwaiter`-Methode zurückgegebene Objekt muss die <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType>-Schnittstelle implementieren.
  
Weitere Informationen über die Methode „Async“ finden Sie unter [Asynchronous Programming with async and await (C#) (Asynchrone Programmierung mit Async und Await (C#))](./index.md).  
  
Jeder Rückgabetyp wird in einem der folgenden Abschnitte untersucht und am Ende des Themas wird ein vollständiges Beispiel aller drei Typen verwenden.  
  
## Rückgabetyp <a name="BKMK_TaskTReturnType"></a> Task\<TResult\>  
Der <xref:System.Threading.Tasks.Task%601>-Rückgabetyp wird für eine asynchrone Methode verwendet, die eine [Rückgabeanweisung](../../../language-reference/keywords/return.md) (C#) enthält, in der der Operand den Typ `TResult` hat.  
  
Im folgenden Beispiel enthält die asynchrone `GetLeisureHours`-Methode eine `return`-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund muss die Methodendeklaration den Rückgabetyp `Task<int>` haben.  Die asynchrone Methode <xref:System.Threading.Tasks.Task.FromResult%2A> ist ein Platzhalter für einen Vorgang, der eine Zeichenfolge zurückgibt.
  
[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns1.cs)]

Wenn `GetLeisureHours` aus einem „await“-Ausdruck in der Methode `ShowTodaysInfo` aufgerufen wird, ruft der „await“-Ausdruck den ganzzahligen Wert ab (der Wert von `leisureHours`), der in der Aufgabe gespeichert wird, die von der Methode `GetLeisureHours` zurückgegeben wird. Weitere Informationen zu await-Ausdrücken finden Sie unter [await](../../../language-reference/operators/await.md).  
  
Sie können die Vorgehensweise besser verstehen, wenn Sie den Aufruf von `GetLeisureHours` von der Anwendung von `await` trennen, wie der folgenden Code zeigt. Ein Aufruf der `GetLeisureHours`-Methode, die nicht sofort eine Antwort erwartet, gibt ein `Task<int>` zurück, wie Sie es von der Deklaration der Methode erwarten. Die Aufgabe wird im Beispiel der `integerTask`-Variablen zugewiesen. Da `integerTask` eine <xref:System.Threading.Tasks.Task%601> ist, enthält es eine <xref:System.Threading.Tasks.Task%601.Result>-Eigenschaft des Typs `TResult`. In diesem Fall stellt `TResult` einen Integertyp dar. Wenn `await` auf `integerTask` angewendet wird, wertet der „await“-Ausdruck den Inhalt der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A> von `integerTask` aus. Der Wert wird der `ret`-Variablen zugewiesen.  
  
> [!IMPORTANT]
> Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft ist eine Blocking-Eigenschaft. Wenn Sie darauf zuzugreifen versuchen, bevor seine Aufgabe beendet ist, wird der momentan aktive Thread blockiert, bis die Aufgabe abgeschlossen und der Wert verfügbar ist. In den meisten Fällen sollten Sie auf den Wert zugreifen, indem Sie `await` verwenden, anstatt direkt auf die Eigenschaft zuzugreifen. <br/> Im vorherigen Beispiel wurde der Wert der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A> abgerufen, um den Hauptthread zu blockieren, sodass die Methode `ShowTodaysInfo` die Ausführung beenden konnte, bevor die Anwendung beendet wurde.  

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns1a.cs#1)]
  
## <a name="BKMK_TaskReturnType"></a> Aufgabenrückgabetyp  
Asynchrone Methoden, die keine `return`-Anweisung enthalten oder eine `return`-Anweisung enthalten, die keinen Operanden zurückgibt, haben normalerweise einen Rückgabetyp von <xref:System.Threading.Tasks.Task>. Solche Methoden geben `void` zurück, wenn sie synchron ausgeführt werden. Wenn Sie einen <xref:System.Threading.Tasks.Task>-Rückgabetyp für eine asynchrone Methode verwenden, kann ein aufrufende Methode einen `await`-Operator verwenden, um den Abschluss des Aufrufers anzuhalten, bis die aufgerufene asynchrone Methode beendet ist.  
  
Im folgenden Beispiel enthält die asynchrone Methode `WaitAndApologize` keine `return`-Anweisung, daher gibt die Methode ein <xref:System.Threading.Tasks.Task>-Objekt zurück. Dadurch wird ermöglicht, dass auf `WaitAndApologize` erwartet wird. Beachten Sie, dass der Typ <xref:System.Threading.Tasks.Task> keine `Result`-Eigenschaft enthält, da er nicht über einen Rückgabewert verfügt.  

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns2.cs)]  
  
`WaitAndApologize` wird erwartet, indem eine „await“-Anweisung anstelle eines „await“-Ausdrucks verwendet wird, ähnlich der Aufrufanweisung einer Methode, die „void“ zurückgibt. Die Anwendung eines Erwartungsoperators erzeugt in diesem Fall keinen Wert.  
  
Wie im vorherigen Beispiel <xref:System.Threading.Tasks.Task%601> können Sie den Aufruf von `WaitAndApologize` mit einem Erwartungsoperator trennen, wie der folgende Code zeigt. Beachten Sie jedoch, dass `Task` über keine `Result`-Eigenschaft verfügt und dass kein Wert erzeugt wird, wenn ein Erwartungsoperator auf `Task` angewendet wird.  
  
Der folgende Code trennt Aufrufe der Methode `WaitAndApologize` vom Erwarten der Aufgabe, die die Methode zurückgibt.  

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns2a.cs#1)]  

## <a name="BKMK_VoidReturnType"></a> Rückgabetyp „Void“

Der Rückgabetyp `void` wird in asynchronen Ereignishandlern verwendet, die den Rückgabetyp `void` erfordern. Für andere Methoden als Ereignishandler, die keinen Wert zurückgeben, sollten Sie stattdessen <xref:System.Threading.Tasks.Task> zurückgeben, da eine asynchrone Methode, die `void` zurückgibt, nicht erwartet werden kann. Jeder Aufrufer einer solchen Methode muss in der Lage sein, in seiner Ausführung bis zum Abschluss fortzufahren, ohne auf die aufgerufene asynchrone Methode zu warten, und der Aufrufer muss unabhängig von den Werten oder Ausnahmen sein, die die asynchrone Methode generiert.  
  
Der Aufrufer einer "void" zurückgebenden asynchronen Methode kann die von der Methode ausgelöste Ausnahmen nicht behandeln, und solche Ausnahmefehler können möglicherweise zu Fehlern in der Anwendung führen. Wenn eine Ausnahme in einer asynchronen Methode auftritt, die <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt, wird die Ausnahme in der zurückgegebenen Aufgabe gespeichert und erneut ausgelöst, wenn die Aufgabe erwartet wird. Stellen Sie daher sicher, dass jede asynchrone Methode, die eine Ausnahme erstellen kann, über den Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> verfügt und die Aufrufe der Methode erwartet werden.  
  
Weitere Informationen zum Auffangen von Ausnahmen in asynchronen Methoden finden Sie im Abschnitt [Ausnahmen in asynchronen Methoden](../../../language-reference/keywords/try-catch.md#exceptions-in-async-methods) im Thema [try-catch (C#-Referenz)](../../../language-reference/keywords/try-catch.md).  
  
Im folgenden Beispiel wird das Verhalten eines asynchronen Ereignishandlers dargestellt. Beachten Sie, dass ein asynchroner Ereignishandler im Beispielcode den Hauptthread wissen lassen muss, wenn dieser abgeschlossen wurde. Anschließend kann der Hauptthread darauf warten, dass ein asynchroner Ereignishandler abgeschlossen wird, bevor das Programm beendet wird.

[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-returns3.cs)]  

## <a name="generalized-async-return-types-and-valuetasktresult"></a>Generalisierte asynchrone Rückgabetypen und ValueTask\<TResult\>

Ab C# 7.0 kann eine asynchrone Methode jeden Typ zurückgeben, der über eine zugängliche `GetAwaiter`-Methode verfügt.

Da es sich bei <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> um Verweistypen handelt, kann bei der Speicherbelegung in leistungskritischen Pfaden, besonders bei Zuordnungen in engen Schleifen, die Leistung beeinträchtigt werden. Die Unterstützung für generalisierte Rückgabetypen bedeutet, dass Sie einen einfachen Werttyp statt eines Verweistypen zurückgeben können, um zusätzliche Speicherbelegungen zu vermeiden.

.NET stellt die Struktur <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> als einfache Implementierung eines generalisierten Werts bereit, der eine Aufgabe zurückgibt. Sie müssen das NuGet-Paket <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> zu Ihrem Projekt hinzufügen, um den Typ `System.Threading.Tasks.Extensions` zu verwenden. Im folgenden Beispiel wird die Struktur <xref:System.Threading.Tasks.ValueTask%601> verwendet, um den Wert von zwei Würfelvorgängen abzurufen.
  
[!code-csharp[return-value](../../../../../samples/snippets/csharp/programming-guide/async/async-valuetask.cs)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Ablaufsteuerung in asynchronen Programmen](./control-flow-in-async-programs.md)
- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
