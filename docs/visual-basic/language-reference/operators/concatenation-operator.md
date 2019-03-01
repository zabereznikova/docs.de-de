---
title: '&amp; -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 2237da5d64ada6817d3a9a88b04b76f573bd76c0
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976511"
---
# <a name="amp-operator-visual-basic"></a>&amp; -Operator (Visual Basic)
Generiert eine zeichenfolgenverkettung aus zwei Ausdrücken.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `String` oder `Object` Variable.  
  
 `expression1`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der auf erweitert wird `String`.  
  
 `expression2`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der auf erweitert wird `String`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Datentyp des `expression1` oder `expression2` nicht `String` jedoch erweitert, um `String`, wird eine Konvertierung in `String`. Wenn entweder der Datentypen ist nicht zu erweitert `String`, generiert der Compiler einen Fehler.  
  
 Der Datentyp des `result` ist `String`. Wenn eine oder beide Ausdrücke [nichts](../../../visual-basic/language-reference/nothing.md) oder den Wert der <xref:System.DBNull.Value?displayProperty=nameWithType>, werden sie behandelt, als eine Zeichenfolge mit dem Wert "".  
  
> [!NOTE]
>  Die `&` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Das kaufmännische und-Zeichen (&) können auch zum Identifizieren von Variablen als Typ verwendet werden `Long`. Weitere Informationen finden Sie unter [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `&` Operator zum Verketten von Zeichenfolgen zu erzwingen. Das Ergebnis ist ein Zeichenfolgenwert, der die Verkettung von den beiden Zeichenfolgenoperanden darstellt.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- [&=-Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Verkettungsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
