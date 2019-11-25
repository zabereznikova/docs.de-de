---
title: Lambdaausdrücke – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/29/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: d401c832dd3b29de609e9eaab69ea3334d6591b9
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417686"
---
# <a name="lambda-expressions-c-programming-guide"></a>Lambdaausdrücke (C#-Programmierhandbuch)

Ein *Lambdaausdruck* ist ein Ausdruck in einer der beiden folgenden Formen:

- Ein [Ausdruckslambda](#expression-lambdas) mit einem Ausdruck als Text:

  ```csharp
  (input-parameters) => expression
  ```

- Ein [Anweisungslambda](#statement-lambdas) mit einem Anweisungsblock als Text:

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

Verwenden Sie den [Lambdadeklarationsoperator `=>`](../../language-reference/operators/lambda-operator.md), um die Parameterliste des Lambdas von dessen Text zu trennen. Geben Sie zum Erstellen eines Lambdaausdrucks Eingabeparameter (falls vorhanden) auf der linken Seite des Lambdaoperators und einen Ausdruck oder Anweisungsblock auf der anderen Seite an.

Jeder Lambdaausdruck kann in einen [Delegat](../../language-reference/builtin-types/reference-types.md#the-delegate-type)-Typ konvertiert werden. Der Delegattyp, in den ein Lambdaausdruck konvertiert werden kann, wird durch die Typen seiner Parameter und Rückgabewerte definiert. Wenn ein Lambdaausdruck keinen Wert zurückgibt, kann er in einen der `Action`-Delegattypen konvertiert werden. Andernfalls kann er in einen der `Func`-Delegattypen konvertiert werden. Ein Lambdaausdruck, der beispielsweise zwei Parameter hat und keinen Wert zurückgibt, kann in einen <xref:System.Action%602>-Delegat konvertiert werden. Außerdem kann ein Lambdaausdruck, der einen Parameter hat und einen Wert zurückgibt, in einen <xref:System.Func%602>-Delegat konvertiert werden. Im folgenden Beispiel wird der Lambdaausdruck `x => x * x`, der einen Parameter `x` angibt und den Wert von `x` im Quadrat zurückgibt, einer Variablen eines Delegattyps zugewiesen:

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

Zudem lassen sich Ausdruckslambdas in [Ausdrucksbaumstruktur](../concepts/expression-trees/index.md)-Typen konvertieren, wie im folgenden Beispiel gezeigt:

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

Sie können Lambdaausdrücke in jedem Code verwenden, der Instanzen von Delegattypen oder Ausdrucksbaumstrukturen erfordert, z.B. als Argument für die <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>-Methode, um den im Hintergrund auszuführenden Code zu übergeben. Wie im folgenden Beispiel gezeigt wird, können Sie beim Schreiben von [LINQ in C#](../../linq/index.md) auch Lambdaausdrücke verwenden:

[!code-csharp-interactive[lambda is argument in LINQ](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

Wenn Sie zum Aufrufen der <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType>-Methode in der <xref:System.Linq.Enumerable?displayProperty=nameWithType>-Klasse methodenbasierte Syntax verwenden, wie in LINQ to Objects und LINQ to XML, ist der Parameter ein Delegattyp <xref:System.Func%602?displayProperty=nameWithType>. Wenn Sie die <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>-Methode in der <xref:System.Linq.Queryable?displayProperty=nameWithType>-Klasse aufrufen, wie in LINQ to SQL, ist der Parametertyp ein Ausdrucksbaumstruktur-Typ [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>). In beiden Fällen können Sie denselben Lambdaausdruck verwenden, um die Parameterwerte anzugeben. Dadurch sehen die `Select`-Aufrufe ähnlich aus, obwohl sich der mithilfe der Lambdas erstellte Objekttyp unterscheidet.
  
## <a name="expression-lambdas"></a>Ausdruckslambdas

Ein Lambdaausdruck mit einem Ausdruck auf der rechten Seite des `=>`-Operators wird als *Ausdruckslambda* bezeichnet. Ausdruckslambdas werden häufig bei der Erstellung von [Ausdrucksbaumstrukturen](../concepts/expression-trees/index.md) verwendet. Ein Ausdruckslambda gibt das Ergebnis des Ausdrucks zurück und hat folgende grundlegende Form:

```csharp
(input-parameters) => expression
```

Die Klammern sind nur optional, wenn das Lambda über einen Eingabeparameter verfügt; andernfalls sind sie erforderlich.

Geben Sie Eingabeparameter von 0 (null) mit leeren Klammern an:  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

Zwei oder mehr Eingabeparameter sind durch Kommas getrennt und in Klammern eingeschlossen:

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

Für den Compiler ist es manchmal unmöglich, die Eingabetypen abzuleiten. Sie können die Typen wie im folgenden Beispiel dargestellt explizit angeben:

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

Eingabeparametertypen müssen alle entweder explizit oder implizit sein. Andernfalls tritt der Compilerfehler [CS0748](../../misc/cs0748.md) auf.

Der Text eines Ausdruckslambdas kann aus einem Methodenaufruf bestehen. Wenn Sie jedoch Ausdrucksbaumstrukturen erstellen, die außerhalb des Kontexts der .NET Common Language Runtime ausgewertet werden, z.B. in SQL Server, sollten Sie in Lambdaausdrücken keine Methodenaufrufe verwenden. Die Methoden haben außerhalb des Kontexts der .NET Common Language Runtime keine Bedeutung.

## <a name="statement-lambdas"></a>Anweisungslambdas

Ein Anweisungslambda ähnelt einem Ausdruckslambda, allerdings sind die Anweisungen in Klammern eingeschlossen:

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

Der Text eines Anweisungslambdas kann aus einer beliebigen Anzahl von Anweisungen bestehen, wobei es sich meistens um höchstens zwei oder drei Anweisungen handelt.

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

Anweisungslambdas können nicht zum Erstellen von Ausdrucksbaumstrukturen verwendet werden.
  
## <a name="async-lambdas"></a>Asynchrone Lambdas

Sie können mit den Schlüsselwörtern [async](../../language-reference/keywords/async.md) und [await](../../language-reference/operators/await.md) Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten, leicht erstellen. Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.

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

Sie können denselben Ereignishandler hinzufügen, indem Sie ein asynchrones Lambda verwenden. Um diesen Handler hinzuzufügen, fügen Sie einen `async`-Modifizierer vor der Lambdaparameterliste hinzu, wie im folgenden Beispiel dargestellt:

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

Weitere Informationen zum Erstellen und Verwenden von asynchronen Methoden finden Sie unter [Asynchronous programming with async and await (Asynchrones Programmieren mit „async“ and „await“)](../concepts/async/index.md).

## <a name="lambda-expressions-and-tuples"></a>Lambdaausdrücke und Tupel

Ab C# 7.0 bietet die C#-Programmiersprache integrierte Unterstützung für [Tupel](../../tuples.md). Sie können ein Tupel einem Lambdaausdruck als Argument bereitstellen, und Ihr Lambdaausdruck kann ebenfalls einen Tupel zurückgeben. In einigen Fällen verwendet der C#-Compiler den Typrückschluss, um den Typ der Tupelkomponenten zu ermitteln.

Sie können ein Tupel definieren, indem Sie eine durch Trennzeichen getrennte Liste seiner Komponenten in Klammern einschließen. In folgendem Beispiel wird ein Tupel mit drei Komponenten verwenden, um eine Zahlensequenz an einen Lambdaausdruck zu übergeben; dadurch wird jeder Wert verdoppelt, und es wird ein Tupel mit drei Komponenten zurückgegeben, das das Ergebnis der Multiplikation enthält.

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

Für gewöhnlich heißen die Felder eines Tupels `Item1`, `Item2`, usw. Sie können allerdings ein Tupel mit benannten Komponenten definieren, wie in folgendem Beispiel veranschaulicht.

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

Weitere Informationen zu C#-Tupeln finden Sie unter [C#-Tupeltypen](../../tuples.md).

## <a name="lambdas-with-the-standard-query-operators"></a>Lambdas mit Standardabfrageoperatoren

LINQ to Objects haben, neben anderen Implementierungen, einen Eingabeparameter, dessen Typ Teil der <xref:System.Func%601>-Familie generischer Delegate ist. Diese Delegaten verwenden Typparameter zur Definition der Anzahl und des Typs der Eingabeparameter sowie des Rückgabetyps des Delegaten. `Func` -Delegaten sind für das Kapseln von benutzerdefinierten Ausdrücken, die für jedes Element in einem Satz von Quelldaten übernommen werden, sehr nützlich. Betrachten Sie z.B. den <xref:System.Func%602>-Delegattyp:  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

Der Delegat kann als `Func<int, bool>`-Instanz instanziiert werden, wobei `int` ein Eingabeparameter und `bool` der Rückgabewert ist. Der Rückgabewert wird immer im letzten Typparameter angegeben. `Func<int, string, bool>` definiert z.B. einen Delegaten mit zwei Eingabeparametern, `int` und `string`, und einen Rückgabetyp von `bool`. Der folgende `Func`-Delegat gibt bei einem Aufruf einen booleschen Wert zurück, um anzugeben, ob der Eingabeparameter gleich fünf ist:

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

Sie können einen Lambdaausdruck auch dann angeben, wenn der Argumenttyp <xref:System.Linq.Expressions.Expression%601> ist, beispielsweise in den Standardabfrageoperatoren, die in Typ <xref:System.Linq.Queryable> definiert sind. Wenn Sie ein <xref:System.Linq.Expressions.Expression%601>-Argument angeben, wird der Lambdaausdruck in eine Ausdrucksbaumstruktur kompiliert.
  
Im folgenden Beispiel wird der <xref:System.Linq.Enumerable.Count%2A>-Standardabfrageoperator verwendet:

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

Der Compiler kann den Typ des Eingabeparameters ableiten, Sie können ihn aber auch explizit angeben. Dieser bestimmte Lambda-Ausdruck zählt die ganzen Zahlen (`n`), bei denen nach dem Dividieren durch zwei als Rest 1 bleibt.

In folgendem Beispiel wird eine Sequenz erzeugt, die alle Elemente im Array `numbers` enthält, die vor der 9 auftreten, da dies die erste Zahl in der Sequenz ist, die die Bedingung nicht erfüllt:

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

In folgendem Beispiel wird gezeigt, wie Sie mehrere Eingabeparameter angeben, indem Sie sie in Klammern einschließen. Mit der Methode werden alle Elemente im `numbers`-Array zurückgegeben, bis eine Zahl erreicht wird, deren Wert kleiner ist als ihre Ordnungspostion im Array:

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a>Typrückschluss in Lambdaausdrücken

Beim Schreiben von Lambdas müssen Sie oftmals keinen Typ für die Eingabeparameter angeben, da der Compiler den Typ auf der Grundlage des Lambdatexts, der Parametertypen und anderer Faktoren ableiten kann, wie in der C#-Programmiersprachenspezifikation beschrieben. Bei den meisten Standardabfrageoperatoren entspricht die erste Eingabe dem Typ der Elemente in der Quellsequenz. Beim Abfragen von `IEnumerable<Customer>` wird die Eingabevariable als `Customer`-Objekt abgeleitet, sodass Sie auf die zugehörigen Methoden und Eigenschaften zugreifen können:  

```csharp
customers.Where(c => c.City == "London");
```

Die allgemeinen Regeln für Typrückschlüsse bei Lambdas lauten wie folgt:

- Der Lambda-Ausdruck muss dieselbe Anzahl von Parametern enthalten wie der Delegattyp.

- Jeder Eingabeparameter im Lambda muss implizit in den entsprechenden Delegatparameter konvertiert werden können.

- Der Rückgabewert des Lambdas (falls vorhanden) muss implizit in den Rückgabetyp des Delegaten konvertiert werden können.
  
Beachten Sie, dass Lambdaausdrücke keinen eigenen Typ haben, da das allgemeine Typsystem kein internes Konzept von „Lambdaausdrücken“ aufweist. Es kann manchmal praktisch sein, informell vom „Typ“ eines Lambdaausdrucks zu sprechen. In einem solchen Fall bezeichnet Typ den Delegattyp bzw. den <xref:System.Linq.Expressions.Expression> -Typ, in den der Lambda-Ausdruck konvertiert wird.

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a>Erfassen äußerer Variablen sowie des Variablenbereichs in Lambdaausdrücken

Lambdas können auf *äußere Variablen* verweisen. Hierbei handelt es sich um die Variablen, die im Bereich der Methode, mit der der Lambdaausdruck definiert wird, oder im Bereich des Typs liegen, der den Lambdaausdruck enthält. Variablen, die auf diese Weise erfasst werden, werden zur Verwendung in Lambda-Ausdrücken gespeichert, auch wenn die Variablen andernfalls außerhalb des Gültigkeitsbereichs liegen und an die Garbage Collection übergeben würden. Eine äußere Variable muss definitiv zugewiesen sein, bevor sie in einem Lambda-Ausdruck verwendet werden kann. Das folgende Beispiel veranschaulicht diese Regeln:

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

Die folgenden Regeln gelten für den Variablenbereich in Lambda-Ausdrücken:  

- Eine erfasste Variable wird erst dann an die Garbage Collection übergeben, wenn der darauf verweisende Delegat für die Garbage Collection geeignet ist.

- Variablen, die in einem Lambdaausdruck eingeführt wurden, sind in der einschließenden Methode nicht sichtbar.

- Ein Lambdaausdruck kann einen [in](../../language-reference/keywords/in-parameter-modifier.md)-, [ref](../../language-reference/keywords/ref.md)- oder [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter nicht direkt von der einschließenden Methode erfassen.

- Eine [return](../../language-reference/keywords/return.md)-Anweisung in einem Lambdaausdruck bewirkt keine Rückgabe durch die einschließende Methode.

- Ein Lambdaausdruck darf keine [goto](../../language-reference/keywords/goto.md)-, [break](../../language-reference/keywords/break.md)- oder [continue](../../language-reference/keywords/continue.md)-Anweisung enthalten, wenn das Ziel dieser Sprunganweisung außerhalb des Lambdaausdrucksblocks liegt. Eine Sprunganweisung darf auch nicht außerhalb des Lambdaausdrucksblocks sein, wenn das Ziel im Block ist.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="featured-book-chapter"></a>Enthaltenes Buchkapitel

[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegaten, Ereignisse und Lambda-Ausdrücke) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (C# 3.0-Cookbook, 3. Auflage: Mehr als 250 Lösungen für C# 3.0-Programmierer)  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [LINQ (Language Integrated Query)](../concepts/linq/index.md)
- [Ausdrucksbaumstrukturen](../concepts/expression-trees/index.md)
- [Lokale Funktionen im Vergleich zu Lambdaausdrücken](../../local-functions-vs-lambdas.md)
- [Implizit typisierte Lambdaausdrücke](../../implicitly-typed-lambda-expressions.md)
- [Visual Studio 2008 C#-Beispiele (siehe LINQ-Beispielabfragedateien und XQuery-Programm)](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [Rekursive Lambda-Ausdrücke](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
