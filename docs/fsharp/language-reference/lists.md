---
title: Listen
description: 'Erfahren Sie mehr über F #-Listen, eine geordnete, unveränderliche Reihe von Elementen desselben Typs.'
ms.date: 05/16/2016
ms.openlocfilehash: 236ae77813a3448f159228c5c58d9fe3d024fbd8
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854970"
---
# <a name="lists"></a>Listen

Eine Liste in F# stellt eine geordnete, unveränderliche Reihe von Elementen desselben Typs dar. Verwenden Sie die Funktionen im [Listen Modul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788), um grundlegende Vorgänge für Listen auszuführen.

> [!NOTE]
> Die docs.Microsoft.com-API-Referenz für F # ist nicht fertig. Wenn Sie auf unterbrochene Verknüpfungen stoßen, verweisen Sie stattdessen auf die [Dokumentation der F #-Kernbibliothek](https://fsharp.github.io/fsharp-core-docs/) .

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

Funktionen zum Ausführen von Vorgängen für Listen sind im [Listen Modul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)verfügbar.

Da Listen in F# unveränderlich sind, erstellen alle modifizierenden Operationen neue Listen, anstatt die vorhandenen Listen zu verändern.

Listen in F # werden als einzeln verknüpfte Listen implementiert. Dies bedeutet, dass Vorgänge, die nur auf den Anfang der Liste zugreifen, o (1) sind und der Element Zugriff o (*n*) ist.

## <a name="properties"></a>Eigenschaften

Der Listentyp unterstützt die folgenden Eigenschaften:

