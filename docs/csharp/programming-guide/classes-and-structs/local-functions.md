---
title: Lokale Funktionen – C#-Programmierhandbuch
ms.date: 06/14/2017
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 200fbd097b7c71a1cd392d62622955528a80fd66
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102943"
---
# <a name="local-functions-c-programming-guide"></a>Lokale Funktionen (C#-Programmierhandbuch)

Ab C#-7.0 unterstützt C# *lokale Funktionen*. Lokale Funktionen sind private Methoden eines Typs, die in einem anderen Member geschachtelt sind. Sie können nur aus ihrem enthaltenden Member aufgerufen werden. Lokale Funktionen können deklariert und aufgerufen werden aus:

- Methoden, insbesondere Iteratormethoden und Async-Methoden
- Konstruktoren
- Eigenschaftenaccessoren
- Ereignisaccessoren
- Anonymen Methoden
- Lambdaausdrücke
- Finalizer
- Anderen lokalen Funktionen

Lokale Funktionen können jedoch nicht in einem Ausdruckskörpermember deklariert werden.

> [!NOTE]
> In einigen Fällen können Sie einen Lambdaausdruck zum Implementieren von Funktionen verwenden, die auch von einer lokalen Funktion unterstützt werden. Einen Vergleich finden Sie unter [Lokale Funktionen im Vergleich zu Lambdaausdrücken](#local-functions-vs-lambda-expressions).

Lokale Funktionen machen den Zweck Ihres Codes deutlich. Beim Lesen des Codes wird deutlich, dass die Methode nur von der enthaltenden Methode aufgerufen werden kann. Bei Teamprojekten wird auch verhindert, dass ein anderer Entwickler die Methode versehentlich direkt an anderer Stelle in der Klasse oder Struktur aufruft.

## <a name="local-function-syntax"></a>Syntax einer lokalen Funktion

Eine lokale Funktion wird definiert als eine geschachtelte Methode in einem enthaltenden Member. Ihre Definition besitzt die folgende Syntax:

```csharp
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

Lokale Funktionen können die Modifizierer [async](../../language-reference/keywords/async.md) und [unsafe](../../language-reference/keywords/unsafe.md) verwenden.

Beachten Sie, dass alle im enthaltenden Member definierten lokalen Variablen, einschließlich der Methodenparameter, in der lokalen Funktion zugänglich sind.

Im Gegensatz zu einer Methodendefinition kann die Definition einer lokalen Funktion keinen Memberzugriffsmodifizierer enthalten. Da alle lokale Funktionen privat sind, generiert das Verwenden eines Zugriffsmodifizierers wie etwa das Schlüsselwort `private` den Compilerfehler CS0106 „Der Modifizierer ‚private‘ ist für dieses Element nicht gültig“.

> [!NOTE]
> Vor C# 8.0 dürfen lokale Funktionen nicht den `static`-Modifizierer enthalten. Die Verwendung des Schlüsselworts `static` generiert den Compilerfehler CS0106 „Der Modifizierer ‚static‘ ist für dieses Element nicht gültig“.

Darüber hinaus können keine Attribute auf lokale Funktionen oder ihre Parameter und Typparameter angewendet werden.

Das folgende Beispiel definiert eine lokale Funktion mit dem Namen `AppendPathSeparator`, die für eine Methode mit dem Namen `GetText` privat ist:

[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  

## <a name="local-functions-and-exceptions"></a>Lokale Funktionen und Ausnahmen

Eine nützliche Funktion von lokalen Funktionen ist die Tatsache, dass sie Ausnahmen sofort verfügbar machen können. Bei Methodeniteratoren werden Ausnahmen erst eingeblendet, wenn die zurückgegebene Sequenz aufgelistet wird, und nicht, wenn der Iterator abgerufen wird. Bei async-Methoden werden Ausnahmen festgestellt, wenn die zurückgegebene Aufgabe erwartet wird.

Das folgende Beispiel definiert eine `OddSequence`-Methode, die ungerade Zahlen in einem angegebenen Bereich aufzählt. Da eine Zahl größer als 100 an die `OddSequence`-Enumeratormethode übergeben wird, wird <xref:System.ArgumentOutOfRangeException> ausgelöst. Die Ausgabe des Beispiels zeigt, dass die Ausnahme erst beim Durchlaufen der Zahlen und nicht beim Abrufen des Enumerators eingeblendet wird.

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)]

Stattdessen können Sie während der Validierung und vor Abrufen des Iterators wie im folgenden Beispiel dargestellt eine Ausnahme auslösen, indem der Iterator aus einer lokalen Funktion zurückgegeben wird.

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

Lokale Funktionen können auf ähnliche Weise verwendet werden, um Ausnahmen außerhalb des asynchronen Vorgangs zu behandeln. Normalerweise erfordern Ausnahmen in einer async-Methode die Überprüfung der inneren Ausnahmen von <xref:System.AggregateException>. Lokale Funktionen ermöglichen einen schnellen Abbruch Ihres Codes. Ihre Ausnahme kann sowohl synchron ausgelöst als auch beobachtet werden.

Im folgenden Beispiel wird eine asynchrone Methode mit dem Namen `GetMultipleAsync` verwendet, um für eine bestimmte Anzahl von Sekunden anzuhalten und ein zufälliges Vielfaches dieser Sekundenanzahl zurückzugeben. Die maximale Verzögerung beträgt 5 Sekunden. <xref:System.ArgumentOutOfRangeException> wird ausgegeben, wenn der Wert größer als 5 ist. Im folgenden Beispiel wird verdeutlicht, dass die Ausnahme, die bei der Übergabe eines Werts größer als 6 an die Methode `GetMultipleAsync` ausgelöst wird, von <xref:System.AggregateException> umschlossen wird, sobald die Methode `GetMultipleAsync` ausgeführt wird.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)]

Wie beim Methodeniterator kann der Code aus diesem Beispiel umgestaltet werden, um die Validierung vor Aufruf der asynchronen Methode durchzuführen. Die Ausgabe des folgenden Beispiels zeigt, dass <xref:System.ArgumentOutOfRangeException> nicht von einer <xref:System.AggregateException> umschlossen wird.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)]

## <a name="local-functions-vs-lambda-expressions"></a>Lokale Funktionen im Vergleich zu Lambdaausdrücken

Auf den ersten Blick sind lokale Funktionen und [Lambdaausdrücke](../statements-expressions-operators/lambda-expressions.md) sehr ähnlich. In vielen Fällen ist die Entscheidung zwischen Lamdaausdrücken und lokalen Funktionen eine Frage des Formats und persönlicher Präferenz. Es gibt allerdings tatsächliche Unterschiede, wann das eine oder das andere verwendet werden kann. Diese sollten Ihnen bekannt sein.

Sehen wir uns die Unterschiede zwischen der Implementierungen des Fakultätsalgorithmus als lokale Funktion und als Lambdaausdruck an. Erste die Version mit einer lokalen Funktion:

[!code-csharp[LocalFunctionFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

Vergleichen Sie diese Implementierung mit einer Version, die Lambdaausdrücke verwendet:

[!code-csharp[26_LambdaFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

Lokale Funktionen haben Namen. Lamdaausdrücke sind anonyme Methoden, die Variablen zugewiesen werden, die `Func`- und `Action`-Typen sind. Wenn Sie eine lokale Funktion deklarieren, sind die Argumenttypen und der Rückgabetyp Teil der Funktionsdeklaration. Statt Teil des Texts des Lambdaausdrucks zu sein, sind die Argumentttypen und der Rückgabetyp Teil der Variablentypdeklaration des Lambdaausdrucks. Diese beiden Unterschiede können zu klarerem Code führen.

Lokale Funktionen haben andere Regeln für definitive Zuweisungen als Lambdaausdrücke. Auf eine Deklaration einer lokalen Funktion kann von jeder Stelle im Code aus, die sich innerhalb des Bereichs befindet, verwiesen werden. Ein Lambdaausdruck muss einer Delegatvariablen zugewiesen werden, bevor darauf zugegriffen werden kann (oder bevor er aufgerufen werden kann, indem der Delegat auf den Lambdaausdruck verweist). Beachten Sie, dass die Version mit Lambdaausdrücken den Lambdaausdruck `nthFactorial` deklarieren und initialisieren muss, bevor er definiert wird. Wird das nicht gemacht, führt dies zu einem Kompilierzeitfehler, weil auf `nthFactorial` verwiesen wurde, bevor es zugewiesen wurde. Diese Unterschiede bedeuten, dass rekursive Algorithmen mit lokalen Funktionen leichter erstellt werden können. Sie können eine lokale Funktion deklarieren und definieren, die sich selbst aufruft. Lambdaausdrücke müssen deklariert werden, und dann muss ihnen ein Standardwert zugewiesen werden, bevor sie erneut einem Text zugewiesen werden können, der auf den gleichen Lambdaausdruck verweist.

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

Der Compiler kann festlegen, dass `LocalFunction``y` bei Aufruf definitiv zuweist. Da `LocalFunction` vor der `return`-Anweisung aufgerufen wird, wird `y` definitiv bei der `return`-Anweisung zugewiesen.

Die Analyse, die diese Beispielanalyse ermöglicht, ist der vierte Unterschied. Je nach Verwendung können lokale Funktionen Heapzuweisungen vermeiden, die immer für Lambdaausdrücke erforderlich sind. Wenn eine lokale Funktion nie in einen Delegaten konvertiert wird und keine der von der lokalen Funktion erfassten Variablen von anderen Lambdaausdrücken oder lokalen Funktionen erfasst wird, die in Delegate konvertiert werden, kann der Compiler Heapzuweisungen vermeiden.

Betrachten Sie das folgende asynchrone Beispiel:

[!code-csharp[TaskLambdaExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

Der Abschluss dieses Lambdaausdrucks enthält die Variablen `address`, `index` und `name`. Im Fall von lokalen Funktionen ist das Objekt, das den Abschluss implementiert, möglicherweise vom Typ `struct`. Dieser struct-Typ würde per Verweis an die lokale Funktion übergeben. Dieser Unterschied bei der Implementierung würde bei einer Zuweisung gespart.

Die für Lambdaausdrücke erforderliche Instanziierung bedeutet zusätzliche Speicherbelegung, was ein Leistungsfaktor in zeitkritischen Codepfaden sein kann. Lokale Funktionen erfordern diesen Mehraufwand nicht. Im obigen Beispiel hat die Version mit der lokalen Funktion zwei Zuordnungen weniger als die Version mit dem Lambdaausdruck.

> [!NOTE]
> Die Entsprechung dieser Methode mit der lokalen Funktion verwendet auch eine Klasse für den Abschluss. Ob der Abschluss für eine lokale Funktion als `class` oder `struct` implementiert wird, ist ein Implementierungsdetail. Eine lokale Funktion verwendet möglicherweise `struct`, während ein Lambdaausdruck immer `class` nutzt.

[!code-csharp[TaskLocalFunctionExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

Eine letzter Vorteil, der in diesem Beispiel zu kurz gekommen ist, besteht darin, dass lokale Funktionen mithilfe der `yield return`-Syntax als Iteratoren implementiert werden können, um eine Sequenz von Werten zu erzeugen. Die `yield return`-Anweisung ist in Lambdaausdrücken unzulässig.

Während lokale Funktionen für Lambdaausdrücke als überflüssig erscheinen, dienen sie tatsächlich anderen Zwecken und haben unterschiedliche Verwendungen. Lokale Funktionen sind effizienter, im Fall dass Sie eine Funktion schreiben möchten, die nur aus dem Kontext einer anderen Methode abgerufen wird.

## <a name="see-also"></a>Siehe auch

- [Methoden](methods.md)
