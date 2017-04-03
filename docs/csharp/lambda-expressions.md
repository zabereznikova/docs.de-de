---
title: "Lambda-Ausdrücke"
description: "Erfahren Sie, wie sie Lambdaausdrücke verwenden können. Lambdaausdrücke sind ausführbare Codeblöcke, die als Argumente übergeben werden können."
keywords: ".NET, .NET Core, lambdaausdrücke, lambdas, delegate"
ms-author: ronpet
author: rpetrusha
ms.date: 11/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: b6a0539a-8ce5-4da7-adcf-44be345a2714
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 82b912eb393aeaf6e222f2ce20e6a1a99b4a3662
ms.lasthandoff: 03/13/2017

---

# <a name="lambda-expressions"></a>Lambdaausdrücke #

Ein *Lambdaausdruck* ist ein Codeblock (bzw. ein Ausdrucks- oder ein Anweisungsblock), der wie ein Objekt behandelt wird. Er kann als Argument an eine Methode übergeben werden, und er kann auch von Methodenaufrufen zurückgegeben werden. Lambdaausdrücke finden bei folgenden Aktionen Anwendung:

- Bei der Übergabe von Code, der als asynchrone Methode ausgeführt wird, wie z.B. @System.Threading.Tasks.Task.Run(System.Action).

- Bei [LINQ-Abfrageausdrücken](linq/index.md).

- Bei Erstellen von [Ausdrucksbaumstrukturen](expression-trees-building.md).

Lambdaausdrücke sind Code, der entweder als Delegat oder als eine Ausdrucksbaumstruktur repräsentiert werden kann, die an einen Delegat kompiliert. Der genaue Delegattyp eines Lambdaausdrucks hängt von dessen Parametern und Rückgabewert ab. Lambdaausdrücke, die keinen Wert zurückgeben, korrespondieren mit einem bestimmten `Action`-Delegat, abhängig von der Anzahl seiner Parameter. Lambdaausdrücke, die keinen Wert zurückgeben, entsprechen einem bestimmten `Func`-Delegat, abhängig von der Anzahl seiner Parameter. Ein Lambdaausdruck, der beispielsweise zwei Parameter hat, aber keinen Wert zurück gibt, entspricht einem @System.Action%602-Delegat. Ein Lambdaausdruck, der beispielsweise zwei Parameter hat, aber keinen Wert zurück gibt, entspricht einem @System.Func%602-Delegat.

Ein Lambdaausdruck verwendet `=>`, den [Lambdadeklarationsoperator](language-reference/operators/lambda-operator.md), um die Parameterliste des Lambdas von dessen ausführbarem Code zu trennen. Zum Erstellen eines Lambdaausdrucks geben Sie Eingabeparameter (falls vorhanden) auf der linken Seite des Lambdaoperators an und stellen den Ausdrucks- oder Anweisungsblock auf die andere Seite. Beispielsweise gibt der Einzelzeilen-Lambdaausdruck `x => x * x` einen Parameter an, der `x` heißt und das Quadrat des Werts von `x` zurückgibt. Dieser Ausdruck kann einem Delegattyp zuwiesen werden, wie im folgenden Beispiel dargestellt:

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/lambda1.cs#1)]

Sie können ihn aber auch als Methodenargument übergeben:

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/lambda2.cs#2)]

## <a name="expression-lambdas"></a>Ausdruckslambdas ##

 Ein Lambdaausdruck mit einem Ausdruck auf der rechten Seite des Operators „=>“ wird als *Ausdruckslambda* bezeichnet. Ausdruckslambdas werden häufig bei der Erstellung von [Ausdrucksbaumstrukturen](expression-trees.md) verwendet. Ein Ausdruckslambda gibt das Ergebnis des Ausdrucks zurück und hat folgende grundlegende Form:

```csharp
(input parameters) => expression
```

Die Klammern sind nur optional, wenn das Lambda über einen Eingabeparameter verfügt; andernfalls sind sie erforderlich. Geben Sie Eingabeparameter von 0 (null) mit leeren Klammern an:

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#1)]

Zwei oder mehr Eingabeparameter sind durch Kommas getrennt und in Klammern eingeschlossen:

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#2)]

Für gewöhnlich verwendet der Compiler den Typrückschluss, um Parametertypen zu ermitteln. Für den Compiler kann es jedoch schwierig oder unmöglich sein, die Eingabetypen abzuleiten. Wenn dieses Problem auftritt, können Sie die Typen explizit angeben, wie im folgenden Beispiel dargestellt:

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#3)]

