---
title: Operatoren und Ausdrücke
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: 01e3a53e998774caee8863675b9151a140606852
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071676"
---
# <a name="operators-and-expressions-in-visual-basic"></a>Operatoren und Ausdrücke in Visual Basic

Ein *Operator* ist ein Codeelement, das einen Vorgang auf einem oder mehreren Codeelementen ausführt, die Werte halten. Wertelemente sind unter anderem Variablen, Konstanten, Literale, Eigenschaften, Rückgaben von `Function`- und `Operator`-Prozeduren sowie Ausdrücke.  
  
 Ein *Ausdruck* ist eine Serie von Wertelementen, die mit Operatoren kombiniert sind, was einen neuen Wert ergibt. Die Operatoren werden auf den Wertelementen ausgeführt, indem Berechnungen, Vergleiche oder andere Vorgänge ausgeführt werden.  
  
## <a name="types-of-operators"></a>Arten von Operatoren  

 Visual Basic stellt die folgenden Typen von Operatoren bereit:  
  
- [Arithmetische Operatoren](arithmetic-operators.md) führen bekannte Berechnungen auf numerischen Werten aus, einschließlich Verschieben der Bitmuster.  
  
- [Vergleichsoperatoren](comparison-operators.md) vergleichen zwei Ausdrücke und geben einen `Boolean`-Wert zurück, der das Ergebnis des Vergleichs darstellt.  
  
- [Verkettungs Operatoren](concatenation-operators.md) verbinden mehrere Zeichen folgen zu einer einzelnen Zeichenfolge.  
  
- [Logische und bitweise Operatoren in Visual Basic](logical-and-bitwise-operators.md) kombinieren `Boolean` oder numerische Werte und geben ein Ergebnis desselben Datentyps wie die Werte zurück.  
  
 Die Wertelemente, die mit einem Operator kombiniert sind, werden *Operanden* dieses Operators genannt. Operatoren, die mit Wertelementen kombiniert sind, bilden Ausdrücke. Eine Ausnahme ist der Zuweisungsoperator, der eine *Anweisung* bildet. Weitere Informationen finden Sie unter [Transact-SQL-Anweisungen](../statements.md).  
  
## <a name="evaluation-of-expressions"></a>Auswertung von Ausdrücken  

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
  
 [!code-vb[VbVbalrOperators#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#56)]  
  
 Im vorangehenden Beispiel führt Visual Basic die Vorgänge im Ausdruck auf der rechten Seite des Zuweisungs Operators () aus `=` und weist dann den resultierenden Wert der Variablen `x` auf der linken Seite zu. Es gibt keine festgelegte Einschränkung für die Anzahl der Operatoren, die in einem Ausdruck kombiniert werden können. Jedoch ist es notwendig, die [Operatorrangfolge in Visual Studio](../../../language-reference/operators/operator-precedence.md) zu verstehen, um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten.  

## <a name="see-also"></a>Siehe auch

- [Operatoren](../../../language-reference/operators/index.md)
- [Effiziente Kombination von Operatoren](efficient-combination-of-operators.md)
- [Anweisungen](../../../language-reference/statements/index.md)
