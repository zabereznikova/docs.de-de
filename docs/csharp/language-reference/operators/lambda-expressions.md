---
title: 'C#-Referenz: Lambdaausdrücke'
description: Erfahren Sie mehr über Lambdaausdrücke. Es gibt Ausdruckslambdas, deren Text ein Ausdruck ist, und Anweisungslambdas, deren Text eine Anweisung ist.
ms.date: 09/25/2020
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: 51bf44af5ec3478f2b2557b047df270c0c22990d
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94556841"
---
# <a name="lambda-expressions-c-reference"></a><span data-ttu-id="c154d-104">Lambdaausdrücke (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c154d-104">Lambda expressions (C# reference)</span></span>

<span data-ttu-id="c154d-105">Ein *Lambdaausdruck* ist ein Ausdruck in einer der beiden folgenden Formen:</span><span class="sxs-lookup"><span data-stu-id="c154d-105">A *lambda expression* is an expression of any of the following two forms:</span></span>

- <span data-ttu-id="c154d-106">Ein [Ausdruckslambda](#expression-lambdas) mit einem Ausdruck als Text:</span><span class="sxs-lookup"><span data-stu-id="c154d-106">[Expression lambda](#expression-lambdas) that has an expression as its body:</span></span>

  ```csharp
  (input-parameters) => expression
  ```

- <span data-ttu-id="c154d-107">Ein [Anweisungslambda](#statement-lambdas) mit einem Anweisungsblock als Text:</span><span class="sxs-lookup"><span data-stu-id="c154d-107">[Statement lambda](#statement-lambdas) that has a statement block as its body:</span></span>

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

<span data-ttu-id="c154d-108">Verwenden Sie den [Lambdadeklarationsoperator `=>`](lambda-operator.md), um die Parameterliste des Lambdas von dessen Text zu trennen.</span><span class="sxs-lookup"><span data-stu-id="c154d-108">Use the [lambda declaration operator `=>`](lambda-operator.md) to separate the lambda's parameter list from its body.</span></span> <span data-ttu-id="c154d-109">Geben Sie zum Erstellen eines Lambdaausdrucks Eingabeparameter (falls vorhanden) auf der linken Seite des Lambdaoperators und einen Ausdruck oder Anweisungsblock auf der anderen Seite an.</span><span class="sxs-lookup"><span data-stu-id="c154d-109">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator and an expression or a statement block on the other side.</span></span>

<span data-ttu-id="c154d-110">Jeder Lambdaausdruck kann in einen [Delegat](../builtin-types/reference-types.md#the-delegate-type)-Typ konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c154d-110">Any lambda expression can be converted to a [delegate](../builtin-types/reference-types.md#the-delegate-type) type.</span></span> <span data-ttu-id="c154d-111">Der Delegattyp, in den ein Lambdaausdruck konvertiert werden kann, wird durch die Typen seiner Parameter und Rückgabewerte definiert.</span><span class="sxs-lookup"><span data-stu-id="c154d-111">The delegate type to which a lambda expression can be converted is defined by the types of its parameters and return value.</span></span> <span data-ttu-id="c154d-112">Wenn ein Lambdaausdruck keinen Wert zurückgibt, kann er in einen der `Action`-Delegattypen konvertiert werden. Andernfalls kann er in einen der `Func`-Delegattypen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c154d-112">If a lambda expression doesn't return a value, it can be converted to one of the `Action` delegate types; otherwise, it can be converted to one of the `Func` delegate types.</span></span> <span data-ttu-id="c154d-113">Ein Lambdaausdruck, der beispielsweise zwei Parameter hat und keinen Wert zurückgibt, kann in einen <xref:System.Action%602>-Delegat konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c154d-113">For example, a lambda expression that has two parameters and returns no value can be converted to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="c154d-114">Außerdem kann ein Lambdaausdruck, der einen Parameter hat und einen Wert zurückgibt, in einen <xref:System.Func%602>-Delegat konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c154d-114">A lambda expression that has one parameter and returns a value can be converted to a <xref:System.Func%602> delegate.</span></span> <span data-ttu-id="c154d-115">Im folgenden Beispiel wird der Lambdaausdruck `x => x * x`, der einen Parameter `x` angibt und den Wert von `x` im Quadrat zurückgibt, einer Variablen eines Delegattyps zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="c154d-115">In the following example, the lambda expression `x => x * x`, which specifies a parameter that's named `x` and returns the value of `x` squared, is assigned to a variable of a delegate type:</span></span>

[!code-csharp-interactive[lambda is delegate](snippets/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="c154d-116">Zudem lassen sich Ausdruckslambdas in [Ausdrucksbaumstruktur](../../programming-guide/concepts/expression-trees/index.md)-Typen konvertieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c154d-116">Expression lambdas can also be converted to the [expression tree](../../programming-guide/concepts/expression-trees/index.md) types, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is expression tree](snippets/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="c154d-117">Sie können Lambdaausdrücke in jedem Code verwenden, der Instanzen von Delegattypen oder Ausdrucksbaumstrukturen erfordert, z.B. als Argument für die <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>-Methode, um den im Hintergrund auszuführenden Code zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c154d-117">You can use lambda expressions in any code that requires instances of delegate types or expression trees, for example as an argument to the <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> method to pass the code that should be executed in the background.</span></span> <span data-ttu-id="c154d-118">Wie im folgenden Beispiel gezeigt wird, können Sie beim Schreiben von [LINQ in C#](../../linq/index.md) auch Lambdaausdrücke verwenden:</span><span class="sxs-lookup"><span data-stu-id="c154d-118">You can also use lambda expressions when you write [LINQ in C#](../../linq/index.md), as the following example shows:</span></span>

[!code-csharp-interactive[lambda is argument in LINQ](snippets/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="c154d-119">Wenn Sie zum Aufrufen der <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType>-Methode in der <xref:System.Linq.Enumerable?displayProperty=nameWithType>-Klasse methodenbasierte Syntax verwenden, wie in LINQ to Objects und LINQ to XML, ist der Parameter ein Delegattyp <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c154d-119">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class, for example in LINQ to Objects and LINQ to XML, the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c154d-120">Wenn Sie die <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>-Methode in der <xref:System.Linq.Queryable?displayProperty=nameWithType>-Klasse aufrufen, wie in LINQ to SQL, ist der Parametertyp ein Ausdrucksbaumstruktur-Typ [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span><span class="sxs-lookup"><span data-stu-id="c154d-120">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class, for example in LINQ to SQL, the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="c154d-121">In beiden Fällen können Sie denselben Lambdaausdruck verwenden, um die Parameterwerte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c154d-121">In both cases you can use the same lambda expression to specify the parameter value.</span></span> <span data-ttu-id="c154d-122">Dadurch sehen die `Select`-Aufrufe ähnlich aus, obwohl sich der mithilfe der Lambdas erstellte Objekttyp unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="c154d-122">That makes the two `Select` calls to look similar although in fact the type of objects created from the lambdas is different.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="c154d-123">Ausdruckslambdas</span><span class="sxs-lookup"><span data-stu-id="c154d-123">Expression lambdas</span></span>

<span data-ttu-id="c154d-124">Ein Lambdaausdruck mit einem Ausdruck auf der rechten Seite des `=>`-Operators wird als *Ausdruckslambda* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c154d-124">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="c154d-125">Ein Ausdruckslambda gibt das Ergebnis des Ausdrucks zurück und hat folgende grundlegende Form:</span><span class="sxs-lookup"><span data-stu-id="c154d-125">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="c154d-126">Der Text eines Ausdruckslambdas kann aus einem Methodenaufruf bestehen.</span><span class="sxs-lookup"><span data-stu-id="c154d-126">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="c154d-127">Wenn Sie jedoch [Ausdrucksbaumstrukturen](../../programming-guide/concepts/expression-trees/index.md) erstellen, die außerhalb des Kontexts der .NET Common Language Runtime (CLR) ausgewertet werden, z. B. in SQL Server, sollten Sie in Lambdaausdrücken keine Methodenaufrufe verwenden.</span><span class="sxs-lookup"><span data-stu-id="c154d-127">However, if you are creating [expression trees](../../programming-guide/concepts/expression-trees/index.md) that are evaluated outside the context of the .NET Common Language Runtime (CLR), such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="c154d-128">Die Methoden haben außerhalb des Kontexts der .NET Common Language Runtime (CLR) keine Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="c154d-128">The methods will have no meaning outside the context of the .NET Common Language Runtime (CLR).</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="c154d-129">Anweisungslambdas</span><span class="sxs-lookup"><span data-stu-id="c154d-129">Statement lambdas</span></span>

<span data-ttu-id="c154d-130">Ein Anweisungslambda ähnelt einem Ausdruckslambda, allerdings sind die Anweisungen in Klammern eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="c154d-130">A statement lambda resembles an expression lambda except that its statements are enclosed in braces:</span></span>

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

<span data-ttu-id="c154d-131">Der Text eines Anweisungslambdas kann aus einer beliebigen Anzahl von Anweisungen bestehen, wobei es sich meistens um höchstens zwei oder drei Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="c154d-131">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatementLambda":::

<span data-ttu-id="c154d-132">Anweisungslambdas können nicht zum Erstellen von Ausdrucksbaumstrukturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c154d-132">You cannot use statement lambdas to create expression trees.</span></span>

## <a name="input-parameters-of-a-lambda-expression"></a><span data-ttu-id="c154d-133">Eingabeparameter eines Lambdaausdrucks</span><span class="sxs-lookup"><span data-stu-id="c154d-133">Input parameters of a lambda expression</span></span>

<span data-ttu-id="c154d-134">Sie schließen die Eingabeparameter eines Lambdaausdrucks in Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="c154d-134">You enclose input parameters of a lambda expression in parentheses.</span></span> <span data-ttu-id="c154d-135">Geben Sie Eingabeparameter von 0 (null) mit leeren Klammern an:</span><span class="sxs-lookup"><span data-stu-id="c154d-135">Specify zero input parameters with empty parentheses:</span></span>  

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetZeroParameters":::

<span data-ttu-id="c154d-136">Wenn ein Lambdaausdruck nur über einen Eingabeparameter verfügt, sind Klammern optional:</span><span class="sxs-lookup"><span data-stu-id="c154d-136">If a lambda expression has only one input parameter, parentheses are optional:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetOneParameter":::

<span data-ttu-id="c154d-137">Zwei oder mehr Eingabeparameter werden durch Kommas getrennt:</span><span class="sxs-lookup"><span data-stu-id="c154d-137">Two or more input parameters are separated by commas:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetTwoParameters":::

<span data-ttu-id="c154d-138">Manchmal kann der Compiler die Typen von Eingabeparametern nicht ableiten.</span><span class="sxs-lookup"><span data-stu-id="c154d-138">Sometimes the compiler can't infer the types of input parameters.</span></span> <span data-ttu-id="c154d-139">Sie können die Typen wie im folgenden Beispiel dargestellt explizit angeben:</span><span class="sxs-lookup"><span data-stu-id="c154d-139">You can specify the types explicitly as shown in the following example:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetExplicitlyTypedParameters":::

<span data-ttu-id="c154d-140">Eingabeparametertypen müssen alle entweder explizit oder implizit sein. Andernfalls tritt der Compilerfehler [CS0748](../../misc/cs0748.md) auf.</span><span class="sxs-lookup"><span data-stu-id="c154d-140">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="c154d-141">Ab C# 9.0 können Sie [discards](../../discards.md) verwenden, um mindestens zwei Eingabeparameter eines Lambdaausdrucks anzugeben, der nicht im Ausdruck verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="c154d-141">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of a lambda expression that aren't used in the expression:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetDiscards":::

<span data-ttu-id="c154d-142">Verwerfungsparameter von Lambdas können nützlich sein, wenn Sie einen Lambdaausdruck zur [Bereitstellung eines Ereignishandlers](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c154d-142">Lambda discard parameters may be useful when you use a lambda expression to [provide an event handler](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c154d-143">Aus Gründen der Abwärtskompatibilität wird innerhalb eines Lambdaausdrucks `_` als Name des Parameters behandelt, wenn nur ein einzelner Eingabeparameter den Namen `_` aufweist.</span><span class="sxs-lookup"><span data-stu-id="c154d-143">For backwards compatibility, if only a single input parameter is named `_`, then, within a lambda expression, `_` is treated as the name of that parameter.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="c154d-144">Asynchrone Lambdas</span><span class="sxs-lookup"><span data-stu-id="c154d-144">Async lambdas</span></span>

<span data-ttu-id="c154d-145">Sie können mit den Schlüsselwörtern [async](../keywords/async.md) und [await](await.md) Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten, leicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="c154d-145">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../keywords/async.md) and [await](await.md) keywords.</span></span> <span data-ttu-id="c154d-146">Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.</span><span class="sxs-lookup"><span data-stu-id="c154d-146">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="c154d-147">Sie können denselben Ereignishandler hinzufügen, indem Sie ein asynchrones Lambda verwenden.</span><span class="sxs-lookup"><span data-stu-id="c154d-147">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="c154d-148">Um diesen Handler hinzuzufügen, fügen Sie einen `async`-Modifizierer vor der Lambdaparameterliste hinzu, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c154d-148">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

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

<span data-ttu-id="c154d-149">Weitere Informationen zum Erstellen und Verwenden von asynchronen Methoden finden Sie unter [Asynchronous programming with async and await (Asynchrones Programmieren mit „async“ and „await“)](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="c154d-149">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="c154d-150">Lambdaausdrücke und Tupel</span><span class="sxs-lookup"><span data-stu-id="c154d-150">Lambda expressions and tuples</span></span>

<span data-ttu-id="c154d-151">Ab C# 7.0 bietet die C#-Programmiersprache integrierte Unterstützung für [Tupel](../builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="c154d-151">Starting with C# 7.0, the C# language provides built-in support for [tuples](../builtin-types/value-tuples.md).</span></span> <span data-ttu-id="c154d-152">Sie können ein Tupel einem Lambdaausdruck als Argument bereitstellen, und Ihr Lambdaausdruck kann ebenfalls einen Tupel zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c154d-152">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="c154d-153">In einigen Fällen verwendet der C#-Compiler den Typrückschluss, um den Typ der Tupelkomponenten zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c154d-153">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="c154d-154">Sie können ein Tupel definieren, indem Sie eine durch Trennzeichen getrennte Liste seiner Komponenten in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="c154d-154">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="c154d-155">In folgendem Beispiel wird ein Tupel mit drei Komponenten verwenden, um eine Zahlensequenz an einen Lambdaausdruck zu übergeben; dadurch wird jeder Wert verdoppelt, und es wird ein Tupel mit drei Komponenten zurückgegeben, das das Ergebnis der Multiplikation enthält.</span><span class="sxs-lookup"><span data-stu-id="c154d-155">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="c154d-156">Für gewöhnlich heißen die Felder eines Tupels `Item1`, `Item2`, usw. Sie können allerdings ein Tupel mit benannten Komponenten definieren, wie in folgendem Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c154d-156">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="c154d-157">Weitere Informationen zu C#-Tupeln finden Sie unter [Tupeltypen](../../language-reference/builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="c154d-157">For more information about C# tuples, see [Tuple types](../../language-reference/builtin-types/value-tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="c154d-158">Lambdas mit Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="c154d-158">Lambdas with the standard query operators</span></span>

<span data-ttu-id="c154d-159">LINQ to Objects haben, neben anderen Implementierungen, einen Eingabeparameter, dessen Typ Teil der <xref:System.Func%601>-Familie generischer Delegate ist.</span><span class="sxs-lookup"><span data-stu-id="c154d-159">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="c154d-160">Diese Delegaten verwenden Typparameter zur Definition der Anzahl und des Typs der Eingabeparameter sowie des Rückgabetyps des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="c154d-160">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="c154d-161">`Func` -Delegaten sind für das Kapseln von benutzerdefinierten Ausdrücken, die für jedes Element in einem Satz von Quelldaten übernommen werden, sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="c154d-161">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="c154d-162">Betrachten Sie z.B. den <xref:System.Func%602>-Delegattyp:</span><span class="sxs-lookup"><span data-stu-id="c154d-162">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="c154d-163">Der Delegat kann als `Func<int, bool>`-Instanz instanziiert werden, wobei `int` ein Eingabeparameter und `bool` der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="c154d-163">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="c154d-164">Der Rückgabewert wird immer im letzten Typparameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="c154d-164">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="c154d-165">`Func<int, string, bool>` definiert z.B. einen Delegaten mit zwei Eingabeparametern, `int` und `string`, und einen Rückgabetyp von `bool`.</span><span class="sxs-lookup"><span data-stu-id="c154d-165">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="c154d-166">Der folgende `Func`-Delegat gibt bei einem Aufruf einen booleschen Wert zurück, um anzugeben, ob der Eingabeparameter gleich fünf ist:</span><span class="sxs-lookup"><span data-stu-id="c154d-166">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="c154d-167">Sie können einen Lambdaausdruck auch dann angeben, wenn der Argumenttyp <xref:System.Linq.Expressions.Expression%601> ist, beispielsweise in den Standardabfrageoperatoren, die in Typ <xref:System.Linq.Queryable> definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c154d-167">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="c154d-168">Wenn Sie ein <xref:System.Linq.Expressions.Expression%601>-Argument angeben, wird der Lambdaausdruck in eine Ausdrucksbaumstruktur kompiliert.</span><span class="sxs-lookup"><span data-stu-id="c154d-168">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="c154d-169">Im folgenden Beispiel wird der <xref:System.Linq.Enumerable.Count%2A>-Standardabfrageoperator verwendet:</span><span class="sxs-lookup"><span data-stu-id="c154d-169">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="c154d-170">Der Compiler kann den Typ des Eingabeparameters ableiten, Sie können ihn aber auch explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="c154d-170">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="c154d-171">Dieser bestimmte Lambda-Ausdruck zählt die ganzen Zahlen (`n`), bei denen nach dem Dividieren durch zwei als Rest 1 bleibt.</span><span class="sxs-lookup"><span data-stu-id="c154d-171">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="c154d-172">In folgendem Beispiel wird eine Sequenz erzeugt, die alle Elemente im Array `numbers` enthält, die vor der 9 auftreten, da dies die erste Zahl in der Sequenz ist, die die Bedingung nicht erfüllt:</span><span class="sxs-lookup"><span data-stu-id="c154d-172">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="c154d-173">In folgendem Beispiel wird gezeigt, wie Sie mehrere Eingabeparameter angeben, indem Sie sie in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="c154d-173">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="c154d-174">Mit der Methode werden alle Elemente im `numbers`-Array zurückgegeben, bis eine Zahl erreicht wird, deren Wert kleiner ist als ihre Ordnungspostion im Array:</span><span class="sxs-lookup"><span data-stu-id="c154d-174">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="c154d-175">Typrückschluss in Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="c154d-175">Type inference in lambda expressions</span></span>

<span data-ttu-id="c154d-176">Beim Schreiben von Lambdas müssen Sie oftmals keinen Typ für die Eingabeparameter angeben, da der Compiler den Typ auf der Grundlage des Lambdatexts, der Parametertypen und anderer Faktoren ableiten kann, wie in der C#-Programmiersprachenspezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c154d-176">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="c154d-177">Bei den meisten Standardabfrageoperatoren entspricht die erste Eingabe dem Typ der Elemente in der Quellsequenz.</span><span class="sxs-lookup"><span data-stu-id="c154d-177">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="c154d-178">Beim Abfragen von `IEnumerable<Customer>` wird die Eingabevariable als `Customer`-Objekt abgeleitet, sodass Sie auf die zugehörigen Methoden und Eigenschaften zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="c154d-178">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="c154d-179">Die allgemeinen Regeln für Typrückschlüsse bei Lambdas lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c154d-179">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="c154d-180">Der Lambda-Ausdruck muss dieselbe Anzahl von Parametern enthalten wie der Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="c154d-180">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="c154d-181">Jeder Eingabeparameter im Lambda muss implizit in den entsprechenden Delegatparameter konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="c154d-181">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="c154d-182">Der Rückgabewert des Lambdas (falls vorhanden) muss implizit in den Rückgabetyp des Delegaten konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="c154d-182">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="c154d-183">Beachten Sie, dass Lambdaausdrücke keinen eigenen Typ haben, da das allgemeine Typsystem kein internes Konzept von „Lambdaausdrücken“ aufweist.</span><span class="sxs-lookup"><span data-stu-id="c154d-183">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="c154d-184">Es kann manchmal praktisch sein, informell vom „Typ“ eines Lambdaausdrucks zu sprechen.</span><span class="sxs-lookup"><span data-stu-id="c154d-184">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="c154d-185">In einem solchen Fall bezeichnet Typ den Delegattyp bzw. den <xref:System.Linq.Expressions.Expression> -Typ, in den der Lambda-Ausdruck konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="c154d-185">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a><span data-ttu-id="c154d-186">Erfassen äußerer Variablen sowie des Variablenbereichs in Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="c154d-186">Capture of outer variables and variable scope in lambda expressions</span></span>

<span data-ttu-id="c154d-187">Lambdas können auf *äußere Variablen* verweisen.</span><span class="sxs-lookup"><span data-stu-id="c154d-187">Lambdas can refer to *outer variables*.</span></span> <span data-ttu-id="c154d-188">Hierbei handelt es sich um die Variablen, die im Bereich der Methode, mit der der Lambdaausdruck definiert wird, oder im Bereich des Typs liegen, der den Lambdaausdruck enthält.</span><span class="sxs-lookup"><span data-stu-id="c154d-188">These are the variables that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="c154d-189">Variablen, die auf diese Weise erfasst werden, werden zur Verwendung in Lambda-Ausdrücken gespeichert, auch wenn die Variablen andernfalls außerhalb des Gültigkeitsbereichs liegen und an die Garbage Collection übergeben würden.</span><span class="sxs-lookup"><span data-stu-id="c154d-189">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="c154d-190">Eine äußere Variable muss definitiv zugewiesen sein, bevor sie in einem Lambda-Ausdruck verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c154d-190">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="c154d-191">Das folgende Beispiel veranschaulicht diese Regeln:</span><span class="sxs-lookup"><span data-stu-id="c154d-191">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](snippets/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="c154d-192">Die folgenden Regeln gelten für den Variablenbereich in Lambda-Ausdrücken:</span><span class="sxs-lookup"><span data-stu-id="c154d-192">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="c154d-193">Eine erfasste Variable wird erst dann an die Garbage Collection übergeben, wenn der darauf verweisende Delegat für die Garbage Collection geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="c154d-193">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="c154d-194">Variablen, die in einem Lambdaausdruck eingeführt wurden, sind in der einschließenden Methode nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c154d-194">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="c154d-195">Ein Lambdaausdruck kann einen [in](../keywords/in-parameter-modifier.md)-, [ref](../keywords/ref.md)- oder [out](../keywords/out-parameter-modifier.md)-Parameter nicht direkt von der einschließenden Methode erfassen.</span><span class="sxs-lookup"><span data-stu-id="c154d-195">A lambda expression cannot directly capture an [in](../keywords/in-parameter-modifier.md), [ref](../keywords/ref.md), or [out](../keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="c154d-196">Eine [return](../keywords/return.md)-Anweisung in einem Lambdaausdruck bewirkt keine Rückgabe durch die einschließende Methode.</span><span class="sxs-lookup"><span data-stu-id="c154d-196">A [return](../keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="c154d-197">Ein Lambdaausdruck darf keine [goto](../keywords/goto.md)-, [break](../keywords/break.md)- oder [continue](../keywords/continue.md)-Anweisung enthalten, wenn das Ziel dieser Sprunganweisung außerhalb des Lambdaausdrucksblocks liegt.</span><span class="sxs-lookup"><span data-stu-id="c154d-197">A lambda expression cannot contain a [goto](../keywords/goto.md), [break](../keywords/break.md), or [continue](../keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="c154d-198">Eine Sprunganweisung darf auch nicht außerhalb des Lambdaausdrucksblocks sein, wenn das Ziel im Block ist.</span><span class="sxs-lookup"><span data-stu-id="c154d-198">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

<span data-ttu-id="c154d-199">Ab C# 9.0 können Sie den `static`-Modifizierer auf einen Lambdaausdruck anwenden, um zu verhindern, dass lokale Variablen oder der Instanzzustand versehentlich durch die Lambdafunktion erfasst werden:</span><span class="sxs-lookup"><span data-stu-id="c154d-199">Beginning with C# 9.0, you can apply the `static` modifier to a lambda expression to prevent unintentional capture of local variables or instance state by the lambda:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatic":::

<span data-ttu-id="c154d-200">Ein statischer Lambdaausdruck kann keine lokalen Variablen oder den Instanzzustand aus einschließenden Bereichen erfassen, kann jedoch auf statische Member und Konstantendefinitionen verweisen.</span><span class="sxs-lookup"><span data-stu-id="c154d-200">A static lambda can't capture local variables or instance state from enclosing scopes, but may reference static members and constant definitions.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c154d-201">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c154d-201">C# language specification</span></span>

<span data-ttu-id="c154d-202">Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c154d-202">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="c154d-203">Weitere Informationen zu in C# 9.0 eingeführten Features finden Sie in den folgenden Featurevorschlägen:</span><span class="sxs-lookup"><span data-stu-id="c154d-203">For more information about features added in C# 9.0, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="c154d-204">Parameter zum Verwerfen von Lambdafunktion</span><span class="sxs-lookup"><span data-stu-id="c154d-204">Lambda discard parameters</span></span>](~/_csharplang/proposals/csharp-9.0/lambda-discard-parameters.md)
- [<span data-ttu-id="c154d-205">Statische anonyme Funktionen</span><span class="sxs-lookup"><span data-stu-id="c154d-205">Static anonymous functions</span></span>](~/_csharplang/proposals/csharp-9.0/static-anonymous-functions.md)

## <a name="see-also"></a><span data-ttu-id="c154d-206">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c154d-206">See also</span></span>

- [<span data-ttu-id="c154d-207">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c154d-207">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c154d-208">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c154d-208">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="c154d-209">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="c154d-209">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="c154d-210">Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="c154d-210">Expression Trees</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="c154d-211">Lokale Funktionen im Vergleich zu Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="c154d-211">Local functions vs. lambda expressions</span></span>](../../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions)
- [<span data-ttu-id="c154d-212">Visual Studio 2008 C#-Beispiele (siehe LINQ-Beispielabfragedateien und XQuery-Programm)</span><span class="sxs-lookup"><span data-stu-id="c154d-212">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
