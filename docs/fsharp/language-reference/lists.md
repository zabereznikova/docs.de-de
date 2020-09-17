---
title: Listen
description: 'Erfahren Sie mehr über F #-Listen, eine geordnete, unveränderliche Reihe von Elementen desselben Typs.'
ms.date: 08/13/2020
ms.openlocfilehash: 567731eb57b77d60d3dd847630d5676e8d047d09
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720347"
---
# <a name="lists"></a>Listen

Eine Liste in F# stellt eine geordnete, unveränderliche Reihe von Elementen desselben Typs dar. Verwenden Sie die Funktionen im [Listen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html), um grundlegende Vorgänge für Listen auszuführen.

## <a name="creating-and-initializing-lists"></a>Erstellen und Initialisieren von Listen

Sie können eine Liste definieren, indem Sie die durch Semikolon getrennten und in eckige Klammern eingeschlossenen Elemente explizit auflisten, wie in folgender Codezeile veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

Sie können Elemente auch durch Zeilenumbrüche trennen, wobei die Semikolons dann optional sind. Letztere Syntax kann den Code übersichtlicher gestalten, wenn die Ausdrücke zur Elementinitialisierung umfangreicher ausfallen oder Sie für jedes Element einen Kommentar einbeziehen möchten.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

Im Allgemeinen müssen alle Listenelemente denselben Typ aufweisen. Eine Ausnahme ist, dass eine Liste, in der für Elemente ein Basistyp angegeben wird, Elemente enthalten darf, die abgeleiteten Typen entsprechen. Somit ist Folgendes zulässig, da sowohl `Button` und `CheckBox` von `Control` abgeleitet werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

Sie können Listenelemente auch durch Verwendung eines Bereichs definieren, der durch ganze Zahlen angegeben wird, die durch den Bereichsoperator (`..`) getrennt sind, wie im folgenden Code veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

Eine leere Liste wird durch ein Paar eckige Klammern angegeben, die nichts einschließen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

