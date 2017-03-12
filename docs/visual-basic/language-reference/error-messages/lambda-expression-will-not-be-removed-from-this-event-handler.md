---
title: "Lambda expression will not be removed from this event handler | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42326"
  - "vbc42326"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42326"
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Lambda expression will not be removed from this event handler
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Der Lambda\-Ausdruck wird nicht aus diesem Ereignishandler entfernt.Weisen Sie den Lambda\-Ausdruck einer Variablen zu, und verwenden Sie die Variable, um das Ereignis hinzuzufügen und zu entfernen.  
  
 Wenn Lambda\-Ausdrücke zusammen mit Ereignishandlern verwendet werden, entspricht das dargestellte Verhalten möglicherweise nicht den Erwartungen.  Der Compiler generiert für jede Definition eines Lambda\-Ausdrucks eine neue Methode, auch wenn sie identisch sind.  Daher zeigt der folgende Code `False` an.  
  
```vb#  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 Wenn Lambda\-Ausdrücke zusammen mit Ereignishandlern verwendet werden, kann dies zu unerwarteten Ergebnissen führen.  Im folgenden Beispiel wird der durch `AddHandler` hinzugefügte Lambda\-Ausdruck nicht durch die `RemoveHandler`\-Anweisung entfernt.  
  
```vb#  
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
  
 Standardmäßig ist diese Meldung eine Warnung.  Weitere Informationen zum Ausblenden von Warnungen bzw. zur Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42326  
  
### So beheben Sie diesen Fehler  
  
-   Um die Warnung zu vermeiden und den Lambda\-Ausdruck zu entfernen, weisen Sie den Lambda\-Ausdruck einer Variablen zu, und verwenden Sie die Variable sowohl in der `AddHandler`\-Anweisung als auch in der `RemoveHandler`\-Anweisung, wie im folgenden Beispiel gezeigt.  
  
    ```vb#  
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
  
## Siehe auch  
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)