|Eigenschaft|type|BESCHREIBUNG|
|--------|----|-----------|
|[Stadt](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|Das erste Element.|
|[Leer](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|Eine statische Eigenschaft, die eine leere Liste des entsprechenden Typs zurückgibt.|
|[IsEmpty](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|Ergibt `true`, wenn die Liste keine Elemente enthält.|
|[Element](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|Das Element am angegebenen (nullbasierten) Index.|
|[Länge](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|Die Anzahl der Elemente.|
|[Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|Die Liste ohne das erste Element.|

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

Das [List-Modul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) stellt Funktionen bereit, die auf die Elemente einer Liste zugreifen. Auf das Anfangselement kann am schnellsten und einfachsten zugegriffen werden. Verwenden Sie die Eigenschafts [Kopfzeile](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) oder die Modul Funktion [List. Head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2). Sie können mit der [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) -Eigenschaft oder der [List. tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) -Funktion auf das Ende einer Liste zugreifen. Um nach einem Element anhand des Indexes zu suchen, verwenden Sie die [List. Nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) -Funktion. Mithilfe von `List.nth` wird die Liste durchlaufen. Daher ist es O (*n*). Wenn in Ihrem Code häufig `List.nth` verwendet wird, können Sie erwägen, ob Sie anstelle der Liste ein Array verwenden möchten. Der Elementzugriff in Arrays entspricht "O(1)".

### <a name="boolean-operations-on-lists"></a>Boolesche Operationen für Listen

Die [List. IsEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) -Funktion bestimmt, ob eine Liste über Elemente verfügt.

Die [List.](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) ist-Funktion wendet einen booleschen Test auf Elemente einer Liste an und gibt zurück, `true` Wenn ein beliebiges Element den Test erfüllt. [List. exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) ist ähnlich, funktioniert aber aufeinander folgende Paare von Elementen in zwei Listen.

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

Sie können [List. ForAll](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) verwenden, wenn Sie testen möchten, ob alle Elemente einer Liste eine Bedingung erfüllen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

Die Ausgabe lautet wie folgt:

```console
true
false
```

Auf ähnliche Weise bestimmt [List. forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) , ob alle Elemente in den entsprechenden Positionen in zwei Listen einen booleschen Ausdruck erfüllen, der jedes Paar von Elementen einschließt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

Die Ausgabe lautet wie folgt:

```console
true
false
```

### <a name="sort-operations-on-lists"></a>Sortieroperationen für Listen

Die Listen. [Sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d)-, [List. SortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359)-und [List. sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) -Funktionen Sortieren Listen. Die Sortierfunktion bestimmt, welche dieser drei Funktionen verwendet wird. `List.sort` verwendet einen generischen Standardvergleich. Beim generischen Vergleich werden globale Operatoren, die auf der allgemeinen Vergleichsfunktion basieren, zum Vergleichen von Werten verwendet. Der generische Vergleich funktioniert mit einer Vielzahl von Elementtypen sehr effizient, z. B. mit einfachen numerischen Typen, Tupeln, Datensätzen, diskriminierten Unions, Listen, Arrays und allen anderen Typen, die `System.IComparable` implementieren. Für Typen, die `System.IComparable` implementieren, wird für den generischen Vergleich die Funktion `System.IComparable.CompareTo()` verwendet. Der generische Vergleich funktioniert auch mit Zeichenfolgen, wobei jedoch eine kulturunabhängige Sortierreihenfolge verwendet wird. Der generische Vergleich sollte nicht für Typen verwendet werden, die nicht unterstützt werden, z. B. für Funktionstypen. Die optimale Leistung erzielt der generische Standardvergleich außerdem für kleine strukturierte Typen. Für größere strukturierte Typen, die häufig verglichen und sortiert werden müssen, sollten Sie die Implementierung von `System.IComparable` erwägen und eine effiziente Implementierung der Methode `System.IComparable.CompareTo()` bereitstellen.

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

Für Listen werden zahlreiche Suchoperationen unterstützt. Das einfachste [List. Find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06)-Element ermöglicht es Ihnen, das erste Element zu finden, das mit einer bestimmten Bedingung übereinstimmt.

Das folgende Codebeispiel veranschaulicht die Verwendung von `List.find` anhand der Suche nach der ersten Zahl in einer Liste, die durch fünf geteilt werden kann.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

The result is 5.

Wenn die Elemente zuerst transformiert werden müssen, nennen Sie [List. Pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), das eine Funktion annimmt, die eine Option zurückgibt, und sucht nach dem ersten Optionswert, der ist `Some(x)` . Anstatt ein Element zurückzugeben, gibt `List.pick` das Ergebnis `x` zurück. Wenn kein übereinstimmendes Element gefunden wird, löst `List.pick` die Ausnahme `System.Collections.Generic.KeyNotFoundException` aus. Im folgenden Code wird die Verwendung von `List.pick` veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

Die Ausgabe lautet wie folgt:

```console
"b"
```

Eine andere Gruppe von Such Vorgängen, [List. tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) und verwandte Funktionen, gibt einen Optionswert zurück. Die `List.tryFind`-Funktion gibt das erste Element einer Liste zurück, das eine Bedingung erfüllt, sofern dieses Element vorhanden ist. Wenn dies nicht der Fall ist, wird der Optionswert `None` zurückgegeben. Die Variations [Liste. tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) gibt den Index des Elements zurück, sofern gefunden, und nicht das Element selbst. Diese Funktionen werden im folgenden Code veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

Die Ausgabe lautet wie folgt:

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a>Arithmetische Operationen für Listen

Allgemeine arithmetische Operationen, wie z. b. Sum und Average, werden in das [Listen Modul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)integriert. Um mit [List. Sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9)arbeiten zu können, muss der List-Elementtyp den `+` -Operator unterstützen und den Wert NULL aufweisen. Alle integrierten arithmetischen Typen erfüllen diese Bedingungen. Um mit [List. Average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1)arbeiten zu können, muss der Elementtyp die Division ohne Rest unterstützen, die ganzzahlige Typen ausschließt, aber Gleit Komma Typen zulässt. Die Funktionen [List. sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) und [List. averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) akzeptieren eine Funktion als Parameter, und die Ergebnisse dieser Funktion werden verwendet, um die Werte für die Summe oder den Durchschnitt zu berechnen.

Das folgende Codebeispiel veranschaulicht die Verwendung von `List.sum`, `List.sumBy` und `List.average`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

Die Ausgabe lautet `1.000000`.

Im folgenden Code wird die Verwendung von `List.averageBy` veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

Die Ausgabe lautet `5.5`.

### <a name="lists-and-tuples"></a>Listen und Tupel

Listen, die Tupel enthalten, können mithilfe von Funktionen zum Zippen und Entzippen verändert werden. Diese Funktionen vereinen zwei Listen mit einzelnen Werten zu einer Liste von Tupeln oder unterteilen eine Liste von Tupeln in zwei Listen mit einzelnen Werten. Die einfachste [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) Funktion übernimmt zwei Listen mit einzelnen Elementen und erzeugt eine einzelne Liste von tupelpaaren. Eine andere Version, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), erfordert drei Listen mit einzelnen Elementen und erzeugt eine einzelne Liste von Tupeln, die drei Elemente enthalten. Das folgende Codebeispiel veranschaulicht die Verwendung von `List.zip`.

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

Die entsprechenden Entzippen Sie-Versionen [List. Entzippen Sie](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) und [List. unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)enthalten Listen von Tupeln und Rückgabe Listen in einem Tupel, wobei die erste Liste alle Elemente enthält, die zuerst in jedem Tupel enthalten waren, und die zweite Liste das zweite Element jedes Tupels usw. enthält.

Im folgenden Codebeispiel wird die Verwendung von [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

Die Ausgabe lautet wie folgt:

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

Im folgenden Codebeispiel wird die Verwendung von [List. unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

Die Ausgabe lautet wie folgt:

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a>Arbeiten mit Listenelementen

F# unterstützt eine Vielzahl von Operationen mit Listenelementen. Das einfachste ist [List. ITER](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), das es Ihnen ermöglicht, eine Funktion für jedes Element einer Liste aufzurufen. Zu den Variationen zählen [List. iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), mit denen Sie einen Vorgang für Elemente von zwei Listen ausführen können, z [. b. List. iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), `List.iter` mit dem Unterschied, dass der Index der einzelnen Elemente als Argument an die Funktion, die für jedes Element aufgerufen wird, und [List. iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), die eine Kombination aus der Funktionalität von und ist, weitergeleitet wird `List.iter2` `List.iteri` . Diese Funktionen werden im folgenden Codebeispiel veranschaulicht.

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

Eine weitere häufig verwendete Funktion zum Transformieren von Listenelementen ist [List. map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), mit der Sie eine Funktion auf jedes Element einer Liste anwenden und alle Ergebnisse in eine neue Liste einfügen können. [List. map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) und [List. map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) sind Variationen, die mehrere Listen annehmen. Sie können auch [List. MAPI](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) und [List. mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49)verwenden, wenn die Funktion zusätzlich zum-Element den Index der einzelnen Elemente an die Funktion übermittelt werden muss. Der einzige Unterschied zwischen `List.mapi2` und `List.mapi` besteht darin, dass `List.mapi2` mit zwei Listen arbeitet. Das folgende Beispiel veranschaulicht [List. map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).

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

[List. Collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) ist ähnlich `List.map` , mit der Ausnahme, dass jedes Element eine Liste erzeugt und alle diese Listen in einer endgültigen Liste verkettet werden. Im folgenden Code generiert jedes Element der Liste drei Zahlen. Diese werden alle in einer Liste erfasst.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

Die Ausgabe lautet wie folgt:

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

Sie können auch [List. Filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248)verwenden, das eine boolesche Bedingung annimmt und eine neue Liste erstellt, die nur aus Elementen besteht, die die angegebene Bedingung erfüllen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

Die Ergebnisliste lautet `[2; 4; 6]`.

Eine Kombination aus Map und Filter, [List. Choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) ermöglicht Ihnen, Elemente gleichzeitig zu transformieren und auszuwählen. `List.choose` wendet eine Funktion an, die eine Option zu den einzelnen Elementen einer Liste zurückgibt, und gibt eine neue Liste der Ergebnisse für Elemente zurück, wenn die Funktion den Optionswert `Some` liefert.

Der folgende Code veranschaulicht die Verwendung von `List.choose`, um Wörter in Großbuchstaben aus einer Wörterliste auszuwählen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

Die Ausgabe lautet wie folgt:

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a>Arbeiten mit mehreren Listen

Listen können verknüpft werden. Verwenden Sie [List. Append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426), um zwei Listen zu einer zu verknüpfen. Verwenden Sie [List. Concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c), um mehr als zwei Listen zu verknüpfen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a>Falt- und Suchoperationen

Einige Listenoperationen umfassen gegenseitige Abhängigkeiten zwischen allen Listenelementen. Die Fold-und Scanvorgänge lauten wie `List.iter` und `List.map` darin, dass Sie für jedes Element eine Funktion aufrufen. diese Vorgänge stellen jedoch einen zusätzlichen Parameter namens *Akkumulator* bereit, der Informationen über die Berechnung enthält.

Verwenden Sie `List.fold`, um eine Berechnung für eine Liste durchzuführen.

Im folgenden Codebeispiel wird die Verwendung von [List. Fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) zum Durchführen verschiedener Vorgänge veranschaulicht.

Die Liste wird durchlaufen. Der Akkumulator `acc` ist ein Wert, der mit voranschreitender Berechnung weitergegeben wird. Das erste Argument übernimmt den Akkumulator sowie das Listenelement und gibt das Zwischenergebnis der Berechnung für dieses Listenelement zurück. Das zweite Argument ist der Ausgangswert des Akkumulators.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

Die Versionen dieser Funktionen, die eine Ziffer im Funktionsnamen enthalten, arbeiten mit mehreren Listen. [List. fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) führt z. b. Berechnungen für zwei Listen aus.

Das folgende Beispiel veranschaulicht die Verwendung von `List.fold2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

`List.fold`und [List. Scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) unterscheiden sich in, das `List.fold` den Endwert des zusätzlichen Parameters zurückgibt, jedoch `List.scan` die Liste der Zwischenwerte (zusammen mit dem endgültigen Wert) des zusätzlichen Parameters zurückgibt.

Jede dieser Funktionen enthält eine umgekehrte Variation, z. b [. List. foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), die sich in der Reihenfolge unterscheidet, in der die Liste durchlaufen wird, und in der Reihenfolge der Argumente. Außerdem `List.fold` haben und `List.foldBack` Variationen, [List. fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) und [List. foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), die zwei Listen gleicher Länge annehmen. Die Funktion, die für die einzelnen Elemente ausgeführt wird, kann entsprechende Elemente beider Listen verwenden, um Aktionen durchzuführen. Die Elementtypen beider Listen können wie im folgenden Beispiel unterschiedlich sein, in dem eine Liste Transaktionsbeträge für ein Bankkonto und die andere Liste den Typ der Transaktion enthält: Einzahlung oder Auszahlung.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

Für eine Berechnung wie bei der Addition weisen `List.fold` und `List.foldBack` denselben Effekt auf, da das Ergebnis nicht von der Reihenfolge des Durchlaufs abhängt. Im folgenden Beispiel wird `List.foldBack` zum Hinzufügen der Elemente zu einer Liste verwendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

Das folgende Beispiel kehrt zum Bankkontobeispiel zurück. Dieses Mal wird ein neuer Transaktionstyp hinzugefügt: Zinsberechnung. Der Endsaldo hängt jetzt von der Reihenfolge der Transaktionen ab.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

Die Funktions [Liste ". Reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) " ähnelt `List.fold` `List.scan` in gewisser Weise und, mit der Ausnahme, dass anstelle eines separaten Akkumulators `List.reduce` eine Funktion, die zwei Argumente des Elementtyps annimmt, anstelle eines solchen Arguments ist, und eines dieser Argumente als Akkumulator fungiert, was bedeutet, dass das Zwischenergebnis der Berechnung gespeichert wird. `List.reduce` beginnt mit der Bearbeitung der ersten beiden Listenelemente und verwendet dann das Ergebnis der Operation zusammen mit dem nächsten Element. Da kein separater Akkumulator mit eigenem Typ vorhanden ist, kann `List.reduce` nur anstelle von `List.fold` verwendet werden, wenn Akkumulator und Elementtyp denselben Typ aufweisen. Das folgende Codebeispiel veranschaulicht die Verwendung von `List.reduce`. `List.reduce` löst eine Ausnahme aus, wenn die bereitgestellte Liste keine Elemente enthält.

Im folgenden Code erhält der Lambdaausdruck die Argumente „2“ und „4“ und gibt „6“ zurück. Der nächste Aufruf erhält die Argumente „6“ und „10“, daher ist das Ergebnis „16“.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a>Konvertieren zwischen Listen und anderen Auflistungstypen

Das `List`-Modul stellt Funktionen zum Konvertieren von Sequenzen in Arrays und umgekehrt bereit. Um in eine oder aus einer Sequenz zu konvertieren, verwenden Sie [List. desetq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) oder [List. of-q](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0). Wenn Sie in ein oder aus einem Array konvertieren möchten, verwenden Sie [List.-Array](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) oder [List. ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).

### <a name="additional-operations"></a>Weitere Operationen

Weitere Informationen zu weiteren Vorgängen in Listen finden Sie im Bibliotheks Referenz Thema [Collections. List-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
- [Sequenzen](sequences.md)
- [Arrays](arrays.md)
- [Optionen](options.md)
