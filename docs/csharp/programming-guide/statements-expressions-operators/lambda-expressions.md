---
title: Lambdaausdrücke – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 03/14/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: dd9b77a90030a96d17104c8c0e48964b6a85d165
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2019
ms.locfileid: "58125732"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="f9a56-102">Lambdaausdrücke (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f9a56-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="f9a56-103">Ein *Lambdaausdruck* ist ein Codeblock (bzw. ein Ausdrucks- oder ein Anweisungsblock), der wie ein Objekt behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="f9a56-103">A *lambda expression* is a block of code (an expression or a statement block) that is treated as an object.</span></span> <span data-ttu-id="f9a56-104">Er kann als Argument an eine Methode übergeben werden, und er kann auch von Methodenaufrufen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9a56-104">It can be passed as an argument to methods, and it can also be returned by method calls.</span></span> <span data-ttu-id="f9a56-105">Lambdaausdrücke finden bei folgenden Aktionen Anwendung:</span><span class="sxs-lookup"><span data-stu-id="f9a56-105">Lambda expressions are used extensively for:</span></span>

- <span data-ttu-id="f9a56-106">Bei der Übergabe von Code, der als asynchrone Methode ausgeführt wird, wie z.B. <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9a56-106">Passing the code that is to be executed to asynchronous methods, such as <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="f9a56-107">Bei [LINQ-Abfrageausdrücken](../../linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9a56-107">Writing [LINQ query expressions](../../linq/index.md).</span></span>

- <span data-ttu-id="f9a56-108">Bei Erstellen von [Ausdrucksbaumstrukturen](../concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9a56-108">Creating [expression trees](../concepts/expression-trees/index.md).</span></span>

<span data-ttu-id="f9a56-109">Lambdaausdrücke sind Code, der entweder als Delegat oder als eine Ausdrucksbaumstruktur repräsentiert werden kann, die an einen Delegat kompiliert.</span><span class="sxs-lookup"><span data-stu-id="f9a56-109">Lambda expressions are code that can be represented either as a delegate, or as an expression tree that compiles to a delegate.</span></span> <span data-ttu-id="f9a56-110">Der genaue Delegattyp eines Lambdaausdrucks hängt von dessen Parametern und Rückgabewert ab.</span><span class="sxs-lookup"><span data-stu-id="f9a56-110">The specific delegate type of a lambda expression depends on its parameters and return value.</span></span> <span data-ttu-id="f9a56-111">Lambdaausdrücke, die keinen Wert zurückgeben, korrespondieren mit einem bestimmten `Action`-Delegat, abhängig von der Anzahl seiner Parameter.</span><span class="sxs-lookup"><span data-stu-id="f9a56-111">Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="f9a56-112">Lambdaausdrücke, die keinen Wert zurückgeben, entsprechen einem bestimmten `Func`-Delegat, abhängig von der Anzahl seiner Parameter.</span><span class="sxs-lookup"><span data-stu-id="f9a56-112">Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="f9a56-113">Ein Lambdaausdruck, der beispielsweise zwei Parameter hat, aber keinen Wert zurückgibt, entspricht einem <xref:System.Action%602>-Delegat.</span><span class="sxs-lookup"><span data-stu-id="f9a56-113">For example, a lambda expression that has two parameters but returns no value corresponds to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="f9a56-114">Ein Lambdaausdruck, der beispielsweise zwei Parameter hat, aber keinen Wert zurückgibt, entspricht einem <xref:System.Func%602>-Delegat.</span><span class="sxs-lookup"><span data-stu-id="f9a56-114">A lambda expression that has one parameter and returns a value corresponds to <xref:System.Func%602> delegate.</span></span>

<span data-ttu-id="f9a56-115">Ein Lambdaausdruck verwendet `=>`, den [Lambdadeklarationsoperator](../../language-reference/operators/lambda-operator.md), um die Parameterliste des Lambdas von dessen ausführbarem Code zu trennen.</span><span class="sxs-lookup"><span data-stu-id="f9a56-115">A lambda expression uses `=>`, the [lambda declaration operator](../../language-reference/operators/lambda-operator.md), to separate the lambda's parameter list from its executable code.</span></span> <span data-ttu-id="f9a56-116">Zum Erstellen eines Lambdaausdrucks geben Sie Eingabeparameter (falls vorhanden) auf der linken Seite des Lambdaoperators an und stellen den Ausdrucks- oder Anweisungsblock auf die andere Seite.</span><span class="sxs-lookup"><span data-stu-id="f9a56-116">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="f9a56-117">Beispielsweise gibt der Einzelzeilen-Lambdaausdruck `x => x * x` einen Parameter an, der `x` heißt und das Quadrat des Werts von `x` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f9a56-117">For example, the single-line lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="f9a56-118">Dieser Ausdruck kann einem Delegattyp zuwiesen werden, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f9a56-118">You can assign this expression to a delegate type, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="f9a56-119">Sie können auch einen Lambdaausdruck einer Ausdrucksbaumstruktur zuweisen:</span><span class="sxs-lookup"><span data-stu-id="f9a56-119">You also can assign a lambda expression to an expression tree type:</span></span>

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="f9a56-120">Sie können ihn aber auch als Methodenargument übergeben:</span><span class="sxs-lookup"><span data-stu-id="f9a56-120">Or you can pass it directly as a method argument:</span></span>

[!code-csharp-interactive[lambda is argument](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="f9a56-121">Wenn Sie zum Aufrufen der <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType>-Methode in der <xref:System.Linq.Enumerable?displayProperty=nameWithType>-Klasse methodenbasierte Syntax verwenden (wie in LINQ to Objects und LINQ to XML), ist der Parameter ein Delegattyp <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9a56-121">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class (as you do in LINQ to Objects and LINQ to XML) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f9a56-122">Ein Lambda-Ausdruck ist die einfachste Möglichkeit zum Erstellen dieses Delegaten.</span><span class="sxs-lookup"><span data-stu-id="f9a56-122">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="f9a56-123">Wenn Sie die <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>-Methode in der <xref:System.Linq.Queryable?displayProperty=nameWithType>-Klasse aufrufen (wie in LINQ to SQL) ist der Parametertyp ein Ausdrucksbaumstruktur-Typ [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span><span class="sxs-lookup"><span data-stu-id="f9a56-123">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in LINQ to SQL) the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="f9a56-124">Wie gesagt, ein Lambda-Ausdruck ist eine sehr präzise Methode, diese Ausdrucksbaumstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9a56-124">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="f9a56-125">Durch die Lambdas können die `Select` -Aufrufe ähnlich aussehen, obwohl sich der mithilfe des Lambdas erstellte Objekttyp unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="f9a56-125">The lambdas allow the `Select` calls to look similar although in fact the type of object created from the lambda is different.</span></span>

<span data-ttu-id="f9a56-126">Alle Einschränkungen für [anonyme Methoden](anonymous-methods.md) gelten auch für Lambdaausdrücke.</span><span class="sxs-lookup"><span data-stu-id="f9a56-126">All restrictions that apply to [anonymous methods](anonymous-methods.md) also apply to lambda expressions.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="f9a56-127">Ausdruckslambdas</span><span class="sxs-lookup"><span data-stu-id="f9a56-127">Expression lambdas</span></span>

<span data-ttu-id="f9a56-128">Ein Lambdaausdruck mit einem Ausdruck auf der rechten Seite des `=>`-Operators wird als *Ausdruckslambda* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f9a56-128">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="f9a56-129">Ausdruckslambdas werden häufig bei der Erstellung von [Ausdrucksbaumstrukturen](../concepts/expression-trees/index.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9a56-129">Expression lambdas are used extensively in the construction of [expression trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="f9a56-130">Ein Ausdruckslambda gibt das Ergebnis des Ausdrucks zurück und hat folgende grundlegende Form:</span><span class="sxs-lookup"><span data-stu-id="f9a56-130">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="f9a56-131">Die Klammern sind nur optional, wenn das Lambda über einen Eingabeparameter verfügt; andernfalls sind sie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f9a56-131">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="f9a56-132">Geben Sie Eingabeparameter von 0 (null) mit leeren Klammern an:</span><span class="sxs-lookup"><span data-stu-id="f9a56-132">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="f9a56-133">Zwei oder mehr Eingabeparameter sind durch Kommas getrennt und in Klammern eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="f9a56-133">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="f9a56-134">Für den Compiler ist es manchmal unmöglich, die Eingabetypen abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="f9a56-134">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="f9a56-135">Sie können die Typen wie im folgenden Beispiel dargestellt explizit angeben:</span><span class="sxs-lookup"><span data-stu-id="f9a56-135">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="f9a56-136">Eingabeparametertypen müssen alle entweder explizit oder implizit sein. Andernfalls tritt der Compilerfehler [CS0748](../../misc/cs0748.md) auf.</span><span class="sxs-lookup"><span data-stu-id="f9a56-136">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="f9a56-137">Der Text eines Ausdruckslambdas kann aus einem Methodenaufruf bestehen.</span><span class="sxs-lookup"><span data-stu-id="f9a56-137">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="f9a56-138">Wenn Sie jedoch Ausdrucksbaumstrukturen erstellen, die außerhalb des Kontexts der .NET Common Language Runtime ausgewertet werden, z.B. in SQL Server, sollten Sie in Lambdaausdrücken keine Methodenaufrufe verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9a56-138">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="f9a56-139">Die Methoden haben außerhalb des Kontexts der .NET Common Language Runtime keine Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="f9a56-139">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="f9a56-140">Anweisungslambdas</span><span class="sxs-lookup"><span data-stu-id="f9a56-140">Statement lambdas</span></span>

<span data-ttu-id="f9a56-141">Ein Anweisungslambda ähnelt einem Ausdruckslambda, allerdings sind die Anweisungen in Klammern eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="f9a56-141">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { statement; }
```

<span data-ttu-id="f9a56-142">Der Text eines Anweisungslambdas kann aus einer beliebigen Anzahl von Anweisungen bestehen, wobei es sich meistens um höchstens zwei oder drei Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="f9a56-142">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="f9a56-143">Anweisungslambdas, wie anonyme Methoden, können nicht zum Erstellen von Ausdrucksbaumstrukturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9a56-143">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="f9a56-144">Asynchrone Lambdas</span><span class="sxs-lookup"><span data-stu-id="f9a56-144">Async lambdas</span></span>

<span data-ttu-id="f9a56-145">Sie können mit den Schlüsselwörtern [async](../../language-reference/keywords/async.md) und [await](../../language-reference/keywords/await.md) Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten, leicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9a56-145">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../language-reference/keywords/async.md) and [await](../../language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="f9a56-146">Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.</span><span class="sxs-lookup"><span data-stu-id="f9a56-146">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="f9a56-147">Sie können denselben Ereignishandler hinzufügen, indem Sie ein asynchrones Lambda verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9a56-147">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="f9a56-148">Um diesen Handler hinzuzufügen, fügen Sie einen `async`-Modifizierer vor der Lambdaparameterliste hinzu, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f9a56-148">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="f9a56-149">Weitere Informationen zum Erstellen und Verwenden von asynchronen Methoden finden Sie unter [Asynchronous programming with async and await (Asynchrones Programmieren mit „async“ and „await“)](../concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9a56-149">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="f9a56-150">Lambdaausdrücke und Tupel</span><span class="sxs-lookup"><span data-stu-id="f9a56-150">Lambda expressions and tuples</span></span>

<span data-ttu-id="f9a56-151">Ab C# 7.0 bietet die C#-Programmiersprache integrierte Unterstützung für [Tupel](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="f9a56-151">Starting with C# 7.0, the C# language provides built-in support for [tuples](../../tuples.md).</span></span> <span data-ttu-id="f9a56-152">Sie können ein Tupel einem Lambdaausdruck als Argument bereitstellen, und Ihr Lambdaausdruck kann ebenfalls einen Tupel zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f9a56-152">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="f9a56-153">In einigen Fällen verwendet der C#-Compiler den Typrückschluss, um den Typ der Tupelkomponenten zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f9a56-153">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="f9a56-154">Sie können ein Tupel definieren, indem Sie eine durch Trennzeichen getrennte Liste seiner Komponenten in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="f9a56-154">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="f9a56-155">In folgendem Beispiel wird ein Tupel mit drei Komponenten verwenden, um eine Zahlensequenz an einen Lambdaausdruck zu übergeben; dadurch wird jeder Wert verdoppelt, und es wird ein Tupel mit drei Komponenten zurückgegeben, das das Ergebnis der Multiplikation enthält.</span><span class="sxs-lookup"><span data-stu-id="f9a56-155">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="f9a56-156">Für gewöhnlich heißen die Felder eines Tupels `Item1`, `Item2`, usw. Sie können allerdings ein Tupel mit benannten Komponenten definieren, wie in folgendem Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f9a56-156">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="f9a56-157">Weitere Informationen zu C#-Tupeln finden Sie unter [C#-Tupeltypen](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="f9a56-157">For more information about C# tuples, see [C# tuple types](../../tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="f9a56-158">Lambdas mit Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="f9a56-158">Lambdas with the standard query operators</span></span>

<span data-ttu-id="f9a56-159">LINQ to Objects haben, neben anderen Implementierungen, einen Eingabeparameter, dessen Typ Teil der <xref:System.Func%601>-Familie generischer Delegate ist.</span><span class="sxs-lookup"><span data-stu-id="f9a56-159">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="f9a56-160">Diese Delegaten verwenden Typparameter zur Definition der Anzahl und des Typs der Eingabeparameter sowie des Rückgabetyps des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="f9a56-160">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="f9a56-161">`Func` -Delegaten sind für das Kapseln von benutzerdefinierten Ausdrücken, die für jedes Element in einem Satz von Quelldaten übernommen werden, sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="f9a56-161">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="f9a56-162">Betrachten Sie z.B. den <xref:System.Func%602>-Delegattyp:</span><span class="sxs-lookup"><span data-stu-id="f9a56-162">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="f9a56-163">Der Delegat kann als `Func<int, bool>`-Instanz instanziiert werden, wobei `int` ein Eingabeparameter und `bool` der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="f9a56-163">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="f9a56-164">Der Rückgabewert wird immer im letzten Typparameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="f9a56-164">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="f9a56-165">`Func<int, string, bool>` definiert z.B. einen Delegaten mit zwei Eingabeparametern, `int` und `string`, und einen Rückgabetyp von `bool`.</span><span class="sxs-lookup"><span data-stu-id="f9a56-165">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="f9a56-166">Der folgende `Func`-Delegat gibt bei einem Aufruf einen booleschen Wert zurück, um anzugeben, ob der Eingabeparameter gleich fünf ist:</span><span class="sxs-lookup"><span data-stu-id="f9a56-166">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="f9a56-167">Sie können einen Lambdaausdruck auch dann angeben, wenn der Argumenttyp <xref:System.Linq.Expressions.Expression%601> ist, beispielsweise in den Standardabfrageoperatoren, die in Typ <xref:System.Linq.Queryable> definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f9a56-167">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="f9a56-168">Wenn Sie ein <xref:System.Linq.Expressions.Expression%601>-Argument angeben, wird der Lambdaausdruck in eine Ausdrucksbaumstruktur kompiliert.</span><span class="sxs-lookup"><span data-stu-id="f9a56-168">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="f9a56-169">Im folgenden Beispiel wird der <xref:System.Linq.Enumerable.Count%2A>-Standardabfrageoperator verwendet:</span><span class="sxs-lookup"><span data-stu-id="f9a56-169">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="f9a56-170">Der Compiler kann den Typ des Eingabeparameters ableiten, Sie können ihn aber auch explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="f9a56-170">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="f9a56-171">Dieser bestimmte Lambda-Ausdruck zählt die ganzen Zahlen (`n`), bei denen nach dem Dividieren durch zwei als Rest 1 bleibt.</span><span class="sxs-lookup"><span data-stu-id="f9a56-171">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="f9a56-172">In folgendem Beispiel wird eine Sequenz erzeugt, die alle Elemente im Array `numbers` enthält, die vor der 9 auftreten, da dies die erste Zahl in der Sequenz ist, die die Bedingung nicht erfüllt:</span><span class="sxs-lookup"><span data-stu-id="f9a56-172">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="f9a56-173">In folgendem Beispiel wird gezeigt, wie Sie mehrere Eingabeparameter angeben, indem Sie sie in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="f9a56-173">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="f9a56-174">Mit der Methode werden alle Elemente im `numbers`-Array zurückgegeben, bis eine Zahl erreicht wird, deren Wert kleiner ist als ihre Ordnungspostion im Array:</span><span class="sxs-lookup"><span data-stu-id="f9a56-174">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="f9a56-175">Typrückschluss in Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="f9a56-175">Type inference in lambda expressions</span></span>

<span data-ttu-id="f9a56-176">Beim Schreiben von Lambdas müssen Sie oftmals keinen Typ für die Eingabeparameter angeben, da der Compiler den Typ auf der Grundlage des Lambdatexts, der Parametertypen und anderer Faktoren ableiten kann, wie in der C#-Programmiersprachenspezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9a56-176">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="f9a56-177">Bei den meisten Standardabfrageoperatoren entspricht die erste Eingabe dem Typ der Elemente in der Quellsequenz.</span><span class="sxs-lookup"><span data-stu-id="f9a56-177">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="f9a56-178">Beim Abfragen von `IEnumerable<Customer>` wird die Eingabevariable als `Customer`-Objekt abgeleitet, sodass Sie auf die zugehörigen Methoden und Eigenschaften zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="f9a56-178">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="f9a56-179">Die allgemeinen Regeln für Typrückschlüsse bei Lambdas lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f9a56-179">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="f9a56-180">Der Lambda-Ausdruck muss dieselbe Anzahl von Parametern enthalten wie der Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="f9a56-180">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="f9a56-181">Jeder Eingabeparameter im Lambda muss implizit in den entsprechenden Delegatparameter konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f9a56-181">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="f9a56-182">Der Rückgabewert des Lambdas (falls vorhanden) muss implizit in den Rückgabetyp des Delegaten konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f9a56-182">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="f9a56-183">Beachten Sie, dass Lambdaausdrücke keinen eigenen Typ haben, da das allgemeine Typsystem kein internes Konzept von „Lambdaausdrücken“ aufweist.</span><span class="sxs-lookup"><span data-stu-id="f9a56-183">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="f9a56-184">Es kann manchmal praktisch sein, informell vom „Typ“ eines Lambdaausdrucks zu sprechen.</span><span class="sxs-lookup"><span data-stu-id="f9a56-184">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="f9a56-185">In einem solchen Fall bezeichnet Typ den Delegattyp bzw. den <xref:System.Linq.Expressions.Expression> -Typ, in den der Lambda-Ausdruck konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="f9a56-185">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="f9a56-186">Variablenbereich in Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="f9a56-186">Variable scope in lambda expressions</span></span>

<span data-ttu-id="f9a56-187">Lambdas können auf *äußere Variablen* verweisen (siehe [Anonyme Methoden](anonymous-methods.md)), die im Bereich der Methode, mit der der Lambdaausdruck definiert wird, oder im Bereich des Typs liegen, der den Lambdaausdruck enthält.</span><span class="sxs-lookup"><span data-stu-id="f9a56-187">Lambdas can refer to *outer variables* (see [Anonymous methods](anonymous-methods.md)) that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="f9a56-188">Variablen, die auf diese Weise erfasst werden, werden zur Verwendung in Lambda-Ausdrücken gespeichert, auch wenn die Variablen andernfalls außerhalb des Gültigkeitsbereichs liegen und an die Garbage Collection übergeben würden.</span><span class="sxs-lookup"><span data-stu-id="f9a56-188">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="f9a56-189">Eine äußere Variable muss definitiv zugewiesen sein, bevor sie in einem Lambda-Ausdruck verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9a56-189">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="f9a56-190">Das folgende Beispiel veranschaulicht diese Regeln:</span><span class="sxs-lookup"><span data-stu-id="f9a56-190">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="f9a56-191">Die folgenden Regeln gelten für den Variablenbereich in Lambda-Ausdrücken:</span><span class="sxs-lookup"><span data-stu-id="f9a56-191">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="f9a56-192">Eine erfasste Variable wird erst dann an die Garbage Collection übergeben, wenn der darauf verweisende Delegat für die Garbage Collection geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="f9a56-192">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="f9a56-193">Variablen, die in einem Lambdaausdruck eingeführt wurden, sind in der einschließenden Methode nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f9a56-193">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="f9a56-194">Ein Lambdaausdruck kann einen [in](../../language-reference/keywords/in-parameter-modifier.md)-, [ref](../../language-reference/keywords/ref.md)- oder [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter nicht direkt von der einschließenden Methode erfassen.</span><span class="sxs-lookup"><span data-stu-id="f9a56-194">A lambda expression cannot directly capture an [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="f9a56-195">Eine [return](../../language-reference/keywords/return.md)-Anweisung in einem Lambdaausdruck bewirkt keine Rückgabe durch die einschließende Methode.</span><span class="sxs-lookup"><span data-stu-id="f9a56-195">A [return](../../language-reference/keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="f9a56-196">Ein Lambdaausdruck darf keine [goto](../../language-reference/keywords/goto.md)-, [break](../../language-reference/keywords/break.md)- oder [continue](../../language-reference/keywords/continue.md)-Anweisung enthalten, wenn das Ziel dieser Sprunganweisung außerhalb des Lambdaausdrucksblocks liegt.</span><span class="sxs-lookup"><span data-stu-id="f9a56-196">A lambda expression cannot contain a [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md), or [continue](../../language-reference/keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="f9a56-197">Eine Sprunganweisung darf auch nicht außerhalb des Lambdaausdrucksblocks sein, wenn das Ziel im Block ist.</span><span class="sxs-lookup"><span data-stu-id="f9a56-197">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f9a56-198">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f9a56-198">C# language specification</span></span>

<span data-ttu-id="f9a56-199">Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f9a56-199">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="f9a56-200">Enthaltenes Buchkapitel</span><span class="sxs-lookup"><span data-stu-id="f9a56-200">Featured book chapter</span></span>

<span data-ttu-id="f9a56-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegaten, Ereignisse und Lambda-Ausdrücke) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (C# 3.0-Cookbook, 3. Auflage: Mehr als 250 Lösungen für C# 3.0-Programmierer)</span><span class="sxs-lookup"><span data-stu-id="f9a56-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a56-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9a56-202">See also</span></span>

- [<span data-ttu-id="f9a56-203">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f9a56-203">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f9a56-204">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="f9a56-204">LINQ (Language-Integrated Query)</span></span>](../concepts/linq/index.md)
- [<span data-ttu-id="f9a56-205">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="f9a56-205">Anonymous Methods</span></span>](anonymous-methods.md)
- [<span data-ttu-id="f9a56-206">Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="f9a56-206">Expression Trees</span></span>](../concepts/expression-trees/index.md)
- [<span data-ttu-id="f9a56-207">Lokale Funktionen im Vergleich zu Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="f9a56-207">Local functions compared to lambda expressions</span></span>](../../local-functions-vs-lambdas.md)
- [<span data-ttu-id="f9a56-208">Implizit typisierte Lambdaausdrücke</span><span class="sxs-lookup"><span data-stu-id="f9a56-208">Implicitly typed lambda expressions</span></span>](../../implicitly-typed-lambda-expressions.md)
- [<span data-ttu-id="f9a56-209">Visual Studio 2008 C#-Beispiele (siehe LINQ-Beispielabfragedateien und XQuery-Programm)</span><span class="sxs-lookup"><span data-stu-id="f9a56-209">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="f9a56-210">Rekursive Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f9a56-210">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
