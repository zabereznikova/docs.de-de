---
title: Lokale Funktionen im Vergleich zu Lambdaausdrücken
description: Erfahren Sie, warum lokale Funktionen unter Umständen besser geeignet sind als Lambdaausdrücke.
ms.date: 06/27/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: a644b6868a37b3d6231a514dc37030cae062785a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73038798"
---
# <a name="local-functions-compared-to-lambda-expressions"></a>Lokale Funktionen im Vergleich zu Lambdaausdrücken

Auf den ersten Blick sind [lokale Funktionen](programming-guide/classes-and-structs/local-functions.md) und [Lambdaausdrücke](./programming-guide/statements-expressions-operators/lambda-expressions.md) sehr ähnlich. In vielen Fällen ist die Entscheidung zwischen Lamdaausdrücken und lokalen Funktionen eine Frage des Formats und persönlicher Präferenz. Es gibt allerdings tatsächliche Unterschiede, wann das eine oder das andere verwendet werden kann. Diese sollten Ihnen bekannt sein.

Sehen wir uns die Unterschiede zwischen der Implementierungen des Fakultätsalgorithmus als lokale Funktion und als Lambdaausdruck an. Erste die Version mit einer lokalen Funktion:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

Vergleichen Sie diese Implementierung mit einer Version, die Lambdaausdrücke verwendet:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

Lokale Funktionen haben Namen. Lamdaausdrücke sind anonyme Methoden, die Variablen zugewiesen werden, die `Func`- und `Action`-Typen sind. Wenn Sie eine lokale Funktion deklarieren, sind die Argumenttypen und der Rückgabetyp Teil der Funktionsdeklaration. Statt Teil des Texts des Lambdaausdrucks zu sein, sind die Argumentttypen und der Rückgabetyp Teil der Variablentypdeklaration des Lambdaausdrucks. Diese beiden Unterschiede können zu klarerem Code führen.

Lokale Funktionen haben andere Regeln für definitive Zuweisungen als Lambdaausdrücke. Auf eine Deklaration einer lokalen Funktion kann von jeder Stelle im Code aus, die sich innerhalb des Bereichs befindet, verwiesen werden. Ein Lambdaausdruck muss einer Delegatvariablen zugewiesen werden, bevor darauf zugegriffen werden kann (oder bevor er aufgerufen werden kann, indem der Delegat auf den Lambdaausdruck verweist). Beachten Sie, dass die Version mit Lambdaausdrücken den Lambdaausdruck `nthFactorial` deklarieren und initialisieren muss, bevor er definiert wird. Wird das nicht gemacht, führt dies zu einem Kompilierzeitfehler, weil auf `nthFactorial` verwiesen wurde, bevor es zugewiesen wurde.
Diese Unterschiede bedeuten, dass rekursive Algorithmen mit lokalen Funktionen leichter erstellt werden können. Sie können eine lokale Funktion deklarieren und definieren, die sich selbst aufruft. Lambdaausdrücke müssen deklariert werden, und dann muss ihnen ein Standardwert zugewiesen werden, bevor sie erneut einem Text zugewiesen werden können, der auf den gleichen Lambdaausdruck verweist.

Regeln für definitive Zuweisungen gelten auch für Variablen, die von der lokalen Funktion oder dem Lambdaausdruck erfasst werden. Sowohl Regeln für lokale Funktionen als auch für Lambdaausdrücke erfordern, dass alle erfassten Variablen dann definitiv zugewiesen werden, wenn die lokale Funktion oder der Lambdaausdruck in einen Delegaten konvertiert wird. Der Unterschied besteht darin, dass Lambdaausdrücke in Delegate konvertiert werden, wenn sie deklariert werden. Lokale Funktionen werden nur dann in Delegate konvertiert, wenn sie als Delegate verwendet werden. Wenn Sie eine lokale Funktion deklarieren und nur darauf verweisen, indem Sie sie wie eine Methode aufrufen, wird sie nicht in einen Delegaten konvertiert. Durch diese Regel können Sie eine lokale Funktion an jeder passenden Stelle in ihrem einschließenden Bereich deklarieren. Es ist üblich, lokale Funktionen am Ende der übergeordneten Methode hinter allen Rückgabeanweisungen zu deklarieren.

Zudem kann der Compiler statische Analysen durchführen, mit denen lokale Funktionen erfasste Variablen im einschließenden Bereich definitiv zuweisen können. Betrachten Sie das folgende Beispiel:

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

Der Compiler kann festlegen, dass `LocalFunction` `y` bei Aufruf definitiv zuweist. Da `LocalFunction` vor der `return`-Anweisung aufgerufen wird, wird `y` definitiv bei der `return`-Anweisung zugewiesen.

Die Analyse, die diese Beispielanalyse ermöglicht, ist der vierte Unterschied.
Je nach Verwendung können lokale Funktionen Heapzuweisungen vermeiden, die immer für Lambdaausdrücke erforderlich sind. Wenn eine lokale Funktion nie in einen Delegaten konvertiert wird und keine der von der lokalen Funktion erfassten Variablen von anderen Lambdaausdrücken oder lokalen Funktionen erfasst wird, die in Delegate konvertiert werden, kann der Compiler Heapzuweisungen vermeiden. 

Betrachten Sie das folgende asynchrone Beispiel:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

Der Abschluss dieses Lambdaausdrucks enthält die Variablen `address`, `index` und `name`. Im Fall von lokalen Funktionen ist das Objekt, das den Abschluss implementiert, möglicherweise vom Typ `struct`. Dieser struct-Typ würde per Verweis an die lokale Funktion übergeben. Dieser Unterschied bei der Implementierung würde bei einer Zuweisung gespart.

Die für Lambdaausdrücke erforderliche Instanziierung bedeutet zusätzliche Speicherbelegung, was ein Leistungsfaktor in zeitkritischen Codepfaden sein kann.
Lokale Funktionen erfordern diesen Mehraufwand nicht. Im obigen Beispiel hat die Version mit der lokalen Funktion zwei Zuordnungen weniger als die Version mit dem Lambdaausdruck.

> [!NOTE]
> Die Entsprechung dieser Methode mit der lokalen Funktion verwendet auch eine Klasse für den Abschluss. Ob der Abschluss für eine lokale Funktion als `class` oder `struct` implementiert wird, ist ein Implementierungsdetail. Eine lokale Funktion verwendet möglicherweise `struct`, während ein Lambdaausdruck immer `class` nutzt.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

Eine letzter Vorteil, der in diesem Beispiel zu kurz gekommen ist, besteht darin, dass lokale Funktionen mithilfe der `yield return`-Syntax als Iteratoren implementiert werden können, um eine Sequenz von Werten zu erzeugen. Die `yield return`-Anweisung ist in Lambdaausdrücken unzulässig.

Während lokale Funktionen für Lambdaausdrücke als überflüssig erscheinen, dienen sie tatsächlich anderen Zwecken und haben unterschiedliche Verwendungen.
Lokale Funktionen sind effizienter, im Fall dass Sie eine Funktion schreiben möchten, die nur aus dem Kontext einer anderen Methode abgerufen wird.
