---
title: "How to: Call an Extension Method (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "calling extension methods"
  - "extension methods [Visual Basic]"
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Call an Extension Method (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Mit Erweiterungsmethoden können Sie einer vorhandenen Klasse Methoden hinzufügen.  Nachdem eine Erweiterungsmethode deklariert und in den Gültigkeitsbereich eingebunden wurde, können Sie sie wie eine Instanzenmethode des Typs aufrufen, der von ihr erweitert wird.  Weitere Informationen über das Schreiben einer Erweiterungsmethode finden Sie unter [How to: Write an Extension Method](../../../../visual-basic/programming-guide/language-features/procedures/how-to-write-an-extension-method.md).  
  
 Die folgenden Anweisungen beziehen sich auf die Erweiterungsmethode `PrintAndPunctuate`, durch die die von ihr aufgerufene Zeichenfolgeninstanz gefolgt von dem Wert angezeigt wird, der für den zweiten Parameter, nämlich `punc`, gesendet wird.  
  
```vb#  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
  
```  
  
 Die Methode muss sich während des Aufrufs innerhalb des Bereichs befinden.  
  
### So rufen Sie eine Erweiterungsmethode auf  
  
1.  Deklarieren Sie eine Variable, die über den Datentyp des ersten Parameters der Erweiterungsmethode verfügt.  Für `PrintAndPunctuate` benötigen Sie eine <xref:System.String>\-Variable:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  Diese Variable ruft die Erweiterungsmethode auf, und ihr Wert wird an den ersten Parameter, `aString`, gebunden.  Durch die folgende aufrufende Anweisung wird `Ready?` angezeigt.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Beachten Sie, dass der Aufruf dieser Erweiterungsmethode mit einem Aufruf der <xref:System.String>\-Instanzenmethoden vergleichbar ist, die einen Parameter erfordern:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  Deklarieren Sie eine weitere Zeichenfolgenvariable, und rufen Sie die Methode erneut auf, um festzustellen, ob sie mit jeder Zeichenfolge funktioniert.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     Dieses Mal lautet das Ergebnis: `or not!!!`.  
  
## Beispiel  
 Der folgende Code ist ein vollständiges Beispiel für die Erstellung und Verwendung einer einfachen Erweiterungsmethode.  
  
```vb#  
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
  
## Siehe auch  
 [How to: Write an Extension Method](../../../../visual-basic/programming-guide/language-features/procedures/how-to-write-an-extension-method.md)   
 [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)