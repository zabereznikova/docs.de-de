---
title: Strukturen (F#)
description: Erfahren Sie mehr über die F#-Struktur, ein kompakter Objekttyp, der häufig effizienter als eine Klasse für Typen mit einer geringeren Menge an Daten und ein einfaches Verhalten.
ms.date: 05/16/2016
ms.openlocfilehash: 08af88132dda28883e246b94585ff4ed8bd2f16a
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46321061"
---
# <a name="structures"></a>Strukturen

Ein *Struktur* ist ein kompakter Objekttyp, die effizienter als eine Klasse für Typen sein können, die eine geringe Datenmenge und ein einfaches Verhalten aufweisen.

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

## <a name="remarks"></a>Hinweise

Strukturen sind *Werttypen*, Felder, d. h., der sie gespeichert sind, direkt auf dem Stapel oder, wenn sie als verwendet werden, oder geben Sie die Elemente des Arrays, Inline im übergeordneten Element. Im Gegensatz zu Klassen und Datensätzen verfügen Strukturen über eine Übergabewertsemantik. Dies bedeutet, dass sie hauptsächlich für kleine Datenaggregate sinnvoll sind, die häufig aufgerufen und kopiert werden.

In der vorherigen Syntax werden zwei Formen gezeigt. Die erste ist nicht die einfache Syntax, aber sie wird trotzdem häufig verwendet, da Sie bei Verwendung der Schlüsselwörter `struct` und `end` das `StructAttribute`-Attribut auslassen können, das in der zweiten Form angezeigt wird. Sie können `StructAttribute` zu `Struct` abkürzen.

Die *-Definition-Elemente-und-Typmember* in der vorherigen Syntax stellt Memberdeklarationen und-Definitionen. Strukturen können über Konstruktoren sowie änderbare und unveränderliche Felder verfügen, und sie können Member und Schnittstellenimplementierungen deklarieren. Weitere Informationen finden Sie unter [Mitglieder](members/index.md).

Strukturen können nicht an der Vererbung beteiligt sein, sie können keine `let`- oder `do`-Bindungen enthalten und können nicht rekursiv Felder des eigenen Typs enthalten (obwohl sie Verweiszellen enthalten können, die auf den eigenen Typ verweisen).

Da Strukturen keine `let`-Bindungen zulassen, müssen Sie Felder in Strukturen mit dem `val`-Schlüsselwort deklarieren. Das `val`-Schlüsselwort definiert ein Feld und den Typ, es lässt jedoch keine Initialisierung zu. In diesem Fall werden `val`-Deklarationen mit 0 oder null initialisiert. Aus diesem Grund erfordern Strukturen, die über einen impliziten Konstruktor verfügen (d. h. Parameter, die direkt nach dem Strukturnamen in der Deklaration angegeben werden), dass `val`-Deklarationen mit dem `DefaultValue`-Attribut gekennzeichnet werden. Strukturen, die über einen definierten Konstruktor verfügen, unterstützen weiterhin die Initialisierung mit 0 (null). Aus diesem Grund ist das `DefaultValue`-Attribut eine Deklaration, dass der Wert 0 (Null) für das Feld gültig ist. Implizite Konstruktoren für Strukturen führen keine Aktionen aus, da `let`- und `do`-Bindungen für den Typ nicht zulässig sind, aber die übergebenen impliziten Konstruktorparameterwerte sind als private Felder verfügbar.

Explizite Konstruktoren können eine Initialisierung von Feldwerten beinhalten. Wenn Sie eine Struktur mit einem expliziten Konstruktor haben, unterstützt sie weiterhin die Initialisierung mit 0 (Null); Sie verwenden jedoch nicht das `DefaultValue`-Attribut auf den `val`-Deklarationen, da es mit dem expliziten Konstruktor in Konflikt steht. Weitere Informationen zu `val` Deklarationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).

Attribute und Zugriffsmodifizierer sind für Strukturen zulässig und folgen denselben Regeln wie jene für andere Typen. Weitere Informationen finden Sie unter [Attribute](attributes.md) und [Zugriffssteuerung](access-control.md).

Die folgenden Codebeispiele veranschaulichen Strukturdefinitionen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>ByRefLike Strukturen

Sie können definieren, dass Sie eigene Strukturen, die folgen können `byref`-Semantik wie: finden Sie unter [Byrefs](byrefs.md) für Weitere Informationen. Dies erfolgt mit der <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> Attribut:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` impliziert nicht `Struct`. Beide müssen für den Typ vorhanden sein.

Ein "`byref`-wie" "Struct" in f# ist ein Stack gebundene Wert. Sie wird nie auf dem verwalteten Heap zugewiesen. Ein `byref`-Struktur für Hochleistungs-Programmierung nützlich ist, wie sie mit leistungsfähiger Prüfungen zur Lebensdauer und nicht-Capture erzwungen wird. Die Regeln sind:

* Sie können verwendet werden Methodenrückgabe als Funktionsparameter, Methodenparameter, lokale Variablen.
* Sie können nicht statisch sein oder Instanzmember einer Klasse oder einer normalen Struktur.
* Sie können nicht anhand des Konstrukte Closure erfasst werden (`async` Methoden oder Lambdaausdrücke).
* Sie können nicht als generischer Parameter verwendet werden.

Obwohl diese Regeln sehr stark Nutzung einzuschränken, werden diese zur Erfüllung der Zusage von High Performance computing, auf sichere Weise.

## <a name="readonly-structs"></a>Schreibgeschützte Strukturen

Sie können mit einer Anmerkung versehen Strukturen mit dem <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> Attribut. Zum Beispiel:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly` impliziert nicht `Struct`. Sie müssen beide haben Hinzufügen einer `IsReadOnly` Struktur.

Verwendung dieses Attributs gibt Metadaten können von f# und c# kennen, die sie behandeln, als `inref<'T>` und `in ref`bzw.

Definieren eines änderbaren Werts innerhalb einer Struktur Readonly erzeugt einen Fehler.

## <a name="struct-records-and-discriminated-unions"></a>Struktur-Datensätze und Unterscheidungs-Unions

Sie können darstellen [Datensätze](records.md) und [Unterscheidungs-Unions](discriminated-unions.md) als Strukturen mit dem `[<Struct>]` Attribut.  Finden Sie alle Artikel, um mehr zu erfahren.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Klassen](classes.md)
- [Datensätze](records.md)
- [Mitglieder](members/index.md)