Beachten Sie im vorherigen Beispiel, dass der Text eines Ausdruckslambdas ein Methodenaufruf sein kann. Wenn Sie allerdings Ausdrucksbaumstrukturen erstellen, die außerhalb des .NET Frameworks ausgewertet werden, wie z.B. in SQL Server oder Entity Framework (EF), sollten Sie davon absehen, Methodenaufrufe in Lambdaausdrücken zu verwenden, da die Methoden möglicherweise außerhalb des Kontexts der .NET-Laufzeit bedeutungslos sind. Falls Sie dennoch Methodenaufrufe verwenden möchten, prüfen Sie diese gründlich, um sicherzustellen, dass die Methodenaufrufe erfolgreich aufgelöst werden können.

## <a name="statement-lambdas"></a>Anweisungslambdas ##

Ein Anweisungslambda ähnelt einem Ausdruckslambda, allerdings sind die Anweisungen in Klammern eingeschlossen:

```csharp
(input parameters) => { statement; }
```

Der Text eines Anweisungslambdas kann aus einer beliebigen Anzahl von Anweisungen bestehen, wobei es sich meistens um höchstens zwei oder drei Anweisungen handelt.

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/statement1.cs#1)]

Anweisungslambdas, wie anonyme Methoden, können nicht zum Erstellen von Ausdrucksbaumstrukturen verwendet werden.

## <a name="async-lambdas"></a>Asynchrone Lambdas ##

Sie können mit den Schlüsselwörtern [async](language-reference/keywords/async.md) und [await](language-reference/keywords/await.md) Lambdaausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten, leicht erstellen. Das Beispiel ruft beispielsweise eine `ShowSquares`-Methode auf, die asynchron ausgeführt wird.

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/async1.cs#1)]

Weitere Informationen zum Erstellen und Verwenden von asynchronen Methoden finden Sie unter [Asynchronous programming with async and await (Asynchrones Programmieren mit „async“ and „await“)](programming-guide/concepts/async/index.md).

## <a name="lambda-expressions-and-tuples"></a>Lambdaausdrücke und Tupel ##

Ab C# 7.0 bietet die C#-Programmiersprache integrierten Support für Tupel. Sie können ein Tupel einem Lambdaausdruck als Argument bereitstellen, und Ihr Lambdaausdruck kann ebenfalls einen Tupel zurückgeben. In einigen Fällen verwendet der C#-Compiler den Typrückschluss, um den Typ der Tupelkomponenten zu ermitteln. 

Sie können ein Tupel definieren, indem Sie eine durch Trennzeichen getrennte Liste seiner Komponenten in Klammern einschließen. In folgendem Beispiel wird ein Tupel mit fünf Komponenten verwenden, um eine Zahlensequenz an einen Lambdaausdruck zu übergeben; dadurch wird jeder Wert verdoppelt, und es wird ein Tupel mit fünf Komponenten zurückgegeben, das das Ergebnis der Multiplikation enthält.

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/tuples1.cs#1)]

Für gewöhnlich heißen die Felder eines Tupels `Item1`, `Item2`, usw. Sie können allerdings ein Tupel mit benannten Komponenten definieren, wie in folgendem Beispiel veranschaulicht.

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/tuples2.cs#1)]

Weitere Informationen zum Support für Tupel in C# finden Sie unter [C# Tuple types (C#-Tupeltypen)](tuples.md).

## <a name="lambdas-with-the-standard-query-operators"></a>Lambdas mit Standardabfrageoperatoren ##

LINQ to Objects haben, neben anderen Implementierungen, einen Eingabeparameter, dessen Typ Teil der @System.Func%601-Familie generischer Delegate ist. Diese Delegaten verwenden Typparameter zur Definition der Anzahl und des Typs der Eingabeparameter sowie des Rückgabetyps des Delegaten. `Func`-Delegaten sind für das Kapseln von benutzerdefinierten Ausdrücken, die für jedes Element in einem Satz von Quelldaten übernommen werden, sehr nützlich. Berücksichtigen z.B. den @System.Func%601-Delegaten, dessen Syntax wie folgt lautet:

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#1)]

Der Delegat kann mit Code wie dem folgenden instanziiert werden

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#2)]

Hier ist `int` ein Eingabeparameter, und `bool` ist der Rückgabewert. Der Rückgabewert wird immer im letzten Typparameter angegeben. Wenn der folgende `Func`-Delegat aufgerufen wird, gibt er TRUE oder FALSE zurück, um anzugeben, ob der Eingabeparameter gleich 5 ist:

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#3)]

Sie können einen Lambdaausdruck auch dann angeben, wenn der Argumenttyp @System.Linq.Expressions.Expression&601 ist, beispielsweise in den Standardabfrageoperatoren, die im Typ @System.Linq.Queryable definiert sind. Wenn Sie ein @System.Linq.Expressions.Expression%601-Argument angeben, wird der Lambdaausdruck in eine Ausdrucksbaumstruktur kompiliert. In folgendem Beispiel wird der Standardabfrageoperator [System.Linq.Enumerable.Count](xref:System.Linq.Enumerable.Count%60%601(System.Collections.Generic.IEnumerable{%60%600})) verwendet.

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#4)]

