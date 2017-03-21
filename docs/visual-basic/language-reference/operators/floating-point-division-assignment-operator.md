---
title: / =-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./=
dev_langs:
- VB
helpviewer_keywords:
- assignment statements, compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ab0a007f039d3dbda989bb605cb80fcf5fc7460a
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-visual-basic"></a>/=-Operator (Visual Basic)
Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das Ergebnis Gleitkommazahl der Variablen oder Eigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Alle numerischen Variablen oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `/=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `/=` Operator dividiert den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators) zuerst den Wert des Ausdrucks (auf der rechten Seite des Operators). Der Operator weist die Gleitkommaergebnis dieses Vorgangs zu der Variablen oder Eigenschaft.  
  
 Diese Anweisung weist ein `Double` Wert der Variablen oder Eigenschaft auf der linken Seite. If `Option Strict` is `On`, `variableorproperty` must be a `Double`. Wenn `Option Strict` ist `Off`, Visual Basic eine implizite Konvertierung ausführt und weist den resultierenden Wert `variableorproperty`, wobei ein Fehler zur Laufzeit. Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="overloading"></a>Überladen  
 Die [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist. Das Überladen der `/` Operator beeinflusst das Verhalten von der `/=` Operator. Wenn im Code `/=` für eine Klasse oder Struktur, die Überladungen `/`, werden Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `/=` Operator, um einen unterteilen `Integer` Variable, indem das zweite und das Zuweisen der Quotient der ersten Variablen.  
  
 [!code-vb[VbVbalrOperators&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)

