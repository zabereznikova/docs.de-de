---
title: "How to: Convert an Object to Another Type in Visual Basic | Microsoft Docs"
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
  - "objects [Visual Basic], converting"
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Convert an Object to Another Type in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Eine `Object`\-Variable kann mithilfe eines Konvertierungsschlüsselworts wie [CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) in einen anderen Datentyp umgewandelt werden.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `Object`\-Variable in eine `Integer`\-Variable und eine `String`\-Variable konvertiert.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Wenn Sie wissen, dass der Inhalt einer `Object`\-Variablen einen bestimmten Datentyp hat, sollten Sie die Variable in den betreffenden Datentyp umwandeln.  Wird stattdessen die `Object`\-Variable weiter verwendet, müssen entweder *Boxing*\- und *Unboxing*\-Operationen \(bei Werttypen\) oder eine *späte Bindung* \(bei Verweistypen\) ausgeführt werden.  Diese Operationen stellen einen zusätzlichen Arbeitsaufwand dar und führen damit zu Leistungseinbußen.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweis auf den <xref:System?displayProperty=fullName>\-Namespace.  
  
## Siehe auch  
 <xref:System.Object>   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)