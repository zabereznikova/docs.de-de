---
title: 'Ausschüsse: Leitfaden für C#'
description: Beschreibt die Unterstützung von C# für Ausschüsse, bei denen es sich um nicht zugewiesene, verwerfbare Variablen handelt, und die Möglichkeiten, wie Ausschüsse verwendet werden können.
ms.technology: csharp-fundamentals
ms.date: 07/21/2017
ms.openlocfilehash: a76e7fc13f92ec0de87153bb35eb3924bb317616
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100636"
---
# <a name="discards---c-guide"></a>Ausschüsse: Leitfaden für C#

Ab C# 7.0 werden Ausschüsse von C# unterstützt. Dabei handelt es sich um temporäre Platzhaltervariablen, die bewusst ungenutzt im Anwendungscode verwendet werden. Ausschüsse entsprechen nicht zugewiesenen Variablen und besitzen keinen Wert. Da es nur eine einzige Ausschussvariable gibt und dieser Variable möglicherweise nicht einmal Speicher zugewiesen ist, kann durch Ausschüsse die Speicherbelegung reduziert werden. Da sie den Zweck Ihres Codes deutlich machen, verbessern Sie dessen Lesbarkeit und Verwaltbarkeit.

Sie geben an, dass es sich bei einer Variable um Ausschuss handelt, indem Sie ihr einen Unterstrich (`_`) als Namen zuweisen. Der folgende Methodenaufruf gibt beispielsweise ein 3-Tupel zurück, in dem der erste und zweite Wert Ausschussvariablen sind und *area* eine zuvor deklarierte Variable ist, die auf die entsprechende dritte Komponente festgelegt wird, die von *GetCityInformation* zurückgegeben wird:

```csharp
(_, _, area) = city.GetCityInformation(cityName);
```

In C# 7.0 werden Ausschussvariablen in Zuweisungen in den folgenden Kontexten unterstützt:

- [Dekonstruieren](deconstruct.md) von Tupeln und Objekten.
- Musterabgleich mit [is](language-reference/keywords/is.md) und [switch](language-reference/keywords/switch.md).
- Aufrufe von Methoden mit `out`-Parametern.
- Ein eigenständiger `_`, wenn sich kein `_` im Bereich befindet.

Wenn es sich bei `_` um einen gültigen Ausschuss handelt, wird beim Versuch, seinen Wert abzurufen oder ihn in einer Zuweisungsoperation zu verwenden, ein Compilerfehler (CS0301, „Der Name ‚\_‘ existiert im aktuellen Kontext nicht“) generiert. Das liegt daran, dass `_` kein Wert und möglicherweise nicht einmal ein Speicherort zugewiesen ist. Wenn es sich dabei um eine tatsächliche Variable handeln würde, könnten Sie nicht wie im vorherigen Beispiel mehr als einen Wert verwerfen.

## <a name="tuple-and-object-deconstruction"></a>Dekonstruieren von Tupeln und Objekten

Ausschüsse sind besonders nützlich, wenn mit Tupeln gearbeitet wird und Ihr Anwendungscode einige Elemente des Tupels verwendet, andere aber ignoriert. Die folgende Methode `QueryCityDataForYears` gibt beispielsweise einen 6-Tupel mit dem Namen einer Stadt, ihrer Fläche, einer Jahreszahl, der Bevölkerung der Stadt in diesem Jahr, einer zweiten Jahreszahl und der Bevölkerung der Stadt im zweiten Jahr zurück. Das Beispiel zeigt die Veränderung der Bevölkerung zwischen diesen beiden Jahren. Von den Daten, die im Tupel verfügbar sind, ist die Fläche der Stadt nicht relevant für uns und außerdem kennen wir den Namen der Stadt und die zwei Datumswerte zur Entwurfszeit. Darum sind wir nur an den zwei Bevölkerungsgwerten interessiert, die im Tupel gespeichert sind und behandeln die restlichen Werte als Ausschuss.  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Weitere Informationen zum Dekonstruieren von Tupeln mit Ausschüssen finden Sie unter [Deconstructing tuples and other types (Dekonstruieren von Tupeln und anderen Typen)](deconstruct.md#deconstructing-tuple-elements-with-discards).

Die Methode `Deconstruct` einer Klasse, Struktur oder Schnittstelle ermöglicht es Ihnen ebenfalls, einen bestimmten Satz von Daten aus einem Objekt abzurufen und zu dekonstruieren. Sie können Ausschüsse verwenden, wenn Sie nur mit einer Teilmenge der dekonstruierten Werte arbeiten möchten. Im folgenden Beispiel wird ein `Person`-Objekt in vier Zeichenfolgen (Vor- und Nachname, Ort und Staat) dekonstruiert, Nachname und Staat werden jedoch verworfen.

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]

