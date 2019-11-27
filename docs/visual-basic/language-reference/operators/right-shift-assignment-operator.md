---
title: '>>Operator ='
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: cad021c7730782d6233c60841483df7173308dc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351995"
---
# <a name="-operator-visual-basic"></a>> > =-Operator (Visual Basic)
Führt eine arithmetische Rechtsverschiebung für den Wert einer Variablen oder Eigenschaft durch und weist das Ergebnis der Variablen oder der Eigenschaft zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>-Komponenten  
 `variableorproperty`  
 Erforderlich Variable oder Eigenschaft eines ganzzahligen Typs (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`oder `ULong`).  
  
 `amount`  
 Erforderlich Numerischer Ausdruck eines Datentyps, der zum `Integer`erweitert wird.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des `>>=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
 Der `>>=`-Operator führt zuerst eine arithmetische Rechtsverschiebung für den Wert der Variablen oder der Eigenschaft aus. Der Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zurück.  
  
 Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden. In einer arithmetischen rechten Schicht werden die Bits, die über die bitmost-Bitposition hinaus verschoben werden, verworfen, und das äußteste linke Bit wird an die auf der linken Seite freigegebenen Bitpositionen weitergegeben. Dies bedeutet, dass die frei gewordenen Positionen auf einen Wert festgelegt werden, wenn `variableorproperty` einen negativen Wert aufweist. Wenn `variableorproperty` positiv ist oder wenn der Datentyp ein nicht signierter Typ ist, werden die frei gewordenen Positionen auf NULL festgelegt.  
  
## <a name="overloading"></a>Überladen  
 Der [> > Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des `>>` Operators wirkt sich auf das Verhalten des `>>=` Operators aus. Wenn Ihr Code `>>=` in einer Klasse oder Struktur verwendet, die `>>`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `>>=`-Operator verwendet, um das Bitmuster einer `Integer` Variablen rechts um den angegebenen Betrag zu verschieben und das Ergebnis der Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Siehe auch

- [>>-Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
