---
title: 'Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: d01596d50db8ba1078e8ac82caa951418645c977
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004612"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)

Erweiterungs Methoden ermöglichen Ihnen das Hinzufügen von Methoden zu einer vorhandenen Klasse. Die Erweiterungsmethode kann so aufgerufen werden, als ob es sich um eine Instanz dieser Klasse handelt.

### <a name="to-define-an-extension-method"></a>So definieren Sie eine Erweiterungsmethode

1. Öffnen Sie in Visual Studio eine neue oder vorhandene Visual Basic Anwendung.

2. Fügen Sie am Anfang der Datei, in der Sie eine Erweiterungsmethode definieren möchten, die folgende Import-Anweisung ein:

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. Beginnen Sie in einem Modul in der neuen oder vorhandenen Anwendung mit der Methoden Definition mit dem [`<Extension>`-](xref:System.Runtime.CompilerServices.ExtensionAttribute) Attribut:

    ```vb
    <Extension()>
    ```
 
   Beachten Sie, dass das `Extension`-Attribut nur auf eine Methode (eine `Sub`-oder `Function`-Prozedur) in einem Visual Basic [Modul](../../../language-reference/statements/module-statement.md)angewendet werden kann. Wenn Sie es auf eine Methode in einer `Class` oder einer `Structure` anwenden, generiert der Visual Basic Compiler den Fehler [BC36551](../../../misc/bc36551.md), "Erweiterungs Methoden können nur in Modulen definiert werden."

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
