---
title: 'Vorgehensweise: Aufrufen einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 2543694e6bf8da5b67ecaccc92633a8448154063
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837127"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Vorgehensweise: Aufrufen einer Erweiterungsmethode (Visual Basic)
Erweiterungsmethoden können Sie einer vorhandenen Klasse Methoden hinzufügen. Nachdem eine Erweiterungsmethode deklariert und in den Gültigkeitsbereich eingebunden ist, können Sie es wie eine Instanzmethode des Typs aufrufen, die sie erweitert. Weitere Informationen dazu, wie Sie eine Erweiterungsmethode zu schreiben, finden Sie unter [Vorgehensweise: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md).  
  
 Die folgenden Anweisungen beziehen sich auf Erweiterungsmethode `PrintAndPunctuate`, die die Zeichenfolgeninstanz angezeigt wird, der, gefolgt von den Wert, ruft Sie, für den zweiten Parameter gesendet `punc`.  
  
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
  
 Die Methode muss im Gültigkeitsbereich sein, wenn sie aufgerufen wird.  
  
### <a name="to-call-an-extension-method"></a>Zum Aufrufen einer Erweiterungsmethode  
  
1.  Deklarieren Sie eine Variable, die den Datentyp des ersten Parameters der Erweiterungsmethode aufweist. Für `PrintAndPunctuate`, müssen Sie eine <xref:System.String> Variable:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  Auf den ersten Parameter, dessen Wert gebunden ist, dass Variablen wird die Erweiterungsmethode aufgerufen `aString`. Die folgende aufrufende Anweisung zeigt `Ready?`.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Beachten Sie, die den Aufruf dieser Erweiterungsmethode nur aussieht wie einen Aufruf eine von der <xref:System.String> Instanzmethoden, die einen Parameter erfordern:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  Deklarieren Sie eine weitere Zeichenfolgenvariable, und rufen Sie die Methode erneut, um festzustellen, dass sie mit einer beliebigen Zeichenfolge funktioniert.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     Das Ergebnis dieser Zeit ist: `or not!!!`.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code ist ein vollständiges Beispiel für die Erstellung und Verwendung einer Erweiterung für einfachen-Methode.  
  
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

- [Vorgehensweise: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md)
- [Erweiterungsmethoden](./extension-methods.md)
- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
