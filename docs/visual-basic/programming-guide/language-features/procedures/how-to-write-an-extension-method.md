---
title: 'Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 31ccb18e0e6d1569764ec2a67201d7f758129425
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332758"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)

Erweiterungs Methoden ermöglichen Ihnen das Hinzufügen von Methoden zu einer vorhandenen Klasse. Die Erweiterungsmethode kann so aufgerufen werden, als ob es sich um eine Instanz dieser Klasse handelt.

### <a name="to-define-an-extension-method"></a>So definieren Sie eine Erweiterungsmethode

1. Öffnen Sie in Visual Studio eine neue oder vorhandene Visual Basic Anwendung.

2. Fügen Sie am Anfang der Datei, in der Sie eine Erweiterungsmethode definieren möchten, die folgende Import-Anweisung ein:

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. Beginnen Sie in einem Modul in der neuen oder vorhandenen Anwendung mit der Methoden Definition mit dem Erweiterungs Attribut:

    ```vb
    <Extension()>
    ```

4. Deklarieren Sie die Methode auf normale Weise, mit der Ausnahme, dass der Typ des ersten Parameters der Datentyp sein muss, den Sie erweitern möchten.

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird eine Erweiterungsmethode im-Modul `StringExtensions` deklariert. Ein zweites Modul, `Module1`, importiert `StringExtensions` und ruft die-Methode auf. Die Erweiterungsmethode muss sich im Gültigkeitsbereich befinden, wenn Sie aufgerufen wird. Erweiterungsmethode `PrintAndPunctuate` erweitert die <xref:System.String>-Klasse mit einer Methode, die die Zeichen folgen Instanz anzeigt, gefolgt von einer Zeichenfolge aus Interpunktions Symbolen, die als Parameter gesendet werden.
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

```vb
' Import the module that holds the extension method you want to use,
' and call it.

Imports ConsoleApplication2.StringExtensions

Module Module1
  
    Sub Main()
        Dim example = "Hello"
        example.PrintAndPunctuate("?")
        example.PrintAndPunctuate("!!!!")
    End Sub
    
End Module
```
  
 Beachten Sie, dass die-Methode mit zwei Parametern definiert und nur mit einem aufgerufen wird. Der erste Parameter `aString` in der Methoden Definition ist an `example` gebunden, die Instanz von `String`, die die-Methode aufruft. Die Ausgabe des Beispiels sieht folgendermaßen aus:
  
 ```console
 Hello?
 Hello!!!!
 ```
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Erweiterungsmethoden](extension-methods.md)
- [Module-Anweisung](../../../language-reference/statements/module-statement.md)
- [Parameter und Argumente von Prozeduren](procedure-parameters-and-arguments.md)
- [Bereich in Visual Basic](../declared-elements/scope.md)
