---
title: Strukturen (F#)
description: Erfahren Sie mehr über die f#-Struktur, ein kompakter Objekttyp, der häufig effizienter als eine Klasse für Typen mit einer kleinen Menge an Daten und einfaches Verhalten.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 14a4799b13c40e363dd400f7effd53264acc5614
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="structures"></a>Strukturen

Ein *Struktur* ist ein kompakter Objekttyp, die effizienter als eine Klasse für Typen sein kann, die eine kleine Menge von Daten und ein einfaches Verhalten aufweisen.

## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a>Hinweise
Strukturen sind *Werttypen*, dies bedeutet, dass diese gespeichert sind, direkt auf dem Stapel oder, wenn sie als verwendet werden, dass Felder oder Array-Elemente Inline in der übergeordneten Tabelle geben. Im Gegensatz zu Klassen und Datensätzen verfügen Strukturen über eine Übergabewertsemantik. Dies bedeutet, dass sie hauptsächlich für kleine Datenaggregate sinnvoll sind, die häufig aufgerufen und kopiert werden.

In der vorherigen Syntax werden zwei Formen gezeigt. Die erste ist nicht die einfache Syntax, aber sie wird trotzdem häufig verwendet, da Sie bei Verwendung der Schlüsselwörter `struct` und `end` das `StructAttribute`-Attribut auslassen können, das in der zweiten Form angezeigt wird. Sie können `StructAttribute` zu `Struct` abkürzen.

Die *-Definitions-Elemente* in der vorherigen Syntax stellt Memberdeklarationen und-Definitionen. Strukturen können über Konstruktoren sowie änderbare und unveränderliche Felder verfügen, und sie können Member und Schnittstellenimplementierungen deklarieren. Weitere Informationen finden Sie unter [Elemente](members/index.md).

Strukturen können nicht an der Vererbung beteiligt sein, sie können keine `let`- oder `do`-Bindungen enthalten und können nicht rekursiv Felder des eigenen Typs enthalten (obwohl sie Verweiszellen enthalten können, die auf den eigenen Typ verweisen).

Da Strukturen keine `let`-Bindungen zulassen, müssen Sie Felder in Strukturen mit dem `val`-Schlüsselwort deklarieren. Das `val`-Schlüsselwort definiert ein Feld und den Typ, es lässt jedoch keine Initialisierung zu. In diesem Fall werden `val`-Deklarationen mit 0 oder null initialisiert. Aus diesem Grund erfordern Strukturen, die über einen impliziten Konstruktor verfügen (d. h. Parameter, die direkt nach dem Strukturnamen in der Deklaration angegeben werden), dass `val`-Deklarationen mit dem `DefaultValue`-Attribut gekennzeichnet werden. Strukturen, die über einen definierten Konstruktor verfügen, unterstützen weiterhin die Initialisierung mit 0 (null). Aus diesem Grund ist das `DefaultValue`-Attribut eine Deklaration, dass der Wert 0 (Null) für das Feld gültig ist. Implizite Konstruktoren für Strukturen führen keine Aktionen aus, da `let`- und `do`-Bindungen für den Typ nicht zulässig sind, aber die übergebenen impliziten Konstruktorparameterwerte sind als private Felder verfügbar.

Explizite Konstruktoren können eine Initialisierung von Feldwerten beinhalten. Wenn Sie eine Struktur mit einem expliziten Konstruktor haben, unterstützt sie weiterhin die Initialisierung mit 0 (Null); Sie verwenden jedoch nicht das `DefaultValue`-Attribut auf den `val`-Deklarationen, da es mit dem expliziten Konstruktor in Konflikt steht. Weitere Informationen zu `val` Deklarationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).

Attribute und Zugriffsmodifizierer sind für Strukturen zulässig und folgen denselben Regeln wie jene für andere Typen. Weitere Informationen finden Sie unter [Attribute](attributes.md) und [Access Control](access-control.md).

Die folgenden Codebeispiele veranschaulichen Strukturdefinitionen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a>Struct-Datensätze und Unterscheidungs-Unions

Ab f# 4.1, Sie können darstellen [Datensätze](records.md) und [Unterscheidungs-Unions](discriminated-unions.md) als Strukturen mit dem `[<Struct>]` Attribut.  Finden Sie unter jeder Artikel, um mehr zu erfahren.
    
## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Klassen](classes.md)

[Datensätze](records.md)

[Mitglieder](members/index.md)
