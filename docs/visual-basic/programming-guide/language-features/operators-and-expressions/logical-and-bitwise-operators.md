---
title: "Logical and Bitwise Operators in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "short-circuiting"
  - "Boolean expressions"
  - "logical operators, Boolean expressions"
  - "operators [Visual Basic], logical"
  - "AndAlso operator"
  - "Not operator [Visual Basic], Boolean expressions"
  - "Xor operator [Visual Basic], Boolean expressions"
  - "And operator [Visual Basic], logical operators"
  - "logical operators"
  - "expressions [Visual Basic], Boolean"
  - "Or operator, logical operators"
  - "Visual Basic code, operators"
  - "short-circuiting, logical operators"
  - "logical operators, short-circuiting"
  - "Visual Basic code, expressions"
  - "logical operators, binary"
  - "OrElse operator [Visual Basic]"
  - "logical operators, unary"
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Logical and Bitwise Operators in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Logische Operatoren vergleichen `Boolean`\-Ausdrücke und geben ein `Boolean`\-Ergebnis zurück.  Die Operatoren `And`, `Or`, `AndAlso`, `OrElse` und `Xor` sind *binär*, weil sie zwei Operanden akzeptieren, während der Operator `Not` *unär* ist, weil er einen einzigen Operanden akzeptiert.  Einige dieser Operatoren können auch bitweise logische Operationen für ganzzahlige Werte ausführen.  
  
## Unärer logischer Operator  
 Der [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) führt eine logische *Negation* für einen `Boolean`\-Ausdruck aus.  Das Ergebnis ist das logische Gegenteil seines Operanden.  Wenn der Ausdruck `True` ergibt, gibt `Not` den Wert `False` zurück. Wenn der Ausdruck `False` ergibt, gibt `Not` den Wert `True` zurück.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operato_1.vb)]  
  
## Binäre logische Operatoren  
 Der [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) führt eine logische *Konjunktion* für zwei `Boolean`\-Ausdrücke aus.  Wenn beide Ausdrücke `True` ergeben, gibt `And` den Wert `True` zurück.  Wenn mindestens einer der Ausdrücke `False` ergibt, gibt `And` den Wert `False` zurück.  
  
 Der [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) führt eine logische *Disjunktion* oder *Inklusion* für zwei `Boolean`\-Ausdrücke aus.  Wenn einer von beiden Ausdrücken `True` ergibt oder wenn beide Ausdrücke `True` ergeben, gibt `Or` den Wert `True` zurück.  Wenn keiner der beiden Ausdrücke `True` ergibt, gibt `Or` den Wert `False` zurück.  
  
 Der [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) führt einen logischen *Ausschluss* für zwei `Boolean`\-Ausdrücke aus.  Wenn genau ein Ausdruck `True` ergibt, jedoch nicht beide Ausdrücke, gibt `Xor` den Wert `True` zurück.  Wenn beide Ausdrücke `True` ergeben oder wenn beide Ausdrücke `False` ergeben, gibt `Xor` den Wert `False` zurück.  
  
 Im folgenden Beispiel werden die Operatoren `And`, `Or` und `Xor` veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operato_2.vb)]  
  
## Logische Kurzschlussoperationen  
 Der [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md)\- ist dem Operator `And` sehr ähnlich. Er führt ebenfalls eine logische Konjunktion für zwei `Boolean`\-Ausdrücke aus.  Der Hauptunterschied zwischen den beiden Operatoren ist, dass `AndAlso` *Kurzschlussverhalten* aufweist.  Wenn der erste Ausdruck in einem `AndAlso`\-Ausdruck `False` ist, wird der zweite Ausdruck nicht ausgewertet, weil das Ergebnis hierdurch nicht geändert wird, und `AndAlso` gibt `False` zurück.  
  
 Der [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) führt eine logische Kurzschlussdisjunktion für zwei `Boolean`\-Ausdrücke aus.  Wenn der erste Ausdruck in einem `OrElse`\-Ausdruck `True` ist, wird der zweite Ausdruck nicht ausgewertet, weil das Ergebnis hierdurch nicht geändert wird, und `OrElse` gibt `True` zurück.  
  
