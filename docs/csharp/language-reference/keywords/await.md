---
title: await – C#-Referenz
ms.custom: seodec18
ms.date: 05/22/2017
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: c80d6598540700fdb8559497f10c66726c384519
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239682"
---
# <a name="await-c-reference"></a>await (C#-Referenz)
Der Operator `await` wird auf eine Aufgabe in einer asynchronen Methode angewendet, um einen Unterbrechungspunkt in die Ausführung der Methode einzufügen, bis die Aufgabe abgeschlossen ist. Die Aufgabe stellt derzeit ausgeführte Arbeit dar.  
  
`await` kann nur in einer asynchronen Methode verwendet werden, die vom Schlüsselwort [async](../../../csharp/language-reference/keywords/async.md) verändert wird. Eine solche mit dem `async`-Modifizierer definierte Methode, die in der Regel mindestens einen `await`-Ausdruck enthält, wird als *asynchrone Methode* bezeichnet.  
  
> [!NOTE]
>  Die Schlüsselwörter `async` und `await` wurden in C# 5 eingeführt. Eine Einführung in die asynchrone Programmierung finden Sie unter [Asynchronous Programming with async and await (Asynchrone Programmierung mit „async“ und „await“)](../../../csharp/programming-guide/concepts/async/index.md).  
  
In der Regel wird die Aufgabe, auf die Sie den Operator `await` anwenden, von einem Aufruf einer Methode zurückgegeben, die das [aufgabenbasierte asynchrone Muster](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) implementiert. Dazu zählen Methoden, die die Objekte <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> und `System.Threading.Tasks.ValueType<TResult>` zurückgeben.  

  
 Im folgenden Beispiel gibt die <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType>-Methode ein `Task<byte[]>`-Objekt zurück. Diese Aufgabe enthält das Versprechen, das tatsächliche Bytearray zu erzeugen, wenn die Aufgabe abgeschlossen ist. Der `await`-Operator hält die Ausführung an, bis die Arbeit der Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> abgeschlossen ist. In der Zwischenzeit wird die Steuerung wieder an den Aufrufer von `GetPageSizeAsync` übergeben. Wenn der Task die Ausführung beendet, wird der `await`-Ausdruck zu einem Bytearray ausgewertet.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await1.cs)]  

> [!IMPORTANT]
>  Das vollständige Beispiel finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sie können das Beispiel aus den [Codebeispielen für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) der Microsoft-Website herunterladen. Das Beispiel befindet sich im AsyncWalkthrough_HttpClient-Projekt.  
  
Wenn `await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der `Task<TResult>` zurückgibt, ist der Typ des `await`-Ausdrucks `TResult`, wie im vorherigen Beispiel gezeigt. Wenn `await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der `Task` zurückgibt, ist der Typ des `await`-Ausdrucks `void`. Der Unterschied wird im folgenden Beispiel veranschaulicht.  
  
```csharp  
// await keyword used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// await keyword used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  

// await keyword used with a method that returns a ValueTask<TResult>.
TResult result = await AsyncMethodThatReturnsValueTaskTResult();
```  
  
Ein `await`-Ausdruck blockiert nicht den Thread, auf dem er ausgeführt wird. Stattdessen bewirkt er, dass der Compiler den Rest der asynchronen Methode als Fortsetzung der erwarteten Aufgabe registriert. Die Steuerung wird dann wieder an den Aufrufer der Async-Methode übergeben. Wenn die Aufgabe abgeschlossen ist, löst sie ihre Fortsetzung aus, und die Ausführung der asynchronen Methode wird da fortgesetzt, wo sie angehalten wurde.  
  
Ein `await`-Ausdruck kann nur in seiner einschließenden Methode, einem Lambdaausdruck oder einer anonymen Methode auftreten, die durch einen `async`-Modifizierer gekennzeichnet sein muss. Der Begriff *await* dient nur in diesem Kontext als Schlüsselwort. In anderen Kontexten wird er als Bezeichner interpretiert. Innerhalb der Methode, des Lambdaausdrucks oder der anonymen Methode kann ein `await`-Ausdruck nicht im Textteil einer synchronen Funktion, einem Abfrageausdruck, im Block einer [lock-Anweisung](../../../csharp/language-reference/keywords/lock-statement.md) oder in einem [unsicheren](../../../csharp/language-reference/keywords/unsafe.md) Kontext auftreten.  
  
## <a name="exceptions"></a>Ausnahmen  
Die meisten asynchronen Methoden geben einen <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück. Die Eigenschaften der zurückgegebenen Aufgabe enthalten Informationen über den Status und Verlauf, z. B. ob die Aufgabe abgeschlossen ist, ob die asynchrone Methode eine Ausnahme verursacht hat oder abgebrochen wurde, und was das Endergebnis ist. Der Operator `await` greift auf diese Eigenschaften zu, indem er Methoden auf dem von der `GetAwaiter`-Methode zurückgegebenen Objekt aufruft.  
  
Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und eine Ausnahme verursacht, löst der Operator `await` die Ausnahme erneut aus.  
  
Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und abgebrochen wird, löst der Operator `await` erneut eine <xref:System.OperationCanceledException> aus.  
  
Eine einzelne Aufgabe, die einen Fehlerzustand aufweist, kann verschiedene Ausnahmen auslösen. Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> sein. Wenn Sie auf eine solche Aufgabe warten, löst die await-Operation nur eine der Ausnahmen erneut aus. Sie können jedoch nicht vorhersagen, welche der Ausnahmen erneut ausgelöst wird.  
  
Beispiele für die Fehlerbehandlung in asynchronen Methoden finden Sie unter [try-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird die Gesamtzahl der Zeichen auf den Seiten zurückgegeben, deren URLs als Befehlszeilenargumente übergeben werden. Im Beispiel wird die Methode `GetPageLengthsAsync` aufgerufen, die mit dem Schlüsselwort `async` gekennzeichnet ist. Die Methode `GetPageLengthsAsync` verwendet wiederum das Schlüsselwort `await`, um auf Aufrufe der Methode <xref:System.Net.Http.HttpClient.GetStringAsync%2A?displayProperty=nameWithType> zu warten.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await2.cs)]  

Im vorhergehenden Beispiel wird C# 7.1 verwendet, was die [`async` `Main`-Methode unterstützt](../../programming-guide/main-and-command-args/index.md). Da frühere C#-Versionen keine Anwendungseinstiegspunkte unterstützen, die <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgeben, können Sie den `async`-Modifikator nicht auf die `Main`-Methode anwenden und auf den Aufruf der `GetPageLengthsAsync`-Methode warten. In diesem Fall können Sie sicherstellen, dass die `Main`-Methode auf den Abschluss des asynchronen Vorgangs wartet, indem der Wert der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> abgerufen wird. Bei Aufgaben, die keinen Wert zurückgeben, wird die Methode <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> aufgerufen. Informationen zum Auswählen der Sprachversion finden Sie unter [Auswählen der C#-Sprachversion](../configure-language-version.md).

## <a name="see-also"></a>Siehe auch  
- [Asynchrone Programmierung mit Async und Await](../../../csharp/programming-guide/concepts/async/index.md)   
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
- [async](../../../csharp/language-reference/keywords/async.md)
