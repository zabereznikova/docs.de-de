---
title: "Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36548"
  - "vbc36548"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36548"
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Der Compiler lässt keine Konvertierung eines anonymen Typs in eine Ausdrucksbaumstruktur zu, wenn eine Eigenschaft des anonymen Typs zur Initialisierung einer anderen Eigenschaft des anonymen Typs verwendet wird.  Im folgenden Code wird `Prop1` beispielsweise in der Initialisierungsliste deklariert und dann als Anfangswert für `Prop2` verwendet.  
  
```vb#  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **Fehler\-ID:** BC36548  
  
### So beheben Sie diesen Fehler  
  
-   Weisen Sie einer lokalen Variable den Anfangswert für `Prop1` zu.  Weisen Sie diese Variable `Prop1` und `Prop2` zu, wie im folgenden Code dargestellt.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## Siehe auch  
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Ausdrucksbaumstrukturen](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)   
 [Gewusst wie: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen](../Topic/How%20to:%20Use%20Expression%20Trees%20to%20Build%20Dynamic%20Queries%20\(C%23%20and%20Visual%20Basic\).md)