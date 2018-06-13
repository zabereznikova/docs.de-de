---
title: '&lt;&lt;=-Operator (Visual Basic)'
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
ms.openlocfilehash: 559624f7097f90d374ee83e3c0a9ac97d9f93444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600726"
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt;=-Operator (Visual Basic)
Führt eine arithmetische Verschiebung nach links auf den Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Variable oder eine Eigenschaft eines ganzzahligen Typs (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).  
  
 `amount`  
 Erforderlich. Numerische Ausdruck eines Datentyps, die erweitert `Integer`.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `<<=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `<<=` -Operator führt eine arithmetische linksverschiebung zuerst auf den Wert der Variablen oder Eigenschaft. Der Operator weist das Ergebnis dieses Vorgangs dann wieder auf diese Variablen oder Eigenschaft.  
  
 Arithmetische Schichten sind nicht zirkulär, d. h. die Bits verschobene ein Ende des Resultsets nicht am anderen Ende wieder hinzugefügt werden. In eine arithmetische linksverschiebung der Bits, die außerhalb des Gültigkeitsbereichs für den Ergebnisdatentyp verschoben werden verworfen, und die Bitpositionen auf der rechten Seite ist auf 0 festgelegt.  
  
## <a name="overloading"></a>Überladen  
 Die [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Überladen der `<<` Operator wirkt sich auf das Verhalten der `<<=` Operator. Wenn im Code verwendet `<<=` auf eine Klasse oder Struktur, die Überladungen `<<`, achten Sie verstehen, dass ihr neu definierten Verhalten. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `<<=` Operator, um das Bitmuster der UMSCHALTTASTE ein `Integer` Variable links von den angegebenen Betrag an und weisen Sie das Ergebnis der Variablen.  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [<<-Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
