---
title: Ausdrucksbaumstrukturen
ms.date: 07/20/2015
ms.assetid: 8bbbb02d-7ffc-476b-8c25-118d82bf5d46
ms.openlocfilehash: 4ca3b56f48368e465560fc5edd60c0df8dd4e1c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344705"
---
# <a name="expression-trees-visual-basic"></a>Ausdrucksbaumstrukturen (Visual Basic)
Ausdrucksbaumstrukturen stellen Code in einer baumähnlichen Datenstruktur dar, in denen jeder Knoten ein Ausdruck ist, z. B. ein Methodenaufruf oder eine binäre Operation wie `x < y`.  
  
 Sie können Code kompilieren und ausführen, der von Ausdrucksbaumstrukturen dargestellt wird. Dies ermöglicht dynamische Änderungen des ausführbaren Codes, die Ausführung von LINQ-Abfragen in verschiedenen Datenbanken und die Erstellung von dynamischen Abfragen. Weitere Informationen zu Ausdrucksbaumstrukturen in LINQ finden Sie unter [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic) (Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen von dynamischen Abfragen (Visual Basic))](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md).  
  
 Ausdrucksbaumstrukturen werden auch in der Dynamic Language Runtime (DLR) verwendet, um Interoperabilität zwischen dynamischen Sprachen und dem .NET-Framework zu gewährleisten und ermöglicht Entwicklern von Compilern, Ausdrucksbaumstrukturen anstelle der Microsoft Intermediate Language (MSIL) auszugeben. Weitere Informationen zur DLR finden Sie unter [Übersicht über die Dynamic Language Runtime](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).  
  
 Sie können den C#- oder Visual Basic-Compiler zur Erstellung einer Ausdrucksbaumstruktur veranlassen, basierend auf einem anonymen Lambda-Ausdruck oder Sie können Ausdrucksbaumstrukturen durch Verwendung des Namespace <xref:System.Linq.Expressions> manuell erstellen.  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a>Erstellen von Ausdrucksbaumstrukturen aus Lambda-Ausdrücken  
 Wenn ein Lambda-Ausdruck einer Variablen vom Typ <xref:System.Linq.Expressions.Expression%601> zugewiesen ist, gibt der Compiler Code aus, um eine Ausdrucksbaumstruktur zu erstellen, die den Lambda-Ausdruck verkörpert.  
  
 Der Visual Basic-Compiler kann Ausdrucksbaumstrukturen nur aus Ausdrucklambdas (oder einzeiligen Lambdas) erstellen. Es kann keine Anweisungslambdas (oder mehrzeiligen Lambdas) analysieren. Weitere Informationen zu Lambdaausdrücken in Visual Basic finden Sie unter [Lambdaausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 In den folgenden Codebeispielen wird veranschaulicht, wie Sie den Visual Basic-Compiler dazu veranlassen, eine Ausdrucksbaumstruktur zu erstellen, die den Lambdaausdruck `Function(num) num < 5` verkörpert.  
  
```vb  
Dim lambda As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a>Erstellen von Ausdrucksbaumstrukturen mit der API  
 Verwenden Sie die Klasse <xref:System.Linq.Expressions.Expression>, um Ausdrucksbaumstrukturen mit der API zu erstellen. Diese Klasse enthält statische Factorymethoden, die bestimmte Ausdrucksstruktur-Knotentypen erstellen können, z. B. <xref:System.Linq.Expressions.ParameterExpression>, der eine Variable oder einen Parameter darstellt oder <xref:System.Linq.Expressions.MethodCallExpression>, der einen Methodenaufruf darstellt. <xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, und die anderen ausdrucksspezifischen Ausdrucksbaumstruktur-Typen werden auch im Namespace <xref:System.Linq.Expressions> definiert. Diese Typen werden vom abstrakten Typ <xref:System.Linq.Expressions.Expression> abgeleitet.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur erstellt wird, die den Lambdaausdruck `Function(num) num < 5` mithilfe der API verkörpert.  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Manually build the expression tree for the lambda expression num => num < 5.  
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")  
Dim five As ConstantExpression = Expression.Constant(5, GetType(Integer))  
Dim numLessThanFive As BinaryExpression = Expression.LessThan(numParam, five)  
Dim lambda1 As Expression(Of Func(Of Integer, Boolean)) =  
  Expression.Lambda(Of Func(Of Integer, Boolean))(  
        numLessThanFive,  
        New ParameterExpression() {numParam})  
```  
  
 In .NET Framework 4 oder höher unterstützt die Ausdrucksbaumstruktur-API auch Zuweisungen und Ablaufsteuerungsausdrücke wie Schleifen, bedingte Blöcke und `try-catch`-Blöcke. Mithilfe der API können Sie Ausdrucksbaumstrukturen erstellen, die komplexer sind als diejenigen, die von Lambdaausdrücken vom Visual Basic-Compiler erstellt werden. Im folgenden Beispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur erstellt wird, welche die Fakultät einer Zahl berechnet.  
  
```vb  
' Creating a parameter expression.  
Dim value As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "value")  
  
' Creating an expression to hold a local variable.   
Dim result As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "result")  
  
' Creating a label to jump to from a loop.  
Dim label As LabelTarget = Expression.Label(GetType(Integer))  
  
' Creating a method body.  
Dim block As BlockExpression = Expression.Block(  
    New ParameterExpression() {result},  
    Expression.Assign(result, Expression.Constant(1)),  
    Expression.Loop(  
        Expression.IfThenElse(  
            Expression.GreaterThan(value, Expression.Constant(1)),  
            Expression.MultiplyAssign(result,  
                Expression.PostDecrementAssign(value)),  
            Expression.Break(label, result)  
        ),  
        label  
    )  
)  
  
' Compile an expression tree and return a delegate.  
Dim factorial As Integer =  
    Expression.Lambda(Of Func(Of Integer, Integer))(block, value).Compile()(5)  
  
Console.WriteLine(factorial)  
' Prints 120.  
```

Weitere Informationen finden Sie unter [Generating Dynamic Methods with Expression Trees in Visual Studio 2010 (Generieren dynamischer Methoden mit Ausdrucksbaumstrukturen in Visual Studio 2010)](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/). Dieser Artikel gilt auch für höhere Versionen von Visual Studio.
  
## <a name="parsing-expression-trees"></a>Analysieren von Ausdrucksbaumstrukturen  
 Im folgenden Codebeispiel wird veranschaulicht, wie die Ausdrucksbaumstruktur, die den Lambdaausdruck `Function(num) num < 5` darstellt, in seine Bestandteile zerlegt werden kann.  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Create an expression tree.  
Dim exprTree As Expression(Of Func(Of Integer, Boolean)) = Function(num) num < 5  
  
' Decompose the expression tree.  
Dim param As ParameterExpression = exprTree.Parameters(0)  
Dim operation As BinaryExpression = exprTree.Body  
Dim left As ParameterExpression = operation.Left  
Dim right As ConstantExpression = operation.Right  
  
Console.WriteLine(String.Format("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value))  
  
' This code produces the following output:  
'  
' Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a>Unveränderlichkeit von Ausdrucksbaumstrukturen  
 Ausdrucksbaumstrukturen sollten unveränderlich sein. Das heißt, wenn Sie eine Ausdrucksbaumstruktur ändern möchten, müssen Sie einen neuen Knoten konstruieren, indem Sie einen vorhandenen Knoten kopieren und die enthaltenen Knoten ersetzen. Sie können einen Ausdrucksbaumstruktur-Besucher verwenden, um die vorhandene Ausdrucksbaumstruktur zu durchlaufen. Weitere Informationen finden Sie unter [How to: Modify Expression Trees (Visual Basic) (Vorgehensweise: Bearbeiten von Ausdrucksbaumstrukturen (Visual Basic))](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md).  
  
## <a name="compiling-expression-trees"></a>Kompilieren von Ausdrucksbaumstrukturen  
 Der Typ <xref:System.Linq.Expressions.Expression%601> bietet die Methode <xref:System.Linq.Expressions.Expression%601.Compile%2A>, welche den durch eine Ausdrucksbaumstruktur dargestellten Code in einen ausführbaren Delegaten kompiliert.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur kompiliert und der daraus resultierende Code ausgeführt wird.  
  
```vb  
' Creating an expression tree.  
Dim expr As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
  
' Compiling the expression tree into a delegate.  
Dim result As Func(Of Integer, Boolean) = expr.Compile()  
  
' Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4))  
  
' Prints True.  
  
' You can also use simplified syntax  
' to compile and run an expression tree.  
' The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4))  
  
' Also prints True.  
```  
  
 Weitere Informationen finden Sie unter [How to: Execute Expression Trees (Visual Basic) (Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (Visual Basic))](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Expressions>
- [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
- [Lambda-Ausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Übersicht über die Dynamic Language Runtime](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [Programming Concepts (Visual Basic) (Programmierkonzepte (Visual Basic))](../../../../visual-basic/programming-guide/concepts/index.md)
