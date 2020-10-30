---
title: Lokale Funktionen – C#-Programmierhandbuch
description: Lokale Funktionen in C# sind private Methoden, die in einem anderen Member geschachtelt sind und aus dem enthaltenden Member aufgerufen werden können.
ms.date: 10/16/2020
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 75accda2e40443073274ece4d8964c13a0945dad
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332899"
---
# <a name="local-functions-c-programming-guide"></a>Lokale Funktionen (C#-Programmierhandbuch)

Ab C#-7.0 unterstützt C# *lokale Funktionen* . Lokale Funktionen sind private Methoden eines Typs, die in einem anderen Member geschachtelt sind. Sie können nur aus ihrem enthaltenden Member aufgerufen werden. Lokale Funktionen können deklariert und aufgerufen werden aus:

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

Sehen wir uns die Unterschiede zwischen der Implementierungen des Fakultätsalgorithmus als lokale Funktion und als Lambdaausdruck an. Dies ist die Version mit einer lokalen Funktion:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="FactorialWithLocal" :::

Diese Version verwendet Lambdaausdrücke:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="FactorialWithLambda" :::

### <a name="naming"></a>Benennung

Lokale Funktionen werden explizit wie Methoden benannt. Lambdaausdrücke sind anonyme Methoden und müssen Variablen eines `delegate`-Typs zugewiesen werden. In der Regel handelt es sich entweder um `Action`- oder `Func`-Typen. Die Deklaration einer lokalen Funktion erfolgt so ähnlich wie das Schreiben einer normalen Methode. Sie müssen dazu einen Rückgabetyp und eine Funktionssignatur deklarieren.

### <a name="function-signatures-and-lambda-expression-types"></a>Funktionssignaturen und Typen für Lambdaausdrücke

Beim Bestimmen der Argument- und Rückgabetypen sind Lambdaausdrücke auf den Typ der `Action`/`Func`-Variablen angewiesen, der sie zugewiesen werden. Da die Syntax in lokalen Funktionen stark einer normalen Methode ähnelt, sind die Argumenttypen und der Rückgabetyp bereits Teil der Funktionsdeklaration.

### <a name="definite-assignment"></a>Definite assignment (Festgelegte Zuweisung)

Lambdaausdrücke sind Objekte, die zur Laufzeit deklariert und zugewiesen werden. Damit ein Lambdaausdruck verwendet werden kann, muss er definitiv zugewiesen werden: die `Action`/`Func`-Variable, der er zugewiesen wird, muss deklariert werden. Anschließend muss der Lambdaausdruck der Variablen zugewiesen werden. Beachten Sie, dass `LambdaFactorial` den Lambdaausdruck `nthFactorial` deklarieren und initialisieren muss, bevor dieser definiert wird. Wird das nicht gemacht, führt dies zu einem Kompilierzeitfehler, weil auf `nthFactorial` verwiesen wurde, bevor es zugewiesen wurde.

Lokale Funktionen werden zur Kompilierzeit definiert. Da sie keinen Variablen zugewiesen werden, kann an jeder Stelle im Code **innerhalb des Gültigkeitsbereichs der Funktion** darauf verwiesen werden. Im ersten Beispiel `LocalFunctionFactorial` konnten Sie die lokale Funktion entweder oberhalb oder unterhalb der `return`-Anweisung deklarieren, ohne Compilerfehler auszulösen.

Diese Unterschiede bedeuten, dass rekursive Algorithmen mit lokalen Funktionen leichter erstellt werden können. Sie können eine lokale Funktion deklarieren und definieren, die sich selbst aufruft. Lambdaausdrücke müssen deklariert werden, und dann muss ihnen ein Standardwert zugewiesen werden, bevor sie erneut einem Text zugewiesen werden können, der auf den gleichen Lambdaausdruck verweist.

### <a name="implementation-as-a-delegate"></a>Implementierung als Delegat

Lambdaausdrücke werden bei der Deklaration in Delegate konvertiert. Lokale Funktionen sind flexibler, da sie wie eine herkömmliche Methode *oder* als Delegat geschrieben werden können. Lokale Funktionen werden nur dann in Delegate konvertiert, wenn sie als Delegate ***verwendet*** werden.

Wenn Sie eine lokale Funktion deklarieren und nur darauf verweisen, indem Sie sie wie eine Methode aufrufen, wird sie nicht in einen Delegaten konvertiert.

