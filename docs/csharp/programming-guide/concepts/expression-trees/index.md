---
title: Ausdrucksbaumstrukturen (C#)
description: Erfahren Sie mehr zu Ausdrucksbaumstrukturen. Erfahren Sie, wie Code, der von diesen Datenstrukturen dargestellt wird, kompiliert und ausgeführt wird, wobei jeder Knoten einen Ausdruck darstellt.
ms.date: 07/20/2015
ms.assetid: 7d0ac21a-6d90-4e2e-8903-528cb78615b7
ms.openlocfilehash: 2fa8577dd945650edebf84459de10c0c3bd04225
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105573"
---
# <a name="expression-trees-c"></a><span data-ttu-id="3fcb0-104">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="3fcb0-104">Expression Trees (C#)</span></span>
<span data-ttu-id="3fcb0-105">Ausdrucksbaumstrukturen stellen Code in einer baumähnlichen Datenstruktur dar, in denen jeder Knoten ein Ausdruck ist, z. B. ein Methodenaufruf oder eine binäre Operation wie `x < y`.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-105">Expression trees represent code in a tree-like data structure, where each node is an expression, for example, a method call or a binary operation such as `x < y`.</span></span>  
  
 <span data-ttu-id="3fcb0-106">Sie können Code kompilieren und ausführen, der von Ausdrucksbaumstrukturen dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-106">You can compile and run code represented by expression trees.</span></span> <span data-ttu-id="3fcb0-107">Dies ermöglicht dynamische Änderungen des ausführbaren Codes, die Ausführung von LINQ-Abfragen in verschiedenen Datenbanken und die Erstellung von dynamischen Abfragen.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-107">This enables dynamic modification of executable code, the execution of LINQ queries in various databases, and the creation of dynamic queries.</span></span> <span data-ttu-id="3fcb0-108">Weitere Informationen zu Ausdrucksbaumstrukturen in LINQ finden Sie unter [Verwenden von Ausdrucksbaumstrukturen zum Erstellen von dynamischen Abfragen (C#)](./how-to-use-expression-trees-to-build-dynamic-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3fcb0-108">For more information about expression trees in LINQ, see [How to use expression trees to build dynamic queries (C#)](./how-to-use-expression-trees-to-build-dynamic-queries.md).</span></span>
  
 <span data-ttu-id="3fcb0-109">Ausdrucksbaumstrukturen werden auch in der Dynamic Language Runtime (DLR) verwendet, um Interoperabilität zwischen dynamischen Sprachen und .NET zu gewährleisten. Dies ermöglicht Entwicklern von Compilern, Ausdrucksbaumstrukturen anstelle der Microsoft Intermediate Language (MSIL) auszugeben.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-109">Expression trees are also used in the dynamic language runtime (DLR) to provide interoperability between dynamic languages and .NET and to enable compiler writers to emit expression trees instead of Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="3fcb0-110">Weitere Informationen zur DLR finden Sie unter [Übersicht über die Dynamic Language Runtime](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3fcb0-110">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
 <span data-ttu-id="3fcb0-111">Sie können den C#- oder Visual Basic-Compiler zur Erstellung einer Ausdrucksbaumstruktur veranlassen, basierend auf einem anonymen Lambda-Ausdruck oder Sie können Ausdrucksbaumstrukturen durch Verwendung des Namespace <xref:System.Linq.Expressions> manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-111">You can have the C# or Visual Basic compiler create an expression tree for you based on an anonymous lambda expression, or you can create expression trees manually by using the <xref:System.Linq.Expressions> namespace.</span></span>  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a><span data-ttu-id="3fcb0-112">Erstellen von Ausdrucksbaumstrukturen aus Lambda-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="3fcb0-112">Creating Expression Trees from Lambda Expressions</span></span>  
 <span data-ttu-id="3fcb0-113">Wenn ein Lambda-Ausdruck einer Variablen vom Typ <xref:System.Linq.Expressions.Expression%601> zugewiesen ist, gibt der Compiler Code aus, um eine Ausdrucksbaumstruktur zu erstellen, die den Lambda-Ausdruck verkörpert.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-113">When a lambda expression is assigned to a variable of type <xref:System.Linq.Expressions.Expression%601>, the compiler emits code to build an expression tree that represents the lambda expression.</span></span>  
  
 <span data-ttu-id="3fcb0-114">Der C#-Compiler kann Ausdrucksbaumstrukturen nur aus Ausdrucklambdas (oder einzeiligen Lambdas) erstellen.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-114">The C# compiler can generate expression trees only from expression lambdas (or single-line lambdas).</span></span> <span data-ttu-id="3fcb0-115">Es kann keine Anweisungslambdas (oder mehrzeiligen Lambdas) analysieren.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-115">It cannot parse statement lambdas (or multi-line lambdas).</span></span> <span data-ttu-id="3fcb0-116">Weitere Informationen zu Lambdaausdrücken in C# finden Sie unter [Lambdaausdrücke](../../statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3fcb0-116">For more information about lambda expressions in C#, see [Lambda Expressions](../../statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="3fcb0-117">In den folgenden Codebeispielen wird veranschaulicht, wie Sie C#-Compiler dazu veranlassen, eine Ausdrucksbaumstruktur zu erstellen, die den Lambdaausdruck `num => num < 5` verkörpert.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-117">The following code examples demonstrate how to have the C# compiler create an expression tree that represents the lambda expression `num => num < 5`.</span></span>  
  
```csharp  
Expression<Func<int, bool>> lambda = num => num < 5;  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a><span data-ttu-id="3fcb0-118">Erstellen von Ausdrucksbaumstrukturen mit der API</span><span class="sxs-lookup"><span data-stu-id="3fcb0-118">Creating Expression Trees by Using the API</span></span>  
 <span data-ttu-id="3fcb0-119">Verwenden Sie die Klasse <xref:System.Linq.Expressions.Expression>, um Ausdrucksbaumstrukturen mit der API zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-119">To create expression trees by using the API, use the <xref:System.Linq.Expressions.Expression> class.</span></span> <span data-ttu-id="3fcb0-120">Diese Klasse enthält statische Factorymethoden, die bestimmte Ausdrucksstruktur-Knotentypen erstellen können, z. B. <xref:System.Linq.Expressions.ParameterExpression>, der eine Variable oder einen Parameter darstellt oder <xref:System.Linq.Expressions.MethodCallExpression>, der einen Methodenaufruf darstellt.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-120">This class contains static factory methods that create expression tree nodes of specific types, for example, <xref:System.Linq.Expressions.ParameterExpression>, which represents a variable or parameter, or <xref:System.Linq.Expressions.MethodCallExpression>, which represents a method call.</span></span> <span data-ttu-id="3fcb0-121"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, und die anderen ausdrucksspezifischen Ausdrucksbaumstruktur-Typen werden auch im Namespace <xref:System.Linq.Expressions> definiert.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-121"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, and the other expression-specific types are also defined in the <xref:System.Linq.Expressions> namespace.</span></span> <span data-ttu-id="3fcb0-122">Diese Typen werden vom abstrakten Typ <xref:System.Linq.Expressions.Expression> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-122">These types derive from the abstract type <xref:System.Linq.Expressions.Expression>.</span></span>  
  
 <span data-ttu-id="3fcb0-123">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur erstellt wird, die den Lambdaausdruck `num => num < 5` mithilfe der API verkörpert.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-123">The following code example demonstrates how to create an expression tree that represents the lambda expression `num => num < 5` by using the API.</span></span>  
  
```csharp  
// Add the following using directive to your code file:  
// using System.Linq.Expressions;  
  
// Manually build the expression tree for
// the lambda expression num => num < 5.  
ParameterExpression numParam = Expression.Parameter(typeof(int), "num");  
ConstantExpression five = Expression.Constant(5, typeof(int));  
BinaryExpression numLessThanFive = Expression.LessThan(numParam, five);  
Expression<Func<int, bool>> lambda1 =  
    Expression.Lambda<Func<int, bool>>(  
        numLessThanFive,  
        new ParameterExpression[] { numParam });  
```  
  
 <span data-ttu-id="3fcb0-124">In .NET Framework 4 oder höher unterstützt die Ausdrucksbaumstruktur-API auch Zuweisungen und Ablaufsteuerungsausdrücke wie Schleifen, bedingte Blöcke und `try-catch`-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-124">In .NET Framework 4 or later, the expression trees API also supports assignments and control flow expressions such as loops, conditional blocks, and `try-catch` blocks.</span></span> <span data-ttu-id="3fcb0-125">Mithilfe der API können Sie Ausdrucksbaumstrukturen erstellen, die komplexer sind als diejenigen, die von Lambda-Ausdrücken vom C#-Compiler erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-125">By using the API, you can create expression trees that are more complex than those that can be created from lambda expressions by the C# compiler.</span></span> <span data-ttu-id="3fcb0-126">Im folgenden Beispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur erstellt wird, welche die Fakultät einer Zahl berechnet.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-126">The following example demonstrates how to create an expression tree that calculates the factorial of a number.</span></span>  
  
```csharp  
// Creating a parameter expression.  
ParameterExpression value = Expression.Parameter(typeof(int), "value");  
  
// Creating an expression to hold a local variable.
ParameterExpression result = Expression.Parameter(typeof(int), "result");  
  
// Creating a label to jump to from a loop.  
LabelTarget label = Expression.Label(typeof(int));  
  
// Creating a method body.  
BlockExpression block = Expression.Block(  
    // Adding a local variable.  
    new[] { result },  
    // Assigning a constant to a local variable: result = 1  
    Expression.Assign(result, Expression.Constant(1)),  
    // Adding a loop.  
        Expression.Loop(  
    // Adding a conditional block into the loop.  
           Expression.IfThenElse(  
    // Condition: value > 1  
               Expression.GreaterThan(value, Expression.Constant(1)),  
    // If true: result *= value --  
               Expression.MultiplyAssign(result,  
                   Expression.PostDecrementAssign(value)),  
    // If false, exit the loop and go to the label.  
               Expression.Break(label, result)  
           ),  
    // Label to jump to.  
       label  
    )  
);  
  
// Compile and execute an expression tree.  
int factorial = Expression.Lambda<Func<int, int>>(block, value).Compile()(5);  
  
Console.WriteLine(factorial);  
// Prints 120.  
```

<span data-ttu-id="3fcb0-127">Weitere Informationen finden Sie unter [Generating Dynamic Methods with Expression Trees in Visual Studio 2010 (Generieren dynamischer Methoden mit Ausdrucksbaumstrukturen in Visual Studio 2010)](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/). Dieser Artikel gilt auch für höhere Versionen von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-127">For more information, see [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/), which also applies to later versions of Visual Studio.</span></span>
  
## <a name="parsing-expression-trees"></a><span data-ttu-id="3fcb0-128">Analysieren von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="3fcb0-128">Parsing Expression Trees</span></span>  
 <span data-ttu-id="3fcb0-129">Im folgenden Codebeispiel wird veranschaulicht, wie die Ausdrucksbaumstruktur, die den Lambdaausdruck `num => num < 5` darstellt, in seine Bestandteile zerlegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-129">The following code example demonstrates how the expression tree that represents the lambda expression `num => num < 5` can be decomposed into its parts.</span></span>  
  
```csharp  
// Add the following using directive to your code file:  
// using System.Linq.Expressions;  
  
// Create an expression tree.  
Expression<Func<int, bool>> exprTree = num => num < 5;  
  
// Decompose the expression tree.  
ParameterExpression param = (ParameterExpression)exprTree.Parameters[0];  
BinaryExpression operation = (BinaryExpression)exprTree.Body;  
ParameterExpression left = (ParameterExpression)operation.Left;  
ConstantExpression right = (ConstantExpression)operation.Right;  
  
Console.WriteLine("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value);  
  
// This code produces the following output:  
  
// Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a><span data-ttu-id="3fcb0-130">Unveränderlichkeit von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="3fcb0-130">Immutability of Expression Trees</span></span>  
 <span data-ttu-id="3fcb0-131">Ausdrucksbaumstrukturen sollten unveränderlich sein.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-131">Expression trees should be immutable.</span></span> <span data-ttu-id="3fcb0-132">Das heißt, wenn Sie eine Ausdrucksbaumstruktur ändern möchten, müssen Sie einen neuen Knoten konstruieren, indem Sie einen vorhandenen Knoten kopieren und die enthaltenen Knoten ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-132">This means that if you want to modify an expression tree, you must construct a new expression tree by copying the existing one and replacing nodes in it.</span></span> <span data-ttu-id="3fcb0-133">Sie können einen Ausdrucksbaumstruktur-Besucher verwenden, um die vorhandene Ausdrucksbaumstruktur zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-133">You can use an expression tree visitor to traverse the existing expression tree.</span></span> <span data-ttu-id="3fcb0-134">Weitere Informationen finden Sie unter [Ändern von Ausdrucksbaumstrukturen (C#)](./how-to-modify-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="3fcb0-134">For more information, see [How to modify expression trees (C#)](./how-to-modify-expression-trees.md).</span></span>
  
## <a name="compiling-expression-trees"></a><span data-ttu-id="3fcb0-135">Kompilieren von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="3fcb0-135">Compiling Expression Trees</span></span>  
 <span data-ttu-id="3fcb0-136">Der Typ <xref:System.Linq.Expressions.Expression%601> bietet die Methode <xref:System.Linq.Expressions.Expression%601.Compile%2A>, welche den durch eine Ausdrucksbaumstruktur dargestellten Code in einen ausführbaren Delegaten kompiliert.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-136">The <xref:System.Linq.Expressions.Expression%601> type provides the <xref:System.Linq.Expressions.Expression%601.Compile%2A> method that compiles the code represented by an expression tree into an executable delegate.</span></span>  
  
 <span data-ttu-id="3fcb0-137">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur kompiliert und der daraus resultierende Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3fcb0-137">The following code example demonstrates how to compile an expression tree and run the resulting code.</span></span>  
  
```csharp  
// Creating an expression tree.  
Expression<Func<int, bool>> expr = num => num < 5;  
  
// Compiling the expression tree into a delegate.  
Func<int, bool> result = expr.Compile();  
  
// Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4));  
  
// Prints True.  
  
// You can also use simplified syntax  
// to compile and run an expression tree.  
// The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4));  
  
// Also prints True.  
```  
  
 <span data-ttu-id="3fcb0-138">Weitere Informationen finden Sie unter [ Ausführen von Ausdrucksbaumstrukturen (C#)](./how-to-execute-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="3fcb0-138">For more information, see [How to execute expression trees (C#)](./how-to-execute-expression-trees.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3fcb0-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fcb0-139">See also</span></span>

- <xref:System.Linq.Expressions>
- [<span data-ttu-id="3fcb0-140">Ausführen von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="3fcb0-140">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="3fcb0-141">Ändern von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="3fcb0-141">How to modify expression trees (C#)</span></span>](./how-to-modify-expression-trees.md)
- [<span data-ttu-id="3fcb0-142">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3fcb0-142">Lambda Expressions</span></span>](../../statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="3fcb0-143">Übersicht über die Dynamic Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3fcb0-143">Dynamic Language Runtime Overview</span></span>](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [<span data-ttu-id="3fcb0-144">Programmierkonzepte (C#)</span><span class="sxs-lookup"><span data-stu-id="3fcb0-144">Programming Concepts (C#)</span></span>](../index.md)
