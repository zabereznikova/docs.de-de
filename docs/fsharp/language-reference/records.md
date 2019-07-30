---
title: Datensätze
description: Erfahren Sie, wie F#-Datensätzen für einfache Aggregate benannter Werte, optional mit Membern darstellen.
ms.date: 06/09/2019
ms.openlocfilehash: d92a1a7517e5b05ee687926df29f33fab123b4dd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627281"
---
# <a name="records"></a>Datensätze

Datensätze stellen einfache Aggregate benannter Werte dar, optional mit Membern. Sie können entweder Strukturen oder Verweis Typen sein.  Standardmäßig handelt es sich dabei um Verweis Typen.

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

In der vorherigen Syntax ist *tykame* der Name des Daten Satz Typs, *Label1* und *Label2* sind Namen von Werten, die als *Bezeichnungen*bezeichnet werden, und *Typ1* und *Typ2* sind die Typen dieser Werte. "Element *-List* " ist die optionale Liste der Member für den Typ.  Mit dem `[<Struct>]` -Attribut können Sie einen Strukturdaten Satz anstelle eines Datensatzes erstellen, bei dem es sich um einen Verweistyp handelt.

Im folgenden finden Sie einige Beispiele.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

Wenn sich jede Bezeichnung in einer separaten Zeile befindet, ist das Semikolon optional.

Sie können Werte in Ausdrücken festlegen, die als *Daten Satz Ausdrücke*bezeichnet werden. Der Compiler leitet den Typ von den verwendeten Bezeichnungen ab (wenn sich die Bezeichnungen ausreichend von denen anderer Daten Satz Typen unterscheiden). Geschweifte Klammern ({}) schließen den Daten Satz Ausdruck ein. Der folgende Code zeigt einen Datensatz-Ausdruck, der einen Datensatz mit drei float-Elementen mit `x`den `y` Bezeichnungen `z`, und initialisiert.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

Verwenden Sie das gekürzte Formular nicht, wenn ein anderer Typ vorhanden sein könnte, der auch über dieselben Bezeichnungen verfügt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

Die Bezeichnungen des zuletzt deklarierten Typs haben Vorrang vor denen des zuvor deklarierten Typs `mypoint3D` `Point3D`. im vorherigen Beispiel wird daher als abgeleitet. Sie können den Daten Satz Typen explizit angeben, wie im folgenden Code.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

Methoden können für Daten Satz Typen genau wie für Klassentypen definiert werden.

## <a name="creating-records-by-using-record-expressions"></a>Erstellen von Datensätzen mithilfe von Daten Satz Ausdrücken

Sie können Datensätze mit den Bezeichnungen initialisieren, die im Datensatz definiert sind. Ein Ausdruck, der dies bewirkt, wird als *Daten Satz Ausdruck*bezeichnet. Verwenden Sie geschweifte Klammern, um den Daten Satz Ausdruck einzuschließen und das Semikolon als Trennzeichen zu verwenden.

Im folgenden Beispiel wird gezeigt, wie ein Datensatz erstellt wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

Die Semikolons nach dem letzten Feld im Daten Satz Ausdruck und in der Typdefinition sind optional, unabhängig davon, ob sich die Felder in einer Zeile befinden.

Wenn Sie einen Datensatz erstellen, müssen Sie Werte für jedes Feld angeben. Sie können nicht auf die Werte anderer Felder im Initialisierungs Ausdruck für ein beliebiges Feld verweisen.

Im folgenden Code `myRecord2` wird der Typ von aus den Namen der Felder abgeleitet. Optional können Sie den Typnamen explizit angeben.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Eine andere Form der Daten Satz Erstellung kann nützlich sein, wenn Sie einen vorhandenen Datensatz kopieren und möglicherweise einige der Feldwerte ändern müssen. Dies wird in der folgenden Codezeile veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

Diese Form des Daten Satz Ausdrucks wird als *Kopier-und Update Daten Satz Ausdruck*bezeichnet.

Datensätze sind standardmäßig unveränderlich. mithilfe eines Kopier-und Update Ausdrucks können Sie jedoch problemlos geänderte Datensätze erstellen. Sie können auch explizit ein änderbares Feld angeben.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

Verwenden Sie das DefaultValue-Attribut nicht mit Datensatz-Feldern. Ein besserer Ansatz besteht darin, Standard Instanzen von Datensätzen mit Feldern zu definieren, die mit Standardwerten initialisiert werden. Anschließend können Sie mithilfe eines Ausdrucks zum Kopieren und Aktualisieren von Datensätzen alle Felder festlegen, die von den Standardwerten abweichen.

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

## <a name="creating-mutually-recursive-records"></a>Erstellen von rekursiven Datensätzen

Wenn Sie einen Datensatz erstellen, ist es möglicherweise von einem anderen Typ abhängig, den Sie später definieren möchten. Dies ist ein Kompilierungsfehler, es sei denn, Sie definieren die Daten Satz Typen, die gegenseitig rekursiv

Das Definieren von gegenseitig rekursiven Daten `and` Sätzen erfolgt mit dem Schlüsselwort. Auf diese Weise können Sie zwei oder mehr Daten Satz Typen miteinander verknüpfen.

Der folgende Code definiert z. b. `Person` einen `Address` -Typ und den-Typ als gegenseitig rekursiv:

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string }
```

Wenn Sie das vorherige Beispiel ohne das `and` Schlüsselwort definieren, würde es nicht kompiliert. Das `and` Schlüsselwort ist für gegenseitig rekursive Definitionen erforderlich.

## <a name="pattern-matching-with-records"></a>Musterabgleich mit Datensätzen

Datensätze können mit Musterabgleich verwendet werden. Sie können einige Felder explizit angeben und Variablen für andere Felder bereitstellen, die zugewiesen werden, wenn eine Entsprechung auftritt. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

Die Ausgabe dieses Codes lautet wie folgt.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>Unterschiede zwischen Datensätzen und Klassen

Daten Satz Felder unterscheiden sich von Klassen darin, dass Sie automatisch als Eigenschaften verfügbar gemacht werden und beim Erstellen und Kopieren von Datensätzen verwendet werden. Die Daten Satz Erstellung unterscheidet sich auch von der Klassen Erstellung In einem Daten Recordtyp können Sie keinen Konstruktor definieren. Stattdessen gilt die in diesem Thema beschriebene Konstruktions Syntax. Klassen haben keine direkte Beziehung zwischen Konstruktorparametern, Feldern und Eigenschaften.

Wie Union-und Strukturtypen haben Datensätze strukturelle Gleichheits Semantik. Klassen verfügen über eine Verweis Gleichheits Semantik. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

Die Ausgabe dieses Codes lautet wie folgt:

```
The records are equal.
```

Wenn Sie denselben Code mit Klassen schreiben, sind die beiden Klassen Objekte ungleich, da die beiden Werte zwei Objekte auf dem Heap darstellen und nur die Adressen verglichen werden würden (es sei denn, der Klassentyp über `System.Object.Equals` schreibt die-Methode).

Wenn Sie Verweis Gleichheit für Datensätze benötigen, fügen Sie `[<ReferenceEquality>]` das Attribut oberhalb des Datensatzes hinzu.

## <a name="see-also"></a>Siehe auch

- [F#-Typen](fsharp-types.md)
- [Klassen](classes.md)
- [F#-Sprachreferenz](index.md)
- [Verweis-Gleichheit](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [Mustervergleich](pattern-matching.md)
