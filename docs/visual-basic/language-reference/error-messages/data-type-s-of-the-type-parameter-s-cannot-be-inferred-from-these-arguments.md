---
title: "Data type(s) of the type parameter(s) cannot be inferred from these arguments | Microsoft Docs"
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
  - "bc36644"
  - "bc36647"
  - "vbc36647"
  - "vbc36644"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36644"
  - "BC36647"
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Data type(s) of the type parameter(s) cannot be inferred from these arguments
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden.Sie können diesen Fehler möglicherweise beheben, indem Sie die Datentypen explizit angeben.  
  
 Dieser Fehler tritt auf, wenn die Überladungsauflösung fehlgeschlagen ist.  Es wird eine untergeordnete Meldung angezeigt, in der angegeben wird, warum eine bestimmte Überladung eliminiert wurde.  Es wird erläutert, dass der Compiler nicht mithilfe des Typrückschlusses Datentypen für die Typparameter suchen kann.  
  
> [!NOTE]
>  Wenn Argumente nicht angegeben werden können \(z. B. von Abfrageoperatoren in Abfrageausdrücken\), wird der zweite Satz der Fehlermeldung nicht angezeigt.  
  
 Der folgende Code veranschaulicht den Fehler.  
  
```vb#  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 **Fehler\-ID:** BC36647 und BC36644  
  
### So beheben Sie diesen Fehler  
  
-   Möglicherweise können Sie einen Datentyp für die Typparameter angeben, anstatt sich auf den Typrückschluss zu verlassen.  
  
## Siehe auch  
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)