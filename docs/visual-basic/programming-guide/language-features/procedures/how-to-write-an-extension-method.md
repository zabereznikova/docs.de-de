---
title: 'Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 00d62d275f7afc06e066a375dc1ffcd74b23c9ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666000"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)
Erweiterungsmethoden können Sie einer vorhandenen Klasse Methoden hinzufügen. Die Erweiterungsmethode kann aufgerufen werden, als handele es sich um eine Instanz dieser Klasse.  
  
### <a name="to-define-an-extension-method"></a>So definieren Sie eine Extension-Methode  
  
1. Öffnen Sie eine neue oder vorhandene Visual Basic-Anwendung in Visual Studio.  
  
2. Am Anfang der Datei, in der Sie eine Erweiterungsmethode definieren möchten, müssen schließen Sie die folgende importanweisung ein:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3. Beginnen Sie in einem Modul in Ihrer neuen oder vorhandenen Anwendung die Definition der Methode mit dem Erweiterungsattribut:  
  
    ```  
    <Extension()>  
    ```  
  
4. Deklarieren Sie die Methode auf die normale Weise, außer dass der Typ des ersten Parameters den Datentyp sein muss, die, den Sie erweitern möchten.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine Erweiterungsmethode in Modul `StringExtensions`. Das zweite Modul `Module1`, importiert `StringExtensions` und ruft die Methode. Wenn sie aufgerufen wird, muss die Erweiterungsmethode im Gültigkeitsbereich befinden. Erweiterungsmethode `PrintAndPunctuate` erweitert die <xref:System.String> Klasse mit einer Methode, die die Zeichenfolgeninstanz zeigt gefolgt durch eine Folge von Interpunktionszeichen, die als Parameter gesendet.  
  
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
  
 Beachten Sie, dass die Methode mit zwei Parametern definiert und mit nur einem aufgerufen. Der erste Parameter, `aString`, in der Methode ist die Definition an gebunden `example`, die Instanz von `String` , die die Methode aufruft. Die Ausgabe des Beispiels sieht folgendermaßen aus:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Erweiterungsmethoden](./extension-methods.md)
- [Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
