---
title: '&gt;&gt;=-Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7e388471b9adf424c55b1ad1042e5aed1ea8ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt;=-Operator (Visual Basic)
Führt eine arithmetische Verschiebung nach rechts auf den Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Variable oder eine Eigenschaft eines ganzzahligen Typs (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).  
  
 `amount`  
 Erforderlich. Numerische Ausdruck eines Datentyps, die erweitert `Integer`.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `>>=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `>>=` -Operator führt eine arithmetische rechtsverschiebung zuerst auf den Wert der Variablen oder Eigenschaft. Der Operator weist das Ergebnis dieses Vorgangs dann der Variablen oder Eigenschaft an.  
  
 Arithmetische Schichten sind nicht zirkulär, d. h. die Bits verschobene ein Ende des Resultsets nicht am anderen Ende wieder hinzugefügt werden. Klicken Sie in eine arithmetische Verschiebung nach rechts die Bits hinter Bit ganz rechts verschoben werden verworfen, und wird das Bit ganz links auf der linken Seite frei gewordene Bitpositionen weitergegeben. Dies bedeutet, dass bei `variableorproperty` hat einen negativen Wert die frei werdenden Positionen auf 1 gesetzt werden. Wenn `variableorproperty` positiv ist, oder wenn der Datentyp ein Typ ohne Vorzeichen ist, werden die frei werdenden Positionen auf 0 (null) festgelegt.  
  
## <a name="overloading"></a>Überladen  
 Die [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Überladen der `>>` Operator wirkt sich auf das Verhalten der `>>=` Operator. Wenn im Code verwendet `>>=` auf eine Klasse oder Struktur, die Überladungen `>>`, achten Sie verstehen, dass ihr neu definierten Verhalten. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `>>=` Operator, um das Bitmuster der UMSCHALTTASTE ein `Integer` Variablen nach rechts, um den angegebenen Betrag und das Ergebnis der Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [>>-Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
