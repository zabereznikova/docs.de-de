---
title: "Teilausdruck (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 43e35bd0386bc56478603ec36437981785cc8ffb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`parameterlist`|Dies ist optional. Eine Liste der Namen lokaler Variablen, die die Parameter der Prozedur darstellen. Die Klammern müssen vorhanden sein, auch wenn die Liste leer ist. Weitere Informationen finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Erforderlich. Eine einzelne Anweisung.|  
|`statements`|Erforderlich. Eine Liste von Anweisungen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein *Lambda-Ausdruck* Unterroutine vorstellen, die nicht über einen Namen verfügt ist und ausgeführt wird, eine oder mehrere Anweisungen. Sie können einen Lambda-Ausdruck an einer beliebigen Stelle verwenden, dass Sie einen Delegattyp, außer als Argument verwenden können `RemoveHandler`. Weitere Informationen über Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt dem von einer standard-Unterroutine. Die Unterschiede sind wie folgt aus:  
  
-   Ein Lambda-Ausdruck weist keine Namen auf.  
  
-   Ein Lambda-Ausdruck kann nicht verfügen über einen Modifizierer, wie z. B. `Overloads` oder `Overrides`.  
  
-   Der Text eines einzeiligen Lambda-Ausdrucks muss es sich um eine Anweisung, kein Ausdruck sein. Der Text kann einen Aufruf an eine Subprozedur, aber nicht auf einen Aufruf an eine Funktionsprozedur bestehen.  
  
-   In einen Lambda-Ausdruck müssen entweder für alle Parameter angegeben haben, Datentypen oder alle Parameter abgeleitet werden müssen.  
  
-   Dies ist optional und `ParamArray` Parameter sind in Lambda-Ausdrücken nicht zulässig.  
  
-   Generische Parameter sind in Lambda-Ausdrücken nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 Es folgt ein Beispiel für einen Lambda-Ausdruck, der einen Wert in die Konsole schreibt. Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Unterroutine. Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
