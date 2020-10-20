---
title: Strukturen
description: 'Erfahren Sie mehr über die F #-Struktur, einen kompakten Objekttyp, der häufig effizienter ist als eine Klasse für Typen mit einer kleinen Datenmenge und einfachem Verhalten.'
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223819"
---
# <a name="structures"></a>Strukturen

Eine *Struktur* ist ein kompakter Objekttyp, der effizienter als eine Klasse für Typen sein kann, die eine geringe Datenmenge und ein einfaches Verhalten aufweisen.

## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a>Bemerkungen

Strukturen sind *Werttypen*. Dies bedeutet, dass Sie direkt auf dem Stapel oder, wenn Sie als Felder oder Array Elemente verwendet werden, Inline im übergeordneten Typ gespeichert werden. Im Gegensatz zu Klassen und Datensätzen verfügen Strukturen über eine Übergabewertsemantik. Dies bedeutet, dass sie hauptsächlich für kleine Datenaggregate sinnvoll sind, die häufig aufgerufen und kopiert werden.

In der vorherigen Syntax werden zwei Formen gezeigt. Die erste ist nicht die einfache Syntax, aber sie wird trotzdem häufig verwendet, da Sie bei Verwendung der Schlüsselwörter `struct` und `end` das `StructAttribute`-Attribut auslassen können, das in der zweiten Form angezeigt wird. Sie können `StructAttribute` zu `Struct` abkürzen.

Die *Type-Definition-Elements-und-* Member in der vorherigen Syntax repräsentieren Member-Deklarationen und-Definitionen. Strukturen können über Konstruktoren sowie änderbare und unveränderliche Felder verfügen, und sie können Member und Schnittstellenimplementierungen deklarieren. Weitere Informationen finden Sie unter [Members](./members/index.md).

Strukturen können nicht an der Vererbung beteiligt sein, sie können keine `let`- oder `do`-Bindungen enthalten und können nicht rekursiv Felder des eigenen Typs enthalten (obwohl sie Verweiszellen enthalten können, die auf den eigenen Typ verweisen).

Da Strukturen keine `let`-Bindungen zulassen, müssen Sie Felder in Strukturen mit dem `val`-Schlüsselwort deklarieren. Das `val`-Schlüsselwort definiert ein Feld und den Typ, es lässt jedoch keine Initialisierung zu. In diesem Fall werden `val`-Deklarationen mit 0 oder null initialisiert. Aus diesem Grund erfordern Strukturen, die über einen impliziten Konstruktor verfügen (d. h. Parameter, die direkt nach dem Strukturnamen in der Deklaration angegeben werden), dass `val`-Deklarationen mit dem `DefaultValue`-Attribut gekennzeichnet werden. Strukturen, die über einen definierten Konstruktor verfügen, unterstützen weiterhin die Initialisierung mit 0 (null). Aus diesem Grund ist das `DefaultValue`-Attribut eine Deklaration, dass der Wert 0 (Null) für das Feld gültig ist. Implizite Konstruktoren für Strukturen führen keine Aktionen aus, da `let`- und `do`-Bindungen für den Typ nicht zulässig sind, aber die übergebenen impliziten Konstruktorparameterwerte sind als private Felder verfügbar.

Explizite Konstruktoren können eine Initialisierung von Feldwerten beinhalten. Wenn Sie eine Struktur mit einem expliziten Konstruktor haben, unterstützt sie weiterhin die Initialisierung mit 0 (Null); Sie verwenden jedoch nicht das `DefaultValue`-Attribut auf den `val`-Deklarationen, da es mit dem expliziten Konstruktor in Konflikt steht. Weitere Informationen zu `val` Deklarationen finden Sie unter [Explizite Felder: das- `val` Schlüsselwort](./members/explicit-fields-the-val-keyword.md).

Attribute und Zugriffsmodifizierer sind für Strukturen zulässig und folgen denselben Regeln wie jene für andere Typen. Weitere Informationen finden Sie unter [Attribute](attributes.md) und [Access Control](access-control.md).

Die folgenden Codebeispiele veranschaulichen Strukturdefinitionen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>ByRef-Strukturen

Sie können eigene Strukturen definieren, die `byref` ähnliche Semantik einhalten können: Weitere Informationen finden Sie unter [ByRefs](byrefs.md) . Dies erfolgt mit dem- <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> Attribut:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` impliziert nicht `Struct` . Beides muss für den Typ vorhanden sein.

Eine " `byref` -like"-Struktur in F # ist ein Stapel gebundener Werttyp. Sie wird niemals dem verwalteten Heap zugeordnet. Eine `byref` ähnliche Struktur eignet sich für Hochleistungs Programmierung, da Sie mit einer Reihe von starken Überprüfungen zur Lebensdauer und nicht Erfassung erzwungen wird. Die Regeln lauten wie folgt:

- Sie können als Funktionsparameter, Methoden Parameter, lokale Variablen und Methoden Rückgaben verwendet werden.
- Sie können keine statischen Member oder Instanzmember einer Klasse oder einer normalen Struktur sein.
- Sie können nicht von einem Closure-Konstrukt ( `async` Methoden oder Lambda-Ausdrücke) aufgezeichnet werden.
- Sie können nicht als generischer Parameter verwendet werden.

Wenngleich diese Regeln die Nutzung stark einschränken, wird dies durchgeführt, um die Zusage von Hochleistungs Computing auf sichere Weise zu erfüllen.

## <a name="readonly-structs"></a>Schreibgeschützte Strukturen

Sie können Strukturen mit dem-Attribut versehen <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> . Beispiel:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly` impliziert nicht `Struct` . Sie müssen beides hinzufügen, um eine Struktur zu haben `IsReadOnly` .

Die Verwendung dieses Attributs gibt Metadaten aus, die F # und c# wissen, dass diese als `inref<'T>` `in ref` bzw. behandelt werden.

Die Definition eines änderbaren Werts in einer schreibgeschützten Struktur führt zu einem Fehler.

## <a name="struct-records-and-discriminated-unions"></a>Strukturdaten Sätze und Unterscheidungs-Unions

Sie können [Datensätze](records.md) und Unterscheidungs- [Unions](discriminated-unions.md) als Strukturen mit dem- `[<Struct>]` Attribut darstellen.  Weitere Informationen finden Sie in den einzelnen Artikeln.

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Klassen](classes.md)
- [Datensätze](records.md)
- [Mitglieder](./members/index.md)
