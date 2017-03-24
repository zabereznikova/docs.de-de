---
title: "ByVal (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ByVal"
  - "ByVal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByVal keyword, contexts"
  - "ByVal keyword"
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# ByVal (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Kennzeichnet ein Argument, das so übergeben wird, dass der Wert einer Variablen, die dem Argument im Aufrufcode zugrunde liegt, von der aufgerufenen Prozedur oder Eigenschaft nicht geändert werden kann.  
  
## Hinweise  
 Der `ByVal`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung des Übergabemechanismus für den `ByVal`\-Parameter mit einem Referenztypargument veranschaulicht.  Im Beispiel ist das `c1`\-Argument eine Instanz der `Class1`\-Klasse.  `ByVal` verhindert, dass der zugrunde liegende Wert des `c1`\-Verweisarguments vom Code in den Prozeduren geändert wird, die Felder und Eigenschaften von `c1`, auf die zugegriffen werden kann, sind jedoch nicht geschützt.  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## Siehe auch  
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)