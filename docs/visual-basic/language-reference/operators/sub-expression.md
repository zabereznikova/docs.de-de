---
title: "Sub Expression (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "lambda expressions [Visual Basic], sub expression"
  - "Sub Expression [Visual Basic]"
  - "subroutines [Visual Basic], sub expressions"
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Sub Expression (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Deklariert die Parameter und den Code, die einen Lambda\-Unterroutinenausdruck definieren.  
  
## Syntax  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`parameterlist`|Optional.  Eine Liste der Namen von lokalen Variablen, die die Parameter der Prozedur darstellen.  Die Klammern müssen auch dann vorhanden sein, wenn die Liste leer ist.  Weitere Informationen finden Sie unter [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Erforderlich.  Eine einzelne Anweisung.|  
|`statements`|Erforderlich.  Eine Liste mit Anweisungen.|  
  
## Hinweise  
 Ein *Lambda\-Ausdruck* ist eine Unterroutine, die nicht über einen Namen verfügt und die eine oder mehrere Anweisungen ausführt.  Sie können einen Lambda\-Ausdruck überall dort verwenden, wo Sie auch einen Delegattyp verwenden können, außer als Argument für `RemoveHandler`.  Weitere Informationen zu Delegaten und der Verwendung von Lambda\-Ausdrücken mit Delegaten, finden Sie unter [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) und [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## Lambda\-Ausdruckssyntax  
 Die Syntax eines Lambda\-Ausdrucks ähnelt der einer Standardunterroutine.  Die Unterschiede sind:  
  
-   Ein Lambda\-Ausdruck verfügt über keinen Namen.  
  
-   Ein Lambda\-Ausdruck darf keinen Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.  
  
-   Der Text des einzeiligen Lambda\-Ausdruck muss eine Anweisung sein, kein Ausdruck.  Der Text kann aus einem Aufruf einer Sub\-Prozedur bestehen, jedoch nicht aus einem Aufruf einer Funktionsprozedur.  
  
-   In einem Lambdaausdruck müssen entweder für alle Parameter Datentypen angegeben sein oder alle Parameter müssen abgeleitet werden.  
  
-   Optionale und `ParamArray`\-Parameter sind in Lambda\-Ausdrücken nicht zulässig.  
  
-   Generische Parameter sind in Lambda\-Ausdrücken nicht zulässig.  
  
## Beispiel  
 Das folgende Beispiel zeigt einen Lambda\-Ausdruck, der einen Wert in die Konsole schreibt.  Dabei wird die Syntax für einzeilige und mehrzeilige Lambda\-Ausdrücke für eine Unterroutine veranschaulicht.  Weitere Beispiele finden Sie unter [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/vbvbalrlambdas/Class1.vb#15)]  
  
## Siehe auch  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)