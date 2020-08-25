---
title: 'Explizite Felder: Das val-Schlüsselwort'
description: 'Erfahren Sie mehr über das F #-Schlüsselwort "Val", das verwendet wird, um einen Speicherort zum Speichern eines Werts in einer Klasse oder einem Strukturtyp zu deklarieren, ohne den Typ zu initialisieren.'
ms.date: 08/15/2020
ms.openlocfilehash: 9f5599a241f27b234eeacf48327b4ccbc46ed38c
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811781"
---
# <a name="explicit-fields-the-val-keyword"></a>Explizite Felder: Das val-Schlüsselwort

Das `val`-Schlüsselwort wird zum Deklarieren eines Speicherort zum Speichern eines Werts in einer Klasse oder einem Strukturtyp verwendet, ohne ihn zu initialisieren. Speicherorte, die auf diese Weise deklariert werden, werden als *Explizite Felder*bezeichnet. Das `val`-Schlüsselwort kann auch zusammen mit dem `member`-Schlüsselwort verwendet werden, um eine automatisch implementierte Eigenschaft zu deklarieren. Weitere Informationen zu automatisch implementierten Eigenschaften finden Sie unter [Eigenschaften](properties.md).

## <a name="syntax"></a>Syntax

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a>Hinweise

In der Regel werden Felder in einer Klasse oder einem Strukturtyp durch eine `let`-Bindung definiert. `let`-Bindungen müssen jedoch als Teil des Klassenkonstruktors initialisiert werden, was nicht immer möglich, notwendig oder gewünscht ist. Sie können das `val`-Schlüsselwort verwenden, wenn Sie ein nicht initialisiertes Feld implementieren möchten.

Explizite Felder können statisch oder nicht statisch sein. Der *Zugriffsmodifizierer* kann `public` , `private` oder sein `internal` . Standardmäßig sind explizite Felder öffentlich. Dies unterscheidet sich von `let`-Bindungen in Klassen, die immer privat sind.

Das [DefaultValue](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-defaultvalueattribute.html) -Attribut ist für explizite Felder in Klassentypen erforderlich, die über einen primären Konstruktor verfügen. Dieses Attribut gibt an, dass das Feld mit 0 (null) initialisiert wird. Der Typ des Felds muss die Initialisierung mit 0 (null) unterstützen. Ein Typ unterstützt die Initialisierung mit 0 (null), wenn er eine der folgenden Bedingungen erfüllt:

- Ein primitiver Typ, der einen Wert von 0 (null) hat.
- Ein Typ, der den Wert 0 (null) unterstützt, entweder als ein normaler Wert, als ein nicht normaler Wert oder als Darstellung eines Werts. Dazu gehören Klassen, Tupel, Datensätze, Funktionen, Schnittstellen, .NET-Verweistypen, der `unit`-Typ und diskriminierte Union-Typen.
- Ein .NET-Werttyp.
- Eine Struktur, deren Felder alle einen Standardwert von 0 (null) unterstützen.

Ein unveränderliches Feld mit der Bezeichnung `someField` verfügt zum Beispiel über ein zugrunde liegendes Feld in der kompilierten .NET-Darstellung, das `someField@` heißt, und Sie greifen auf den gespeicherten Wert mit einer Eigenschaft mit der Bezeichnung `someField` zu.

Bei einem veränderlichen Feld ist die kompilierte .NET-Darstellung ein .NET-Feld.

> [!WARNING]
> Der .NET Framework-Namespace `System.ComponentModel` enthält ein Attribut mit demselben Namen. Informationen zu diesem Attribut finden Sie unter <xref:System.ComponentModel.DefaultValueAttribute>.

Der folgende Code zeigt die Verwendung expliziter Felder und zum Vergleich eine `let`-Bindung in einer Klasse, die über einen primären Konstruktor verfügt. Beachten Sie, dass das `let`-gebundene Feld `myInt1` privat ist. Wenn das `let`-gebundene Feld `myInt1` von einer Membermethode referenziert wird, ist der Selbstbezeichner `this` nicht erforderlich. Wenn Sie jedoch die expliziten Felder `myInt2` und `myString` referenzieren, ist der Selbstbezeichner erforderlich.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

Die Ausgabe lautet wie folgt:

```console
11 12 abc
30 def
```

Der folgende Code zeigt die Verwendung von expliziten Feldern in einer Klasse, die nicht über einen primären Konstruktor verfügt. In diesem Fall ist das `DefaultValue`-Attribut nicht erforderlich, es müssen jedoch alle Felder in den Konstruktoren initialisiert werden, die für den Typ definiert sind.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

Die Ausgabe lautet `35 22`.

Der folgende Code zeigt die Verwendung von expliziten Feldern in einer Struktur. Da eine Struktur ein Werttyp ist, verfügt sie automatisch über einen Parameter losen Konstruktor, der die Werte der Felder auf 0 (null) festlegt. Daher ist das `DefaultValue`-Attribut nicht erforderlich.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

Die Ausgabe lautet `11 xyz`.

**Vorsicht**: Wenn Sie die Struktur mit `mutable` Feldern ohne `mutable` Schlüsselwort initialisieren, funktionieren Ihre Zuweisungen an einer Kopie der Struktur, die direkt nach der Zuweisung verworfen wird. Daher ändert sich Ihre Struktur nicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6704.fs)]

Explizite Felder sind nicht für die routinemäßige Verwendung gedacht. Im Allgemeinen sollten Sie möglichst eine `let`-Bindung in einer Klasse verwenden, statt eines expliziten Felds. Explizite Felder sind in bestimmten Interoperabilitätsszenarios hilfreich, wenn Sie z. B. eine Struktur definieren müssen, die in einem Plattformaufruf einer systemeigenen API oder in COM-Interop-Szenarien verwendet wird. Weitere Informationen finden Sie unter [externe Funktionen](../functions/external-functions.md). Eine andere Situation, in der ein explizites Feld möglicherweise erforderlich, besteht dann, wenn Sie mit einem F#-Codegenerator arbeiten, der Klassen ohne primären Konstruktor ausgibt. Explizite Felder sind auch für threadstatische Variablen oder ähnliche Konstrukte sinnvoll. Weitere Informationen finden Sie unter `System.ThreadStaticAttribute`.

Wenn die Schlüsselwörter `member val` zusammen in einer Typdefinition angezeigt werden, handelt es sich um eine Definition einer automatisch implementierten Eigenschaft. Weitere Informationen finden Sie unter [Eigenschaften](properties.md)definiert sind.

## <a name="see-also"></a>Siehe auch

- [Eigenschaften](properties.md)
- [Mitglieder](index.md)
- [`let` Bindungen in Klassen](let-bindings-in-classes.md)
