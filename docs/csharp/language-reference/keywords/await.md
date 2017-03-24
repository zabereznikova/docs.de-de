---
title: "await (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "await_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "await [C#]"
  - "Await-Schlüsselwort [C#]"
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 36
---
# await (C#-Referenz)
Der Operator `await` wird auf eine Aufgabe in einer asynchronen Methode angewendet, um die Ausführung der Methode anzuhalten, bis die Aufgabe abgeschlossen ist.  Die Aufgabe stellt derzeit ausgeführte Arbeit dar.  
  
 Die asynchrone Methode, in der `await` verwendet wird, muss mit dem Schlüsselwort [async](../../../csharp/language-reference/keywords/async.md) modifiziert werden.  Eine solche mit dem `async`\-Modifizierer definierte Methode, die in der Regel mindestens einen `await`\-Ausdruck enthält, wird als *Async\-Methode* bezeichnet.  
  
> [!NOTE]
>  Die Schlüsselwörter `async` und `await` wurden in Visual Studio 2012 eingeführt.  Eine Einführung über die asynchrone Programmierung finden Sie unter [Asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 In der Regel ist die Aufgabe, auf die Sie den Operator `await` anwenden, der Rückgabewert eines Aufrufs einer Methode, die das [aufgabenbasierte asynchrone Muster](http://go.microsoft.com/fwlink/?LinkId=204847).  Zu den Beispielen zählen Werte des Typs <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>.  
  
 Im folgenden Code gibt die <xref:System.Net.Http.HttpClient>\-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> einen `Task\<byte[]>``getContentsTask` zurück.  Diese Aufgabe enthält das Versprechen, das tatsächliche Bytearray zu erzeugen, wenn die Aufgabe abgeschlossen ist.  Der Operator `await` wird auf `getContentsTask` angewendet, um die Ausführung in `SumPageSizesAsync` anzuhalten, bis `getContentsTask` abgeschlossen wurde.  In der Zwischenzeit wird die Steuerung wieder an den Aufrufer von `SumPageSizesAsync` übergeben.  Wenn `getContentsTask` beendet ist, wird der `await`\-Ausdruck in ein Bytearray ausgewertet.  
  
```c#  
  
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
>  Das vollständige Beispiel finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Sie können das Beispiel unter [Entwickler\-Codebeispiele](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) auf der Microsoft\-Website herunterladen.  Das Beispiel befindet sich im AsyncWalkthrough\_HttpClient\-Projekt.  
  
 Wird `await` auf das Ergebnis eines Methodenaufrufs angewendet, der `Task<TResult>` zurückgibt, ist der Typ des `await`\-Ausdrucks "TResult", wie im vorherigen Beispiel gezeigt.  Wird `await` auf das Ergebnis eines Methodenaufrufs angewendet, der `Task` zurückgibt, ist der Typ des `await`\-Ausdrucks "void".  Der Unterschied wird im folgenden Beispiel veranschaulicht.  
  
```c#  
// Keyword await used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// Keyword await used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  
  
```  
  
 Ein `await`\-Ausdruck blockiert nicht den Thread, auf dem er ausgeführt wird.  Stattdessen bewirkt er, dass der Compiler den Rest der asynchronen Methode als Fortsetzung der erwarteten Aufgabe registriert.  Die Steuerung wird dann wieder an den Aufrufer der Async\-Methode übergeben.  Wenn die Aufgabe abgeschlossen ist, löst sie ihre Fortsetzung aus, und die Ausführung der asynchronen Methode wird da fortgesetzt, wo sie angehalten wurde.  
  
 Ein `await`\-Ausdruck kann nur in einer unmittelbar einschließenden Methode, einem Lambda\-Ausdruck oder einer anonymen Methode auftreten, die durch einen `async`\-Modifizierer gekennzeichnet ist.  Der Begriff *await* dient nur in diesem Kontext als Schlüsselwort.  In anderen Kontexten wird er als Bezeichner interpretiert.  Innerhalb der Methode, des Lambda\-Ausdrucks oder der anonymen Methode kann ein `await`\-Ausdruck nicht im Textteil einer synchronen Funktion, einem Abfrageausdruck, im Block einer [Ausnahmebehandlungsanweisung](../../../csharp/language-reference/keywords/lock-statement.md) oder in einem [unsicheren](../../../csharp/language-reference/keywords/unsafe.md) Kontext auftreten.  
  
## Ausnahmen  
 Die meisten asynchronen Methoden geben einen <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück.  Die Eigenschaften der zurückgegebenen Aufgabe enthalten Informationen über den Status und Verlauf, z. B. ob die Aufgabe abgeschlossen ist, ob die asynchrone Methode eine Ausnahme verursacht hat oder abgebrochen wurde, und was das Endergebnis ist.  Der Operator `await` greift auf diese Eigenschaften zu.  
  
 Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und eine Ausnahme verursacht, löst der Operator `await` die Ausnahme erneut aus.  
  
 Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und abgebrochen wird, löst der Operator `await` erneut eine <xref:System.OperationCanceledException> aus.  
  
 Eine einzelne Aufgabe, die einen Fehlerzustand aufweist, kann verschiedene Ausnahmen auslösen.  Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> sein.  Wenn Sie auf eine solche Aufgabe warten, löst die await\-Operation nur eine der Ausnahmen erneut aus.  Sie können jedoch nicht vorhersagen, welche der Ausnahmen erneut ausgelöst wird.  
  
 Beispiele für die Fehlerbehandlung in asynchronen Methoden finden Sie unter [try\-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## Beispiel  
 Im folgenden Windows Forms\-Beispielen wird die Verwendung von `await` in einer asynchronen Methode, `WaitAsynchronouslyAsync`, veranschaulicht.  Vergleichen Sie das Verhalten der Methode mit dem Verhalten von `WaitSynchronously`.  Ohne den `await`\-Operator in der Aufgabe wird `WaitSynchronously` trotz der Verwendung des `async`\-Modifizierers in ihrer Definition und einem Aufruf an <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> in ihrem Text synchron ausgeführt.  
  
```c#  
  
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
  
## Siehe auch  
 [Asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [async](../../../csharp/language-reference/keywords/async.md)