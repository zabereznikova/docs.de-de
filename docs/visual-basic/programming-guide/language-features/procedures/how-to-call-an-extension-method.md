---
title: 'Vorgehensweise: Aufrufen einer Erweiterungsmethode'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 54419c99ae08c9ca2e3cfa86993dc99bc02bbb64
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388659"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Gewusst wie: Aufrufen einer Erweiterungsmethode (Visual Basic)

Erweiterungs Methoden ermöglichen Ihnen das Hinzufügen von Methoden zu einer vorhandenen Klasse. Nachdem eine Erweiterungsmethode deklariert und in den Gültigkeitsbereich eingefügt wurde, können Sie Sie wie eine Instanzmethode des Typs, der Sie erweitert, abrufen. Weitere Informationen zum Schreiben einer Erweiterungsmethode finden Sie unter Gewusst [wie: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md).

 Die folgenden Anweisungen beziehen sich auf die Erweiterungsmethode `PrintAndPunctuate` , die die Zeichen folgen Instanz anzeigt, die diese aufruft, gefolgt von dem Wert, der in für den zweiten Parameter gesendet wird `punc` .

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

1. Deklarieren Sie eine Variable, die den Datentyp des ersten Parameters der Erweiterungsmethode aufweist. Für `PrintAndPunctuate` benötigen Sie eine <xref:System.String> Variable:

    ```vb
    Dim example = "Ready"
    ```

2. Diese Variable Ruft die Erweiterungsmethode auf, und ihr Wert wird an den ersten Parameter gebunden `aString` . Die folgende Aufruf Anweisung wird angezeigt `Ready?` .

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

     Das Ergebnis ist diese Zeit: `or not!!!` .

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

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md)
- [Erweiterungsmethoden](./extension-methods.md)
- [Gültigkeitsbereich in Visual Basic](../declared-elements/scope.md)
