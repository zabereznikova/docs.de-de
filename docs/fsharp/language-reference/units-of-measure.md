---
title: Maßeinheiten (F#)
description: Erfahren Sie, wie für Gleitkommawerte und signierten Integer-Werte in f# können Einheiten, die in der Regel verwendet werden, Länge, Volumen und die Masse an verknüpft haben.
ms.date: 05/16/2016
ms.openlocfilehash: ad2193e25f3c0cee6e73cd529ab43d1e4b6b549b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45616152"
---
# <a name="units-of-measure"></a>Maßeinheiten

Gleitkomma- und signierten Integer-Werte in f# kann Maßeinheiten zugeordnet haben die in der Regel an Länge, Volumen, Masse usw. verwendet werden. Mengen mit Einheiten verwenden, aktivieren Sie den Compiler an, überprüfen Sie, ob arithmetische Beziehungen die richtigen Einheiten, die verhindert, dass Programmierfehler.

## <a name="syntax"></a>Syntax

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Hinweise

Die vorherige Syntax definiert *Einheitenname* als eine Einheit. Das optionale Teil wird verwendet, um ein neues Measure in Bezug auf die zuvor definierte Einheiten zu definieren. Die folgende Zeile definiert z. B. das Measure `cm` (Zentimeter).

```fsharp
[<Measure>] type cm
```

Die folgende Zeile definiert das Measure `ml` (Milliliter) als ein kubische Zentimeter (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

In der vorherigen Syntax *Measure* ist eine Formel, die Einheiten umfasst. Klicken Sie in Formeln, die Einheiten umfassen, ganzzahlige Potenzen werden unterstützt (positive und negative), Leerzeichen zwischen Einheiten geben ein Produkt der beiden Einheiten an, `*` gibt auch an einem Produkt Einheiten und `/` einen Quotienten von Einheiten angibt. Für eine gegenseitige Einheit, können Sie entweder eine negative ganze Zahl Potenz verwenden oder ein `/` , die eine Trennung zwischen der Zähler und Nenner eine Einheitenformel angibt. Mehrere Einheiten im Nenner müssen in Klammern eingeschlossen werden. Einheiten durch Leerzeichen getrennt nach einer `/` interpretiert werden, als Teil der Nenner jedoch Einheiten nach einer `*` als Teil der Zähler interpretiert werden.

Sie können 1 Einheitenausdrücke, entweder allein an eine dimensionslose Größe oder zusammen mit anderen Einheiten, z. B. in der Zähler verwenden. Beispielsweise würde die Einheit für die Geschwindigkeit geschrieben werden, als `1/s`, wobei `s` Sekunden angibt. In Komponententests Formeln werden keine Klammern verwendet. Sie angeben nicht numerische Konvertierungskonstanten in den Formeln für Komponententest; Allerdings können Sie Konvertierungskonstanten separat mit Einheiten definieren und deren Verwendung in Berechnungen Einheit überprüft.

Unit-Formeln, die das gleiche gemeint, können auf verschiedene Weise geschrieben werden. Aus diesem Grund konvertiert der Compiler Einheitenformeln in ein konsistentes Format, der negative Zehnerpotenzen Umkehrwerte, die Gruppen-Einheiten in einer einzelnen Zähler und Nenner konvertiert werden soll, und sortiert sie alphabetisch die Einheiten, in der Zähler und Nenner.

Z. B. die Einheitenformeln `kg m s^-2` und `m /s s * kg` werden in konvertiert `kg m/s^2`.

Sie verwenden die Maßeinheiten in Gleitkommaausdrücken. Gleitkommazahlen zusammen mit zugehörigen Einheiten des Measures mit einer weiteren Ebene der typsicherheit hinzugefügt, und trägt so zur fehlervermeidung die Einheit Konflikt-Fehler, die bei der Verwendung von schwach typisierten Gleitkommazahlen in Formeln auftreten können. Wenn Sie einen Gleitkommawert schreiben Point-Ausdruck, der Einheiten, die Einheiten, in dem Ausdruck übereinstimmen.

Sie können Literale mit einer Einheitenformel in spitzen Klammern versehen, wie in den folgenden Beispielen gezeigt.

```fsharp
1.0<cm>
55.0<miles/hour>
```

Sie sind nicht auf ein Leerzeichen zwischen der Anzahl und die Spitze Klammer abzulegen. Sie können jedoch einschließen, ein literales Suffix wie z. B. `f`, wie im folgenden Beispiel.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Eine solche Anmerkung ändert den Typ des Literals aus einem primitiven Typ (z. B. `float`) in einem dimensionierten Typ, z. B. `float<cm>` oder, in diesem Fall `float<miles/hour>`. Eine Einheit Anmerkung `<1>` gibt an, dass eine dimensionslose Größe und Typ der primitive Typ ohne Parameter Einheit entspricht.

Der Typ des eine Maßeinheit ist ein Gleitkomma oder ganzzahligen Typ mit Vorzeichen zusammen mit der eine zusätzliche Einheit-Anmerkung, die in Klammern angegeben. Daher beim Schreiben des Typs einer Konvertierung von `g` (g), `kg` (kg), geben Sie die Typen, die wie folgt.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Maßeinheiten dienen zur Kompilierzeit Einheit überprüft jedoch nicht in der Runtime-Umgebung beibehalten werden. Aus diesem Grund sie die Leistung nicht beeinträchtigt.

Maßeinheiten können auf einen beliebigen Typ, nicht nur die Gleitkommatypen angewendet werden. allerdings nur Gleitkommatypen, ganzzahlige Typen und Mengen von Dezimaltypen dimensioniert Unterstützung angemeldet. Aus diesem Grund ist es nur sinnvoll, Maßeinheiten zu verwenden, auf den primitiven Typen und Aggregate, die die primitive Typen enthalten.

Das folgende Beispiel veranschaulicht die Verwendung von Maßeinheiten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

Im folgenden Codebeispiel wird veranschaulicht, wie eine dimensionslose Gleitkommazahl in eine dimensionierten Gleitkommawert konvertiert wird. Sie multiplizieren Sie einfach mit 1,0, der Dimensionen auf der 1.0 angewendet. Sie können dies in einer Funktion wie abstrahieren `degreesFahrenheit`.

Auch wenn Sie dimensionierte Werte an Funktionen, die dimensionslose Gleitkommazahlen erwarten übergeben, müssen Sie die Einheiten oder umgewandelt `float` mithilfe der `float` Operator. In diesem Beispiel Teilen Sie Sie durch `1.0<degC>` für die Argumente `printf` da `printf` dimensionslose Größen erwartet.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

Die folgende beispielsitzung wird gezeigt, die von Eingaben und Ausgaben für diesen Code.

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Verwenden von generischen Einheiten

Sie können generische Funktionen, die ausgeführt werden Daten schreiben, die über eine zugeordnete Maßeinheit verfügt. Sie dazu einen Typ zusammen mit einer generischen Einheit angeben, wie ein Typparameter, wie im folgenden Codebeispiel gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>Erstellen von Aggregattypen mit generischen Einheiten

Der folgende Code zeigt, wie Sie einen aggregierten Typ erstellen, der von einzelnen Gleitkommawerte Einheiten besteht, die generisch sind. Dadurch wird einen einzelnen Typ erstellt werden, der mit einer Vielzahl von Einheiten funktioniert. Darüber hinaus beibehalten generische Einheiten typsicherheit, indem Sie sicherstellen, dass ein generischer Typ, der einen Satz von Einheiten hat einen anderen Typ als den gleichen generischen Typ mit einem anderen Satz von Einheiten ist. Diese Technik basiert auf, die die `Measure` Attribut kann auf den Typparameter angewendet werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>Einheiten zur Laufzeit

Maßeinheiten werden für die Überprüfung des statischen Typs verwendet. Wenn Gleitkommawerte kompiliert werden, werden die Einheiten entfernt, damit die Einheiten, die zur Laufzeit nicht mehr vorhanden sind. Jeder Versuch, die Funktionalität zu implementieren, der Überprüfung der Einheiten zur Laufzeit abhängig ist daher nicht möglich. Beispielsweise implementiert ein `ToString` Funktion zum Ausgeben der Einheiten ist nicht möglich.

## <a name="conversions"></a>Konvertierungen

Zum Konvertieren eines Typs, die Einheiten (z. B. `float<'u>`) auf einen Typ, der nicht Einheiten verfügt, können Sie die standardkonvertierung-Funktion. Beispielsweise können Sie `float` zum Konvertieren einer `float` Wert, der nicht-Einheiten, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Um einen Wert ohne Einheiten auf einen Wert zu konvertieren, die Einheiten hat, können Sie multiplizieren mit Wert 1 oder 1,0, der mit Anmerkungen versehen wird mit den entsprechenden Einheiten. Für das Schreiben von Ebenen der Interoperabilität, gibt es jedoch auch einige explizite-Funktionen, die Sie verwenden können, ohne Einheiten Werte in Werte mit Einheiten zu konvertieren. Diese sind in der [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) Modul. Beispielsweise, um ohne Einheiten in `float` auf eine `float<cm>`, verwenden Sie [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>Maßeinheiten in der F#-Kernbibliothek

Eine Einheitenbibliothek finden Sie in der `FSharp.Data.UnitSystems.SI` Namespace. Er enthält sowohl die Symbol-Form SI-Einheiten (wie `m` für Verbrauchseinheit) in der `UnitSymbols` Sub-Namespace und der vollständige Name (wie `meter` für Verbrauchseinheit) in der `UnitNames` Sub-Namespace.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
