---
title: '&amp;=-Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 929a9e8c3384451679fc52ad478eb03219d67192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a>&amp;=-Operator (Visual Basic)
Verkettet eine `String` Ausdruck, der eine `String` Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Alle `String` Variablen oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Beliebiger `String`-Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `&=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Die `&=` verkettet die `String` Ausdruck auf der rechten Seite, um die `String` Variablen oder Eigenschaft auf der linken und weist das Ergebnis der Variablen oder Eigenschaft auf der linken Seite.  
  
## <a name="overloading"></a>Überladen  
 Die [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Überladen der `&` Operator wirkt sich auf das Verhalten der `&=` Operator. Wenn im Code verwendet `&=` auf eine Klasse oder Struktur, die Überladungen `&`, achten Sie verstehen, dass ihr neu definierten Verhalten. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `&=` Operator zum Verketten von zwei `String` Variablen und das Ergebnis die erste Variable zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
