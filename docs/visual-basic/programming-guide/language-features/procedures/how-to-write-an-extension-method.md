---
title: 'Gewusst wie: Schreiben einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: e220a025c39757b492be033caeb8924523515804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Gewusst wie: Schreiben einer Erweiterungsmethode (Visual Basic)
Erweiterungsmethoden können Sie Methoden zur einer vorhandenen Klasse hinzugefügt. Die Erweiterungsmethode kann aufgerufen werden, als handele es sich um eine Instanz dieser Klasse.  
  
### <a name="to-define-an-extension-method"></a>Um eine Erweiterungsmethode zu definieren.  
  
1.  Öffnen einer neuen oder vorhandenen Visual Basic-Anwendung in Visual Studio.  
  
2.  Am Anfang der Datei, in der Sie eine Erweiterungsmethode definieren möchten, müssen schließen Sie die folgende importanweisung ein:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  Beginnen Sie innerhalb eines Moduls in der neuen oder vorhandenen Anwendung die Methodendefinition mit dem Erweiterungsattribut:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Deklarieren Sie die Methode auf die übliche Weise, mit dem Unterschied, dass der Typ des ersten Parameters den Datentyp sein muss, die, den Sie erweitern möchten.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine Erweiterungsmethode in Modul `StringExtensions`. Das zweite Modul `Module1`, importiert `StringExtensions` und ruft die Methode. Die Erweiterungsmethode muss im Gültigkeitsbereich sein, wenn sie aufgerufen wird. Erweiterungsmethode `PrintAndPunctuate` erweitert die <xref:System.String> Klasse mit einer Methode, die die Zeichenfolgeninstanz zeigt gefolgt von einem Interpunktionszeichen als Parameter gesendet.  
  
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
  
 Beachten Sie, dass die Methode mit zwei Parametern definiert und mit nur einem aufgerufen wird. Der erste Parameter `aString`, in der Methode Definition gebunden ist, um `example`, die Instanz von `String` die Methode aufruft. Die Ausgabe des Beispiels lautet wie folgt:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [Erweiterungsmethoden](./extension-methods.md)  
 [Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
