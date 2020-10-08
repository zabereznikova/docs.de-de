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
ms.openlocfilehash: a3a753ccea45193c57f31453d7318c14f4898864
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247708"
---
# <a name="lambda-expressions-c-reference"></a>Lambdaausdrücke (C#-Referenz)

Ein *Lambdaausdruck* ist ein Ausdruck in einer der beiden folgenden Formen:

- Ein [Ausdruckslambda](#expression-lambdas) mit einem Ausdruck als Text:

  ```csharp
  (input-parameters) => expression
  ```

- Ein [Anweisungslambda](#statement-lambdas) mit einem Anweisungsblock als Text:

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

Verwenden Sie den [Lambdadeklarationsoperator `=>`](lambda-operator.md), um die Parameterliste des Lambdas von dessen Text zu trennen. Geben Sie zum Erstellen eines Lambdaausdrucks Eingabeparameter (falls vorhanden) auf der linken Seite des Lambdaoperators und einen Ausdruck oder Anweisungsblock auf der anderen Seite an.

Jeder Lambdaausdruck kann in einen [Delegat](../builtin-types/reference-types.md#the-delegate-type)-Typ konvertiert werden. Der Delegattyp, in den ein Lambdaausdruck konvertiert werden kann, wird durch die Typen seiner Parameter und Rückgabewerte definiert. Wenn ein Lambdaausdruck keinen Wert zurückgibt, kann er in einen der `Action`-Delegattypen konvertiert werden. Andernfalls kann er in einen der `Func`-Delegattypen konvertiert werden. Ein Lambdaausdruck, der beispielsweise zwei Parameter hat und keinen Wert zurückgibt, kann in einen <xref:System.Action%602>-Delegat konvertiert werden. Außerdem kann ein Lambdaausdruck, der einen Parameter hat und einen Wert zurückgibt, in einen <xref:System.Func%602>-Delegat konvertiert werden. Im folgenden Beispiel wird der Lambdaausdruck `x => x * x`, der einen Parameter `x` angibt und den Wert von `x` im Quadrat zurückgibt, einer Variablen eines Delegattyps zugewiesen:

[!code-csharp-interactive[lambda is delegate](snippets/lambda-expressions/Introduction.cs#Delegate)]

Zudem lassen sich Ausdruckslambdas in [Ausdrucksbaumstruktur](../../programming-guide/concepts/expression-trees/index.md)-Typen konvertieren, wie im folgenden Beispiel gezeigt:

[!code-csharp-interactive[lambda is expression tree](snippets/lambda-expressions/Introduction.cs#ExpressionTree)]

Sie können Lambdaausdrücke in jedem Code verwenden, der Instanzen von Delegattypen oder Ausdrucksbaumstrukturen erfordert, z.B. als Argument für die <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>-Methode, um den im Hintergrund auszuführenden Code zu übergeben. Wie im folgenden Beispiel gezeigt wird, können Sie beim Schreiben von [LINQ in C#](../../linq/index.md) auch Lambdaausdrücke verwenden:

[!code-csharp-interactive[lambda is argument in LINQ](snippets/lambda-expressions/Introduction.cs#Argument)]

Wenn Sie zum Aufrufen der <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType>-Methode in der <xref:System.Linq.Enumerable?displayProperty=nameWithType>-Klasse methodenbasierte Syntax verwenden, wie in LINQ to Objects und LINQ to XML, ist der Parameter ein Delegattyp <xref:System.Func%602?displayProperty=nameWithType>. Wenn Sie die <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>-Methode in der <xref:System.Linq.Queryable?displayProperty=nameWithType>-Klasse aufrufen, wie in LINQ to SQL, ist der Parametertyp ein Ausdrucksbaumstruktur-Typ [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>). In beiden Fällen können Sie denselben Lambdaausdruck verwenden, um die Parameterwerte anzugeben. Dadurch sehen die `Select`-Aufrufe ähnlich aus, obwohl sich der mithilfe der Lambdas erstellte Objekttyp unterscheidet.
  
## <a name="expression-lambdas"></a>Ausdruckslambdas

Ein Lambdaausdruck mit einem Ausdruck auf der rechten Seite des `=>`-Operators wird als *Ausdruckslambda* bezeichnet. Ein Ausdruckslambda gibt das Ergebnis des Ausdrucks zurück und hat folgende grundlegende Form:

```csharp
(input-parameters) => expression
```

Der Text eines Ausdruckslambdas kann aus einem Methodenaufruf bestehen. Wenn Sie jedoch [Ausdrucksbaumstrukturen](../../programming-guide/concepts/expression-trees/index.md) erstellen, die außerhalb des Kontexts der .NET Common Language Runtime ausgewertet werden, z. B. in SQL Server, sollten Sie in Lambdaausdrücken keine Methodenaufrufe verwenden. Die Methoden haben außerhalb des Kontexts der .NET Common Language Runtime keine Bedeutung.

## <a name="statement-lambdas"></a>Anweisungslambdas

Ein Anweisungslambda ähnelt einem Ausdruckslambda, allerdings sind die Anweisungen in Klammern eingeschlossen:

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

Der Text eines Anweisungslambdas kann aus einer beliebigen Anzahl von Anweisungen bestehen, wobei es sich meistens um höchstens zwei oder drei Anweisungen handelt.

:::code language="csharp" interactive="try-dotnet-method" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatementLambda":::

Anweisungslambdas können nicht zum Erstellen von Ausdrucksbaumstrukturen verwendet werden.

## <a name="input-parameters-of-a-lambda-expression"></a>Eingabeparameter eines Lambdaausdrucks

Sie schließen die Eingabeparameter eines Lambdaausdrucks in Klammern ein. Geben Sie Eingabeparameter von 0 (null) mit leeren Klammern an:  

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetZeroParameters":::

Wenn ein Lambdaausdruck nur über einen Eingabeparameter verfügt, sind Klammern optional:

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetOneParameter":::

Zwei oder mehr Eingabeparameter werden durch Kommas getrennt:

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetTwoParameters":::

Manchmal kann der Compiler die Typen von Eingabeparametern nicht ableiten. Sie können die Typen wie im folgenden Beispiel dargestellt explizit angeben:

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetExplicitlyTypedParameters":::

Eingabeparametertypen müssen alle entweder explizit oder implizit sein. Andernfalls tritt der Compilerfehler [CS0748](../../misc/cs0748.md) auf.

Ab C# 9.0 können Sie [discards](../../discards.md) verwenden, um mindestens zwei Eingabeparameter eines Lambdaausdrucks anzugeben, der nicht im Ausdruck verwendet wird:

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetDiscards":::

Verwerfungsparameter von Lambdas können nützlich sein, wenn Sie einen Lambdaausdruck zur [Bereitstellung eines Ereignishandlers](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) verwenden.

> [!NOTE]
> Aus Gründen der Abwärtskompatibilität wird innerhalb eines Lambdaausdrucks `_` als Name des Parameters behandelt, wenn nur ein einzelner Eingabeparameter den Namen `_` aufweist.

## <a name="async-lambdas"></a>Asynchrone Lambdas

Sie können mit den Schlüsselwörtern [async](../keywords/async.md) und [await](await.md) Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten, leicht erstellen. Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.

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

Weitere Informationen zum Erstellen und Verwenden von asynchronen Methoden finden Sie unter [Asynchronous programming with async and await (Asynchrones Programmieren mit „async“ and „await“)](../../programming-guide/concepts/async/index.md).

## <a name="lambda-expressions-and-tuples"></a>Lambdaausdrücke und Tupel

Ab C# 7.0 bietet die C#-Programmiersprache integrierte Unterstützung für [Tupel](../builtin-types/value-tuples.md). Sie können ein Tupel einem Lambdaausdruck als Argument bereitstellen, und Ihr Lambdaausdruck kann ebenfalls einen Tupel zurückgeben. In einigen Fällen verwendet der C#-Compiler den Typrückschluss, um den Typ der Tupelkomponenten zu ermitteln.

Sie können ein Tupel definieren, indem Sie eine durch Trennzeichen getrennte Liste seiner Komponenten in Klammern einschließen. In folgendem Beispiel wird ein Tupel mit drei Komponenten verwenden, um eine Zahlensequenz an einen Lambdaausdruck zu übergeben; dadurch wird jeder Wert verdoppelt, und es wird ein Tupel mit drei Komponenten zurückgegeben, das das Ergebnis der Multiplikation enthält.

[!code-csharp-interactive[lambda and tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

Für gewöhnlich heißen die Felder eines Tupels `Item1`, `Item2`, usw. Sie können allerdings ein Tupel mit benannten Komponenten definieren, wie in folgendem Beispiel veranschaulicht.

[!code-csharp-interactive[lambda and named tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

Weitere Informationen zu C#-Tupeln finden Sie unter [Tupeltypen](../../language-reference/builtin-types/value-tuples.md).

## <a name="lambdas-with-the-standard-query-operators"></a>Lambdas mit Standardabfrageoperatoren

LINQ to Objects haben, neben anderen Implementierungen, einen Eingabeparameter, dessen Typ Teil der <xref:System.Func%601>-Familie generischer Delegate ist. Diese Delegaten verwenden Typparameter zur Definition der Anzahl und des Typs der Eingabeparameter sowie des Rückgabetyps des Delegaten. `Func` -Delegaten sind für das Kapseln von benutzerdefinierten Ausdrücken, die für jedes Element in einem Satz von Quelldaten übernommen werden, sehr nützlich. Betrachten Sie z.B. den <xref:System.Func%602>-Delegattyp:  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

Der Delegat kann als `Func<int, bool>`-Instanz instanziiert werden, wobei `int` ein Eingabeparameter und `bool` der Rückgabewert ist. Der Rückgabewert wird immer im letzten Typparameter angegeben. `Func<int, string, bool>` definiert z.B. einen Delegaten mit zwei Eingabeparametern, `int` und `string`, und einen Rückgabetyp von `bool`. Der folgende `Func`-Delegat gibt bei einem Aufruf einen booleschen Wert zurück, um anzugeben, ob der Eingabeparameter gleich fünf ist:

[!code-csharp-interactive[Func example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

Sie können einen Lambdaausdruck auch dann angeben, wenn der Argumenttyp <xref:System.Linq.Expressions.Expression%601> ist, beispielsweise in den Standardabfrageoperatoren, die in Typ <xref:System.Linq.Queryable> definiert sind. Wenn Sie ein <xref:System.Linq.Expressions.Expression%601>-Argument angeben, wird der Lambdaausdruck in eine Ausdrucksbaumstruktur kompiliert.
  
Im folgenden Beispiel wird der <xref:System.Linq.Enumerable.Count%2A>-Standardabfrageoperator verwendet:

[!code-csharp-interactive[Count example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

Der Compiler kann den Typ des Eingabeparameters ableiten, Sie können ihn aber auch explizit angeben. Dieser bestimmte Lambda-Ausdruck zählt die ganzen Zahlen (`n`), bei denen nach dem Dividieren durch zwei als Rest 1 bleibt.

In folgendem Beispiel wird eine Sequenz erzeugt, die alle Elemente im Array `numbers` enthält, die vor der 9 auftreten, da dies die erste Zahl in der Sequenz ist, die die Bedingung nicht erfüllt:

[!code-csharp-interactive[TakeWhile example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

In folgendem Beispiel wird gezeigt, wie Sie mehrere Eingabeparameter angeben, indem Sie sie in Klammern einschließen. Mit der Methode werden alle Elemente im `numbers`-Array zurückgegeben, bis eine Zahl erreicht wird, deren Wert kleiner ist als ihre Ordnungspostion im Array:

[!code-csharp-interactive[TakeWhile example 2](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

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

[!code-csharp[variable scope](snippets/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

Die folgenden Regeln gelten für den Variablenbereich in Lambda-Ausdrücken:  

- Eine erfasste Variable wird erst dann an die Garbage Collection übergeben, wenn der darauf verweisende Delegat für die Garbage Collection geeignet ist.

- Variablen, die in einem Lambdaausdruck eingeführt wurden, sind in der einschließenden Methode nicht sichtbar.

- Ein Lambdaausdruck kann einen [in](../keywords/in-parameter-modifier.md)-, [ref](../keywords/ref.md)- oder [out](../keywords/out-parameter-modifier.md)-Parameter nicht direkt von der einschließenden Methode erfassen.

- Eine [return](../keywords/return.md)-Anweisung in einem Lambdaausdruck bewirkt keine Rückgabe durch die einschließende Methode.

- Ein Lambdaausdruck darf keine [goto](../keywords/goto.md)-, [break](../keywords/break.md)- oder [continue](../keywords/continue.md)-Anweisung enthalten, wenn das Ziel dieser Sprunganweisung außerhalb des Lambdaausdrucksblocks liegt. Eine Sprunganweisung darf auch nicht außerhalb des Lambdaausdrucksblocks sein, wenn das Ziel im Block ist.

Ab C# 9.0 können Sie den `static`-Modifizierer auf einen Lambdaausdruck anwenden, um zu verhindern, dass lokale Variablen oder der Instanzzustand versehentlich durch die Lambdafunktion erfasst werden:

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatic":::

Ein statischer Lambdaausdruck kann keine lokalen Variablen oder den Instanzzustand aus einschließenden Bereichen erfassen, kann jedoch auf statische Member und Konstantendefinitionen verweisen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Weitere Informationen zu in C# 9.0 eingeführten Features finden Sie in den folgenden Featurevorschlägen:

- [Parameter zum Verwerfen von Lambdafunktion](~/_csharplang/proposals/csharp-9.0/lambda-discard-parameters.md)
- [Statische anonyme Funktionen](~/_csharplang/proposals/csharp-9.0/static-anonymous-functions.md)

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [LINQ (Language Integrated Query)](../../programming-guide/concepts/linq/index.md)
- [Ausdrucksbaumstrukturen](../../programming-guide/concepts/expression-trees/index.md)
- [Lokale Funktionen im Vergleich zu Lambdaausdrücken](../../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions)
- [Visual Studio 2008 C#-Beispiele (siehe LINQ-Beispielabfragedateien und XQuery-Programm)](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
