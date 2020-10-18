---
title: Die Verwendung der Iterationsvariablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: d0deea94084565ea91debe2b6db30def4cd9e00e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161490"
---
# <a name="bc42324-using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>BC42324: die Verwendung der Iterations Variablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen.

Die Verwendung der Iterations Variablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen. Erstellen Sie stattdessen eine lokale Variable innerhalb der Schleife, und weisen Sie Ihr den Wert der Iterations Variablen zu.

 Diese Warnung wird angezeigt, wenn Sie eine Schleifen Iterations Variable in einem Lambda Ausdruck verwenden, der innerhalb der-Schleife deklariert ist. Beispielsweise bewirkt das folgende Beispiel, dass die Warnung angezeigt wird.

```vb
For i As Integer = 1 To 10
    ' The warning is given for the use of i.
    Dim exampleFunc As Func(Of Integer) = Function() i
Next
```

 Das folgende Beispiel zeigt die unerwarteten Ergebnisse, die auftreten können.

```vb
Module Module1
    Sub Main()
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}

        For i As Integer = 0 To 4
            array1(i) = Function() i
        Next

        For Each funcElement In array1
            System.Console.WriteLine(funcElement())
        Next

    End Sub
End Module
```

 Die- `For` Schleife erstellt ein Array von Lambda-Ausdrücken, von denen jede den Wert der Schleifen Iterations Variablen zurückgibt `i` . Wenn die Lambda-Ausdrücke in der- `For Each` Schleife ausgewertet werden, erwarten Sie möglicherweise, dass 0, 1, 2, 3 und 4 angezeigt werden, die aufeinander folgenden Werte von `i` in der- `For` Schleife. Stattdessen wird der endgültige Wert von `i` fünfmal angezeigt:

 `5`

 `5`

 `5`

 `5`

 `5`

 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC42324

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Weisen Sie den Wert der Iterations Variablen einer lokalen Variablen zu, und verwenden Sie die lokale Variable im Lambda-Ausdruck.

```vb
Module Module1
    Sub Main()
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}

        For i As Integer = 0 To 4
            Dim j = i
            array1(i) = Function() j
        Next

        For Each funcElement In array1
            System.Console.WriteLine(funcElement())
        Next

    End Sub
End Module
```

## <a name="see-also"></a>Siehe auch

- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
