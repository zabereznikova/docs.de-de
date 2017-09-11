---
title: "Lambda-Ausdrücke (C#-Programmierhandbuch)"
ms.date: 2017-03-03
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
caps.latest.revision: 64
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c952c72d9108775fbd0f824f82cacdab5ba91d09
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="883c4-102">Lambda-Ausdrücke (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="883c4-102">Lambda Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="883c4-103">Ein Lambda-Ausdruck ist eine [anonyme Funktion](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) , mit der Typen für [Delegaten](../../../csharp/programming-guide/delegates/using-delegates.md) oder die [Ausdrucksbaumstruktur](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="883c4-103">A lambda expression is an [anonymous function](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) that you can use to create [delegates](../../../csharp/programming-guide/delegates/using-delegates.md) or [expression tree](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) types.</span></span> <span data-ttu-id="883c4-104">Mit Lambda-Ausdrücken können lokale Funktionen geschrieben werden, die als Argumente übergeben oder als Wert von Funktionsaufrufen zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="883c4-104">By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls.</span></span> <span data-ttu-id="883c4-105">Lambda-Ausdrücke sind besonders für das Schreiben von LINQ-Abfrageausdrücken hilfreich.</span><span class="sxs-lookup"><span data-stu-id="883c4-105">Lambda expressions are particularly helpful for writing LINQ query expressions.</span></span>  
  
 <span data-ttu-id="883c4-106">Zum Erstellen eines Lambda-Ausdrucks geben Sie Eingabeparameter (falls vorhanden) auf der linken Seite des Lambda-Operators [=>](../../../csharp/language-reference/operators/lambda-operator.md)an und stellen den Ausdruck oder den Anweisungsblock auf die andere Seite.</span><span class="sxs-lookup"><span data-stu-id="883c4-106">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator [=>](../../../csharp/language-reference/operators/lambda-operator.md), and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="883c4-107">Beispielsweise gibt der Lambda-Ausdruck `x => x * x` einen Parameter an, der `x` heißt und den Wert `x` quadriert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="883c4-107">For example, the lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="883c4-108">Dieser Ausdruck kann einem Delegattyp zuwiesen werden, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="883c4-108">You can assign this expression to a delegate type, as the following example shows:</span></span>  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 <span data-ttu-id="883c4-109">So erstellen Sie einen Typ für die Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="883c4-109">To create an expression tree type:</span></span>  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="883c4-110">Der Operator `=>` hat die gleiche Rangfolge wie Zuordnung (`=`) und ist [rechtsassoziativ](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (siehe Abschnitt „Assoziativität“ im Artikel „Operatoren“).</span><span class="sxs-lookup"><span data-stu-id="883c4-110">The `=>` operator has the same precedence as assignment (`=`) and is [right associative](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (see "Associativity" section of the Operators article).</span></span>  
  
 <span data-ttu-id="883c4-111">Lambdas werden in methodenbasierten [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen als Argumente für Standardabfrageoperator-Methoden wie <xref:System.Linq.Enumerable.Where%2A> verwendet.</span><span class="sxs-lookup"><span data-stu-id="883c4-111">Lambdas are used in method-based [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries as arguments to standard query operator methods such as <xref:System.Linq.Enumerable.Where%2A>.</span></span>  
  
 <span data-ttu-id="883c4-112">Wenn Sie zum Aufrufen der <xref:System.Linq.Enumerable.Where%2A> -Methode in der <xref:System.Linq.Enumerable> -Klasse methodenbasierte Syntax verwenden (wie in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects und [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]), ist der Parameter ein Delegattyp <xref:System.Func%602?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="883c4-112">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Where%2A> method in the <xref:System.Linq.Enumerable> class (as you do in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) the parameter is a delegate type <xref:System.Func%602?displayProperty=fullName>.</span></span> <span data-ttu-id="883c4-113">Ein Lambda-Ausdruck ist die einfachste Möglichkeit zum Erstellen dieses Delegaten.</span><span class="sxs-lookup"><span data-stu-id="883c4-113">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="883c4-114">Wenn Sie dieselbe Methode z.B. in der <xref:System.Linq.Queryable?displayProperty=fullName>-Klasse aufrufen (wie in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]), handelt es sich bei dem Parametertyp um eine <xref:System.Linq.Expressions.Expression?displayProperty=fullName><Funktion\>, wobei „Funktion“ für beliebige Funktionsdelegaten mit bis zu 16 Eingabeparametern steht.</span><span class="sxs-lookup"><span data-stu-id="883c4-114">When you call the same method in, for example, the <xref:System.Linq.Queryable?displayProperty=fullName> class (as you do in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) then the parameter type is an <xref:System.Linq.Expressions.Expression?displayProperty=fullName><Func\> where Func is any of the Func delegates with up to sixteen input parameters.</span></span> <span data-ttu-id="883c4-115">Wie gesagt, ein Lambda-Ausdruck ist eine sehr präzise Methode, diese Ausdrucksbaumstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="883c4-115">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="883c4-116">Durch die Lambdas können die `Where` -Aufrufe ähnlich aussehen, obwohl sich der mithilfe des Lambdas erstellte Objekttyp unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="883c4-116">The lambdas allow the `Where` calls to look similar although in fact the type of object created from the lambda is different.</span></span>  
  
 <span data-ttu-id="883c4-117">Beachten Sie im vorigen Beispiel, dass die Signatur des Delegaten über einen implizit typisierten Eingabeparameter vom Typ `int`verfügt und `int`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="883c4-117">In the previous example, notice that the delegate signature has one implicitly-typed input parameter of type `int`, and returns an `int`.</span></span> <span data-ttu-id="883c4-118">Der Lambda-Ausdruck kann in einen Delegaten dieses Typs konvertiert werden, da er auch über einen Eingabeparameter (`x`) und einen Rückgabewert verfügt, der vom Compiler implizit in den Typ `int` konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="883c4-118">The lambda expression can be converted to a delegate of that type because it also has one input parameter (`x`) and a return value that the compiler can implicitly convert to type `int`.</span></span> <span data-ttu-id="883c4-119">(Der Typrückschluss wird in den folgenden Abschnitten ausführlicher erläutert.) Wenn der Delegat durch Verwendung des Eingabeparameters 5 aufgerufen wird, wird als Ergebnis 25 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="883c4-119">(Type inference is discussed in more detail in the following sections.) When the delegate is invoked by using an input parameter of 5, it returns a result of 25.</span></span>  
  
 <span data-ttu-id="883c4-120">Lambdas sind auf der linken Seite des Operators [is](../../../csharp/language-reference/keywords/is.md) oder [as](../../../csharp/language-reference/keywords/as.md) nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="883c4-120">Lambdas are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) or [as](../../../csharp/language-reference/keywords/as.md) operator.</span></span>  
  
 <span data-ttu-id="883c4-121">Alle Einschränkungen für anonyme Methoden gelten auch für Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="883c4-121">All restrictions that apply to anonymous methods also apply to lambda expressions.</span></span> <span data-ttu-id="883c4-122">Weitere Informationen finden Sie unter [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="883c4-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
## <a name="expression-lambdas"></a><span data-ttu-id="883c4-123">Ausdruckslambdas</span><span class="sxs-lookup"><span data-stu-id="883c4-123">Expression Lambdas</span></span>  
 <span data-ttu-id="883c4-124">Ein Lambdaausdruck mit einem Ausdruck auf der rechten Seite des Operators „=>“ wird als *Ausdruckslambda* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="883c4-124">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="883c4-125">Ausdruckslambdas werden häufig bei der Erstellung von [Ausdrucksbaumstrukturen](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)verwendet.</span><span class="sxs-lookup"><span data-stu-id="883c4-125">Expression lambdas are used extensively in the construction of [Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b).</span></span> <span data-ttu-id="883c4-126">Ein Ausdruckslambda gibt das Ergebnis des Ausdrucks zurück und hat folgende grundlegende Form:</span><span class="sxs-lookup"><span data-stu-id="883c4-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>  
  
```csharp
(input-parameters) => expression
```

 <span data-ttu-id="883c4-127">Die Klammern sind nur optional, wenn das Lambda über einen Eingabeparameter verfügt; andernfalls sind sie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="883c4-127">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="883c4-128">Zwei oder mehr Eingabeparameter sind durch Kommas getrennt und in Klammern eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="883c4-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>  
  
```csharp
(x, y) => x == y
```

 <span data-ttu-id="883c4-129">Für den Compiler kann es schwierig oder unmöglich sein, die Eingabetypen abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="883c4-129">Sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="883c4-130">Wenn dieses Problem auftritt, können Sie die Typen explizit angeben, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="883c4-130">When this occurs, you can specify the types explicitly as shown in the following example:</span></span>  
  
```csharp
(int x, string s) => s.Length > x
```

 <span data-ttu-id="883c4-131">Geben Sie Eingabeparameter von 0 (null) mit leeren Klammern an:</span><span class="sxs-lookup"><span data-stu-id="883c4-131">Specify zero input parameters with empty parentheses:</span></span>  
  
```csharp
() => SomeMethod()
```

 <span data-ttu-id="883c4-132">Beachten Sie im vorherigen Beispiel, dass der Text eines Ausdruckslambdas ein Methodenaufruf sein kann.</span><span class="sxs-lookup"><span data-stu-id="883c4-132">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="883c4-133">Wenn Sie jedoch Ausdrucksbaumstrukturen erstellen, die auf einer anderen Plattform als .NET Framework ausgewertet werden, z. B. SQL Server, sollten Sie in Lambda-Ausdrücken keine Methodenaufrufe verwenden.</span><span class="sxs-lookup"><span data-stu-id="883c4-133">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="883c4-134">Die Methoden haben außerhalb des Kontexts der .NET Common Language Runtime keine Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="883c4-134">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>  
  
## <a name="statement-lambdas"></a><span data-ttu-id="883c4-135">Anweisungslambdas</span><span class="sxs-lookup"><span data-stu-id="883c4-135">Statement Lambdas</span></span>  
 <span data-ttu-id="883c4-136">Ein Anweisungslambda ähnelt einem Ausdruckslambda, allerdings sind die Anweisungen in Klammern eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="883c4-136">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>  
  
<span data-ttu-id="883c4-137">(input-parameters) => { statement; }</span><span class="sxs-lookup"><span data-stu-id="883c4-137">(input-parameters) => { statement; }</span></span>

 <span data-ttu-id="883c4-138">Der Text eines Anweisungslambdas kann aus einer beliebigen Anzahl von Anweisungen bestehen, wobei es sich meistens um höchstens zwei oder drei Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="883c4-138">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>  
  
<span data-ttu-id="883c4-139">[!code-csharp[StatementLamba#1](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="883c4-139">[!code-csharp[StatementLamba#1](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#1)]</span></span>

<span data-ttu-id="883c4-140">[!code-csharp[StatementLamba#2](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="883c4-140">[!code-csharp[StatementLamba#2](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#2)]</span></span>

 <span data-ttu-id="883c4-141">Anweisungslambdas, wie anonyme Methoden, können nicht zum Erstellen von Ausdrucksbaumstrukturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="883c4-141">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="883c4-142">Asynchrone Lambdas</span><span class="sxs-lookup"><span data-stu-id="883c4-142">Async Lambdas</span></span>  
 <span data-ttu-id="883c4-143">Sie können mit den Schlüsselwörtern [async](../../../csharp/language-reference/keywords/async.md) und [await](../../../csharp/language-reference/keywords/await.md) Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten, leicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="883c4-143">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../../csharp/language-reference/keywords/async.md) and [await](../../../csharp/language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="883c4-144">Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.</span><span class="sxs-lookup"><span data-stu-id="883c4-144">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 <span data-ttu-id="883c4-145">Sie können denselben Ereignishandler hinzufügen, indem Sie ein asynchrones Lambda verwenden.</span><span class="sxs-lookup"><span data-stu-id="883c4-145">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="883c4-146">Um diesen Handler hinzuzufügen, fügen Sie einen `async` -Modifizierer vor der Lambda-Parameterliste, wie im folgenden Beispiel dargestellt, hinzu.</span><span class="sxs-lookup"><span data-stu-id="883c4-146">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 <span data-ttu-id="883c4-147">Weitere Informationen zum Erstellen und Verwenden von asynchronen Methoden finden Sie unter [Asynchronous programming with async and await (Asynchrones Programmieren mit „async“ and „await“)](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="883c4-147">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="883c4-148">Lambdas mit Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="883c4-148">Lambdas with the Standard Query Operators</span></span>  
 <span data-ttu-id="883c4-149">Viele Standardabfrageoperatoren weisen einen Eingabeparameter auf, deren Typ einem der Typen aus der <xref:System.Func%602> -Familie generischer Delegaten entspricht.</span><span class="sxs-lookup"><span data-stu-id="883c4-149">Many Standard query operators have an input parameter whose type is one of the <xref:System.Func%602> family of generic delegates.</span></span> <span data-ttu-id="883c4-150">Diese Delegaten verwenden Typparameter zur Definition der Anzahl und des Typs der Eingabeparameter sowie des Rückgabetyps des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="883c4-150">These delegates use type parameters to define the number and types of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="883c4-151">`Func` -Delegaten sind für das Kapseln von benutzerdefinierten Ausdrücken, die für jedes Element in einem Satz von Quelldaten übernommen werden, sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="883c4-151">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="883c4-152">Betrachten Sie z. B. den folgenden Delegattyp:</span><span class="sxs-lookup"><span data-stu-id="883c4-152">For example, consider the following delegate type:</span></span>  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 <span data-ttu-id="883c4-153">Der Delegat kann als `Func<int,bool> myFunc` instanziiert werden, wobei `int` ein Eingabeparameter und `bool` der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="883c4-153">The delegate can be instantiated as `Func<int,bool> myFunc` where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="883c4-154">Der Rückgabewert wird immer im letzten Typparameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="883c4-154">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="883c4-155">`Func<int, string, bool>` definiert einen Delegaten mit zwei Eingabeparametern, `int` und `string`, und einen Rückgabetyp von `bool`.</span><span class="sxs-lookup"><span data-stu-id="883c4-155">`Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="883c4-156">Der folgende `Func` -Delegat gibt bei einem Aufruf true oder false zurück, um anzugeben, ob der Eingabeparameter gleich 5 ist:</span><span class="sxs-lookup"><span data-stu-id="883c4-156">The following `Func` delegate, when it is invoked, will return true or false to indicate whether the input parameter is equal to 5:</span></span>  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 <span data-ttu-id="883c4-157">Sie können einen Lambda-Ausdruck auch dann angeben, wenn der Argumenttyp `Expression<Func>`ist, beispielsweise in den Standardabfrageoperatoren, die in System.Linq.Queryable definiert sind.</span><span class="sxs-lookup"><span data-stu-id="883c4-157">You can also supply a lambda expression when the argument type is an `Expression<Func>`, for example in the standard query operators that are defined in System.Linq.Queryable.</span></span> <span data-ttu-id="883c4-158">Wenn Sie ein `Expression<Func>` -Argument angeben, wird der Lambda-Ausdruck in eine Ausdrucksbaumstruktur kompiliert.</span><span class="sxs-lookup"><span data-stu-id="883c4-158">When you specify an `Expression<Func>` argument, the lambda will be compiled to an expression tree.</span></span>  
  
 <span data-ttu-id="883c4-159">Hier wird ein Standardabfrageoperator, die <xref:System.Linq.Enumerable.Count%2A> -Methode, angezeigt:</span><span class="sxs-lookup"><span data-stu-id="883c4-159">A standard query operator, the <xref:System.Linq.Enumerable.Count%2A> method, is shown here:</span></span>  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 <span data-ttu-id="883c4-160">Der Compiler kann den Typ des Eingabeparameters ableiten, Sie können ihn aber auch explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="883c4-160">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="883c4-161">Dieser bestimmte Lambda-Ausdruck zählt die ganzen Zahlen (`n`), bei denen nach dem Dividieren durch zwei als Rest 1 bleibt.</span><span class="sxs-lookup"><span data-stu-id="883c4-161">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>  
  
 <span data-ttu-id="883c4-162">Mit der folgenden Codezeile wird eine Sequenz erzeugt, die alle Elemente im `numbers` -Array enthält, die vor der 9 auftreten, da dies die erste Zahl in der Sequenz ist, die die Bedingung nicht erfüllt:</span><span class="sxs-lookup"><span data-stu-id="883c4-162">The following line of code produces a sequence that contains all elements in the `numbers` array that are to the left side of the 9 because that's the first number in the sequence that doesn't meet the condition:</span></span>  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 <span data-ttu-id="883c4-163">In diesem Beispiel wird gezeigt, wie Sie mehrere Eingabeparameter angeben, indem Sie sie in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="883c4-163">This example shows how to specify multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="883c4-164">Mit der Methode werden alle Elemente im Zahlenarray zurückgegeben, bis eine Zahl erreicht wird, deren Wert kleiner ist als seine Position.</span><span class="sxs-lookup"><span data-stu-id="883c4-164">The method returns all the elements in the numbers array until a number is encountered whose value is less than its position.</span></span> <span data-ttu-id="883c4-165">Verwechseln Sie den Lambda-Operator (`=>`) nicht mit dem Operator "Größer als oder gleich" (`>=`).</span><span class="sxs-lookup"><span data-stu-id="883c4-165">Do not confuse the lambda operator (`=>`) with the greater than or equal operator (`>=`).</span></span>  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a><span data-ttu-id="883c4-166">Typrückschluss in Lambdas</span><span class="sxs-lookup"><span data-stu-id="883c4-166">Type Inference in Lambdas</span></span>  
 <span data-ttu-id="883c4-167">Beim Schreiben von Lambdas müssen Sie oftmals keinen Typ für die Eingabeparameter angeben, da der Compiler den Typ auf der Grundlage des Lambda-Texts, des zugrunde liegenden Delegattyps des Parameters und anderer Faktoren per Rückschluss ableiten kann, wie in der C#-Programmiersprachenspezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="883c4-167">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter’s delegate type, and other factors as described in the C# Language Specification.</span></span> <span data-ttu-id="883c4-168">Bei den meisten Standardabfrageoperatoren entspricht die erste Eingabe dem Typ der Elemente in der Quellsequenz.</span><span class="sxs-lookup"><span data-stu-id="883c4-168">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="883c4-169">Beim Abfragen von `IEnumerable<Customer>`wird die Eingabevariable als `Customer` -Objekt abgeleitet, sodass Sie auf die zugehörigen Methoden und Eigenschaften zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="883c4-169">So if you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 <span data-ttu-id="883c4-170">Die allgemeinen Regeln für Lambdas lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="883c4-170">The general rules for lambdas are as follows:</span></span>  
  
-   <span data-ttu-id="883c4-171">Der Lambda-Ausdruck muss dieselbe Anzahl von Parametern enthalten wie der Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="883c4-171">The lambda must contain the same number of parameters as the delegate type.</span></span>  
  
-   <span data-ttu-id="883c4-172">Jeder Eingabeparameter im Lambda muss implizit in den entsprechenden Delegatparameter konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="883c4-172">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>  
  
-   <span data-ttu-id="883c4-173">Der Rückgabewert des Lambdas (falls vorhanden) muss implizit in den Rückgabetyp des Delegaten konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="883c4-173">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>  
  
 <span data-ttu-id="883c4-174">Beachten Sie, dass Lambda-Ausdrücke keinen eigenen Typ haben, da das allgemeine Typsystem kein internes Konzept von "Lambda-Ausdrücken" aufweist.</span><span class="sxs-lookup"><span data-stu-id="883c4-174">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="883c4-175">Es kann manchmal praktisch sein, informell vom "Typ" eines Lambda-Ausdrucks zu sprechen.</span><span class="sxs-lookup"><span data-stu-id="883c4-175">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="883c4-176">In einem solchen Fall bezeichnet Typ den Delegattyp bzw. den <xref:System.Linq.Expressions.Expression> -Typ, in den der Lambda-Ausdruck konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="883c4-176">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>  
  
## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="883c4-177">Variablenbereich in Lambda-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="883c4-177">Variable Scope in Lambda Expressions</span></span>  
 <span data-ttu-id="883c4-178">Lambdas können auf *äußere Variablen* verweisen (siehe [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)), die im Bereich der Methode, mit der die Lambdafunktion definiert wird, oder im Bereich des Typs liegen, der den Lambdaausdruck enthält.</span><span class="sxs-lookup"><span data-stu-id="883c4-178">Lambdas can refer to *outer variables* (see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="883c4-179">Variablen, die auf diese Weise erfasst werden, werden zur Verwendung in Lambda-Ausdrücken gespeichert, auch wenn die Variablen andernfalls außerhalb des Gültigkeitsbereichs liegen und an die Garbage Collection übergeben würden.</span><span class="sxs-lookup"><span data-stu-id="883c4-179">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="883c4-180">Eine äußere Variable muss definitiv zugewiesen sein, bevor sie in einem Lambda-Ausdruck verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="883c4-180">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="883c4-181">Das folgende Beispiel veranschaulicht diese Regeln:</span><span class="sxs-lookup"><span data-stu-id="883c4-181">The following example demonstrates these rules:</span></span>  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
```  
  
 <span data-ttu-id="883c4-182">Die folgenden Regeln gelten für den Variablenbereich in Lambda-Ausdrücken:</span><span class="sxs-lookup"><span data-stu-id="883c4-182">The following rules apply to variable scope in lambda expressions:</span></span>  
  
-   <span data-ttu-id="883c4-183">Eine erfasste Variable wird erst dann an die Garbage Collection übergeben, wenn der darauf verweisende Delegat für die Garbage Collection geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="883c4-183">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>  
  
-   <span data-ttu-id="883c4-184">Variablen, die in einem Lambda-Ausdruck eingeführt wurden, sind in der äußeren Methode nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="883c4-184">Variables introduced within a lambda expression are not visible in the outer method.</span></span>  
  
-   <span data-ttu-id="883c4-185">Ein Lambda-Ausdruck kann einen `ref` - oder `out` -Parameter nicht direkt von einer einschließenden Methode erfassen.</span><span class="sxs-lookup"><span data-stu-id="883c4-185">A lambda expression cannot directly capture a `ref` or `out` parameter from an enclosing method.</span></span>  
  
-   <span data-ttu-id="883c4-186">Eine return-Anweisung in einem Lambda-Ausdruck bewirkt keine Rückgabe durch die einschließende Methode.</span><span class="sxs-lookup"><span data-stu-id="883c4-186">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>  
  
-   <span data-ttu-id="883c4-187">Ein Lambda-Ausdruck kann eine `goto` -Anweisung, `break` -Anweisung oder `continue` -Anweisung enthalten, die innerhalb der Lambda-Funktion liegt, wenn das Ziel der jump-Anweisung außerhalb des Blocks liegt.</span><span class="sxs-lookup"><span data-stu-id="883c4-187">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="883c4-188">Eine jump-Anweisung darf auch nicht außerhalb des Lambda-Funktionsblocks sein, wenn das Ziel im Block ist.</span><span class="sxs-lookup"><span data-stu-id="883c4-188">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="883c4-189">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="883c4-189">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="883c4-190">Enthaltenes Buchkapitel</span><span class="sxs-lookup"><span data-stu-id="883c4-190">Featured Book Chapter</span></span>  
 <span data-ttu-id="883c4-191">[Delegaten, Ereignisse und Lambda-Ausdrücke](http://go.microsoft.com/fwlink/?LinkId=195395) im [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="883c4-191">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="883c4-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="883c4-192">See Also</span></span>  
 <span data-ttu-id="883c4-193">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="883c4-193">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="883c4-194">[LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="883c4-194">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="883c4-195">[Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="883c4-195">[Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
 <span data-ttu-id="883c4-196">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="883c4-196">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="883c4-197">[Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) </span><span class="sxs-lookup"><span data-stu-id="883c4-197">[Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) </span></span>  
 <span data-ttu-id="883c4-198">[Visual Studio 2008 C#-Beispiele (siehe LINQ-Beispielabfragedateien und XQuery-Programm)](http://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba) </span><span class="sxs-lookup"><span data-stu-id="883c4-198">[Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)](http://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba) </span></span>  
 [<span data-ttu-id="883c4-199">Rekursive Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="883c4-199">Recursive lambda expressions</span></span>](http://go.microsoft.com/fwlink/?LinkId=112395)