### Vor\-und Nachteile von Kurzschlussverhalten  
 Durch Kurzschlussverhalten kann die Leistung erhöht werden, weil ein Ausdruck, der das Ergebnis der logischen Operation nicht ändern kann, nicht ausgewertet wird.  Wenn dieser Ausdruck zusätzliche Aktionen ausführt, werden diese Aktionen jedoch bei Kurzschlussverhalten übersprungen.  Wenn der Ausdruck z. B. einen Aufruf einer `Function`\-Prozedur enthält, wird diese Prozedur nicht aufgerufen, sofern der Ausdruck kurzgeschlossen wird, und zusätzlicher Code in `Function` wird nicht ausgeführt.  Deshalb wird die Funktion möglicherweise nur gelegentlich ausgeführt werden und somit nicht ordnungsgemäß getestet.  Oder die Programmlogik könnte vom Code in `Function` abhängen.  
  
 Im folgenden Beispiel wird der Unterschied zwischen `And`, `Or` und ihren entsprechenden Kurzschlussoperatoren veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operato_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operato_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operato_5.vb)]  
  
 Beachten Sie im vorhergehenden Beispiel, dass wichtiger Code in `checkIfValid()` nicht ausgeführt wird, wenn der Aufruf kurzgeschlossen wird.  Die erste `If`\-Anweisung ruft `checkIfValid()` auf, obwohl `12 > 45` `False` zurückgibt, da `And` keinen Kurzschluss ausführt.  Die zweite `If`\-Anweisung ruft `checkIfValid()` nicht auf, weil mit `AndAlso` der zweite Ausdruck kurzgeschlossen wird, wenn `12 > 45` `False` zurückgibt.  Die dritte `If`\-Anweisung ruft `checkIfValid()` auf, obwohl `12 < 45` `True` zurückgibt, da `Or` keinen Kurzschluss ausführt.  Die vierte `If`\-Anweisung ruft `checkIfValid()` nicht auf, weil mit `OrElse` der zweite Ausdruck kurzgeschlossen wird, wenn `12 < 45` `True` zurückgibt.  
  
## Bitweise Operationen  
 Bitweise Operationen werten zwei ganzzahlige Werte in binärer Form \(Basis 2\) aus.  Sie vergleichen die Bits an den entsprechenden Positionen und weisen dann auf dem Vergleich basierende Werte zu.  Im folgenden Beispiel wird der Operator `And` veranschaulicht.  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operato_6.vb)]  
  
 Im vorherigen Beispiel wird der Wert von `x` auf 1 festgelegt.  Dies geschieht aus den folgenden Gründen:  
  
-   Die Werte werden als binär behandelt:  
  
     3 in binärer Form \= 011  
  
     5 in binärer Form \= 101  
  
-   Der Operator `And` vergleicht die binären Darstellungen, und zwar jeweils eine binäre Position \(ein Bit\).  Wenn beide Bits an einer angegebenen Position 1 sind, wird als Ergebnis eine 1 an dieser Position gesetzt.  Wenn eines der Bits 0 ist, wird als Ergebnis eine 0 an dieser Position gesetzt.  Im vorherigen Beispiel ergibt dies Folgendes:  
  
     011 \(3 in binärer Form\)  
  
     101 \(5 in binärer Form\)  
  
     001 \(das Ergebnis in binärer Form\)  
  
-   Das Ergebnis wird als Dezimalzahl behandelt.  Der Wert 001 ist die binäre Darstellung von 1, daher `x` \= 1.  
  
 Die bitweise `Or`\-Operation ist ähnlich, nur wird dem Ergebnisbit 1 zugewiesen, wenn eines oder beide der verglichenen Bits 1 sind.  `Xor` weist dem Ergebnisbit 1 zu, wenn nur eines \(jedoch nicht beide\) der verglichenen Bits 1 ist.  `Not` akzeptiert einen einzigen Operanden und kehrt alle Bits um, einschließlich des Vorzeichenbits, und weist dem Ergebnis diesen Wert zu.  Das bedeutet, dass `Not` für positive Zahlen mit Vorzeichen immer einen negativen Wert zurückgibt und dass `Not` für negative Zahlen immer eine positive Zahl oder 0 \(null\) zurückgibt.  
  
 Der Operator `AndAlso` und der Operator `OrElse` unterstützen keine bitweisen Operationen.  
  
> [!NOTE]
>  Bitweise Operationen können nur für ganzzahlige Typen ausgeführt werden.  Gleitkommawerte müssen in ganzzahlige Typen konvertiert werden, bevor bitweise Operationen ausgeführt werden können.  
  
## Siehe auch  
 [Logical\/Bitwise Operators](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Boolean Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)