---
title: "Anonymous type member name can be inferred only from a simple or qualified name with no arguments | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc36556"
  - "bc36556"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36556"
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Anonymous type member name can be inferred only from a simple or qualified name with no arguments
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können von einem komplexen Ausdruck keinen anonymen Typmembernamen ableiten.  
  
```vb#  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Weitere Informationen zu Quellen, aus denen anonyme Typen Membernamen und \-typen ableiten bzw. nicht ableiten können, finden Sie unter [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
 **Fehler\-ID:** BC36556  
  
### So beheben Sie diesen Fehler  
  
-   Weisen Sie einem Membernamen den Ausdruck zu, wie im folgenden Code veranschaulicht:  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## Siehe auch  
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)