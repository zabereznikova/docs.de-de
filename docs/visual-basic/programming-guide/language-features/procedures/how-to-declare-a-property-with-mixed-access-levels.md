---
title: "How to: Declare a Property with Mixed Access Levels (Visual Basic) | Microsoft Docs"
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
  - "access levels, properties"
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "mixed access levels"
  - "Visual Basic code, properties"
  - "properties [Visual Basic], access levels"
  - "Property statement, declaring mixed access levels"
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Declare a Property with Mixed Access Levels (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn die `Get`\-Prozedur und die `Set`\-Prozedur einer Eigenschaft verschiedene Zugriffsebenen haben sollen, kann in der `Property`\-Anweisung die weniger einschränkende Zugriffsebene und in der `Get`\-Anweisung oder der `Set`\-Anweisung die restriktivere Ebene verwendet werden.  Innerhalb einer Eigenschaft können gemischte Zugriffsebenen verwendet werden, wenn bestimmte Codeteile den Wert der Eigenschaft abrufen und andere Teile des Codes den Wert ändern können sollen.  
  
 Weitere Informationen zu Zugriffsebenen finden Sie unter [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### So deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen  
  
1.  Deklarieren Sie die Eigenschaft auf die übliche Weise, und geben Sie in der `Property`\-Anweisung die weniger restriktive Zugriffsebene an \(z. B. `Public`\).  
  
2.  Deklarieren Sie entweder die `Get`\-Prozedur oder die `Set`\-Prozedur unter Angabe der restriktiveren Zugriffsebene \(z. B. `Friend`\).  
  
3.  Geben Sie für die andere Eigenschaftenprozedur keine Zugriffsebene an.  Dann wird die in der `Property`\-Anweisung deklarierte Zugriffsebene übernommen.  Sie können den Zugriff nur bei einer der Eigenschaftenprozeduren beschränken.  
  
     [!code-vb[VbVbcnProcedures#10](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-declare-a-propert_1.vb)]  
  
     Im vorhergehenden Beispiel hat die `Get`\-Prozedur den gleichen `Protected`\-Zugriff wie die Eigenschaft selbst. Die `Set`\-Prozedur hat dagegen `Private`\-Zugriff.  Eine von `employee` abgeleitete Klasse kann den `salary`\-Wert lesen, aber nur die `employee`\-Klasse kann ihn festlegen.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)