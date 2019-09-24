---
title: Maßeinheiten
description: Erfahren Sie, wie für Gleitkommawerte und signierten Integer-Werte in F# können Einheiten, die in der Regel verwendet werden, Länge, Volumen und die Masse an verknüpft haben.
ms.date: 05/16/2016
ms.openlocfilehash: a81f7760301dc580e333d4659a72e6259d2c916b
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216690"
---
# <a name="units-of-measure"></a>Maßeinheiten

Gleitkomma- und signierten Integer-Werte in F# kann Maßeinheiten zugeordnet haben die in der Regel an Länge, Volumen, Masse usw. verwendet werden. Durch die Verwendung von Mengen mit Einheiten ermöglichen Sie es dem Compiler, zu überprüfen, ob arithmetische Beziehungen über die richtigen Einheiten verfügen, sodass Programmierfehler vermieden werden.

## <a name="syntax"></a>Syntax

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Hinweise

Die vorherige Syntax definiert *Unit-Name* als Maßeinheit. Der optionale Teil wird verwendet, um ein neues Measure in Bezug auf zuvor definierte Einheiten zu definieren. Die folgende Zeile definiert z. b. das `cm` Measure (Zentimeter).

```fsharp
[<Measure>] type cm
```

Die folgende Zeile definiert das Measure `ml` (Milliliter) als kubischen Zentimeter (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

In der vorherigen Syntax ist *Measure* eine Formel, die Einheiten umfasst. In Formeln, die Einheiten einschließen, werden ganzzahlige Kräfte unterstützt (positiv und negativ), Leerzeichen zwischen Einheiten geben ein Produkt `*` der beiden Einheiten an, geben auch ein `/` Produkt von Einheiten an und geben einen Quotienten von Einheiten an. Für eine wechselseitige Einheit können Sie entweder eine negative ganzzahlige Potenz oder `/` eine verwenden, die eine Trennung zwischen dem Zähler und dem Nenner einer Einheitsformel angibt. Mehrere Einheiten im Nenner müssen in Klammern eingeschlossen werden. Einheiten, die nach `/` einem durch Leerzeichen getrennt sind, werden als Teil des Nenners interpretiert, aber alle nach einem `*` folgenden Einheiten werden als Teil des zähators interpretiert.

Sie können 1 in Einheiten Ausdrücken verwenden, und zwar entweder allein zum Angeben einer dimensionierten Menge oder in Verbindung mit anderen Einheiten, wie z. b. im Zähler. Beispielsweise werden die Einheiten für eine Rate als `1/s`geschrieben, wobei `s` die Sekunden angibt. In Einheits Formeln werden keine Klammern verwendet. Sie geben keine numerischen Konvertierungs Konstanten in den Einheits Formeln an; Allerdings können Sie Konvertierungs Konstanten mit Einheiten separat definieren und in Berechnungen mit Einheiten Prüfung verwenden.

Einheits Formeln, die das gleiche bedeuten, können auf verschiedene Weise geschrieben werden. Daher konvertiert der Compiler Einheits Formeln in ein konsistentes Formular, das negative Kräfte in Rückstände konvertiert, Einheiten in einen einzelnen Zähler und einen Nenner gruppiert und die Einheiten im Zähler und Nenner alphabetisch sortiert.

Beispielsweise werden die Einheiten Formeln `kg m s^-2` und `m /s s * kg` in `kg m/s^2`konvertiert.

In Gleit Komma Ausdrücken verwenden Sie Maßeinheiten. Die Verwendung von Gleit Komma Zahlen zusammen mit zugeordneten Maßeinheiten fügt eine weitere Ebene der Typsicherheit hinzu und hilft dabei, die Fehler bei der Einheiten Übereinstimmung zu vermeiden, die bei der Verwendung von schwach typisierten Gleit Komma Zahlen in Formeln auftreten können. Wenn Sie einen Gleit Komma Ausdruck schreiben, der Einheiten verwendet, müssen die Einheiten im Ausdruck Stimmen.

Literale können mit einer Einheitsformel in spitzen Klammern kommentiert werden, wie in den folgenden Beispielen gezeigt.

```fsharp
1.0<cm>
55.0<miles/hour>
```

Zwischen der Zahl und der Spitze Klammer wird kein Leerzeichen eingefügt. Sie können jedoch ein literales Suffix wie `f`im folgenden Beispiel einschließen.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Eine solche Anmerkung ändert den Typ des Literals vom primitiven Typ (z `float`. b `float<miles/hour>`.) in einen dimensionierten Typ, `float<cm>` wie z. b. oder, in diesem Fall. Eine Einheits Anmerkung von `<1>` gibt eine dimensionlose Menge an, und ihr Typ entspricht dem primitiven Typ ohne einen Unit-Parameter.

Der Typ einer Maßeinheit ist ein Gleit Komma Wert oder ein ganzzahliger ganzzahliger Typ mit einer zusätzlichen Einheiten Anmerkung, der in eckigen Klammern angegeben ist. Wenn Sie also den Typ einer Konvertierung von `g` (grams) in `kg` (Kilogramm) schreiben, beschreiben Sie die Typen wie folgt.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Maßeinheiten werden für die Kompilierzeit-Einheiten Überprüfung verwendet, aber nicht in der Laufzeitumgebung beibehalten. Daher wirken Sie sich nicht auf die Leistung aus.

Maßeinheiten können auf jeden beliebigen Typ angewendet werden, nicht nur auf Gleit Komma Typen. Allerdings unterstützen nur Gleit Komma Typen, ganzzahlige ganzzahlige Typen und dezimale Typen dimensionierte Mengen. Daher ist es nur sinnvoll, Maßeinheiten für die primitiven Typen und für Aggregate zu verwenden, die diese primitiven Typen enthalten.

Das folgende Beispiel veranschaulicht die Verwendung von Maßeinheiten.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

Im folgenden Codebeispiel wird veranschaulicht, wie Sie von einer dimensionlosen Gleit Komma Zahl in einen Wert mit einem Wert mit Dimensionswert konvertieren. Sie multiplizieren einfach um 1,0 und wenden die Dimensionen auf 1,0 an. Sie können dies in eine Funktion wie `degreesFahrenheit`abstrahieren.

Wenn Sie dimensionierte Werte an Funktionen übergeben, die wenig Gleit Komma Zahlen erwarten, müssen Sie außerdem die Einheiten abbrechen oder mithilfe des `float` `float` -Operators in umwandeln. In diesem Beispiel Dividieren Sie durch `1.0<degC>` für die Argumente von `printf` , `printf` da eine dimensionlose Menge erwartet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

Die folgende Beispielsitzung zeigt die Ausgaben von und Eingaben für diesen Code.

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Verwenden generischer Einheiten

Sie können generische Funktionen schreiben, die auf Daten mit zugeordneten Maßeinheiten angewendet werden. Hierzu geben Sie einen Typ und eine generische Einheit als Typparameter an, wie im folgenden Codebeispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>Erstellen von Aggregat Typen mit generischen Einheiten

Der folgende Code zeigt, wie ein Aggregattyp erstellt wird, der aus einzelnen Gleit Komma Werten besteht, die generische Einheiten aufweisen. Dadurch kann ein einzelner Typ erstellt werden, der mit einer Vielzahl von Einheiten funktioniert. Außerdem behalten generische Einheiten die Typsicherheit bei, indem sichergestellt wird, dass ein generischer Typ mit einem Satz von Einheiten einen anderen Typ aufweist als derselbe generische Typ mit einem anderen Satz von Einheiten. Die Basis dieser Technik ist, dass das `Measure` -Attribut auf den Typparameter angewendet werden kann.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>Einheiten zur Laufzeit

Maßeinheiten werden für die Überprüfung statischer Typen verwendet. Wenn Gleit Komma Werte kompiliert werden, werden die Maßeinheiten beseitigt, sodass die Einheiten zur Laufzeit verloren gehen. Daher ist jeder Versuch, Funktionen zu implementieren, die von der Überprüfung der Einheiten zur Laufzeit abhängen, nicht möglich. Beispielsweise ist die Implementierung `ToString` einer Funktion zum Ausdrucken der Einheiten nicht möglich.

## <a name="conversions"></a>Konvertierungen

Um einen Typ mit Einheiten (z `float<'u>`. b.) in einen Typ zu konvertieren, der nicht über Einheiten verfügt, können Sie die Standard Konvertierungs Funktion verwenden. Beispielsweise können Sie verwenden `float` , um in einen `float` -Wert zu konvertieren, der keine-Einheiten enthält, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Um einen unitless-Wert in einen Wert mit Einheiten zu konvertieren, können Sie ihn mit einem Wert von 1 oder 1,0 multiplizieren, der mit den entsprechenden Einheiten kommentiert wird. Zum Schreiben von Interoperabilitäts Ebenen gibt es jedoch auch einige explizite Funktionen, die Sie verwenden können, um unitlose Werte in Werte mit Einheiten zu konvertieren. Diese befinden sich im Modul [Microsoft. FSharp. Core. LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) . Wenn Sie z. b. von einem `float` -Paar in einen `float<cm>`konvertieren möchten, verwenden Sie [floatwithmeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), wie im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>Maßeinheiten in der F# Kernbibliothek

Eine-Einheiten Bibliothek ist im `FSharp.Data.UnitSystems.SI` -Namespace verfügbar. Sie enthält SI-Einheiten in `m` ihrer Symbol Form (z. b. für die `UnitSymbols` Verbrauchseinheit) im untergeordneten Namespace und `meter` Ihren vollständigen Namen (z. `UnitNames` b. für die Verbrauchseinheit) im untergeordneten Namespace.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
