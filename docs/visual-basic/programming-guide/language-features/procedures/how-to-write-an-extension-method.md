---
title: 'Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 7a7a9d16d9f69071e9d1dacb0558f7ca92e1d21e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631036"
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
    Public Sub SubName (ByVal para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird eine Erweiterungsmethode im- `StringExtensions`Modul deklariert. Ein zweites Modul, `Module1`, importiert `StringExtensions` und ruft die-Methode auf. Die Erweiterungsmethode muss sich im Gültigkeitsbereich befinden, wenn Sie aufgerufen wird. Erweiterungsmethode `PrintAndPunctuate` erweitert die <xref:System.String> -Klasse mit einer Methode, die die Zeichen folgen Instanz anzeigt, gefolgt von einer Zeichenfolge aus Interpunktions Symbolen, die als Parameter gesendet werden.
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
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
  
 Beachten Sie, dass die-Methode mit zwei Parametern definiert und nur mit einem aufgerufen wird. Der erste Parameter `aString`,, in der Methoden Definition ist an `example`gebunden, d. h `String` . die Instanz von, die die-Methode aufruft. Die Ausgabe des Beispiels sieht folgendermaßen aus:
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Erweiterungsmethoden](./extension-methods.md)
- [Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Bereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
