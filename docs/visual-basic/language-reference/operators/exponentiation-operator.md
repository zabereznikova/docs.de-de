---
title: ^-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: ce9cd527aff1203f30543b03f1520d429d038da3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978950"
---
# <a name="-operator-visual-basic"></a>^-Operator (Visual Basic)
Potenziert eine Zahl potenziert mit einer anderen Zahl.  
  
## <a name="syntax"></a>Syntax  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a>Teile  
 `number`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `exponent`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist `number` potenziert mit der `exponent`, immer als ein `Double` Wert.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 `Double`. Die Operanden eines anderen Typs werden in konvertiert `Double`.  
  
## <a name="remarks"></a>Hinweise  
 Visual Basic führt immer die Potenzierung der [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md).  
  
 Der Wert des `exponent` möglich Bruch, negativ oder beides.  
  
 Wenn mehr als eine Potenzierung, in einem einzelnen Ausdruck ausgeführt wird, der `^` Operator wird ausgewertet, wie sie von links nach rechts gefunden wird.  
  
> [!NOTE]
>  Die `^` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `^` Operator, um eine Zahl potenziert mit einem Exponenten zu erheben. Das Ergebnis ist der erste Operand des zweiten hoch.  
  
 [!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]  
  
 Im obige Beispiel ergibt sich Folgendes:  
  
 `exp1` ist auf 4 (2-squared) festgelegt.  
  
 `exp2` wird auf 19683 (3 cubed, klicken Sie dann diesen Wert Kubik) festgelegt.  
  
 `exp3` wird auf-125 (-5 Kubik) festgelegt.  
  
 `exp4` wird auf 625 (4 -5) festgelegt.  
  
 `exp5` ist auf 2 (Kubikwurzel von 8) festgelegt.  
  
 `exp6` ist auf 0,5 (1.0, geteilt durch die Kubikwurzel von 8) festgelegt.  
  
 Beachten Sie die Wichtigkeit der runden Klammern in der die Ausdrücke im vorherigen Beispiel. Aufgrund der *Operatorrangfolge*, Visual Basic normalerweise führt die `^` Operator vor allen anderen auch den unären `–` Operator. Wenn `exp4` und `exp6` berechnet worden ohne Klammern, sie würden die folgenden Ergebnisse erzeugt haben:  
  
 `exp4 = -5 ^ 4` wird berechnet als: (5 4), was-625 ergeben würde.  
  
 `exp6 = 8 ^ -1.0 / 3.0` wird berechnet als (8 die – 1 oder 0,125) geteilt durch 3.0, das 0,041666666666666666666666666666667 führen würde.  
  
## <a name="see-also"></a>Siehe auch
- [^=-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
