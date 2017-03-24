---
title: "Gewusst wie: Ausführen von Ausdrucksbaumstrukturen (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e12c45b417310f097d597561b2652ee793a4b2c0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-execute-expression-trees-visual-basic"></a>Gewusst wie: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)
In diesem Thema erfahren Sie, wie eine Ausdrucksbaumstruktur ausgeführt wird. Ausführen einer Ausdrucksbaumstruktur kann einen Wert zurückgeben, oder es kann nur eine Aktion, z. B. das Aufrufen einer Methode ausführen.  
  
 Nur Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, können ausgeführt werden. Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, sind vom Typ <xref:System.Linq.Expressions.LambdaExpression>oder <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression> Um diese Ausdrucksbaumstrukturen auszuführen, rufen Sie die <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>Methode, um einen ausführbaren Delegaten erstellen und das Delegat dann aufzurufen.</xref:System.Linq.Expressions.LambdaExpression.Compile%2A>  
  
> [!NOTE]
>  Wenn der Typ des Delegaten nicht bekannt ist, d. h., der Lambda-Ausdruck ist vom Typ <xref:System.Linq.Expressions.LambdaExpression>und nicht <xref:System.Linq.Expressions.Expression%601>, müssen Sie aufrufen, die <xref:System.Delegate.DynamicInvoke%2A>Methode für den Delegaten statt direkt aufzurufen.</xref:System.Delegate.DynamicInvoke%2A> </xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression>  
  
 Wenn eine Ausdrucksbaumstruktur keinen Lambda-Ausdruck darstellt, können, erstellen Sie einen neue Lambda-Ausdruck mit die ursprüngliche Ausdrucksbaumstruktur als Text enthält, durch Aufrufen der <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>-Methode.</xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> Anschließend können Sie den Lambda-Ausdruck ausführen, wie weiter oben in diesem Abschnitt beschrieben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur ausgeführt wird, das Potenzieren einer Zahl mit einem Exponenten, indem ein Lambdaausdruck erstellt und ausgeführt wird. Das Ergebnis, das die Zahl darstellt, wird angezeigt.  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Fügen Sie einen Projektverweis auf System.Core.dll hinzu, wenn es nicht bereits verwiesen wird.  
  
-   Schließen Sie den System.Linq.Expressions-Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Gewusst wie: Ändern von Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
