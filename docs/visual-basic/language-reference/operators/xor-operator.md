---
title: "Xor Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Xor"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "exclusive OR operator"
  - "logical exclusion"
  - "operators [Visual Basic], exclusive or"
  - "exclusion operator"
  - "operators [Visual Basic], bitwise"
  - "bitwise operators, XOR operator"
  - "Xor operator [Visual Basic]"
  - "Xor keyword"
  - "bitwise comparison"
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Xor Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Führt einen logischen Ausschluss zweier `Boolean`\-Ausdrücke oder einen bitweisen Ausschluss zweier numerischer Ausdrücke durch.  
  
## Syntax  
  
```  
  
result = expression1 Xor expression2  
```  
  
## Teile  
 `result`  
 Erforderlich.  Beliebiger `Boolean`\-Ausdruck oder numerische Variable.  Bei booleschen Vergleichen ist `result` der logische Ausschluss \(exklusive logische Disjunktion\) aus zwei `Boolean`\-Werten.  Bei bitweisen Operationen ist `result` ein numerischer Wert, der den bitweisen Ausschluss \(exklusive bitweise Disjunktion\) aus zwei numerischen Bitmustern darstellt.  
  
 `expression1`  
 Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck oder numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck oder numerischer Ausdruck.  
  
## Hinweise  
 Bei booleschen Vergleichen ist `result` dann und nur dann `True`, wenn genau einer der beiden Ausdrücke `expression1` oder `expression2` den Wert `True`ergibt.  Das heißt, nur wenn `expression1` und `expression2` entgegengesetzte `Boolean` Werte ergeben.  Die folgende Tabelle veranschaulicht, wie `result` bestimmt wird.  
  
|Wert von `expression1`|Und `expression2` gleich|hat `result` den Wert|  
|----------------------------|------------------------------|---------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In einem booleschen Vergleich wertet der Operator `Xor` immer beide Ausdrücke aus, wobei u. U. Prozeduraufrufe ausgeführt werden können.  Es gibt keine Kurzschlussentsprechung für `Xor`, da das Ergebnis immer von beiden Operanden abhängt.  Informationen über *logische Kurzschlussoperatoren* finden Sie unter [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) und [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Bei bitweisen Operationen vergleicht der Operator `Xor` bitweise Bits, die in zwei numerischen Ausdrücken identisch positioniert sind, und legt das entsprechende Bit gemäß der folgenden Tabelle auf `result` fest.  
  
|Wenn Bit in `expression1` gleich|Und Bit in `expression2` gleich|Dann ist das Bit in `result` gleich|  
|--------------------------------------|-------------------------------------|-----------------------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren einen niedrigeren Rang als andere arithmetische und relationale Operatoren haben, müssen alle bitweisen Operationen in Klammern platziert werden, damit eine genaue Ausführung gewährleistet ist.  
  
 Beispielsweise steht 5 `Xor` 3 für 6.  Um zu diesem Ergebnis zu kommen, müssen Sie 5 und 3 in ihre binären Darstellungen, d. h. 101 und 011, konvertieren.  Anschließend müssen Sie anhand der vorherigen Tabelle festlegen, dass 101 Xor 011 für 110 steht. Dies ist die binäre Darstellung der Dezimalzahl 6.  
  
## Datentypen  
 Wenn die Operanden aus einem `Boolean`\-Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean`\-Ausdruck in einen numerischen Wert \(–1 für `True` und 0 für `False`\) und führt eine bitweise Operation aus.  
  
 Bei einem `Boolean`\-Vergleich ist der Datentyp des Ergebnisses `Boolean`.  Bei einem bitweisen Vergleich ist der Datentyp des Ergebnisses ein numerischer Typ, der für die Datentypen von `expression1` und `expression2` geeignet ist.  Siehe die Tabelle "Relationale und bitweise Vergleiche" in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## Überladen  
 Der Operator `Xor` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall dessen neu definiertes Verhalten kennen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 In diesem Beispiel wird mit dem Operator `Xor` ein logischer Ausschluss \(exklusive logische Disjunktion\) mit zwei Ausdrücken ausgeführt.  Das Ergebnis ist ein `Boolean`\-Wert, der darstellt, ob genau einer der beiden Ausdrücke `True` ist.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 Durch das vorherige Beispiel werden die Ergebnisse `False`, `True` bzw. `False` erzeugt.  
  
## Beispiel  
 Im folgenden Beispiel wird mit dem Operator `Xor` ein logischer Ausschluss \(exklusive logische Disjunktion\) für zwei einzelne Bits von zwei numerischen Ausdrücken ausgeführt.  Das Bit im Ergebnismuster wird gesetzt, wenn genau eines der entsprechenden Bits in den Operanden auf 1 gesetzt wird.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 Durch das vorherige Beispiel werden die Ergebnisse 2, 12 bzw. 14 erzeugt.  
  
## Siehe auch  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)