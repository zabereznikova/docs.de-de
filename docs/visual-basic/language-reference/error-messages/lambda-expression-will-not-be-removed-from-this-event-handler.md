---
title: Der Lambdaausdruck wird nicht aus diesem Ereignishandler entfernt
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 07ace3f1b9c5e512227dc1f718ef768b631c8303
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397375"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>Der Lambdaausdruck wird nicht aus diesem Ereignishandler entfernt

Der Lambda-Ausdruck wird nicht aus diesem Ereignishandler entfernt. Weisen Sie den Lambda-Ausdruck einer Variablen zu, und verwenden Sie die Variable, um das Ereignis hinzuzufügen und zu entfernen.

Wenn Lambda-Ausdrücke mit Ereignis Handlern verwendet werden, wird das erwartete Verhalten möglicherweise nicht angezeigt. Der Compiler generiert eine neue Methode für jede Lambda-Ausdrucks Definition, auch wenn diese identisch sind. Der folgende Code zeigt daher an `False` .

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

Wenn Lambda-Ausdrücke mit Ereignis Handlern verwendet werden, kann dies zu unerwarteten Ergebnissen führen. Im folgenden Beispiel wird der von hinzugefügte Lambda-Ausdruck `AddHandler` nicht durch die- `RemoveHandler` Anweisung entfernt.

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

Um die Warnung zu vermeiden und den Lambda-Ausdruck zu entfernen, weisen Sie den Lambda-Ausdruck einer Variablen zu, und verwenden Sie die-Variable in der `AddHandler` -und der- `RemoveHandler` Anweisung, wie im folgenden Beispiel gezeigt.

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

## <a name="see-also"></a>Weitere Informationen

- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Gelockerte Delegatenkonvertierung](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Ereignisse](../../programming-guide/language-features/events/index.md)