Sie können eine Liste auch mithilfe von Sequenzausdrücken erstellen. Weitere Informationen finden Sie unter [Sequence Expressions](sequences.md#sequence-expressions) . Der folgende Code erstellt z. B. eine Liste mit den Quadratzahlen der ganzen Zahlen von 1 bis 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a>Operatoren für die Arbeit mit Listen

Sie können Elemente mithilfe des Operators `::` (Cons) zu einer Liste hinzufügen. Wenn `list1` den Werten `[2; 3; 4]` entspricht, erstellt der folgende Code für `list2` die Werte `[100; 2; 3; 4]`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

Sie können Listen, die kompatible Typen aufweisen, wie im folgenden Code mithilfe des Operators `@` verketten. Wenn `list1` den Werten `[2; 3; 4]` und `list2` den Werten `[100; 2; 3; 4]` entspricht, erstellt dieser Code für `list3` die Werte `[2; 3; 4; 100; 2; 3; 4]`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

Funktionen zum Ausführen von Vorgängen für Listen sind im [Listen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)verfügbar.

Da Listen in F# unveränderlich sind, erstellen alle modifizierenden Operationen neue Listen, anstatt die vorhandenen Listen zu verändern.

Listen in F # werden als einzeln verknüpfte Listen implementiert. Dies bedeutet, dass Vorgänge, die nur auf den Anfang der Liste zugreifen, o (1) sind und der Element Zugriff o (*n*) ist.

## <a name="properties"></a>Eigenschaften

Der Listentyp unterstützt die folgenden Eigenschaften:

|Eigenschaft|Typ|BESCHREIBUNG|
|--------|----|-----------|
|[Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|Das erste Element.|
|[Leer](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|Eine statische Eigenschaft, die eine leere Liste des entsprechenden Typs zurückgibt.|
|[IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|Ergibt `true`, wenn die Liste keine Elemente enthält.|
|[Element](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|Das Element am angegebenen (nullbasierten) Index.|
|[Länge](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|Die Anzahl der Elemente.|
|[Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|Die Liste ohne das erste Element.|

Nachfolgend sind einige Beispiele zur Verwendung dieser Eigenschaften aufgeführt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a>Verwenden von Listen

Durch die Programmierung mit Listen können Sie mit wenig Code komplexe Operationen durchführen. In diesem Abschnitt werden die allgemeinen Operationen für Listen beschrieben, die für die funktionale Programmierung von Bedeutung sind.

### <a name="recursion-with-lists"></a>Rekursion mit Listen

Listen sind beispiellos für rekursive Programmierverfahren geeignet. Betrachten Sie eine Operation, die für jedes Element einer Liste ausgeführt werden muss. Sie können dazu rekursiv vorgehen, indem Sie den Listenanfang verarbeiten und dann den Rest der Liste, bei dem es sich um eine kleinere Liste handelt, die aus der ursprünglichen Liste ohne das erste Element besteht, zurück an die nächste Rekursionsstufe übergeben.

Sie verwenden zum Schreiben einer derartigen rekursiven Funktion den Cons-Operator (`::`) für den Mustervergleich, der es Ihnen ermöglicht, den Listenanfang vom Rest zu trennen.

Das folgende Codebeispiel zeigt, wie eine rekursive Funktion mithilfe des Musterabgleichs implementiert wird, die Operationen mit einer Liste ausführt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

Der vorherige Code ist für kleine Listen geeignet, aber bei größeren Listen könnten Stapelüberläufe auftreten. Der folgende Code verwendet ein Akkumulatorargument, ein Standardverfahren für die Arbeit mit rekursiven Funktionen, um den vorherigen Code zu verbessern. Durch die Verwendung des Akkumulatorarguments wird die Funktion zur endrekursiven Funktion, wodurch Stapelspeicher gespart wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

Die Funktion `RemoveAllMultiples` ist eine rekursive Funktion, die zwei Listen übernimmt. Die erste Liste enthält die Zahlen, deren Vielfaches entfernt wird. Die zweite Liste ist die Liste, aus der die Zahlen entfernt werden. Der Code im folgenden Beispiel verwendet diese rekursive Funktion, um alle Nichtprimzahlen aus der Liste zu entfernen, sodass als Ergebnis eine Liste der Primzahlen verbleibt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

Die Ausgabe lautet wie folgt:

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a>Modulfunktionen

Das [List-Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) stellt Funktionen bereit, die auf die Elemente einer Liste zugreifen. Auf das Anfangselement kann am schnellsten und einfachsten zugegriffen werden. Verwenden Sie die Eigenschafts [Kopfzeile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) oder die Modul Funktion [List. Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head). Sie können mit der [Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) -Eigenschaft oder der [List. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) -Funktion auf das Ende einer Liste zugreifen. Um nach einem Element anhand des Indexes zu suchen, verwenden Sie die [List. Nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) -Funktion. Mithilfe von `List.nth` wird die Liste durchlaufen. Daher ist es O (*n*). Wenn in Ihrem Code häufig `List.nth` verwendet wird, können Sie erwägen, ob Sie anstelle der Liste ein Array verwenden möchten. Der Elementzugriff in Arrays entspricht "O(1)".

### <a name="boolean-operations-on-lists"></a>Boolesche Operationen für Listen

Die [List. IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) -Funktion bestimmt, ob eine Liste über Elemente verfügt.

Die [List.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) ist-Funktion wendet einen booleschen Test auf Elemente einer Liste an und gibt zurück, `true` Wenn ein beliebiges Element den Test erfüllt. [List. exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) ist ähnlich, funktioniert aber aufeinander folgende Paare von Elementen in zwei Listen.

Das folgende Codebeispiel veranschaulicht die Verwendung von `List.exists`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

Die Ausgabe lautet wie folgt:

```console
For list [0; 1; 2; 3], contains zero is true
```

Das folgende Beispiel veranschaulicht die Verwendung von `List.exists2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

Die Ausgabe lautet wie folgt:

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

Sie können [List. ForAll](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) verwenden, wenn Sie testen möchten, ob alle Elemente einer Liste eine Bedingung erfüllen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

Die Ausgabe lautet wie folgt:

```console
true
false
```

Auf ähnliche Weise bestimmt [List. forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) , ob alle Elemente in den entsprechenden Positionen in zwei Listen einen booleschen Ausdruck erfüllen, der jedes Paar von Elementen einschließt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

Die Ausgabe lautet wie folgt:

```console
true
false
```

### <a name="sort-operations-on-lists"></a>Sortieroperationen für Listen

Die Listen. [Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort)-, [List. SortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)-und [List. sortWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) -Funktionen Sortieren Listen. Die Sortierfunktion bestimmt, welche dieser drei Funktionen verwendet wird. `List.sort` verwendet einen generischen Standardvergleich. Beim generischen Vergleich werden globale Operatoren, die auf der allgemeinen Vergleichsfunktion basieren, zum Vergleichen von Werten verwendet. Der generische Vergleich funktioniert mit einer Vielzahl von Elementtypen sehr effizient, z. B. mit einfachen numerischen Typen, Tupeln, Datensätzen, diskriminierten Unions, Listen, Arrays und allen anderen Typen, die `System.IComparable` implementieren. Für Typen, die `System.IComparable` implementieren, wird für den generischen Vergleich die Funktion `System.IComparable.CompareTo()` verwendet. Der generische Vergleich funktioniert auch mit Zeichenfolgen, wobei jedoch eine kulturunabhängige Sortierreihenfolge verwendet wird. Der generische Vergleich sollte nicht für Typen verwendet werden, die nicht unterstützt werden, z. B. für Funktionstypen. Die optimale Leistung erzielt der generische Standardvergleich außerdem für kleine strukturierte Typen. Für größere strukturierte Typen, die häufig verglichen und sortiert werden müssen, sollten Sie die Implementierung von `System.IComparable` erwägen und eine effiziente Implementierung der Methode `System.IComparable.CompareTo()` bereitstellen.

`List.sortBy` übernimmt eine Funktion, die einen Wert zurückgibt, der als Sortierkriterium verwendet wird, während `List.sortWith` eine Vergleichsfunktion als Argument übernimmt. Die letzten beiden Funktionen sind hilfreich, wenn Sie mit Typen arbeiten, die keinen Vergleich unterstützen bzw. wenn der Vergleich eine komplexere Vergleichssemantik als bei kulturfähige Zeichenfolgen erfordert.

Das folgende Beispiel veranschaulicht die Verwendung von `List.sort`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

Die Ausgabe lautet wie folgt:

```console
[-2; 1; 4; 5; 8]
```

Das folgende Beispiel veranschaulicht die Verwendung von `List.sortBy`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

Die Ausgabe lautet wie folgt:

```console
[1; -2; 4; 5; 8]
```

Das nächste Beispiel veranschaulicht die Verwendung von `List.sortWith`. In diesem Beispiel wird die benutzerdefinierte Vergleichsfunktion `compareWidgets` zunächst dazu verwendet, um ein Feld mit benutzerdefiniertem Typ zu vergleichen. Anschließend wird ein weiteres Feld verglichen, wenn die Werte des ersten Felds gleich sind.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

Die Ausgabe lautet wie folgt:

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a>Suchoperationen für Listen

Für Listen werden zahlreiche Suchoperationen unterstützt. Das einfachste [List. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find)-Element ermöglicht es Ihnen, das erste Element zu finden, das mit einer bestimmten Bedingung übereinstimmt.

Das folgende Codebeispiel veranschaulicht die Verwendung von `List.find` anhand der Suche nach der ersten Zahl in einer Liste, die durch fünf geteilt werden kann.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

The result is 5.

Wenn die Elemente zuerst transformiert werden müssen, nennen Sie [List. Pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), das eine Funktion annimmt, die eine Option zurückgibt, und sucht nach dem ersten Optionswert, der ist `Some(x)` . Anstatt ein Element zurückzugeben, gibt `List.pick` das Ergebnis `x` zurück. Wenn kein übereinstimmendes Element gefunden wird, löst `List.pick` die Ausnahme `System.Collections.Generic.KeyNotFoundException` aus. Im folgenden Code wird die Verwendung von `List.pick` veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

Die Ausgabe lautet wie folgt:

```console
"b"
```

Eine andere Gruppe von Such Vorgängen, [List. tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) und verwandte Funktionen, gibt einen Optionswert zurück. Die `List.tryFind`-Funktion gibt das erste Element einer Liste zurück, das eine Bedingung erfüllt, sofern dieses Element vorhanden ist. Wenn dies nicht der Fall ist, wird der Optionswert `None` zurückgegeben. Die Variations [Liste. tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) gibt den Index des Elements zurück, sofern gefunden, und nicht das Element selbst. Diese Funktionen werden im folgenden Code veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

Die Ausgabe lautet wie folgt:

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a>Arithmetische Operationen für Listen

Allgemeine arithmetische Operationen, wie z. b. Sum und Average, werden in das [Listen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)integriert. Um mit [List. Sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum)arbeiten zu können, muss der List-Elementtyp den `+` -Operator unterstützen und den Wert NULL aufweisen. Alle integrierten arithmetischen Typen erfüllen diese Bedingungen. Um mit [List. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average)arbeiten zu können, muss der Elementtyp die Division ohne Rest unterstützen, die ganzzahlige Typen ausschließt, aber Gleit Komma Typen zulässt. Die Funktionen [List. sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) und [List. averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) akzeptieren eine Funktion als Parameter, und die Ergebnisse dieser Funktion werden verwendet, um die Werte für die Summe oder den Durchschnitt zu berechnen.

Das folgende Codebeispiel veranschaulicht die Verwendung von `List.sum`, `List.sumBy` und `List.average`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

Die Ausgabe lautet `1.000000`.

Im folgenden Code wird die Verwendung von `List.averageBy` veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

Die Ausgabe lautet `5.5`.

### <a name="lists-and-tuples"></a>Listen und Tupel

Listen, die Tupel enthalten, können mithilfe von Funktionen zum Zippen und Entzippen verändert werden. Diese Funktionen vereinen zwei Listen mit einzelnen Werten zu einer Liste von Tupeln oder unterteilen eine Liste von Tupeln in zwei Listen mit einzelnen Werten. Die einfachste [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) Funktion übernimmt zwei Listen mit einzelnen Elementen und erzeugt eine einzelne Liste von tupelpaaren. Eine andere Version, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), erfordert drei Listen mit einzelnen Elementen und erzeugt eine einzelne Liste von Tupeln, die drei Elemente enthalten. Das folgende Codebeispiel veranschaulicht die Verwendung von `List.zip`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

Die Ausgabe lautet wie folgt:

```console
[(1, -1); (2, -2); (3; -3)]
```

Das folgende Codebeispiel veranschaulicht die Verwendung von `List.zip3`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

Die Ausgabe lautet wie folgt:

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

Die entsprechenden Entzippen Sie-Versionen [List. Entzippen Sie](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) und [List. unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3)enthalten Listen von Tupeln und Rückgabe Listen in einem Tupel, wobei die erste Liste alle Elemente enthält, die zuerst in jedem Tupel enthalten waren, und die zweite Liste das zweite Element jedes Tupels usw. enthält.

Im folgenden Codebeispiel wird die Verwendung von [List. unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

Die Ausgabe lautet wie folgt:

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

Im folgenden Codebeispiel wird die Verwendung von [List. unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3)veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

Die Ausgabe lautet wie folgt:

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a>Arbeiten mit Listenelementen

F# unterstützt eine Vielzahl von Operationen mit Listenelementen. Das einfachste ist [List. ITER](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), das es Ihnen ermöglicht, eine Funktion für jedes Element einer Liste aufzurufen. Zu den Variationen zählen [List. iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), mit denen Sie einen Vorgang für Elemente von zwei Listen ausführen können, z [. b. List. iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), `List.iter` mit dem Unterschied, dass der Index der einzelnen Elemente als Argument an die Funktion, die für jedes Element aufgerufen wird, und [List. iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), die eine Kombination aus der Funktionalität von und ist, weitergeleitet wird `List.iter2` `List.iteri` . Diese Funktionen werden im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

Die Ausgabe lautet wie folgt:

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

Eine weitere häufig verwendete Funktion zum Transformieren von Listenelementen ist [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), mit der Sie eine Funktion auf jedes Element einer Liste anwenden und alle Ergebnisse in eine neue Liste einfügen können. [List. map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) und [List. map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) sind Variationen, die mehrere Listen annehmen. Sie können auch [List. MAPI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) und [List. mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2)verwenden, wenn die Funktion zusätzlich zum-Element den Index der einzelnen Elemente an die Funktion übermittelt werden muss. Der einzige Unterschied zwischen `List.mapi2` und `List.mapi` besteht darin, dass `List.mapi2` mit zwei Listen arbeitet. Das folgende Beispiel veranschaulicht [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

Die Ausgabe lautet wie folgt:

```console
[2; 3; 4]
```

Im folgenden Beispiel wird die Verwendung von `List.map2` veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

Die Ausgabe lautet wie folgt:

```console
[5; 7; 9]
```

Im folgenden Beispiel wird die Verwendung von `List.map3` veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

Die Ausgabe lautet wie folgt:

```console
[7; 10; 13]
```

Im folgenden Beispiel wird die Verwendung von `List.mapi` veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

Die Ausgabe lautet wie folgt:

```console
[1; 3; 5]
```

Im folgenden Beispiel wird die Verwendung von `List.mapi2` veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

Die Ausgabe lautet wie folgt:

```console
[0; 7; 18]
```

[List. Collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) ist ähnlich `List.map` , mit der Ausnahme, dass jedes Element eine Liste erzeugt und alle diese Listen in einer endgültigen Liste verkettet werden. Im folgenden Code generiert jedes Element der Liste drei Zahlen. Diese werden alle in einer Liste erfasst.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

Die Ausgabe lautet wie folgt:

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

Sie können auch [List. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter)verwenden, das eine boolesche Bedingung annimmt und eine neue Liste erstellt, die nur aus Elementen besteht, die die angegebene Bedingung erfüllen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

Die Ergebnisliste lautet `[2; 4; 6]`.

Eine Kombination aus Map und Filter, [List. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) ermöglicht Ihnen, Elemente gleichzeitig zu transformieren und auszuwählen. `List.choose` wendet eine Funktion an, die eine Option zu den einzelnen Elementen einer Liste zurückgibt, und gibt eine neue Liste der Ergebnisse für Elemente zurück, wenn die Funktion den Optionswert `Some` liefert.

Der folgende Code veranschaulicht die Verwendung von `List.choose`, um Wörter in Großbuchstaben aus einer Wörterliste auszuwählen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

Die Ausgabe lautet wie folgt:

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a>Arbeiten mit mehreren Listen

Listen können verknüpft werden. Verwenden Sie [List. Append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append), um zwei Listen zu einer zu verknüpfen. Verwenden Sie [List. Concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat), um mehr als zwei Listen zu verknüpfen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a>Falt- und Suchoperationen

Einige Listenoperationen umfassen gegenseitige Abhängigkeiten zwischen allen Listenelementen. Die Fold-und Scanvorgänge lauten wie `List.iter` und `List.map` darin, dass Sie für jedes Element eine Funktion aufrufen. diese Vorgänge stellen jedoch einen zusätzlichen Parameter namens *Akkumulator* bereit, der Informationen über die Berechnung enthält.

Verwenden Sie `List.fold`, um eine Berechnung für eine Liste durchzuführen.

Im folgenden Codebeispiel wird die Verwendung von [List. Fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) zum Durchführen verschiedener Vorgänge veranschaulicht.

Die Liste wird durchlaufen. Der Akkumulator `acc` ist ein Wert, der mit voranschreitender Berechnung weitergegeben wird. Das erste Argument übernimmt den Akkumulator sowie das Listenelement und gibt das Zwischenergebnis der Berechnung für dieses Listenelement zurück. Das zweite Argument ist der Ausgangswert des Akkumulators.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

Die Versionen dieser Funktionen, die eine Ziffer im Funktionsnamen enthalten, arbeiten mit mehreren Listen. [List. fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) führt z. b. Berechnungen für zwei Listen aus.

Das folgende Beispiel veranschaulicht die Verwendung von `List.fold2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

`List.fold` und [List. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) unterscheiden sich in, das `List.fold` den Endwert des zusätzlichen Parameters zurückgibt, jedoch `List.scan` die Liste der Zwischenwerte (zusammen mit dem endgültigen Wert) des zusätzlichen Parameters zurückgibt.

Jede dieser Funktionen enthält eine umgekehrte Variation, z. b [. List. foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), die sich in der Reihenfolge unterscheidet, in der die Liste durchlaufen wird, und in der Reihenfolge der Argumente. Außerdem `List.fold` haben und `List.foldBack` Variationen, [List. fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) und [List. foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), die zwei Listen gleicher Länge annehmen. Die Funktion, die für die einzelnen Elemente ausgeführt wird, kann entsprechende Elemente beider Listen verwenden, um Aktionen durchzuführen. Die Elementtypen beider Listen können wie im folgenden Beispiel unterschiedlich sein, in dem eine Liste Transaktionsbeträge für ein Bankkonto und die andere Liste den Typ der Transaktion enthält: Einzahlung oder Auszahlung.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

Für eine Berechnung wie bei der Addition weisen `List.fold` und `List.foldBack` denselben Effekt auf, da das Ergebnis nicht von der Reihenfolge des Durchlaufs abhängt. Im folgenden Beispiel wird `List.foldBack` zum Hinzufügen der Elemente zu einer Liste verwendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

Das folgende Beispiel kehrt zum Bankkontobeispiel zurück. Dieses Mal wird ein neuer Transaktionstyp hinzugefügt: Zinsberechnung. Der Endsaldo hängt jetzt von der Reihenfolge der Transaktionen ab.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

Die Funktions [Liste ". Reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) " ähnelt `List.fold` `List.scan` in gewisser Weise und, mit der Ausnahme, dass anstelle eines separaten Akkumulators `List.reduce` eine Funktion, die zwei Argumente des Elementtyps annimmt, anstelle eines solchen Arguments ist, und eines dieser Argumente als Akkumulator fungiert, was bedeutet, dass das Zwischenergebnis der Berechnung gespeichert wird. `List.reduce` beginnt mit der Bearbeitung der ersten beiden Listenelemente und verwendet dann das Ergebnis der Operation zusammen mit dem nächsten Element. Da kein separater Akkumulator mit eigenem Typ vorhanden ist, kann `List.reduce` nur anstelle von `List.fold` verwendet werden, wenn Akkumulator und Elementtyp denselben Typ aufweisen. Das folgende Codebeispiel veranschaulicht die Verwendung von `List.reduce`. `List.reduce` löst eine Ausnahme aus, wenn die bereitgestellte Liste keine Elemente enthält.

Im folgenden Code erhält der Lambdaausdruck die Argumente „2“ und „4“ und gibt „6“ zurück. Der nächste Aufruf erhält die Argumente „6“ und „10“, daher ist das Ergebnis „16“.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a>Konvertieren zwischen Listen und anderen Auflistungstypen

Das `List`-Modul stellt Funktionen zum Konvertieren von Sequenzen in Arrays und umgekehrt bereit. Um in eine oder aus einer Sequenz zu konvertieren, verwenden Sie [List. desetq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) oder [List. of-q](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq). Wenn Sie in ein oder aus einem Array konvertieren möchten, verwenden Sie [List.-Array](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) oder [List. ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).

### <a name="additional-operations"></a>Weitere Operationen

Weitere Informationen zu weiteren Vorgängen in Listen finden Sie im Bibliotheks Referenz Thema [List Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
- [Sequenzen](sequences.md)
- [Arrays](arrays.md)
- [Optionen](options.md)
