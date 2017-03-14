---
title: "Await Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Await"
helpviewer_keywords: 
  - "Await operator [Visual Basic]"
  - "Await [Visual Basic]"
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Await Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie wenden den Operator `Await` auf einen Operanden in einer asynchronen Methode oder einem Lambda\-Ausdruck an, um die Ausführung der Methode anzuhalten, bis die erwartete Aufgabe ausgeführt wurde.  Die Aufgabe stellt derzeit ausgeführte Arbeit dar.  
  
 Die Methode, bei der `Await` verwendet wird, muss einen [Async](../../../visual-basic/language-reference/modifiers/async.md)\-Modifizierer haben.  Eine solche mit dem `Async`\-Modifizierer definierte Methode, die in der Regel mindestens einen `Await`\-Ausdruck enthält, wird als *Async\-Methode* bezeichnet.  
  
> [!NOTE]
>  Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt.  Eine Einführung in die Grundlagen der asynchronen Programmierung finden Sie unter [Asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 In der Regel ist die Aufgabe, auf die Sie den Operator `Await` anwenden, der Rückgabewert eines Aufrufes einer Methode, mit der das [aufgabenbasierte asynchrone Muster](http://go.microsoft.com/fwlink/?LinkId=204847) implementiert wird, d. h. eine <xref:System.Threading.Tasks.Task> oder eine <xref:System.Threading.Tasks.Task%601>.  
  
 Im folgenden Code gibt die <xref:System.Net.Http.HttpClient>\-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> `getContentsTask`, eine `Task(Of Byte())` zurück.  Die Aufgabe enthält das Versprechen, das tatsächliche Bytearray zu erzeugen, wenn die Operation abgeschlossen ist.  Der Operator `Await` wird auf `getContentsTask` angewendet, um die Ausführung in `SumPageSizesAsync` anzuhalten, bis `getContentsTask` abgeschlossen wurde.  In der Zwischenzeit wird die Steuerung wieder an den Aufrufer von `SumPageSizesAsync` übergeben.  Wenn `getContentsTask` beendet ist, wird der `Await`\-Ausdruck in ein Bytearray ausgewertet.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  Das vollständige Beispiel finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Sie können das Beispiel aus den [Codebeispielen für Entwickler](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) der Microsoft\-Website herunterladen.  Das Beispiel befindet sich im AsyncWalkthrough\_HttpClient\-Projekt.  
  
 Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task(Of TResult)` zurückgibt, ist der Typ des `Await`\-Ausdrucks TResult.  Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task` zurückgibt, gibt der `Await`\-Ausdruck keinen Wert zurück.  Der Unterschied wird im folgenden Beispiel veranschaulicht.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Ein `Await`\-Ausdruck oder eine Await\-Anweisung blockiert nicht den Thread, auf dem sie ausgeführt wird.  Stattdessen wird damit verursacht, dass der Compiler den Rest der asynchronen Methode nach dem `Await`\-Ausdruck als Fortsetzung der erwarteten Aufgabe registriert.  Die Steuerung wird dann wieder an den Aufrufer der Async\-Methode übergeben.  Wenn die Aufgabe abgeschlossen ist, löst sie ihre Fortsetzung aus, und die Ausführung der asynchronen Methode wird da fortgesetzt, wo sie angehalten wurde.  
  
 Ein `Await`\-Ausdruck kann nur im Text einer unmittelbar einschließenden Methode oder eines Lambda\-Ausdrucks auftreten, die oder der durch einen `Async`\-Modifizierer gekennzeichnet ist.  Der Begriff *Await* dient nur in diesem Kontext als Schlüsselwort.  In anderen Kontexten wird er als Bezeichner interpretiert.  Innerhalb der asynchronen Methode oder des Lambda\-Ausdrucks kann ein `Await`\- Ausdruck nicht in einem Abfrageausdruck, im `catch`\- oder `finally`\-Block einer [Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)\-Anweisung, im Variablenausdruck für die Schleifensteuerung einer `For`\- oder `For Each`\-Schleife oder im Text einer [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md)\-Anweisung auftreten.  
  
## Ausnahmen  
 Die meisten asynchronen Methoden geben einen <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück.  Die Eigenschaften der zurückgegebenen Aufgabe enthalten Informationen über den Status und Verlauf, z. B. ob die Aufgabe abgeschlossen ist, ob die asynchrone Methode eine Ausnahme verursacht hat oder abgebrochen wurde, und was das Endergebnis ist.  Der Operator `Await` greift auf diese Eigenschaften zu.  
  
 Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und eine Ausnahme verursacht, löst der Operator `Await` die Ausnahme erneut aus.  
  
 Wenn Sie eine asynchrone Methode erwarten, die eine Aufgabe zurückgibt und abgebrochen wird, löst der Operator `Await` erneut eine <xref:System.OperationCanceledException> aus.  
  
 Eine einzelne Aufgabe, die einen Fehlerzustand aufweist, kann verschiedene Ausnahmen auslösen.  Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> sein.  Wenn Sie auf eine solche Aufgabe warten, löst die await\-Operation nur eine der Ausnahmen erneut aus.  Sie können jedoch nicht vorhersagen, welche der Ausnahmen erneut ausgelöst wird.  
  
 Beispiele für die Fehlerbehandlung in asynchronen Methoden finden Sie unter [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Beispiel  
 Im folgenden Windows Forms\-Beispielen wird die Verwendung von `Await` in einer asynchronen Methode, `WaitAsynchronouslyAsync`, veranschaulicht.  Vergleichen Sie das Verhalten der Methode mit dem Verhalten von `WaitSynchronously`.  Ohne einen `Await`\-Operator wird `WaitSynchronously` trotz der Verwendung des `Async`\-Modifizierers in der Definition und in einem Aufruf von <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> im Text synchron ausgeführt.  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## Siehe auch  
 [Asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Async](../../../visual-basic/language-reference/modifiers/async.md)