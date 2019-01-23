---
title: Teilausdruck (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: d27ca262aa2349d34d78844e0aea0f96a1ced65c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496308"
---
# <a name="sub-expression-visual-basic"></a>Teilausdruck (Visual Basic)
Deklariert die Parameter und den Code, der einen Unterroutine Lambda-Ausdruck definieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`parameterlist`|Dies ist optional. Eine Liste von Namen lokaler Variablen, die die Parameter der Prozedur darstellen. Die Klammern müssen vorhanden sein, selbst wenn die Liste leer ist. Weitere Informationen finden Sie unter [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Erforderlich. Eine einzelne Anweisung.|  
|`statements`|Erforderlich. Eine Liste von Anweisungen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein *Lambda-Ausdruck* ist eine Unterroutine, die nicht über einen Namen verfügt, und eine oder mehrere Anweisungen ausgeführt wird. Sie können einen Lambda-Ausdruck an einer beliebigen Stelle, dass Sie einen Delegattyp, außer als Argument verwenden können `RemoveHandler`. Weitere Informationen zu Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt eine standard-Unterroutine. Die Unterschiede sind wie folgt aus:  
  
-   Ein Lambda-Ausdruck ist nicht auf einen Namen haben.  
  
-   Ein Lambda-Ausdruck kann nicht verfügen über einen Modifizierer, z. B. `Overloads` oder `Overrides`.  
  
-   Der Text eines einzeiligen Lambda-Ausdrucks muss es sich um eine Anweisung, die kein Ausdruck sein. Der Text kann einen Aufruf an eine Subprozedur, aber nicht aus einem Aufruf einer Funktion Prozedur bestehen.  
  
-   Alle Parameter in einem Lambdaausdruck entweder müssen angegeben haben, dass die Datentypen oder für alle Parameter abgeleitet werden müssen.  
  
-   Optionale und `ParamArray` Parameter sind in Lambda-Ausdrücken nicht zulässig.  
  
-   Generische Parameter sind in Lambda-Ausdrücken nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 Es folgt ein Beispiel für einen Lambda-Ausdruck, der einen Wert an die Konsole schreibt. Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Unterroutine. Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