Der Compiler kann den Typ des Eingabeparameters ableiten, Sie können ihn aber auch explizit angeben. Dieser bestimmte Lambdaausdruck zählt die Ganzzahlen (`n`), bei denen nach dem Dividieren durch zwei als Rest 1 bleibt.

In folgendem Beispiel wird eine Sequenz erzeugt, die alle Elemente im Array `numbers` enthält, die vor der 9 auftreten, da dies die erste Zahl in der Sequenz ist, die die Bedingung nicht erfüllt.

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#5)]

In folgendem Beispiel wird gezeigt, wie Sie mehrere Eingabeparameter angeben, indem Sie sie in Klammern einschließen. Mit der Methode werden alle Elemente im Zahlenarray zurückgegeben, bis eine Zahl erreicht wird, deren Wert kleiner ist als seine Ordnungspostion im Array.

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#6)]

## <a name="type-inference-in-lambda-expressions"></a>Typrückschluss in Lambdaausdrücken ##

Beim Schreiben von Lambdas müssen Sie oftmals keinen Typ für die Eingabeparameter angeben, da der Compiler den Typ auf der Grundlage des Lambdatexts, des zugrunde liegenden Typs des Parameters und anderer Faktoren per Rückschluss ableiten kann, wie in der C#-Programmiersprachenspezifikation beschrieben. Bei den meisten Standardabfrageoperatoren entspricht die erste Eingabe dem Typ der Elemente in der Quellsequenz. Beim Abfragen von `IEnumerable<Customer>` wird die Eingabevariable als `Customer`-Objekt abgeleitet, sodass Sie auf die zugehörigen Methoden und Eigenschaften zugreifen können:

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/infer1.cs#1)]

Die allgemeinen Regeln für Typrückschlüsse bei Lambdas lauten wie folgt:

- Der Lambda-Ausdruck muss dieselbe Anzahl von Parametern enthalten wie der Delegattyp.

- Jedes Eingabeargument im Lambda muss implizit in den entsprechenden Delegatparameter konvertierbar sein.

- Der Rückgabewert des Lambdas (falls vorhanden) muss implizit in den Rückgabetyp des Delegaten konvertiert werden können.

Beachten Sie, dass Lambda-Ausdrücke keinen eigenen Typ haben, da das allgemeine Typsystem kein internes Konzept von "Lambda-Ausdrücken" aufweist. Es kann manchmal praktisch sein, informell vom "Typ" eines Lambda-Ausdrucks zu sprechen. In einem solchen Fall bezeichnet Typ den Delegattyp bzw. den @System.Linq.Expressions.Expression-Typ, in den der Lambda-Ausdruck konvertiert wird.

## <a name="variable-scope-in-lambda-expressions"></a>Variablenbereich in Lambda-Ausdrücken ##

Lambdas können auf *äußere Variablen* verweisen (siehe [Anonyme Methoden](programming-guide/statements-expressions-operators/anonymous-methods.md)), die im Bereich der Methode, mit der die Lambdafunktion definiert wird, oder im Bereich des Typs liegen, der den Lambdaausdruck enthält. Variablen, die auf diese Weise erfasst werden, werden zur Verwendung in Lambda-Ausdrücken gespeichert, auch wenn die Variablen andernfalls außerhalb des Gültigkeitsbereichs liegen und an die Garbage Collection übergeben würden. Eine äußere Variable muss definitiv zugewiesen sein, bevor sie in einem Lambda-Ausdruck verwendet werden kann. Das folgende Beispiel veranschaulicht diese Regeln.

[!CODE [csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/scope.cs#1)]

 Die folgenden Regeln gelten für den Variablenbereich in Lambda-Ausdrücken:

- Eine erfasste Variable wird erst dann an die Garbage Collection übergeben, wenn der darauf verweisende Delegat für die Garbage Collection geeignet ist.

- Variablen, die in einem Lambda-Ausdruck eingeführt wurden, sind in der äußeren Methode nicht sichtbar.

- Ein Lambda-Ausdruck kann einen `ref` - oder `out` -Parameter nicht direkt von einer einschließenden Methode erfassen.

- Eine return-Anweisung in einem Lambda-Ausdruck bewirkt keine Rückgabe durch die einschließende Methode.

- Ein Lambda-Ausdruck kann eine `goto` -Anweisung, `break` -Anweisung oder `continue` -Anweisung enthalten, die innerhalb der Lambda-Funktion liegt, wenn das Ziel der jump-Anweisung außerhalb des Blocks liegt. Eine jump-Anweisung darf auch nicht außerhalb des Lambda-Funktionsblocks sein, wenn das Ziel im Block ist.

## <a name="see-also"></a>Siehe auch ##

[LINQ (Language Integrated Query)](../standard/using-linq.md)   
[Anonyme Methoden](programming-guide/statements-expressions-operators/anonymous-methods.md)   
[Ausdrucksbaumstrukturen](expression-trees.md)

