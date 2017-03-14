---
title: "Not Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Not"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean expressions, negating"
  - "operators [Visual Basic], bitwise"
  - "negation operator"
  - "inverse bit values in variables"
  - "bitwise operators, NOT operator"
  - "bitwise comparison"
  - "Not operator [Visual Basic]"
  - "logical negation"
  - "operators [Visual Basic], negation"
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Not Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Führt eine logische Negation eines `Boolean`\-Ausdrucks oder eine bitweise Negation eines numerischen Ausdrucks aus.  
  
## Syntax  
  
```  
  
result = Not expression  
```  
  
## Teile  
 `result`  
 Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck oder numerischer Ausdruck.  
  
 `expression`  
 Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck oder numerischer Ausdruck.  
  
## Hinweise  
 Die folgende Tabelle veranschaulicht für `Boolean`\-Ausdrücke, wie `result` ermittelt wird.  
  
|Wert von `expression`|hat `result` den Wert|  
|---------------------------|---------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Bei numerischen Ausdrücken invertiert der Operator `Not` die Bitwerte eines beliebigen numerischen Ausdrucks und setzt das jeweilige Bit in `result` gemäß der folgenden Tabelle.  
  
|Wenn Bit in `expression` gleich|Dann ist das Bit in `result` gleich|  
|-------------------------------------|-----------------------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren einen niedrigeren Rang als andere arithmetische und relationale Operatoren haben, müssen alle bitweisen Operationen in Klammern platziert werden, damit eine genaue Ausführung gewährleistet ist.  
  
## Datentypen  
 Bei einer booleschen Negation ist der Datentyp des Ergebnisses `Boolean`.  Bei einer bitweisen Negation entspricht der Datentyp des Ergebnisses dem Datentyp von `expression`.  Wenn der Ausdruck jedoch zum `Decimal`\-Datentyp gehört, weist das Ergebnis den `Long`\-Datentyp auf.  
  
## Überladen  
 Der Operator `Not` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definieren kann, wenn sein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird mit dem Operator `Not` eine logische Negation eines `Boolean`\-Ausdrucks ausgeführt.  Das Ergebnis ist ein `Boolean`\-Wert, der das Gegenteil des Werts des Ausdrucks darstellt.  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 Mit dem obigen Beispiel werden die Ergebnisse `False` bzw. `True` erzeugt.  
  
## Beispiel  
 Im folgenden Beispiel wird mit dem Operator `Not` eine logische Negation der einzelnen Bits eines numerischen Ausdrücks ausgeführt.  Das Bit im Ergebnismuster ist auf das Gegenteil des entsprechenden Bits im Operandenmuster eingestellt, einschließlich dem Vorzeichenbit.  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 Durch das vorangehende Beispiel werden die Ergebnisse \-11, \-9 bzw. \-7 erzeugt.  
  
## Siehe auch  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)