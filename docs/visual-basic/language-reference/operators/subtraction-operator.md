---
title: '- -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 1a5c47a2f1bc8a8b9e1b0263b90006a0e58e17bb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830668"
---
# <a name="--operator-visual-basic"></a>--Operator (Visual Basic)
Gibt die Differenz zwischen zwei numerischen Ausdrücken oder den negativen Wert eines numerischen Ausdrucks zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>Teile  
 `expression1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich, wenn die `–` Operator einen negativen Wert berechnet. Ein beliebiger numerischer Ausdruck.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2`, oder der negierte Wert der `expression1`.  
  
 Der Ergebniswert vom Datentyp eines numerischen Typs, die für die Datentypen der entsprechenden `expression1` und `expression2`. Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Unterstützte Typen  
 allen numerischen Typen Dazu gehören auch die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.  
  
## <a name="remarks"></a>Hinweise  
 In der ersten Verwendung angezeigt, in der zuvor gezeigten Syntax der `–` Operator ist der *binäre* arithmetischer Subtraktionsoperator für den Unterschied zwischen zwei numerische Ausdrücke.  
  
 Im zweiten Anwendungsbeispiel in der zuvor gezeigten Syntax der `–` Operator ist der *unäre* Negationsoperator für den negativen Wert eines Ausdrucks. In diesem Sinne, das die Negation Umkehrung des Vorzeichens von besteht aus `expression1` , damit das Ergebnis positiv ist. wenn `expression1` ist negativ.  
  
 Wenn die beiden Ausdrücke ist ["Nothing"](../../../visual-basic/language-reference/nothing.md), `–` Operator wird er als 0 (null) behandelt.  
  
> [!NOTE]
>  Die `–` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet werden, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `–` Operator zum Berechnen und Zurückgeben des Unterschied zwischen zwei Zahlen, und klicken Sie dann eine Zahl zu negieren.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 Nach der Ausführung dieser Anweisungen ist `binaryResult` 124.45 enthält und `unaryResult` –334.90 enthält.  
  
## <a name="see-also"></a>Siehe auch

- [Operator-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
