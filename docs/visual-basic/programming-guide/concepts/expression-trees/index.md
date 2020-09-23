---
title: Ausdrucksbaumstrukturen
ms.date: 07/20/2015
ms.assetid: 8bbbb02d-7ffc-476b-8c25-118d82bf5d46
ms.openlocfilehash: 29f2545a3bc1d53e8ab28478f63ef7b0dfe7a15e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075407"
---
# <a name="expression-trees-visual-basic"></a><span data-ttu-id="0f554-102">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f554-102">Expression Trees (Visual Basic)</span></span>

<span data-ttu-id="0f554-103">Ausdrucksbaumstrukturen stellen Code in einer baumähnlichen Datenstruktur dar, in denen jeder Knoten ein Ausdruck ist, z. B. ein Methodenaufruf oder eine binäre Operation wie `x < y`.</span><span class="sxs-lookup"><span data-stu-id="0f554-103">Expression trees represent code in a tree-like data structure, where each node is an expression, for example, a method call or a binary operation such as `x < y`.</span></span>  
  
 <span data-ttu-id="0f554-104">Sie können Code kompilieren und ausführen, der von Ausdrucksbaumstrukturen dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0f554-104">You can compile and run code represented by expression trees.</span></span> <span data-ttu-id="0f554-105">Dies ermöglicht dynamische Änderungen des ausführbaren Codes, die Ausführung von LINQ-Abfragen in verschiedenen Datenbanken und die Erstellung von dynamischen Abfragen.</span><span class="sxs-lookup"><span data-stu-id="0f554-105">This enables dynamic modification of executable code, the execution of LINQ queries in various databases, and the creation of dynamic queries.</span></span> <span data-ttu-id="0f554-106">Weitere Informationen zu Ausdrucksbaumstrukturen in LINQ finden Sie unter [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic) (Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen von dynamischen Abfragen (Visual Basic))](how-to-use-expression-trees-to-build-dynamic-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0f554-106">For more information about expression trees in LINQ, see [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](how-to-use-expression-trees-to-build-dynamic-queries.md).</span></span>  
  
 <span data-ttu-id="0f554-107">Ausdrucksbaumstrukturen werden auch in der Dynamic Language Runtime (DLR) verwendet, um Interoperabilität zwischen dynamischen Sprachen und dem .NET-Framework zu gewährleisten und ermöglicht Entwicklern von Compilern, Ausdrucksbaumstrukturen anstelle der Microsoft Intermediate Language (MSIL) auszugeben.</span><span class="sxs-lookup"><span data-stu-id="0f554-107">Expression trees are also used in the dynamic language runtime (DLR) to provide interoperability between dynamic languages and the .NET Framework and to enable compiler writers to emit expression trees instead of Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="0f554-108">Weitere Informationen zur DLR finden Sie unter [Übersicht über die Dynamic Language Runtime](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f554-108">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
 <span data-ttu-id="0f554-109">Sie können den C#- oder Visual Basic-Compiler zur Erstellung einer Ausdrucksbaumstruktur veranlassen, basierend auf einem anonymen Lambda-Ausdruck oder Sie können Ausdrucksbaumstrukturen durch Verwendung des Namespace <xref:System.Linq.Expressions> manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f554-109">You can have the C# or Visual Basic compiler create an expression tree for you based on an anonymous lambda expression, or you can create expression trees manually by using the <xref:System.Linq.Expressions> namespace.</span></span>  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a><span data-ttu-id="0f554-110">Erstellen von Ausdrucksbaumstrukturen aus Lambda-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="0f554-110">Creating Expression Trees from Lambda Expressions</span></span>  

 <span data-ttu-id="0f554-111">Wenn ein Lambda-Ausdruck einer Variablen vom Typ <xref:System.Linq.Expressions.Expression%601> zugewiesen ist, gibt der Compiler Code aus, um eine Ausdrucksbaumstruktur zu erstellen, die den Lambda-Ausdruck verkörpert.</span><span class="sxs-lookup"><span data-stu-id="0f554-111">When a lambda expression is assigned to a variable of type <xref:System.Linq.Expressions.Expression%601>, the compiler emits code to build an expression tree that represents the lambda expression.</span></span>  
  
 <span data-ttu-id="0f554-112">Der Visual Basic-Compiler kann Ausdrucksbaumstrukturen nur aus Ausdrucklambdas (oder einzeiligen Lambdas) erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f554-112">The Visual Basic compiler can generate expression trees only from expression lambdas (or single-line lambdas).</span></span> <span data-ttu-id="0f554-113">Es kann keine Anweisungslambdas (oder mehrzeiligen Lambdas) analysieren.</span><span class="sxs-lookup"><span data-stu-id="0f554-113">It cannot parse statement lambdas (or multi-line lambdas).</span></span> <span data-ttu-id="0f554-114">Weitere Informationen zu Lambdaausdrücken in Visual Basic finden Sie unter [Lambdaausdrücke](../../language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0f554-114">For more information about lambda expressions in Visual Basic, see [Lambda Expressions](../../language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="0f554-115">In den folgenden Codebeispielen wird veranschaulicht, wie Sie den Visual Basic-Compiler dazu veranlassen, eine Ausdrucksbaumstruktur zu erstellen, die den Lambdaausdruck `Function(num) num < 5` verkörpert.</span><span class="sxs-lookup"><span data-stu-id="0f554-115">The following code examples demonstrate how to have the Visual Basic compiler create an expression tree that represents the lambda expression `Function(num) num < 5`.</span></span>  
  
```vb  
Dim lambda As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a><span data-ttu-id="0f554-116">Erstellen von Ausdrucksbaumstrukturen mit der API</span><span class="sxs-lookup"><span data-stu-id="0f554-116">Creating Expression Trees by Using the API</span></span>  

 <span data-ttu-id="0f554-117">Verwenden Sie die Klasse <xref:System.Linq.Expressions.Expression>, um Ausdrucksbaumstrukturen mit der API zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f554-117">To create expression trees by using the API, use the <xref:System.Linq.Expressions.Expression> class.</span></span> <span data-ttu-id="0f554-118">Diese Klasse enthält statische Factorymethoden, die bestimmte Ausdrucksstruktur-Knotentypen erstellen können, z. B. <xref:System.Linq.Expressions.ParameterExpression>, der eine Variable oder einen Parameter darstellt oder <xref:System.Linq.Expressions.MethodCallExpression>, der einen Methodenaufruf darstellt.</span><span class="sxs-lookup"><span data-stu-id="0f554-118">This class contains static factory methods that create expression tree nodes of specific types, for example, <xref:System.Linq.Expressions.ParameterExpression>, which represents a variable or parameter, or <xref:System.Linq.Expressions.MethodCallExpression>, which represents a method call.</span></span> <span data-ttu-id="0f554-119"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, und die anderen ausdrucksspezifischen Ausdrucksbaumstruktur-Typen werden auch im Namespace <xref:System.Linq.Expressions> definiert.</span><span class="sxs-lookup"><span data-stu-id="0f554-119"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, and the other expression-specific types are also defined in the <xref:System.Linq.Expressions> namespace.</span></span> <span data-ttu-id="0f554-120">Diese Typen werden vom abstrakten Typ <xref:System.Linq.Expressions.Expression> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="0f554-120">These types derive from the abstract type <xref:System.Linq.Expressions.Expression>.</span></span>  
  
 <span data-ttu-id="0f554-121">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur erstellt wird, die den Lambdaausdruck `Function(num) num < 5` mithilfe der API verkörpert.</span><span class="sxs-lookup"><span data-stu-id="0f554-121">The following code example demonstrates how to create an expression tree that represents the lambda expression `Function(num) num < 5` by using the API.</span></span>  
  
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
  
 <span data-ttu-id="0f554-122">In .NET Framework 4 oder höher unterstützt die Ausdrucksbaumstruktur-API auch Zuweisungen und Ablaufsteuerungsausdrücke wie Schleifen, bedingte Blöcke und `try-catch`-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="0f554-122">In .NET Framework 4 or later, the expression trees API also supports assignments and control flow expressions such as loops, conditional blocks, and `try-catch` blocks.</span></span> <span data-ttu-id="0f554-123">Mithilfe der API können Sie Ausdrucksbaumstrukturen erstellen, die komplexer sind als diejenigen, die von Lambdaausdrücken vom Visual Basic-Compiler erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0f554-123">By using the API, you can create expression trees that are more complex than those that can be created from lambda expressions by the Visual Basic compiler.</span></span> <span data-ttu-id="0f554-124">Im folgenden Beispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur erstellt wird, welche die Fakultät einer Zahl berechnet.</span><span class="sxs-lookup"><span data-stu-id="0f554-124">The following example demonstrates how to create an expression tree that calculates the factorial of a number.</span></span>  
  
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

<span data-ttu-id="0f554-125">Weitere Informationen finden Sie unter [Generating Dynamic Methods with Expression Trees in Visual Studio 2010 (Generieren dynamischer Methoden mit Ausdrucksbaumstrukturen in Visual Studio 2010)](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/). Dieser Artikel gilt auch für höhere Versionen von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f554-125">For more information, see [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/), which also applies to later versions of Visual Studio.</span></span>
  
## <a name="parsing-expression-trees"></a><span data-ttu-id="0f554-126">Analysieren von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="0f554-126">Parsing Expression Trees</span></span>  

 <span data-ttu-id="0f554-127">Im folgenden Codebeispiel wird veranschaulicht, wie die Ausdrucksbaumstruktur, die den Lambdaausdruck `Function(num) num < 5` darstellt, in seine Bestandteile zerlegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f554-127">The following code example demonstrates how the expression tree that represents the lambda expression `Function(num) num < 5` can be decomposed into its parts.</span></span>  
  
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
  
## <a name="immutability-of-expression-trees"></a><span data-ttu-id="0f554-128">Unveränderlichkeit von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="0f554-128">Immutability of Expression Trees</span></span>  

 <span data-ttu-id="0f554-129">Ausdrucksbaumstrukturen sollten unveränderlich sein.</span><span class="sxs-lookup"><span data-stu-id="0f554-129">Expression trees should be immutable.</span></span> <span data-ttu-id="0f554-130">Das heißt, wenn Sie eine Ausdrucksbaumstruktur ändern möchten, müssen Sie einen neuen Knoten konstruieren, indem Sie einen vorhandenen Knoten kopieren und die enthaltenen Knoten ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0f554-130">This means that if you want to modify an expression tree, you must construct a new expression tree by copying the existing one and replacing nodes in it.</span></span> <span data-ttu-id="0f554-131">Sie können einen Ausdrucksbaumstruktur-Besucher verwenden, um die vorhandene Ausdrucksbaumstruktur zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="0f554-131">You can use an expression tree visitor to traverse the existing expression tree.</span></span> <span data-ttu-id="0f554-132">Weitere Informationen finden Sie unter [How to: Modify Expression Trees (Visual Basic) (Vorgehensweise: Bearbeiten von Ausdrucksbaumstrukturen (Visual Basic))](how-to-modify-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="0f554-132">For more information, see [How to: Modify Expression Trees (Visual Basic)](how-to-modify-expression-trees.md).</span></span>  
  
## <a name="compiling-expression-trees"></a><span data-ttu-id="0f554-133">Kompilieren von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="0f554-133">Compiling Expression Trees</span></span>  

 <span data-ttu-id="0f554-134">Der Typ <xref:System.Linq.Expressions.Expression%601> bietet die Methode <xref:System.Linq.Expressions.Expression%601.Compile%2A>, welche den durch eine Ausdrucksbaumstruktur dargestellten Code in einen ausführbaren Delegaten kompiliert.</span><span class="sxs-lookup"><span data-stu-id="0f554-134">The <xref:System.Linq.Expressions.Expression%601> type provides the <xref:System.Linq.Expressions.Expression%601.Compile%2A> method that compiles the code represented by an expression tree into an executable delegate.</span></span>  
  
 <span data-ttu-id="0f554-135">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur kompiliert und der daraus resultierende Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0f554-135">The following code example demonstrates how to compile an expression tree and run the resulting code.</span></span>  
  
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
  
 <span data-ttu-id="0f554-136">Weitere Informationen finden Sie unter [How to: Execute Expression Trees (Visual Basic) (Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (Visual Basic))](how-to-execute-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="0f554-136">For more information, see [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f554-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f554-137">See also</span></span>

- <xref:System.Linq.Expressions>
- [<span data-ttu-id="0f554-138">How to: Execute Expression Trees (Visual Basic) (Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="0f554-138">How to: Execute Expression Trees (Visual Basic)</span></span>](how-to-execute-expression-trees.md)
- [<span data-ttu-id="0f554-139">How to: Modify Expression Trees (Visual Basic) (Vorgehensweise: Bearbeiten von Audrucksbaumstrukturen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="0f554-139">How to: Modify Expression Trees (Visual Basic)</span></span>](how-to-modify-expression-trees.md)
- [<span data-ttu-id="0f554-140">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0f554-140">Lambda Expressions</span></span>](../../language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="0f554-141">Übersicht über die Dynamic Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0f554-141">Dynamic Language Runtime Overview</span></span>](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [<span data-ttu-id="0f554-142">Programmier Konzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f554-142">Programming Concepts (Visual Basic)</span></span>](../index.md)
