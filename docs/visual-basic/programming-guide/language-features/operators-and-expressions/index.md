---
title: "Operatoren und Ausdrücke in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands, definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 069178fe753c3e09116c8a4845f96faf13eb72ec
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
<a id="operators-and-expressions-in-visual-basic" class="xliff"></a>

# Operatoren und Ausdrücke in Visual Basic
Ein *Operator* ist ein Codeelement, das einen Vorgang auf einem oder mehreren Codeelementen ausführt, die Werte halten. Wertelemente sind unter anderem Variablen, Konstanten, Literale, Eigenschaften, Rückgaben von `Function`- und `Operator`-Prozeduren sowie Ausdrücke.  
  
 Ein *Ausdruck* ist eine Serie von Wertelementen, die mit Operatoren kombiniert sind, was einen neuen Wert ergibt. Die Operatoren werden auf den Wertelementen ausgeführt, indem Berechnungen, Vergleiche oder andere Vorgänge ausgeführt werden.  
  
<a id="types-of-operators" class="xliff"></a>

## Arten von Operatoren  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] stellt folgende Arten von Operatoren bereit:  
  
-   [Arithmetische Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) führen bekannte Berechnungen auf numerischen Werten aus, einschließlich Verschieben der Bitmuster.  
  
-   [Vergleichsoperatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) vergleichen zwei Ausdrücke und geben einen `Boolean`-Wert zurück, der das Ergebnis des Vergleichs darstellt.  
  
-   [Verkettungsoperatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge.  
  
-   [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) kombinieren `Boolean` oder numerische Werte und geben ein Ergebnis desselben Datentyps wie die Werte zurück.  
  
 Die Wertelemente, die mit einem Operator kombiniert sind, werden *Operanden* dieses Operators genannt. Operatoren, die mit Wertelementen kombiniert sind, bilden Ausdrücke. Eine Ausnahme ist der Zuweisungsoperator, der eine *Anweisung* bildet. Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/programming-guide/language-features/statements.md).  
  
<a id="evaluation-of-expressions" class="xliff"></a>

## Auswertung von Ausdrücken  
 Das Endergebnis eines Ausdrucks stellt einen Wert dar, der normalerweise ein bekannter Datentyp ist, z.B. `Boolean`, `String` oder ein numerischer Typ.  
  
 Nachstehend sind Beispiele für Ausdrücke.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Einige Operatoren können Aktionen in einzelnen Ausdrücken oder einer Anweisung ausführen, wie das folgende Beispiel darstellt.  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 Im vorhergehenden Beispiel führt [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] die Vorgänge im Ausdruck auf der rechten Seite des Zuweisungsoperators (`=`) aus und weist den ergebenden Wert dann der Variable `x` auf der linken Seite zu. Es gibt keine festgelegte Einschränkung für die Anzahl der Operatoren, die in einem Ausdruck kombiniert werden können. Jedoch ist es notwendig, die [Operatorrangfolge in Visual Studio](../../../../visual-basic/language-reference/operators/operator-precedence.md) zu verstehen, um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten.  
  
 Weitere Informationen und Beispiele finden Sie unter [Operator Overloading in Visual Basic 2005 (Operatorüberladung in Visual Basic 2005)](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
<a id="see-also" class="xliff"></a>

## Siehe auch  
 [Operatoren](../../../../visual-basic/language-reference/operators/index.md)   
 [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)   
 [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)
