---
title: Der Lambdaausdruck wird nicht aus diesem Ereignishandler entfernt
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 2f8b10082bb39c76ba1393daf8327df2ed631caf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568100"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>Der Lambdaausdruck wird nicht aus diesem Ereignishandler entfernt
Lambda-Ausdruck wird nicht aus diesem Ereignishandler entfernt werden. Weisen Sie den Lambda-Ausdruck einer Variablen zu und verwenden Sie die Variable hinzufügen und entfernen das Ereignis.  
  
 Wenn Lambda-Ausdrücken mit Ereignishandlern verwendet werden, möglicherweise nicht das Verhalten angezeigt, die, das Sie erwarten. Der Compiler generiert eine neue Methode für jede Definition des Lambda-Ausdrucks, auch wenn sie identisch sind. Der folgende code aus diesem Grund zeigt `False`.  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 Wenn Lambda-Ausdrücken mit Ereignishandlern verwendet werden, kann dies unerwartete Ergebnissen führen. Im folgenden Beispiel wird der Lambda-Ausdruck durch hinzugefügt `AddHandler` wird nicht entfernt werden, indem die `RemoveHandler` Anweisung.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen und zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42326  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Um die Warnung zu vermeiden, und entfernen Sie den Lambda-Ausdruck, den Lambda-Ausdruck einer Variablen zuweisen und verwenden Sie die Variable in beiden die `AddHandler` und `RemoveHandler` -Anweisungen, wie im folgenden Beispiel gezeigt.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Dim PrintHandler As ProcessIntegerEventHandler  
  
    Sub Main()  
  
        ' Assign the lambda expression to a variable.  
        PrintHandler = Function(m As Integer) m  
  
        ' Use the variable to add the listener.  
        AddHandler ProcessInteger, PrintHandler  
  
        ' Use the variable again when you want to remove the listener.  
        RemoveHandler ProcessInteger, PrintHandler  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>Siehe auch
- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
