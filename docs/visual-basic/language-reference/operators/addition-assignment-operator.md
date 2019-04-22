---
title: +=-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 4b8f36397d0f52866ebe9fa188d6b163364aeffc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839012"
---
# <a name="-operator-visual-basic"></a>+=-Operator (Visual Basic)
Der Wert einer numerischen Variablen oder Eigenschaft den Wert eines numerischen Ausdrucks hinzugefügt, und weist das Ergebnis der Variablen oder Eigenschaft. Kann auch verwendet werden, zum Verketten von einer `String` Ausdruck, der eine `String` Variablen oder einer Eigenschaft sowie das Ergebnis der Variablen oder Eigenschaft zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Alle numerischen oder `String` Variable oder eine Eigenschaft.  
  
 `expression`  
 Erforderlich. Alle numerischen oder `String` Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `+=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `+=` Operator fügt den Wert auf der rechten Seite der Variablen oder die Eigenschaft auf der linken Seite und weist das Ergebnis der Variablen oder Eigenschaft auf der linken Seite. Die `+=` Operator kann auch zum Verketten verwendet werden die `String` Ausdruck auf der rechten Seite, um die `String` Variable oder Eigenschaft auf der linken Seite, und weisen Sie das Ergebnis der Variablen oder Eigenschaft in der linken Seite.  
  
> [!NOTE]
>  Bei Verwendung der `+=` Operator an, Sie möglicherweise nicht bestimmen, ob die Additions- oder Zeichenfolge Verkettung erfolgt. Verwenden der `&=` Operator zum Verketten, um Mehrdeutigkeit zu vermeiden und um selbst dokumentierender Code bereitzustellen.  
  
 Dieser Zuweisungsoperator führt implizit erweitern, aber keine einschränkende Konvertierungen, wenn der kompilierungsumgebung strikte Semantik erzwingt. Weitere Informationen zu dieser Konvertierungen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Weitere Informationen zu strikte und flexible Semantik, finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Wenn Semantik zulässig sind, die `+=` Operator führt implizit eine Vielzahl von Zeichenfolgen- und numerische Konvertierungen identisch, mit denen die `+` Operator. Weitere Informationen zu dieser Konvertierungen finden Sie unter [+-Operator](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Überladen  
 Die `+` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Das Überladen der `+` Operator beeinflusst das Verhalten von der `+=` Operator. Wenn Ihr Code verwendet `+=` für eine Klasse oder Struktur, die Überladungen `+`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `+=` Operator, um den Wert einer Variablen zu kombinieren. Der erste Teil verwendet `+=` mit numerischen Variablen einen Wert in einen anderen hinzufügen. Der zweite Teil verwendet `+=` mit `String` Variablen, einem Wert mit einem anderen zu verketten. In beiden Fällen wird das Ergebnis der ersten Variablen zugewiesen.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 Der Wert des `num1` ist jetzt 13 und den Wert der `str1` ist jetzt "103".  
  
## <a name="see-also"></a>Siehe auch

- [+-Operator](../../../visual-basic/language-reference/operators/addition-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
