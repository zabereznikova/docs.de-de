---
title: Datensätze (F#)
description: Erfahren Sie, wie f#-Datensätzen für einfache Aggregate benannter Werte, optional mit Membern darstellen.
ms.date: 05/16/2016
ms.openlocfilehash: 6103d96b6b80a9e2ed168755958dbe800f7fa862
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44368215"
---
# <a name="records"></a>Datensätze

Datensätze stellen einfache Aggregate benannter Werte dar, optional mit Membern.  Ab f# 4.1, können sie entweder den Strukturen oder Verweistypen sein.  Sie sind Verweistypen standardmäßig.

## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Typename* ist der Name des Datensatztyps, *label1* und *label2* sind Namen von Werten, um genannte *Bezeichnungen*, und *type1* und *Typ2* sind die Typen dieser Werte. *Memberliste* ist die optionale Liste von Elementen für den Typ.  Sie können die `[<Struct>]` Attribut um einen Datensatz, der ein Verweistyp ist, statt einen Eintrag für die Struktur zu erstellen.

Es folgen einige Beispiele.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

Wenn jede Bezeichnung in einer separaten Zeile ist, ist das Semikolon optional.

Sie können Werte in Ausdrücken, die als bekannt festlegen *aufzeichnen Ausdrücke*. Der Compiler leitet den Typ von Bezeichnungen verwendet (wenn die Bezeichnungen ausreichend unterscheiden, andere Eintragstypen werden). Geschweifte Klammern ({}) einschließen der Datensatzausdruck. Der folgende Code zeigt einen Datensatzausdruck, der einen Datensatz mit drei Float-Elemente mit Bezeichnungen initialisiert `x`, `y` und `z`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

Verwenden Sie nicht die abgekürzte Form aus, wenn möglicherweise einen anderen Typ, der auch die gleichen Bezeichnungen aufweist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

Die Bezeichnungen von der die zuletzt deklarierte Typ haben Vorrang gegenüber denen des zuvor deklarierten Typs im vorherigen Beispiel `mypoint3D` wird davon ausgegangen werden `Point3D`. Sie können den Datensatztyp, wie im folgenden Code explizit angeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

Methoden können für Record-Typen, genau wie bei Klassentypen definiert werden.

## <a name="creating-records-by-using-record-expressions"></a>Erstellen von Datensätzen mithilfe von Datensatz-Ausdrücken

Sie können Einträge initialisieren, indem Sie mit den Bezeichnungen, die im Datensatz definiert sind. Ein Ausdruck, der dieses wird als bezeichnet ein *aufzeichnen Ausdruck*. Verwenden Sie geschweifte Klammern zum Einschließen der Datensatzausdruck und verwenden Sie das Semikolon als Trennzeichen ein.

Das folgende Beispiel zeigt, wie Sie einen Datensatz zu erstellen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

Die Semikolons aus, nachdem das letzte Feld in der Datensatzausdruck und in der Typdefinition sind optional, unabhängig davon, ob die Felder in einer Zeile.

Wenn Sie einen Datensatz erstellen, müssen Sie Werte für jedes Feld angeben. Sie können nicht auf die Werte der anderen Felder in den Initialisierungsausdruck für ein Feld verweisen.

Im folgenden Code, den Typ des `myRecord2` wird abgeleitet aus den Namen der Felder. Optional können Sie den Typnamen explizit angeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Eine andere Form der Datensatzkonstruktion kann nützlich sein, beim Kopieren eines vorhandenen Datensatzes, und möglicherweise einige Werte der Felder ändern. Die folgende Codezeile veranschaulicht dies.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

Diese Form des datensatzausdrucks heißt die *kopieren und Aktualisieren des Datensatzes Ausdruck*.

Datensätze sind standardmäßig nicht verändert werden. Allerdings können Sie leicht geänderte Datensätze mithilfe eines Ausdrucks kopieren und aktualisieren erstellen. Sie können auch explizit ein veränderlichen Feld angeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

Verwenden Sie das DefaultValue-Attribut nicht mit Feldern Datensatzes an. Ein besserer Ansatz ist Standardinstanzen von Datensätzen mit Feldern, die initialisiert werden, auf die Standardwerte definieren und dann eine Kopie verwenden und aktualisieren Datensatzausdruck ein, um alle Felder festgelegt, die von den Standardwerten abweichen.

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="pattern-matching-with-records"></a>Musterabgleich mit Datensätzen

Datensätze können mit dem Mustervergleich verwendet werden. Sie können einige Felder explizit angeben und Bereitstellen von Variablen für die anderen Felder, die zugewiesen werden soll, wenn eine Übereinstimmung auftritt. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

Die Ausgabe dieses Codes lautet wie folgt aus.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>Unterschiede zwischen Datensätzen und Klassen

Datensatzfelder unterscheiden sich von Klassen, sie werden automatisch als Eigenschaften verfügbar gemacht, und es handelt sich bei der Erstellung verwendet und der Datensätze kopieren. Datensatzkonstruktion unterscheidet sich auch von der Klassenkonstruktion. Einen Konstruktor kann nicht in einem Datensatz vom Typ definiert werden. Stattdessen gilt die Konstruktionssyntax, die in diesem Thema beschrieben. Klassen verfügen über keine direkte Beziehung zwischen Konstruktorparameter, Felder und Eigenschaften.

Wie Union- und Struktur enthalten Datensätze strukturelle Gleichheit-Semantik. Klassen verfügen über Gleichheitssemantik auf. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

Die Ausgabe dieses Codes lautet wie folgt aus:

```
The records are equal.
```

Wenn Sie den gleichen Code mit Klassen schreiben, die beiden Klassenobjekte wäre ungleich daran, dass zwei Objekte auf dem Heap die beiden Werte darstellen, und nur die Adressen verglichen werden sollen (es sei denn, der den Klassentyp überschreibt die `System.Object.Equals` Methode).

Wenn Sie überprüft die Gleichheit für Datensätze verweisen müssen, fügen Sie das Attribut `[<ReferenceEquality>]` über dem Datensatz.

## <a name="see-also"></a>Siehe auch

- [F#-Typen](fsharp-types.md)
- [Klassen](classes.md)
- [F#-Sprachreferenz](index.md)
- [Verweisgleichheit](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [Mustervergleich](pattern-matching.md)
