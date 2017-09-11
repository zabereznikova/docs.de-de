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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4cc2c9890c1f5efbc4036d94eef1adb05094ae40
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-execute-expression-trees-visual-basic"></a><span data-ttu-id="29064-102">Gewusst wie: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29064-102">How to: Execute Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="29064-103">In diesem Thema erfahren Sie, wie eine Ausdrucksbaumstruktur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="29064-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="29064-104">Ausführen einer Ausdrucksbaumstruktur kann einen Wert zurückgeben, oder es kann nur eine Aktion, z. B. das Aufrufen einer Methode ausführen.</span><span class="sxs-lookup"><span data-stu-id="29064-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="29064-105">Nur Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="29064-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="29064-106">Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, sind vom Typ <xref:System.Linq.Expressions.LambdaExpression>oder <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="29064-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="29064-107">Um diese Ausdrucksbaumstrukturen auszuführen, rufen Sie die <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>Methode, um einen ausführbaren Delegaten erstellen und das Delegat dann aufzurufen.</xref:System.Linq.Expressions.LambdaExpression.Compile%2A></span><span class="sxs-lookup"><span data-stu-id="29064-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29064-108">Wenn der Typ des Delegaten nicht bekannt ist, d. h., der Lambda-Ausdruck ist vom Typ <xref:System.Linq.Expressions.LambdaExpression>und nicht <xref:System.Linq.Expressions.Expression%601>, müssen Sie aufrufen, die <xref:System.Delegate.DynamicInvoke%2A>Methode für den Delegaten statt direkt aufzurufen.</xref:System.Delegate.DynamicInvoke%2A> </xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="29064-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="29064-109">Wenn eine Ausdrucksbaumstruktur keinen Lambda-Ausdruck darstellt, können, erstellen Sie einen neue Lambda-Ausdruck mit die ursprüngliche Ausdrucksbaumstruktur als Text enthält, durch Aufrufen der <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>-Methode.</xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29></span><span class="sxs-lookup"><span data-stu-id="29064-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="29064-110">Anschließend können Sie den Lambda-Ausdruck ausführen, wie weiter oben in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29064-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29064-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29064-111">Example</span></span>  
 <span data-ttu-id="29064-112">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur ausgeführt wird, das Potenzieren einer Zahl mit einem Exponenten, indem ein Lambdaausdruck erstellt und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="29064-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="29064-113">Das Ergebnis, das die Zahl darstellt, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29064-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="29064-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="29064-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="29064-115">Fügen Sie einen Projektverweis auf System.Core.dll hinzu, wenn es nicht bereits verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="29064-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="29064-116">Schließen Sie den System.Linq.Expressions-Namespace.</span><span class="sxs-lookup"><span data-stu-id="29064-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29064-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29064-117">See Also</span></span>  
 <span data-ttu-id="29064-118">[Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="29064-118">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="29064-119"> [Gewusst wie: Ändern von Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="29064-119"> [How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span></span>
