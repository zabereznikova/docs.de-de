---
title: await (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- await_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 36
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 3656141c32a04e3a32a2992185f4c418c6915482
ms.contentlocale: de-de
ms.lasthandoff: 03/24/2017

---
# <a name="await-c-reference"></a>await (C#-Referenz)
Der Operator `await` wird auf eine Aufgabe in einer asynchronen Methode angewendet, um die Ausführung der Methode anzuhalten, bis die Aufgabe abgeschlossen ist. Die Aufgabe stellt derzeit ausgeführte Arbeit dar.  
  
 Die asynchrone Methode, in der `await` verwendet wird, muss mit dem Schlüsselwort [async](../../../csharp/language-reference/keywords/async.md) modifiziert werden. Eine solche mit dem `async`-Modifizierer definierte Methode, die in der Regel mindestens einen `await`-Ausdruck enthält, wird als *async-Methode* bezeichnet.  
  
> [!NOTE]
>  Die Schlüsselwörter `async` und `await` wurden in Visual Studio 2012 eingeführt. Eine Einführung in die asynchrone Programmierung finden Sie unter [Asynchronous Programming with async and await (Asynchrone Programmierung mit „async“ und „await“)](../../../csharp/programming-guide/concepts/async/index.md).  
  
 In der Regel ist die Aufgabe, auf die Sie den Operator `await` anwenden, der Rückgabewert eines Aufrufs einer Methode, die das [aufgabenbasierte asynchrone Muster](http://go.microsoft.com/fwlink/?LinkId=204847) implementiert. Beispiele dafür sind u.a. Werte der Typen <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>.  
  
 In folgendem Code gibt die <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> `Task\<byte[]>` und `getContentsTask` zurück. Diese Aufgabe enthält das Versprechen, das tatsächliche Bytearray zu erzeugen, wenn die Aufgabe abgeschlossen ist. Der Operator `await` wird auf `getContentsTask` angewendet, um die Ausführung in `SumPageSizesAsync` anzuhalten, bis `getContentsTask` abgeschlossen wurde. In der Zwischenzeit wird die Steuerung wieder an den Aufrufer von `SumPageSizesAsync` übergeben. Wenn `getContentsTask` beendet ist, wird der `await`-Ausdruck in ein Bytearray ausgewertet.  
  
```csharp  
private async Task SumPageSizesAsync()  
{  
    // To use the HttpClient type in desktop apps, you must include a using directive and add a   
    // reference for the System.Net.Http namespace.  
    HttpClient client = new HttpClient();  
    // . . .  
    Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);  
    byte[] urlContents = await getContentsTask;  
  
    // Equivalently, now that you see how it works, you can write the same thing in a single line.  
    //byte[] urlContents = await client.GetByteArrayAsync(url);  
    // . . .  
}  
```  
  
> [!IMPORTANT]
>  Das vollständige Beispiel finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sie können das Beispiel aus den [Codebeispielen für Entwickler](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) der Microsoft-Website herunterladen. Das Beispiel befindet sich im AsyncWalkthrough_HttpClient-Projekt.  
  
 Wird `await` auf das Ergebnis eines Methodenaufrufs angewendet, der `Task<TResult>` zurückgibt, ist der Typ des `await`-Ausdrucks "TResult", wie im vorherigen Beispiel gezeigt. Wird `await` auf das Ergebnis eines Methodenaufrufs angewendet, der `Task` zurückgibt, ist der Typ des `await`-Ausdrucks "void". Der Unterschied wird im folgenden Beispiel veranschaulicht.  
  
```csharp  
// Keyword await used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// Keyword await used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  
```  
  
 Ein `await`-Ausdruck blockiert nicht den Thread, auf dem er ausgeführt wird. Stattdessen bewirkt er, dass der Compiler den Rest der asynchronen Methode als Fortsetzung der erwarteten Aufgabe registriert. Die Steuerung wird dann wieder an den Aufrufer der Async-Methode übergeben. Wenn die Aufgabe abgeschlossen ist, löst sie ihre Fortsetzung aus, und die Ausführung der asynchronen Methode wird da fortgesetzt, wo sie angehalten wurde.  
  
 Ein `await`-Ausdruck kann nur in einer unmittelbar einschließenden Methode, einem Lambda-Ausdruck oder einer anonymen Methode auftreten, die durch einen `async`-Modifizierer gekennzeichnet ist. Der Begriff *await* dient nur in diesem Kontext als Schlüsselwort. In anderen Kontexten wird er als Bezeichner interpretiert. Innerhalb der Methode, des Lambdaausdrucks oder der anonymen Methode kann ein `await`-Ausdruck nicht im Textteil einer synchronen Funktion, einem Abfrageausdruck, im Block einer [lock-Anweisung](../../../csharp/language-reference/keywords/lock-statement.md) oder in einem [unsicheren](../../../csharp/language-reference/keywords/unsafe.md) Kontext auftreten.  
  
## <a name="exceptions"></a>Ausnahmen  
 Die meisten asynchronen Methoden geben einen <xref:System.Threading.Tasks.Task> oder einen <xref:System.Threading.Tasks.Task%601> zurück. Die Eigenschaften der zurückgegebenen Aufgabe enthalten Informationen über den Status und Verlauf, z. B. ob die Aufgabe abgeschlossen ist, ob die asynchrone Methode eine Ausnahme verursacht hat oder abgebrochen wurde, und was das Endergebnis ist. Der Operator `await` greift auf diese Eigenschaften zu.  
  
 Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und eine Ausnahme verursacht, löst der Operator `await` die Ausnahme erneut aus.  
  
 Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und abgebrochen wird, löst der Operator `await` erneut eine <xref:System.OperationCanceledException> aus.  
  
 Eine einzelne Aufgabe, die einen Fehlerzustand aufweist, kann verschiedene Ausnahmen auslösen. Die Aufgabe kann z. B. das Ergebnis eines Aufrufs von <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> sein. Wenn Sie auf eine solche Aufgabe warten, löst die await-Operation nur eine der Ausnahmen erneut aus. Sie können jedoch nicht vorhersagen, welche der Ausnahmen erneut ausgelöst wird.  
  
 Beispiele für die Fehlerbehandlung in asynchronen Methoden finden Sie unter [try-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Windows Forms-Beispielen wird die Verwendung von `await` in einer asynchronen Methode, `WaitAsynchronouslyAsync`, veranschaulicht. Vergleichen Sie das Verhalten der Methode mit dem Verhalten von `WaitSynchronously`. Ohne den `await`-Operator in der Aufgabe wird `WaitSynchronously` trotz der Verwendung des `async`-Modifizierers in ihrer Definition und einem Aufruf an <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> in ihrem Text synchron ausgeführt.  
  
```csharp  
private async void button1_Click(object sender, EventArgs e)  
{  
    // Call the method that runs asynchronously.  
    string result = await WaitAsynchronouslyAsync();  
  
    // Call the method that runs synchronously.  
    //string result = await WaitSynchronously ();  
  
    // Display the result.  
    textBox1.Text += result;  
}  
  
// The following method runs asynchronously. The UI thread is not  
// blocked during the delay. You can move or resize the Form1 window   
// while Task.Delay is running.  
public async Task<string> WaitAsynchronouslyAsync()  
{  
    await Task.Delay(10000);  
    return "Finished";  
}  
  
// The following method runs synchronously, despite the use of async.  
// You cannot move or resize the Form1 window while Thread.Sleep  
// is running because the UI thread is blocked.  
public async Task<string> WaitSynchronously()  
{  
    // Add a using directive for System.Threading.  
    Thread.Sleep(10000);  
    return "Finished";  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchrone Programmierung mit Async und Await](../../../csharp/programming-guide/concepts/async/index.md)   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [async](../../../csharp/language-reference/keywords/async.md)