Weitere Informationen zum Dekonstruieren von benutzerdefinierten Typen mit Ausschüssen finden Sie unter [Deconstructing tuples and other types (Dekonstruieren von Tupeln und anderen Typen)](deconstruct.md#deconstructing-a-user-defined-type-with-discards).

## <a name="pattern-matching-with-switch-and-is"></a>Musterabgleich mit `switch` und `is`

Das *Ausschussmuster* kann beim Musterabgleich mit den Schlüsselwörtern [is](language-reference/keywords/is.md) und [switch](language-reference/keywords/switch.md) verwendet werden. Jeder Ausdruck stimmt immer mit dem Ausschussmuster überein.

Im folgenden Beispiel wird die Methode `ProvidesFormatInfo` definiert, die [is](language-reference/keywords/is.md)-Anweisungen verwendet, um zu bestimmen, ob ein Objekt eine <xref:System.IFormatProvider>-Implementierung bereitstellt und überprüft, ob das Objekt `null` ist. Sie verwendet auch das Ausschussmuster, um Nicht-NULL-Objekte eines anderen Typs zu verarbeiten.

[!code-csharp[discard-pattern](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]

## <a name="calls-to-methods-with-out-parameters"></a>Aufrufe von Methoden mit out-Parametern

Wenn die Methode `Deconstruct` aufgerufen wird, um einen benutzerdefinierten Typ (eine Instanz einer Klasse, Struktur oder Schnittstelle) zu dekonstruieren, können Sie die Werte einzelner `out`-Argumente verwerfen. Sie können ebenfalls den Wert von `out`-Argumenten verwerfen, wenn Sie eine Methode mit einem out-Parameter aufrufen.

Im folgenden Beispiel wird die Methode [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) aufgerufen, um zu bestimmen, ob die Zeichenfolgendarstellung eines Datums in der aktuellen Kultur gültig ist. Da das Beispiel darauf beschränkt ist, die Datumszeichenfolge zu überprüfen und diese nicht analysiert wird, um das Datum zu extrahieren, ist das Argument `out` der Methode ein Ausschuss.

[!code-csharp[discard-with-out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]

## <a name="a-standalone-discard"></a>Ein eigenständiger Ausschuss

Sie können einen eigenständigen Ausschuss verwenden, um eine beliebige Variable anzugeben, die Sie ignorieren möchten. Im folgenden Beispiel wird ein eigenständiger Ausschuss verwendet, um das Objekt <xref:System.Threading.Tasks.Task> zu ignorieren, das von einem asynchronen Vorgang zurückgegeben wird. Dadurch wird die Ausnahme unterdrückt, die vom Vorgang kurz vor dem Abschluss ausgelöst wird.

[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]

Beachten Sie, dass `_` auch ein gültiger Bezeichner ist. Bei der Verwendung außerhalb eines unterstützten Kontexts wird `_` nicht als Ausschuss, sondern als gültige Variable behandelt. Wenn bereits ein Bezeichner mit dem Namen `_` im Bereich vorhanden ist, kann die Verwendung von `_` als eigenständiger Ausschuss zu Folgendem führen:

- Versehentliche Änderung des Werts der im Bereich befindlichen Variable `_`, indem dieser der Wert eines beabsichtigten Ausschusses zugewiesen wird. Zum Beispiel:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]

- Ein Compilerfehler wegen Verletzung der Typsicherheit. Zum Beispiel:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]

- Compilerfehler CS0136: „A local or parameter named '\_' cannot be declared in this scope because that name is used in an enclosing local scope to define a local or parameter.“ (Eine lokale Variable oder ein Parameter mit dem Namen „_“ kann in diesem Bereich nicht deklariert werden, da der Name in einem einschließenden lokalen Bereich verwendet wird, um eine lokale Variable oder einen Parameter zu definieren.) Beispiel:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]

## <a name="see-also"></a>Siehe auch

- [Dekonstruieren von Tupeln und anderen Typen](deconstruct.md)
- [`is`Schlüsselwort](language-reference/keywords/is.md)
- [`switch`Schlüsselwort](language-reference/keywords/switch.md)
