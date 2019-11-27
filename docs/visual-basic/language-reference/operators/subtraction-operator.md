---
title: '- Operator'
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
ms.openlocfilehash: 9687c366c5b23693c05ab5c6b34f50c04131dfda
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348228"
---
# <a name="--operator-visual-basic"></a>--Operator (Visual Basic)
Gibt die Differenz zwischen zwei numerischen Ausdrücken oder dem negativen Wert eines numerischen Ausdrucks zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
expression1 – expression2
```
  
oder

```vb  
–expression1  
```  
  
## <a name="parts"></a>-Komponenten  
 `expression1`  
 Erforderlich Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich, es sei denn, der `–`-Operator berechnet einen negativen Wert. Ein beliebiger numerischer Ausdruck.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2`oder dem negiert-Wert von `expression1`.  
  
 Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von `expression1` und `expression2`geeignet ist. Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
  
## <a name="supported-types"></a>Unterstützte Typen  
 allen numerischen Typen Dies schließt die unsignierten und Gleit Komma Typen und `Decimal`ein.  
  
## <a name="remarks"></a>Hinweise  
 In der ersten Verwendung in der zuvor gezeigten Syntax ist der `–`-Operator der *binäre* arithmetische Subtraktions Operator für den Unterschied zwischen zwei numerischen Ausdrücken.  
  
 In der zweiten Syntax, die in der zuvor gezeigten Syntax angezeigt wird, ist der `–`-Operator der *unäre* Negations Operator für den negativen Wert eines Ausdrucks. In diesem Sinne besteht die Negation darin, das Vorzeichen `expression1` umzukehren, damit das Ergebnis positiv ist, wenn `expression1` negativ ist.  
  
 Wenn ein Ausdruck zu " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, behandelt der `–` Operator ihn als 0 (null).  
  
> [!NOTE]
> Der `–`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `–`-Operator verwendet, um die Differenz zwischen zwei Zahlen zu berechnen und zurückzugeben, und um dann eine Zahl zu negieren.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 Nach der Ausführung dieser Anweisungen enthält `binaryResult` 124,45 und `unaryResult` enthält – 334,90.  
  
## <a name="see-also"></a>Siehe auch

- [Operator-= (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
