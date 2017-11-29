---
title: '&lt;&lt;=-Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c5c36e4f91155c09d01b448777483941d018d9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