### <a name="variable-capture"></a>Erfassung von Variablen

Die Regeln für [definitive Zuweisungen](../../../../_csharplang/spec/variables.md#definite-assignment) gelten auch für alle Variablen, die von der lokalen Funktion oder dem Lambdaausdruck erfasst werden. Zudem kann der Compiler statische Analysen durchführen, mit denen lokale Funktionen erfasste Variablen im einschließenden Gültigkeitsbereich definitiv zuweisen können. Betrachten Sie das folgende Beispiel:

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

Beachten Sie, dass die lokale Funktion als Delegattyp implementiert wird, wenn diese lokale Funktion Variablen im einschließenden Gültigkeitsbereich erfasst.

### <a name="heap-allocations"></a>Heapzuweisungen

Je nach Verwendung können lokale Funktionen Heapzuweisungen vermeiden, die immer für Lambdaausdrücke erforderlich sind. Wenn eine lokale Funktion nie in einen Delegaten konvertiert wird und keine der von der lokalen Funktion erfassten Variablen von anderen Lambdaausdrücken oder lokalen Funktionen, die in Delegate konvertiert werden, erfasst wird, kann der Compiler Heapzuweisungen vermeiden.

Betrachten Sie das folgende asynchrone Beispiel:

:::code language="csharp" source="snippets/local-functions/Program.cs" id="AsyncWithLambda" :::

Der Abschluss dieses Lambdaausdrucks enthält die Variablen `address`, `index` und `name`. Im Fall von lokalen Funktionen ist das Objekt, das den Abschluss implementiert, möglicherweise vom Typ `struct`. Dieser struct-Typ würde per Verweis an die lokale Funktion übergeben. Dieser Unterschied bei der Implementierung würde bei einer Zuweisung gespart.

Die für Lambdaausdrücke erforderliche Instanziierung bedeutet zusätzliche Speicherbelegung, was ein Leistungsfaktor in zeitkritischen Codepfaden sein kann. Lokale Funktionen erfordern diesen Mehraufwand nicht. Im obigen Beispiel hat die Version mit der lokalen Funktion zwei Zuordnungen weniger als die Version mit dem Lambdaausdruck.

Wenn Sie wissen, dass Ihre lokale Funktion nicht in einen Delegaten konvertiert wird und dass keine der von ihr erfassten Variablen auch von anderen Lambdaausdrücken oder lokalen Funktionen, die in Delegate konvertiert werden, erfasst wird, können Sie durch Deklarieren der lokalen Funktion als statisch (`static`) verhindern, dass Ihre lokale Funktion im Heap zugewiesen wird. Beachten Sie, dass dieses Feature in C# 8.0 und höher verfügbar ist.

> [!NOTE]
> Die Entsprechung dieser Methode mit der lokalen Funktion verwendet auch eine Klasse für den Abschluss. Ob der Abschluss für eine lokale Funktion als `class` oder `struct` implementiert wird, ist ein Implementierungsdetail. Eine lokale Funktion verwendet möglicherweise `struct`, während ein Lambdaausdruck immer `class` nutzt.

:::code language="csharp" source="snippets/local-functions/Program.cs" id="AsyncWithLocal" :::

### <a name="usage-of-the-yield-keyword"></a>Verwendung des Schlüsselworts `yield`

Eine letzter Vorteil, der in diesem Beispiel zu kurz gekommen ist, besteht darin, dass lokale Funktionen mithilfe der `yield return`-Syntax als Iteratoren implementiert werden können, um eine Sequenz von Werten zu erzeugen.

:::code language="csharp" source="snippets/local-functions/Program.cs" id="YieldReturn" :::

Die `yield return`-Anweisung ist in Lambdaausdrücken unzulässig. Weitere Informationen finden Sie unter [Compilerfehler CS1621](../../misc/cs1621.md).

Während lokale Funktionen für Lambdaausdrücke als überflüssig erscheinen, dienen sie tatsächlich anderen Zwecken und haben unterschiedliche Verwendungen. Lokale Funktionen sind effizienter, im Fall dass Sie eine Funktion schreiben möchten, die nur aus dem Kontext einer anderen Methode abgerufen wird.

## <a name="see-also"></a>Siehe auch

- [Methoden](methods.md)
