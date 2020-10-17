---
title: Lokale Funktionen – C#-Programmierhandbuch
description: Lokale Funktionen in C# sind private Methoden, die in einem anderen Member geschachtelt sind und aus dem enthaltenden Member aufgerufen werden können.
ms.date: 10/09/2020
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: a2d389c8b1c687dc4885004fcdc33e0ed7ada977
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955680"
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
<modifiers> <return-type> <method-name> <parameter-list>
```

Sie können die folgenden Modifizierer mit einer lokalen Funktion verwenden:

- [`async`](../../language-reference/keywords/async.md)
- [`unsafe`](../../language-reference/keywords/unsafe.md)
- [`static`](../../language-reference/keywords/static.md) (in C# 8.0 und höher). Eine statische lokale Funktion kann keine lokalen Variablen oder den Instanzzustand erfassen.
- [`extern`](../../language-reference/keywords/extern.md) (in C# 9.0 und höher). Eine externe lokale Funktion muss `static` sein.

Alle im enthaltenden Member definierten lokalen Variablen, einschließlich der Methodenparameter, sind in einer nicht statischen lokalen Funktion zugänglich.

Im Gegensatz zu einer Methodendefinition kann die Definition einer lokalen Funktion keinen Memberzugriffsmodifizierer enthalten. Da alle lokale Funktionen privat sind, generiert das Verwenden eines Zugriffsmodifizierers wie etwa das Schlüsselwort `private` den Compilerfehler CS0106 „Der Modifizierer ‚private‘ ist für dieses Element nicht gültig“.

Das folgende Beispiel definiert eine lokale Funktion mit dem Namen `AppendPathSeparator`, die für eine Methode mit dem Namen `GetText` privat ist:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="Basic" :::

Ab C# 9.0 können Sie Attribute auf eine lokale Funktion, ihre Parameter und Typparameter anwenden. Sehen Sie sich dazu das folgende Beispiel an:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="WithAttributes" :::

Im vorherigen Beispiel wird ein [spezielles Attribut](../../language-reference/attributes/nullable-analysis.md) verwendet, um den Compiler bei der statischen Analyse in einem Nullable-Kontext zu unterstützen.

## <a name="local-functions-and-exceptions"></a>Lokale Funktionen und Ausnahmen

Eine nützliche Funktion von lokalen Funktionen ist die Tatsache, dass sie Ausnahmen sofort verfügbar machen können. Bei Methodeniteratoren werden Ausnahmen erst eingeblendet, wenn die zurückgegebene Sequenz aufgelistet wird, und nicht, wenn der Iterator abgerufen wird. Bei async-Methoden werden Ausnahmen festgestellt, wenn die zurückgegebene Aufgabe erwartet wird.

Das folgende Beispiel definiert eine `OddSequence`-Methode, die ungerade Zahlen in einem angegebenen Bereich aufzählt. Da eine Zahl größer als 100 an die `OddSequence`-Enumeratormethode übergeben wird, wird <xref:System.ArgumentOutOfRangeException> ausgelöst. Die Ausgabe des Beispiels zeigt, dass die Ausnahme erst beim Durchlaufen der Zahlen und nicht beim Abrufen des Enumerators eingeblendet wird.

:::code language="csharp" source="snippets/local-functions/IteratorWithoutLocal.cs" :::

Wenn Sie Iteratorlogik in eine lokale Funktion platzieren, werden Ausnahmen bei der Argumentvalidierung ausgelöst, wenn Sie den Enumerator abrufen. Sehen Sie sich dazu das folgende Beispiel an:

:::code language="csharp" source="snippets/local-functions/IteratorWithLocal.cs" :::

Sie können lokale Funktionen auf ähnliche Weise wie asynchrone Vorgänge nutzen. Ausnahmen, die in einer asynchronen Methode ausgelöst werden, treten auf, wenn der entsprechende Task erwartet wird. Lokale Funktionen ermöglichen einen schnellen Abbruch Ihres Codes. Ihre Ausnahme kann sowohl synchron ausgelöst als auch beobachtet werden.

Im folgenden Beispiel wird eine asynchrone Methode mit dem Namen `GetMultipleAsync` verwendet, um für eine bestimmte Anzahl von Sekunden anzuhalten und ein zufälliges Vielfaches dieser Sekundenanzahl zurückzugeben. Die maximale Verzögerung beträgt 5 Sekunden. <xref:System.ArgumentOutOfRangeException> wird ausgegeben, wenn der Wert größer als 5 ist. Wie das folgende Beispiel zeigt, tritt die Ausnahme, die ausgelöst wird, wenn an die `GetMultipleAsync`-Methode ein Wert von 6 übergeben wird, nur dann auf, wenn der Task erwartet wird.

:::code language="csharp" source="snippets/local-functions/AsyncWithoutLocal.cs" :::

Wie beim Methodeniterator können Sie das vorherige Beispiel umgestalten und den Code eines asynchronen Vorgangs in eine lokale Funktion platzieren. Wie die Ausgabe des folgenden Beispiels zeigt, wird <xref:System.ArgumentOutOfRangeException> ausgelöst, sobald die `GetMultiple`-Methode aufgerufen wird.

:::code language="csharp" source="snippets/local-functions/AsyncWithLocal.cs" :::

## <a name="local-functions-vs-lambda-expressions"></a>Lokale Funktionen im Vergleich zu Lambdaausdrücken

Auf den ersten Blick sind lokale Funktionen und [Lambdaausdrücke](../../language-reference/operators/lambda-expressions.md) sehr ähnlich. In vielen Fällen ist die Entscheidung zwischen Lamdaausdrücken und lokalen Funktionen eine Frage des Formats und persönlicher Präferenz. Es gibt allerdings tatsächliche Unterschiede, wann das eine oder das andere verwendet werden kann. Diese sollten Ihnen bekannt sein.

Sehen wir uns die Unterschiede zwischen der Implementierungen des Fakultätsalgorithmus als lokale Funktion und als Lambdaausdruck an. Erste die Version mit einer lokalen Funktion:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="FactorialWithLocal" :::

Vergleichen Sie diese Implementierung mit einer Version, die Lambdaausdrücke verwendet:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="FactorialWithLambda" :::

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

:::code language="csharp" source="snippets/local-functions/Program.cs" id="AsyncWithLambda" :::

Der Abschluss dieses Lambdaausdrucks enthält die Variablen `address`, `index` und `name`. Im Fall von lokalen Funktionen ist das Objekt, das den Abschluss implementiert, möglicherweise vom Typ `struct`. Dieser struct-Typ würde per Verweis an die lokale Funktion übergeben. Dieser Unterschied bei der Implementierung würde bei einer Zuweisung gespart.

Die für Lambdaausdrücke erforderliche Instanziierung bedeutet zusätzliche Speicherbelegung, was ein Leistungsfaktor in zeitkritischen Codepfaden sein kann. Lokale Funktionen erfordern diesen Mehraufwand nicht. Im obigen Beispiel hat die Version mit der lokalen Funktion zwei Zuordnungen weniger als die Version mit dem Lambdaausdruck.

> [!NOTE]
> Die Entsprechung dieser Methode mit der lokalen Funktion verwendet auch eine Klasse für den Abschluss. Ob der Abschluss für eine lokale Funktion als `class` oder `struct` implementiert wird, ist ein Implementierungsdetail. Eine lokale Funktion verwendet möglicherweise `struct`, während ein Lambdaausdruck immer `class` nutzt.

:::code language="csharp" source="snippets/local-functions/Program.cs" id="AsyncWithLocal" :::

Eine letzter Vorteil, der in diesem Beispiel zu kurz gekommen ist, besteht darin, dass lokale Funktionen mithilfe der `yield return`-Syntax als Iteratoren implementiert werden können, um eine Sequenz von Werten zu erzeugen. Die `yield return`-Anweisung ist in Lambdaausdrücken unzulässig.

Während lokale Funktionen für Lambdaausdrücke als überflüssig erscheinen, dienen sie tatsächlich anderen Zwecken und haben unterschiedliche Verwendungen. Lokale Funktionen sind effizienter, im Fall dass Sie eine Funktion schreiben möchten, die nur aus dem Kontext einer anderen Methode abgerufen wird.

## <a name="see-also"></a>Siehe auch

- [Methoden](methods.md)
