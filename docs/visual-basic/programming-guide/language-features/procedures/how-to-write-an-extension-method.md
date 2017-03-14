---
title: "How to: Write an Extension Method (Visual Basic) | Microsoft Docs"
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
  - "extending data types"
  - "writing extension methods"
  - "extension methods [Visual Basic]"
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Write an Extension Method (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Mit Erweiterungsmethoden können Sie einer vorhandenen Klasse Methoden hinzufügen.  Die Erweiterungsmethode kann aufgerufen werden, als wäre sie eine Instanz dieser Klasse.  
  
### So definieren Sie eine Erweiterungsmethode  
  
1.  Öffnen Sie eine neue oder vorhandene Visual Basic\-Anwendung in Visual Studio.  
  
2.  Fügen Sie am Anfang der Datei, in der Sie eine Erweiterungsmethode definieren möchten, die folgende Importanweisung ein:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  Beginnen Sie innerhalb eines Moduls in einer neuen oder vorhandenen Anwendung die Methodendefinition mit dem Erweiterungsattribut:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Deklarieren Sie die Methode auf die übliche Weise, mit der Ausnahme, dass der Typ des ersten Parameters dem zu erweiternden Datentyp entsprechen muss.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## Beispiel  
 Im folgenden Beispiel wird eine Erweiterungsmethode in Modul `StringExtensions` deklariert.  Das zweite Modul `Module1` importiert `StringExtensions` und ruft die Methode auf.  Die Erweiterungsmethode muss sich während des Aufrufs innerhalb des Bereichs befinden.  Durch die Erweiterungsmethode `PrintAndPunctuate` wird die <xref:System.String>\-Klasse mit einer Methode erweitert, die die Zeichenfolgeninstanz, gefolgt von einer Zeichenfolge aus Satzzeichensymbolen, die als Parameter gesendet wurden, anzeigt.  
  
```vb#  
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
  
```vb#  
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
  
 Beachten Sie, dass die Methode mit zwei Parametern definiert und mit nur einem aufgerufen wird.  Der erste Parameter \(`aString`\) in der Methodendefinition ist an `example`, die Instanz von `String`, gebunden, durch die die Methode aufgerufen wird.  Die Ausgabe des Beispiels sieht wie folgt aus:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## Siehe auch  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)