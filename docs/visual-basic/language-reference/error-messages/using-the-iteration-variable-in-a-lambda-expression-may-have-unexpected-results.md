---
title: "Using the iteration variable in a lambda expression may have unexpected results | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42324"
  - "bc42324"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42324"
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Using the iteration variable in a lambda expression may have unexpected results
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die Verwendung der Iterationsvariablen in einem lambda\-Ausdruck kann zu unerwarteten Ergebnissen führen.Erstellen Sie stattdessen in der Schleife eine lokale Variable, und weisen Sie dieser den Wert der Iterationsvariablen zu.  
  
 Diese Warnung wird angezeigt, wenn Sie eine Schleifeniterationsvariable in einem lambda\-Ausdruck verwenden, der innerhalb der Schleife deklariert wird.  In folgendem Beispiel wird die Warnung angezeigt.  
  
```vb#  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 In folgendem Beispiel werden die unerwarteten Ergebnisse, die auftreten könnten, veranschaulicht.  
  
```vb#  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 Die `For`\-Schleife erzeugt ein Array von lambda\-Ausdrücken, von denen jeder den Wert der Schleifeniterationsvariable `i` zurückgibt.  Wenn die lambda\-Ausdrücke in der `For Each`\-Schleife ausgewertet werden, erwarten Sie wahrscheinlich, dass die aufeinanderfolgenden Werte von `i` in der `For`\-Schleife – 0, 1, 2, 3 und 4 – angezeigt werden.  Stattdessen wird der letzte Wert von `i` fünfmal angezeigt:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 Standardmäßig ist diese Meldung eine Warnung.  Weitere Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42324  
  
### So beheben Sie diesen Fehler  
  
-   Weisen Sie einer lokalen Variable den Wert der Iterationsvariable zu, und verwenden Sie die lokale Variable im lambda\-Ausdruck.  
  
    ```vb#  
    Module Module1  
        Sub Main()  
            Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
            For i As Integer = 0 To 4  
                Dim j = i  
                array1(i) = Function() j  
            Next  
  
            For Each funcElement In array1  
                System.Console.WriteLine(funcElement())  
            Next  
  
        End Sub  
    End Module  
    ```  
  
## Siehe auch  
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)