---
title: Strukturen
description: Erfahren Sie mehr über die F-Struktur, einen kompakten Objekttyp, der häufig effizienter ist als eine Klasse für Typen mit einer kleinen Datenmenge und einfachem Verhalten.
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401124"
---
# <a name="structures"></a>Strukturen

Eine *Struktur* ist ein kompakter Objekttyp, der effizienter sein kann als eine Klasse für Typen mit einer geringen Datenmenge und einem einfachen Verhalten.

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

Strukturen sind *Werttypen*, d. h., sie werden direkt im Stapel oder, wenn sie als Felder oder Arrayelemente verwendet werden, im übergeordneten Typ inline gespeichert. Im Gegensatz zu Klassen und Datensätzen verfügen Strukturen über eine Übergabewertsemantik. Dies bedeutet, dass sie hauptsächlich für kleine Datenaggregate sinnvoll sind, die häufig aufgerufen und kopiert werden.

In der vorherigen Syntax werden zwei Formen gezeigt. Die erste ist nicht die einfache Syntax, aber sie wird trotzdem häufig verwendet, da Sie bei Verwendung der Schlüsselwörter `struct` und `end` das `StructAttribute`-Attribut auslassen können, das in der zweiten Form angezeigt wird. Sie können `StructAttribute` zu `Struct` abkürzen.

Die *typ-definition-elements-and-members* in der vorherigen Syntax stellen Memberdeklarationen und -definitionen dar. Strukturen können über Konstruktoren sowie änderbare und unveränderliche Felder verfügen, und sie können Member und Schnittstellenimplementierungen deklarieren. Weitere Informationen finden Sie unter [Mitglieder](./members/index.md).

Strukturen können nicht an der Vererbung beteiligt sein, sie können keine `let`- oder `do`-Bindungen enthalten und können nicht rekursiv Felder des eigenen Typs enthalten (obwohl sie Verweiszellen enthalten können, die auf den eigenen Typ verweisen).

Da Strukturen keine `let`-Bindungen zulassen, müssen Sie Felder in Strukturen mit dem `val`-Schlüsselwort deklarieren. Das `val`-Schlüsselwort definiert ein Feld und den Typ, es lässt jedoch keine Initialisierung zu. In diesem Fall werden `val`-Deklarationen mit 0 oder null initialisiert. Aus diesem Grund erfordern Strukturen, die über einen impliziten Konstruktor verfügen (d. h. Parameter, die direkt nach dem Strukturnamen in der Deklaration angegeben werden), dass `val`-Deklarationen mit dem `DefaultValue`-Attribut gekennzeichnet werden. Strukturen, die über einen definierten Konstruktor verfügen, unterstützen weiterhin die Initialisierung mit 0 (null). Aus diesem Grund ist das `DefaultValue`-Attribut eine Deklaration, dass der Wert 0 (Null) für das Feld gültig ist. Implizite Konstruktoren für Strukturen führen keine Aktionen aus, da `let`- und `do`-Bindungen für den Typ nicht zulässig sind, aber die übergebenen impliziten Konstruktorparameterwerte sind als private Felder verfügbar.

Explizite Konstruktoren können eine Initialisierung von Feldwerten beinhalten. Wenn Sie eine Struktur mit einem expliziten Konstruktor haben, unterstützt sie weiterhin die Initialisierung mit 0 (Null); Sie verwenden jedoch nicht das `DefaultValue`-Attribut auf den `val`-Deklarationen, da es mit dem expliziten Konstruktor in Konflikt steht. Weitere Informationen `val` zu Deklarationen finden Sie unter [Explizite Felder: `val` Das Schlüsselwort](./members/explicit-fields-the-val-keyword.md).

Attribute und Zugriffsmodifizierer sind für Strukturen zulässig und folgen denselben Regeln wie jene für andere Typen. Weitere Informationen finden Sie unter [Attribute](attributes.md) und [Zugriffssteuerung](access-control.md).

Die folgenden Codebeispiele veranschaulichen Strukturdefinitionen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>ByRefLike-Strukturen

Sie können ihre eigenen Strukturen definieren, die sich an `byref`-like semantics halten können: siehe [Byrefs](byrefs.md) für weitere Informationen. Dies geschieht <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> mit dem Attribut:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`bedeutet `Struct`nicht . Beide müssen auf dem Typ vorhanden sein.

Eine`byref`" -like"-Struktur in F ist ein stapelgebundener Werttyp. Sie wird nie auf dem verwalteten Heap zugewiesen. Eine `byref`-like struct ist nützlich für die Hochleistungsprogrammierung, da sie mit einer Reihe starker Überprüfungen der Lebensdauer und Nicht-Capture erzwungen wird. Die Regeln sind:

- Sie können als Funktionsparameter, Methodenparameter, lokale Variablen, Methodenrückgaben verwendet werden.
- Sie können keine statischen oder Instanzmember einer Klasse oder normalen Struktur sein.
- Sie können nicht von einem`async` Abschlusskonstrukt erfasst werden (Methoden oder Lambda-Ausdrücke).
- Sie können nicht als generischer Parameter verwendet werden.

Obwohl diese Regeln die Nutzung stark einschränken, tun sie dies, um das Versprechen von Hochleistungs-Computing auf sichere Weise zu erfüllen.

## <a name="readonly-structs"></a>ReadOnly-Strukturen

Sie können Strukturen mit dem <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> Attribut kommentieren. Beispiel:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly`bedeutet `Struct`nicht . Sie müssen beide hinzufügen, um eine `IsReadOnly` Struktur zu haben.

Die Verwendung dieses Attributs gibt Metadaten aus, sodass `inref<'T>` F- und C-Zeichen wissen, dass sie als bzw. `in ref`behandelt werden.

Das Definieren eines veränderlichen Werts innerhalb einer schreibgeschützten Struktur führt zu einem Fehler.

## <a name="struct-records-and-discriminated-unions"></a>Struct Records und diskriminierte Gewerkschaften

Sie können [Datensätze](records.md) und [diskriminierte Unions](discriminated-unions.md) `[<Struct>]` als Strukturen mit dem Attribut darstellen.  Weitere Informationen finden Sie in jedem Artikel.

## <a name="see-also"></a>Weitere Informationen

- [Sprachreferenz](index.md)
- [Klassen](classes.md)
- [Datensätze](records.md)
- [Mitglieder](./members/index.md)
