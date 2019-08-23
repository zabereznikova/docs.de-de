---
title: '&amp;Operator (Visual Basic)'
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
ms.openlocfilehash: d387b2dfdbb3fefe357364f7b2a3dde155cbd489
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968355"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operator (Visual Basic)
Generiert eine Zeichen folgen Verkettung von zwei Ausdrücken.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Beliebige `String` - `Object` oder-Variable.  
  
 `expression1`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der zu `String`erweitert wird.  
  
 `expression2`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der zu `String`erweitert wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Datentyp von `expression1` oder `expression2` `String` `String`nicht ist `String`, wird er in konvertiert. Wenn einer der Datentypen nicht in `String`erweitert wird, generiert der Compiler einen Fehler.  
  
 Der Datentyp von `result` ist `String`. Wenn ein oder beide Ausdrücke als " [Nothing](../../../visual-basic/language-reference/nothing.md) " ausgewertet werden oder den <xref:System.DBNull.Value?displayProperty=nameWithType>Wert aufweisen, werden Sie als Zeichenfolge mit dem Wert "" behandelt.  
  
> [!NOTE]
> Der `&` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Das kaufmännische und-Zeichen (&) kann auch verwendet werden, um Variablen als Typ `Long`zu identifizieren. Weitere Informationen finden Sie unter [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird `&` der-Operator verwendet, um die Zeichen folgen Verkettung zu erzwingen. Das Ergebnis ist ein Zeichen folgen Wert, der die Verkettung der beiden Zeichen folgen Operanden darstellt.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [&=-Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Verkettungs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
