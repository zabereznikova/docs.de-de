---
title: Await-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b50b9c7283ddd4d3f8484854bdffff3d76181c9f
ms.lasthandoff: 03/13/2017

---
# <a name="await-operator-visual-basic"></a>Await-Operator (Visual Basic)
Sie wenden den Operator `Await` auf einen Operanden in einer asynchronen Methode oder einem Lambda-Ausdruck an, um die Ausführung der Methode anzuhalten, bis die erwartete Aufgabe ausgeführt wurde. Die Aufgabe stellt derzeit ausgeführte Arbeit dar.  
  
 Die Methode, in der `Await` wird verwendet, muss ein [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer. Solche definierte Methode, mit der `Async` -Modifizierer und in der Regel mit einem oder mehreren `Await` Ausdrücke, wird als bezeichnet ein *Async-Methode*.  
  
> [!NOTE]
>  Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt. Eine Einführung in die asynchrone Programmierung, finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 In der Regel die Aufgabe, die auf den Sie anwenden der `Await` Operator ist der Rückgabewert bei einem Aufruf einer Methode, die implementiert die [Task-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=204847), d. h., einen <xref:System.Threading.Tasks.Task>oder eine <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
 Im folgenden Code wird die <xref:System.Net.Http.HttpClient>Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>gibt `getContentsTask`, `Task(Of Byte())`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> </xref:System.Net.Http.HttpClient> Die Aufgabe enthält das Versprechen, das tatsächliche Bytearray zu erzeugen, wenn die Operation abgeschlossen ist. Der Operator `Await` wird auf `getContentsTask` angewendet, um die Ausführung in `SumPageSizesAsync` anzuhalten, bis `getContentsTask` abgeschlossen wurde. In der Zwischenzeit wird die Steuerung wieder an den Aufrufer von `SumPageSizesAsync` übergeben. Wenn `getContentsTask` beendet ist, wird der `Await`-Ausdruck in ein Bytearray ausgewertet.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  Das vollständige Beispiel finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web durch Verwenden von Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sie können aus das Beispiel herunterladen [Codebeispielen für Entwickler](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) auf der Microsoft-Website. Das Beispiel befindet sich im AsyncWalkthrough_HttpClient-Projekt.  
  
 Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task(Of TResult)` zurückgibt, ist der Typ des `Await`-Ausdrucks TResult. Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task` zurückgibt, gibt der `Await`-Ausdruck keinen Wert zurück. Der Unterschied wird im folgenden Beispiel veranschaulicht.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Ein `Await`-Ausdruck oder eine Await-Anweisung blockiert nicht den Thread, auf dem sie ausgeführt wird. Stattdessen wird damit verursacht, dass der Compiler den Rest der asynchronen Methode nach dem `Await`-Ausdruck als Fortsetzung der erwarteten Aufgabe registriert. Die Steuerung wird dann wieder an den Aufrufer der Async-Methode übergeben. Wenn die Aufgabe abgeschlossen ist, löst sie ihre Fortsetzung aus, und die Ausführung der asynchronen Methode wird da fortgesetzt, wo sie angehalten wurde.  
  
 Ein `Await`-Ausdruck kann nur im Text einer unmittelbar einschließenden Methode oder eines Lambda-Ausdrucks auftreten, die oder der durch einen `Async`-Modifizierer gekennzeichnet ist. Der Begriff *"await"* dient als Schlüsselwort nur in diesem Kontext. In anderen Kontexten wird er als Bezeichner interpretiert. Innerhalb der asynchronen Methode oder einem Lambda-Ausdrucks eine `Await` Ausdruck kann nicht in einem Abfrageausdruck auftreten, der `catch` oder `finally` -Block eine [versuchen... Catch... Schließlich](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) -Anweisung, in der Steuerelement-Schleifenausdruck der ein `For` oder `For Each` Schleife oder im Hauptteil einer [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) Anweisung.  
  
## <a name="exceptions"></a>Ausnahmen  
 Die meisten asynchronen Methoden zurück <xref:System.Threading.Tasks.Task>oder <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> Die Eigenschaften der zurückgegebenen Aufgabe enthalten Informationen über den Status und Verlauf, z. B. ob die Aufgabe abgeschlossen ist, ob die asynchrone Methode eine Ausnahme verursacht hat oder abgebrochen wurde, und was das Endergebnis ist. Der Operator `Await` greift auf diese Eigenschaften zu.  
  
 Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und eine Ausnahme verursacht, löst der Operator `Await` die Ausnahme erneut aus.  
  
 Wenn Sie eine Aufgabe zurückgebende asynchrone Methode warten, die abgebrochen wird, die `Await` Operator löst eine <xref:System.OperationCanceledException>.</xref:System.OperationCanceledException>  
  
 Eine einzelne Aufgabe, die einen Fehlerzustand aufweist, kann verschiedene Ausnahmen auslösen.  Der Task kann z. B. das Ergebnis eines Aufrufs von <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> werden. Wenn Sie auf eine solche Aufgabe warten, löst die await-Operation nur eine der Ausnahmen erneut aus. Sie können jedoch nicht vorhersagen, welche der Ausnahmen erneut ausgelöst wird.  
  
 Beispiele für die Fehlerbehandlung in asynchronen Methoden, finden Sie unter [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Windows Forms-Beispielen wird die Verwendung von `Await` in einer asynchronen Methode, `WaitAsynchronouslyAsync`, veranschaulicht. Vergleichen Sie das Verhalten der Methode mit dem Verhalten von `WaitSynchronously`. Ohne ein `Await` Operator `WaitSynchronously` synchron ausgeführt, obwohl die Verwendung von der `Async` Modifizierer in ihrer Definition und ein Aufruf von <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>in ihrem Text.</xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Async](../../../visual-basic/language-reference/modifiers/async.md)
