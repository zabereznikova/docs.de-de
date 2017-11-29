---
title: ^-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e7159f289b687055c7d75cc8da58d6f76607a83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>^-Operator (Visual Basic)
Potenziert eine Zahl zur Potenz einer anderen Zahl.  
  
## <a name="syntax"></a>Syntax  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a>Teile  
 `number`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `exponent`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist `number` potenziert mit der `exponent`, immer als eine `Double` Wert.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 `Double`. Die Operanden eines anderen Typs konvertiert werden `Double`.  
  
## <a name="remarks"></a>Hinweise  
 Visual Basic führt immer Potenzierung der [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md).  
  
 Der Wert des `exponent` kann Bruch, negativ oder beides.  
  
 Wenn mehr als eine Potenzierung in einem einzelnen Ausdruck erfolgt die `^` Operators ausgewertet wird, wie sie von links nach rechts entdeckt wird.  
  
> [!NOTE]
>  Die `^` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `^` Operator, um eine Zahl und einen Exponenten auslösen. Das Ergebnis ist der erste Operand potenziert mit der zweiten.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 Das obige Beispiel ergibt sich Folgendes aus:  
  
 `exp1`4 (2 Quadrat) festgelegt ist.  
  
 `exp2`wird auf 19683 (3 Kubik, klicken Sie dann diesen Wert Kubik) festgelegt.  
  
 `exp3`wird auf-125 (-5 Kubik) festgelegt.  
  
 `exp4`wird auf 625 (-5 4) festgelegt.  
  
 `exp5`wird auf 2 (Kubikwurzel von 8) festgelegt.  
  
 `exp6`ist auf 0,5 (1.0, dividiert durch die Kubikwurzel von 8) festgelegt.  
  
 Beachten Sie die Wichtigkeit der Klammern der Ausdrücke im vorangehenden Beispiel aus. Aufgrund der *Operatorrangfolge*, Visual Basic normalerweise führt die `^` Operator vor allen anderen auch den unären `–` Operator. Wenn `exp4` und `exp6` berechnet worden ohne Klammern sie hätte die folgenden Ergebnisse:  
  
 `exp4 = -5 ^ 4`würde als – 5 mit dem vierten Exponenten, berechnet der-625 würde.  
  
 `exp6 = 8 ^ -1.0 / 3.0`würde als (8, um die Leistungsfähigkeit von – 1 oder 0,125) berechnet werden geteilt durch 3.0, was 0,041666666666666666666666666666667 führen würde.  
  
## <a name="see-also"></a>Siehe auch  
 [^=-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
