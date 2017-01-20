---
title: "How to: Put a Value in a Property (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "property values"
  - "Visual Basic code, procedures"
  - "values, properties"
  - "Visual Basic code, properties"
  - "properties [Visual Basic], values"
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Put a Value in a Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Um einen Wert in einer Eigenschaft zu speichern, fügen Sie den Namen der Eigenschaft auf der linken Seite einer Zuweisungsanweisung ein.  
  
 Die `Set`\-Prozedur der Eigenschaft speichert einen Wert. Sie rufen die Eigenschaft jedoch nicht explizit über ihren Namen auf.  Sie verwenden die Eigenschaft wie eine Variable.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ruft die Prozeduren der Eigenschaft auf.  
  
### So speichern Sie einen Wert in einer Eigenschaft  
  
1.  Verwenden Sie den Namen der Eigenschaft auf der linken Seite einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der `TimeOfDay`\-Eigenschaft von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] auf Mittag gesetzt, wobei deren `Set`\-Prozedur implizit aufgerufen wird.  
  
     [!code-vb[VbVbcnProcedures#11](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-put-a-value-in-a-pro_1.vb)]  
  
2.  Wenn die Eigenschaft Argumente annimmt, fügen Sie nach dem Eigenschaftennamen runde Klammern ein, die die Argumentliste einschließen.  Wenn keine Argumente vorliegen, können Sie die Klammern auch weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, und trennen Sie die Argumente durch Kommas.  Geben Sie die Argumente unbedingt in genau der Reihenfolge an, in der die Eigenschaft die entsprechenden Parameter definiert.  
  
4.  Der Wert, der auf der rechten Seite der Zuweisungsanweisung generiert wird, wird in der Eigenschaft gespeichert.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)