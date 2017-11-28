---
title: 'Gewusst wie: Aufrufen einer Erweiterungsmethode (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25b5a86af15694e6f64f96a5d5d645a01f8f1f12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Gewusst wie: Aufrufen einer Erweiterungsmethode (Visual Basic)
Erweiterungsmethoden können Sie Methoden zur einer vorhandenen Klasse hinzugefügt. Nachdem eine Erweiterungsmethode deklariert und in den Gültigkeitsbereich eingebunden ist, können Sie es wie eine Instanzmethode des Typs aufrufen, die sie erweitert. Weitere Informationen über das Schreiben einer Erweiterungsmethode finden Sie unter [wie: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md).  
  
 Nachfolgend finden Sie unter Erweiterungsmethode `PrintAndPunctuate`, die die Zeichenfolgeninstanz angezeigt werden, die, gefolgt von den Wert, den aufgerufen, für den zweiten Parameter gesendet `punc`.  
  
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
  
### <a name="to-call-an-extension-method"></a>Aufrufen eine Erweiterungsmethode  
  
1.  Deklarieren Sie eine Variable, die den Datentyp des ersten Parameters der Erweiterungsmethode aufweist. Für `PrintAndPunctuate`, müssen Sie eine <xref:System.String> Variablen:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  Variable wird die Erweiterungsmethode aufgerufen, und sein Wert wird auf den ersten Parameter gebunden `aString`. Zeigt die folgenden aufrufanweisung `Ready?`.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Beachten Sie, die den Aufruf dieser Erweiterungsmethode nur aussieht wie einen Aufruf eines der <xref:System.String> Instanzmethoden, die einen Parameter erfordern:  
  
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
 [Gewusst wie: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md)  
 [Erweiterungsmethoden](./extension-methods.md)  
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
