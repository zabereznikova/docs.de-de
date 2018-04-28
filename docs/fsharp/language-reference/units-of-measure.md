---
title: Maßeinheiten (F#)
description: Erfahren Sie, wie für Gleitkommawerte und Ganzzahl mit Vorzeichen Werte in f# können Einheiten, die in der Regel verwendet werden, um anzugeben, Länge, Volume und Massenspeichertreiber zugeordnet sein.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 336a1e04426fb39f5ceb98e06a06cd7eadc36e85
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="units-of-measure"></a>Maßeinheiten

Gleitkomma- und Werte für ganze Zahl mit Vorzeichen in f# kann Maßeinheiten, verknüpft haben die in der Regel, Länge, Volumen, um anzugeben, Masse usw. verwendet werden. Mengen mit Einheiten verwenden, aktivieren Sie den Compiler an, überprüfen Sie, ob arithmetische Beziehungen die richtige Einheiten, die verhindert Programmierfehler.


## <a name="syntax"></a>Syntax

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Hinweise
Die vorherige Syntax definiert *Einheitenname* als eine Einheit. Das optionale Teil wird verwendet, um ein neues Measure im Hinblick auf die zuvor definierte Einheiten zu definieren. Die folgende Zeile definiert z. B. das Measure `cm` (Zentimeter).

```fsharp
[<Measure>] type cm
```

Die folgende Zeile wird das Measure definiert `ml` (Milliliter) als eine kubische Zentimeter (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

In der vorherigen Syntax *Measure* ist eine Formel, die Einheiten. In Formeln, die Einheiten einschließen, ganzzahlige Potenzen werden unterstützt (positive und negative), Leerzeichen zwischen Einheiten geben ein Produkt der beiden Einheiten `*` gibt ebenfalls ein Produkt von Einheiten, und `/` gibt einen Quotienten von Einheiten. Für eine reziproke Unit, können Sie entweder eine negative ganze Zahl Potenz verwenden oder eine `/` , die eine Trennung zwischen der Zähler und Nenner eine Einheitenformel angibt. Mehrere Einheiten im Nenner müssen in Klammern eingeschlossen werden. Einheiten getrennt durch Leerzeichen nach einer `/` werden als Teil der Nenner jedoch Einheiten nach interpretiert eine `*` als Teil der Zähler interpretiert werden.

Sie können 1 Einheitenausdrücke, entweder allein, um eine reine Menge anzugeben oder zusammen mit anderen Einheiten, z. B. in der Zähler verwenden. Beispielsweise würde die Einheiten für einen Satz geschrieben werden, als `1/s`, wobei `s` Sekunden angibt. In Einheitenformeln sind keine Klammern verwendet. Sie angeben keinen numerische Konvertierungskonstanten in der Einheitenformeln; Sie können jedoch Konvertierungskonstanten separat mit Einheiten definieren und in der Einheit geprüfte Berechnungen verwenden.

Unit-Formeln, die der gleichen Bedeutung können auf verschiedene Weise geschrieben werden. Daher konvertiert der Compiler Einheitenformeln in ein konsistentes Format, der negative Zehnerpotenzen Umkehrwerte, Gruppen Einheiten in einen einzelnen Zähler und Nenner konvertiert, und sortiert die Einheiten in der Zähler und Nenner alphabetisch.

Z. B. die Einheitenformeln `kg m s^-2` und `m /s s * kg` werden in konvertiert `kg m/s^2`.

Sie können die Maßeinheiten in floating Point-Ausdrücke verwenden. Mit Gleitkommazahlen zusammen mit zugehörigen Einheiten Measure Fügt eine weitere Ebene von typsicherheit und hilft vermeiden, die Einheit Konflikt auftretende Fehler in Formeln können bei der Verwendung von schwach typisierten Gleitkommazahlen. Wenn Sie einen Gleitkommawert schreiben Point-Ausdruck, der Einheiten verwendet, die Einheiten im Ausdruck übereinstimmen.

Sie können Literale mit einer Einheitenformel in spitzen Klammern, mit Anmerkungen versehen, wie in den folgenden Beispielen gezeigt.

```fsharp
1.0<cm>
55.0<miles/hour>
```

Sie nehmen kein Leerzeichen zwischen der Anzahl und der spitzen Klammer einfügen; Sie dürfen jedoch enthalten ein literales Suffix z. B. `f`, wie im folgenden Beispiel.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Eine solche Anmerkung ändert den Typ des Literals von einem primitiven Typ (z. B. `float`) in einen dimensionierten Typ, z. B. `float<cm>` oder in diesem Fall `float<miles/hour>`. Eine Einheit Anmerkung `<1>` gibt an, dass eine reine Menge und Typ der primitive Typ ohne Parameter Einheit entspricht.

Der Typ des eine Maßeinheit eines Gleitkommatyps ist oder zusammen mit einer zusätzlichen Einheit-Anmerkung, die in Klammern angegebenen ganzzahligen Typ mit Vorzeichen. Daher wird beim Schreiben des Typs einer Konvertierung von `g` (g), `kg` (Kilogramm), beschreiben Sie die Typen, die wie folgt.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Maßeinheiten werden zum Zeitpunkt der Kompilierung Einheit überprüft jedoch nicht in der Laufzeitumgebung beibehalten werden. Aus diesem Grund sie die Leistung nicht beeinträchtigt.

Maßeinheiten können auf einen beliebigen Typ, der nicht nur die Gleitkommatypen angewendet werden. Allerdings signiert nur Gleitkommatypen, ganzzahlige Typen und Dezimaltypen Unterstützung dimensioniert Mengen. Aus diesem Grund ist es nur sinnvoll, verwenden Maßeinheiten für primitiven Typen und Aggregate, die diese primitiven Typen enthalten.

Das folgende Beispiel veranschaulicht die Verwendung von Maßeinheiten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
Im folgenden Codebeispiel wird veranschaulicht, wie eine reine Gleitkommazahl in eine dimensionierten Gleitkommawert konvertiert wird. Sie multiplizieren Sie einfach mit 1.0, die Dimensionen der 1.0 anwenden. Sie können dies in einer Funktion wie abstrakte `degreesFahrenheit`.

Auch wenn Sie dimensionierte Werte an Funktionen, die reine Gleitkommazahlen erwarten übergeben, müssen Sie die Einheiten oder umgewandelt `float` mithilfe der `float` Operator. In diesem Beispiel Teilen Sie Sie durch `1.0<degC>` für die Argumente für `printf` da `printf` reine Mengen erwartet.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

Das folgende Beispiel-Sitzung wird gezeigt, die über Eingaben und Ausgaben für diesen Code.

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Verwenden von generischen Einheiten
Sie können generische Funktionen, die ausgeführt werden für Daten schreiben, die über eine zugeordnete Maßeinheit verfügt. Sie dazu durch Angabe eines Typs zusammen mit einer generischen Einheit als ein Type-Parameter, wie im folgenden Codebeispiel gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a>Erstellen von Aggregattypen mit generischen Einheiten
Der folgende Code zeigt, wie einen aggregierten Typ erstellt, aus der einzelne Gleitkommawerte besteht, die Zeiteinheiten darstellen, die generisch sind. Dadurch wird einen einzelnen Typ erstellt werden, der mit einer Vielzahl von Einheiten funktioniert. Darüber hinaus beibehalten generische Einheiten typsicherheit, indem Sie sicherstellen, dass ein generischer Typ, der eine Gruppe von Einheiten hat einen anderen Typ als den gleichen generischen Typ mit einem anderen Satz von Einheiten ist. Die Grundlage für diese Technik ist, die die `Measure` Attribut kann an den Typparameter angewendet werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a>Einheiten zur Laufzeit
Maßeinheiten werden für die Überprüfung des statischen Typs verwendet. Wenn Gleitkommawerte kompiliert werden, sind die Maßeinheiten entfernt, sodass die Einheiten, die zur Laufzeit nicht mehr vorhanden sind. Jeder Versuch, die Funktionalität zu implementieren, die davon abhängen, überprüfen die Einheiten zur Laufzeit ist daher nicht möglich. Implementieren Sie z. B. eine `ToString` Funktion zum Ausgeben der Einheiten ist nicht möglich.


## <a name="conversions"></a>Konvertierungen
Beim Konvertieren eines Typs, die Einheiten (z. B. `float<'u>`) in einen Typ, der nicht Einheiten verfügt, können Sie die standardkonvertierung-Funktion verwenden. Beispielsweise können Sie `float` konvertieren in eine `float` -Wert, der nicht Einheiten verfügt, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Um einen Wert ohne Einheiten auf einen Wert zu konvertieren, die Einheiten besitzt, können Sie multiplizieren mit Wert 1 oder 1.0, der kommentiert wird mit den entsprechenden Einheiten. Zum Schreiben von Ebenen der Interoperabilität, gibt es jedoch auch einige explizite-Funktionen, die Sie verwenden können, ohne Einheiten Werte in Werte mit Einheiten zu konvertieren. Diese befinden sich die [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) Modul. Beispielsweise, um ohne Einheiten in `float` auf eine `float<cm>`, verwenden Sie [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a>Maßeinheiten im f# Power Pack
Ist eine Einheitenbibliothek in F#-PowerPack verfügbar. Die Einheitenbibliothek enthält SI-Einheiten und physikalische Konstanten.


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)
