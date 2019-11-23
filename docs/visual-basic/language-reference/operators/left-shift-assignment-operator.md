---
title: < < =-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: aae71069bdcb88efa5842526dd7eb47806f248d0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701106"
---
# <a name="-operator-visual-basic"></a>\<\<=-Operator (Visual Basic)
Führt eine arithmetische Verschiebung nach Links für den Wert einer Variablen oder Eigenschaft durch und weist das Ergebnis wieder der Variablen oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>-Komponenten  
 `variableorproperty`  
 Erforderlich Variable oder Eigenschaft eines ganzzahligen Typs (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`oder `ULong`).  
  
 `amount`  
 Erforderlich Numerischer Ausdruck eines Datentyps, der zum `Integer`erweitert wird.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des `<<=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
 Der `<<=`-Operator führt zuerst eine arithmetische Verschiebung nach Links für den Wert der Variablen oder der Eigenschaft aus. Der Operator weist dann das Ergebnis dieses Vorgangs wieder dieser Variablen oder Eigenschaft zu.  
  
 Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden. In einer arithmetischen linken Schicht werden die Bits, die nach dem Bereich des Ergebnis Datentyps verschoben werden, verworfen, und die auf der rechten Seite frei gewordenen Bitpositionen werden auf 0 (null) festgelegt.  
  
## <a name="overloading"></a>Überladen  
 Der [< < Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des `<<` Operators wirkt sich auf das Verhalten des `<<=` Operators aus. Wenn Ihr Code `<<=` in einer Klasse oder Struktur verwendet, die `<<`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `<<=`-Operator verwendet, um das Bitmuster einer `Integer` Variablen um den angegebenen Betrag nach Links zu verschieben und das Ergebnis der Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>Siehe auch

- [<<-Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
