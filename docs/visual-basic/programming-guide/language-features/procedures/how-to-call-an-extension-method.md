---
title: 'Gewusst wie: Aufrufen einer Erweiterungsmethode'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: a19705a8f90833d48869df26a18d19b0ad1488e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340399"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Gewusst wie: Aufrufen einer Erweiterungsmethode (Visual Basic)

Erweiterungs Methoden ermöglichen Ihnen das Hinzufügen von Methoden zu einer vorhandenen Klasse. Nachdem eine Erweiterungsmethode deklariert und in den Gültigkeitsbereich eingefügt wurde, können Sie Sie wie eine Instanzmethode des Typs, der Sie erweitert, abrufen. Weitere Informationen zum Schreiben einer Erweiterungsmethode finden Sie unter Gewusst [wie: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md).

 Die folgenden Anweisungen beziehen sich auf die Erweiterungsmethode `PrintAndPunctuate`, die die Zeichen folgen Instanz anzeigt, die diese aufruft, gefolgt von dem Wert, der für den zweiten Parameter, `punc`, gesendet wird.

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

Die Methode muss sich im Gültigkeitsbereich befinden, wenn Sie aufgerufen wird.

### <a name="to-call-an-extension-method"></a>So greifen Sie auf eine Erweiterungsmethode zu

1. Deklarieren Sie eine Variable, die den Datentyp des ersten Parameters der Erweiterungsmethode aufweist. Für `PrintAndPunctuate`benötigen Sie eine <xref:System.String> Variable:

    ```vb
    Dim example = "Ready"
    ```

2. Diese Variable Ruft die Erweiterungsmethode auf, und ihr Wert wird an den ersten Parameter, `aString`, gebunden. Mit der folgenden aufrufenden Anweisung wird `Ready?`angezeigt.

    ```vb
    example.PrintAndPunctuate("?")
    ```

     Beachten Sie, dass der Aufrufen dieser Erweiterungsmethode genau wie ein Aufrufen einer der <xref:System.String> Instanzmethoden aussieht, die einen Parameter erfordern:

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. Deklarieren Sie eine weitere Zeichen folgen Variable, und rufen Sie die Methode erneut auf, um zu überprüfen, ob Sie mit

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     Das Ergebnis ist dieses Mal: `or not!!!`.

## <a name="example"></a>Beispiel
 Der folgende Code ist ein umfassendes Beispiel für die Erstellung und Verwendung einer einfachen Erweiterungsmethode.

```vb
Imports System.Runtime.CompilerServices
Imports ConsoleApplication1.StringExtensions

Module Module1

    Sub Main()

        Dim example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")

        Dim example2 = "Goodbye"
        example2.PrintAndPunctuate("?")
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module

' Output:
' Hello.
' Hello!!!!
' Goodbye?
```

## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md)
- [Erweiterungsmethoden](./extension-methods.md)
- [Bereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
