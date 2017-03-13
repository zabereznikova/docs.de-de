---
title: "How to: Use a Class that Defines Operators (Visual Basic) | Microsoft Docs"
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
  - "operator procedures, calling"
  - "procedures, operator"
  - "procedures, calling"
  - "examples [Visual Basic], CType"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "return values, Operator procedures"
  - "operator overloading"
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# How to: Use a Class that Defines Operators (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie eine Klasse oder Struktur verwenden, die ihre eigenen Operatoren definiert, können Sie in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] auf diese Operatoren zugreifen.  
  
 Das Definieren eines Operators für eine Klasse oder Struktur wird auch als *Überladen* bezeichnet.  
  
## Beispiel  
 Im folgenden Beispiel erfolgt ein Zugriff auf die SQL\-Struktur <xref:System.Data.SqlTypes.SqlString>, mit der die Operatoren \([CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)\) für die Konvertierung in beide Richtungen, nämlich zwischen einer SQL\-Zeichenfolge und einer [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Zeichenfolge, definiert werden.  Verwenden Sie `CType(`*SQL\-Zeichenfolgenausdruck*, `String)`, um eine SQL\-Zeichenfolge in eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Zeichenfolge zu konvertieren, und `CType(`*Visual Basic\-Zeichenfolgenausdruck*, <xref:System.Data.SqlTypes.SqlString>`)` für die Konvertierung in die andere Richtung.  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 Die <xref:System.Data.SqlTypes.SqlString>\-Struktur definiert einen Operator \([CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)\) für die Konvertierung von `String` in <xref:System.Data.SqlTypes.SqlString> und einen weiteren Operator für die die Konvertierung von <xref:System.Data.SqlTypes.SqlString> in `String`.  Die Anweisung, durch die `title` dem Objekt `jobTitle` zugewiesen wird, verwendet den ersten Operator, während im Aufruf der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>\-Funktion der zweite Operator verwendet wird.  
  
## Kompilieren des Codes  
 Stellen Sie sicher, dass der zu verwendende Operator durch die Klasse oder die Struktur definiert wird, die Sie verwenden.  Gehen Sie nicht davon aus, dass in der Klasse oder Struktur jeder zum Überladen verfügbare Operator definiert ist.  Eine Liste der verfügbaren Operatoren finden Sie unter [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Fügen Sie am Anfang der Quelldatei \(in diesem Fall <xref:System.Data.SqlTypes>\) die entsprechende `Imports`\-Anweisung für die SQL\-Zeichenfolge ein.  
  
 Das Projekt muss Verweise auf System.Data und System.XML enthalten.  
  
## Siehe auch  
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [How to: Call an Operator Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)