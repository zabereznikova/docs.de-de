---
title: "Datensätze (F#)"
description: "Erfahren Sie, wie einfache Aggregate benannter Werte, optional mit Mitgliedern von f#-Datensätzen darstellen."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3a3701ea-4308-4fa1-9b5c-b955c470f17a
ms.openlocfilehash: f5ade1db39431d99f10eb6967f02335123b83d34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="records"></a>Datensätze

Datensätze stellen einfache Aggregate benannter Werte dar, optional mit Membern.  Ab f# 4.1, können sie entweder den Strukturen oder Verweistypen sein.  Diese sind standardmäßig Verweistypen.

## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
type [accessibility-modifier] typename = {
    [ mutable ] label1 : type1;
    [ mutable ] label2 : type2;
    ...
}
    [ member-list ]
```

## <a name="remarks"></a>Hinweise
In der vorherigen Syntax *Typename* ist der Name des Datensatztyps, *label1* und *label2* sind Namen von Werten, die so genannte *Bezeichnungen*, und *Typ1* und *Typ2* sind die folgenden Werte sind. *Memberliste* ist die optionale Liste von Elementen für den Typ.  Sie können die `[<Struct>]` Attribut um einen Datensatz, der ein Verweistyp ist, anstatt einen Datensatz für die Struktur zu erstellen.

Es folgen einige Beispiele.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

Wenn jede Bezeichnung in einer separaten Zeile befindet, ist das Semikolon optional.

Sie können Werte in Ausdrücken, die genannte festlegen *aufzeichnen Ausdrücke*. Der Compiler leitet den Typ von Bezeichnungen verwendet (wenn die Bezeichnungen ausreichend von den anderen Datensatztypen unterscheiden). Geschweifte Klammern ({}) schließen Sie den Datensatzausdruck. Der folgende Code zeigt einen Datensatzausdruck, der einen Datensatz mit drei "float"-Elementen mit Bezeichnungen initialisiert `x`, `y` und `z`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

Verwenden Sie die abgekürzte Form nicht, wenn es kann einen anderen Typ, der auch die Bezeichnungen gleichen verfügt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

Die Bezeichnungen der meisten zuletzt deklarierten Typ haben Vorrang gegenüber denen des zuvor deklarierten Typs im vorherigen Beispiel `mypoint3D` wird davon ausgegangen werden `Point3D`. Sie können den Datensatztyp, wie im folgenden Code explizit angeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

Methoden können für Datensatztypen, so wie für Klassentypen definiert werden.

## <a name="creating-records-by-using-record-expressions"></a>Erstellen von Datensätzen mithilfe von Datensatz-Ausdrücken
Sie können Datensätze initialisieren, indem Sie die Bezeichnungen, die im Datensatz definiert sind. Ein Ausdruck, die dies tut wird als bezeichnet eine *aufzeichnen Ausdruck*. Verwenden Sie geschweifte Klammern, um schließen die Datensatzausdruck ein, und verwenden Sie das Semikolon als Trennzeichen.

Im folgende Beispiel wird gezeigt, wie einen Datensatz erstellt wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

Die Semikolons nach dem letzten Feld im Datensatzausdruck und in der Definition sind optional, unabhängig davon, ob die Felder vollständig in einer Zeile.

Wenn Sie einen Datensatz zu erstellen, müssen Sie Werte für jedes Feld angeben. Sie können nicht mit den Werten anderer Felder in der Initialisierungsausdruck für ein Feld verweisen.

Im folgenden Code, den Typ des `myRecord2` wird von den Namen der Felder abgeleitet. Optional können Sie den vollständigen Typnamen explizit angeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Eine andere Form der Erstellung des Datensatzes kann nützlich sein, wenn müssen Sie einen vorhandenen Datensatz kopieren und möglicherweise einige der Werte der Felder ändern. Dies wird anhand der folgenden Codezeile veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

Diese Form des Ausdrucks Datensatz wird aufgerufen, die *kopieren und update der Datensatz Ausdruck*.

Datensätze sind standardmäßig unveränderlich. Allerdings können Sie leicht geänderten Datensätze mithilfe eines Ausdrucks kopieren und Update erstellen. Sie können auch explizit ein veränderlichen Feld angeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

Verwenden Sie das DefaultValue-Attribut nicht mit Feldern Datensatzes. Ein besserer Ansatz ist zum Standardinstanzen von Datensätzen mit Feldern, die initialisiert werden mit Standardwerten zu definieren und dann eine Kopie verwenden und aktualisieren Datensatzausdruck ein, um alle Felder festlegen, die von den Standardwerten abweichen.

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
{
    field1 : int
    field2 : int
}

let defaultRecord1 = { field1 = 0; field2 = 0 }
let defaultRecord2 = { field1 = 1; field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with field2 = 42 }
```

## <a name="pattern-matching-with-records"></a>Mustervergleich mit Datensätzen
Datensätze können mit dem Mustervergleich verwendet werden. Sie können einige Felder explizit angeben und Bereitstellen von Variablen für die anderen Felder, die zugewiesen wird, wenn eine Übereinstimmung auftritt. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

Die Ausgabe dieses Codes lautet wie folgt.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>Unterschiede zwischen Datensätzen und Klassen
Datensatzfelder unterscheiden sich von Klassen, sie werden automatisch als Eigenschaften verfügbar gemacht, und es handelt sich bei der Erstellung verwendet und Kopieren von Datensätzen. Datensatz Konstruktion unterscheidet sich auch von der Klassenkonstruktion. Einen Konstruktor kann nicht definieren, in einen Datensatztyp. Stattdessen gilt die Konstruktionssyntax, die in diesem Thema beschrieben. Klassen verfügen über keine direkte Beziehung zwischen Konstruktorparameter, Felder und Eigenschaften.

Wie Union "und" Struktur weisen Datensätze strukturelle Gleichheitssemantik auf. Klassen verfügen über Gleichheitssemantik auf. Dies wird im folgenden Codebeispiel wird veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

Wenn Sie den gleichen Code mit Klassen schreiben, die zwei Klassenobjekte wäre ungleich daran, dass die beiden Werte zwei Objekte auf dem Heap darstellen und nur die Adressen verglichen werden würde (es sei denn, der Klassentyp überschreibt die `System.Object.Equals` Methode).

Wenn Sie auf Gleichheit Datensätze verweisen müssen, fügen Sie das Attribut `[<ReferenceEquality>]` oberhalb des Datensatzes.

## <a name="see-also"></a>Siehe auch
[F#-Typen](fsharp-types.md)

[Klassen](classes.md)

[F#-Sprachreferenz](index.md)

[Verweisgleichheit](https://msdn.microsoft.com/en-us/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)

[Mustervergleich](pattern-matching.md)
