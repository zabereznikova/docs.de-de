---
title: 'C#-Tutorial: Verwenden von Datensatztypen'
description: In diesem Tutorial erfahren Sie, wie Sie Datensatztypen verwenden, Hierarchien von Datensätzen erstellen und wann Datensätze anstelle von Klassen verwendet werden sollten.
ms.date: 11/12/2020
ms.openlocfilehash: 8a2cb6966ab4f93432723fd6f82618efa86b26aa
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688556"
---
# <a name="create-record-types"></a>Erstellen von Datensatztypen

Mit C# 9 wurden *Datensätze* eingeführt. Dabei handelt es sich um einen neuen Verweistyp, den Sie anstelle von Klassen oder Strukturen erstellen können. Datensätze unterscheiden sich insofern von Klassen, dass Datensatztypen *wertbasierte Gleichheit* verwenden. Zwei Variablen eines Datensatztyps sind gleich, wenn die Datensatztypdefinitionen identisch sind und wenn die Werte in beiden Datensätzen für alle Felder identisch sind. Zwei Variablen eines Klassentyps sind identisch, wenn die Objekte, auf die verwiesen wird, denselben Klassentyp aufweisen und die Variablen auf dasselbe Objekt verweisen. Die wertbasierte Gleichheit impliziert andere Funktionen, die Sie wahrscheinlich in Datensatztypen benötigen. Der Compiler generiert viele dieser Member, wenn Sie `record` anstelle von `class` deklarieren.

In diesem Tutorial lernen Sie Folgendes:

> [!div class="checklist"]
>
> - Wann Sie `class` oder `record` deklarieren sollten
> - Deklarieren von Datensatztypen und Datensatztypen mit fester Breite
> - Ersetzen Ihrer Methoden für vom Compiler generierte Methoden in Datensätzen

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET 5 oder höher einrichten, einschließlich des Compilers von C# 9.0 oder höher. Der C# 9.0-Compiler steht ab [Visual Studio 2019 Version 16.8](https://visualstudio.microsoft.com/vs) oder mit dem [.NET 5.0 SDK](https://dotnet.microsoft.com/download) zur Verfügung.

## <a name="characteristics-of-records"></a>Charakteristiken von Datensätzen

Sie definieren einen *Datensatz*, indem Sie einen Typ mit dem Schlüsselwort `record` deklarieren, anstatt mit dem Schlüsselwort `class` oder `struct`. Ein Datensatz ist ein Verweistyp und unterliegt der Semantik der wertbasierten Gleichheit. Zum Erzwingen der Wertsemantik generiert der Compiler mehrere Methoden für Ihren Datensatztyp:

- Eine Überschreibung von <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>
- Eine virtuelle `Equals`-Methode, deren Parameter der Datensatztyp ist
- Eine Überschreibung von <xref:System.Object.GetHashCode?displayProperty=nameWithType>
- Methoden für `operator ==` und `operator !=`
- Datensatztypen implementieren <xref:System.IEquatable%601?displayProperty=nameWithType>

Darüber hinaus stellen Datensätze eine Überschreibung von <xref:System.Object.ToString?displayProperty=nameWithType> bereit. Der Compiler synthetisiert Methoden zum Anzeigen von Datensätzen mit <xref:System.Object.ToString?displayProperty=nameWithType>. Diese Member untersuchen Sie, während Sie Code für dieses Tutorial schreiben. Datensätze unterstützen `with`-Ausdrücke, um nicht destruktive Änderungen von Datensätzen zu ermöglichen.

Sie können auch *Datensätze mit fester Breite* mithilfe einer kürzeren Syntax deklarieren. Der Compiler synthetisiert mehr Methoden für Sie, wenn Sie Datensätze mit fester Breite deklarieren:

- Ein primärer Konstruktor, dessen Parameter mit den Parametern mit fester Breite der Datensatzdeklaration übereinstimmen
- Öffentliche init-only-Eigenschaften für jeden Parameter eines primären Konstruktors
- Eine `Deconstruct`-Methode zum Extrahieren von Eigenschaften aus dem Datensatz

## <a name="build-temperature-data"></a>Erstellen von Temperaturdaten

Daten und Statistiken gehören zu den Szenarios, in denen Sie Datensätze verwenden sollten. Für dieses Tutorial erstellen Sie eine Anwendung, die *Wärmesummen* für verschiedene Verwendungszwecke berechnet. *Wärmesummen* sind ein Maß für Temperaturwerte über einen gewissen Zeitraum von Tagen, Wochen oder Monaten. Wärmesummen verfolgen den Energieverbrauch und prognostizieren diesen. Eine größere Anzahl von Tagen mit hohen Temperaturen führt zu erhöhter Nutzung von Klimaanlagen, während eine größere Anzahl von Tagen mit niedrigen Temperaturen zu erhöhter Nutzung von Heizkörpern führt. Wärmesummen werden für die Verwaltung der Pflanzenpopulation verwendet. Mit dem Wechsel der Jahreszeiten korrelieren Wärmesummen mit dem Wachstum von Pflanzen. Wärmesummen werden außerdem zur Nachverfolgung von Tierwanderungen für Spezies verwendet, die sich dem Klima entsprechend bewegen.

Die Formel basiert auf der Durchschnittstemperatur eines jeweiligen Tages und einer Baselinetemperatur. Zum Berechnen von Wärmesummen über Zeit benötigen Sie die Höchst- und Mindesttemperaturen für jeden Tag eines Zeitraums. Im Folgenden beginnen Sie mit der Erstellung einer neuen Anwendung. Erstellen Sie eine neue Konsolenanwendung. Erstellen Sie einen neuen Datensatztyp in einer neuen Datei namens „DailyTemperature.cs“:

:::code language="csharp" source="snippets/record-types/InterimSteps.cs" ID="DailyRecord":::

Mit dem obigen Code wird ein *Datensatz mit fester Breite* definiert. Sie haben einen Verweistyp erstellt, der zwei Eigenschaften umfasst: `HighTemp` und `LowTemp`. Bei diesen Eigenschaften handelt es sich um *init-only-Eigenschaften*, d. h., sie können im Konstruktor oder mithilfe eines Eigenschafteninitialisierers festgelegt werden. Der Typ `DailyTemperature` verfügt ebenfalls über einen *primären Konstruktor*, der über zwei Parameter verfügt, die den zwei Eigenschaften entsprechen. Sie verwenden den primären Konstruktor zum Initialisieren eines `DailyTemperature`-Datensatzes:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="DeclareData":::

Sie können Ihre eigenen Eigenschaften oder Methoden zu Datensätzen hinzufügen, dazu zählen auch Datensätze mit fester Breite. Sie müssen die Durchschnittstemperatur für jeden Tag berechnen. Diese Eigenschaft können Sie zum Datensatz `DailyTemperature` hinzufügen:

:::code language="csharp" source="snippets/record-types/DailyTemperature.cs" ID="TemperatureRecord":::

Als Nächstes stellen Sie sicher, dass Sie diese Daten verwenden können. Fügen Sie der `Main`-Methode den folgenden Code hinzu:

```csharp
foreach (var item in data)
    Console.WriteLine(item);
```

Führen Sie Ihre Anwendung aus. Daraufhin sollte Ihnen eine Ausgabe angezeigt werden, die der folgenden Anzeige ähnelt (einige Zeilen wurden aus Platzgründen entfernt):

```dotnetcli
DailyTemperature { HighTemp = 57, LowTemp = 30, Mean = 43.5 }
DailyTemperature { HighTemp = 60, LowTemp = 35, Mean = 47.5 }


DailyTemperature { HighTemp = 80, LowTemp = 60, Mean = 70 }
DailyTemperature { HighTemp = 85, LowTemp = 66, Mean = 75.5 }
```

Der obige Code zeigt die Ausgabe der Überschreibung von `ToString` an, die vom Compiler synthetisiert wurde. Wenn Sie einen anderen Text verwenden möchten, können Sie Ihre eigene Version von `ToString` schreiben. Dies hindert den Compiler daran, eine Version für Sie zu synthetisieren.

## <a name="compute-degree-days"></a>Berechnen von Wärmesummen

Zum Berechnen der Wärmesummen verwenden Sie die Differenz zwischen einer Baselinetemperatur und einer Durchschnittstemperatur für einen Tag. Zum Berechnen der Wärmesumme über Zeit entfernen Sie alle Tage, an denen die Durchschnittstemperatur unterhalb der Baselinetemperatur liegt. Zum Berechnen der Kältesumme über Zeit entfernen Sie alle Tage, an denen die Durchschnittstemperatur über der Baselinetemperatur liegt. Beispielsweise verwenden die USA 65 F als Baselinetemperatur für Wärme- und Kältesummen. Bei dieser Temperatur ist weder Heizung noch Kühlung erforderlich. Ein Tag mit einer Durchschnittstemperatur von 70 F weist eine Kältesumme von „5“und eine Wärmesumme von „0“ auf. Wenn die Durchschnittstemperatur also 55 F entspricht, weist der Tag dementsprechend eine Wärmesumme von „10“ und eine Kältesumme von „0“ auf.

Sie können diese Formeln in Form einer kleinen Hierarchie aus Datensatztypen ausdrücken: ein abstrakter Temperatursummentyp und zwei konkrete Typen für Wärmesummen und Kältesummen. Bei diesen Typen kann es sich außerdem um Datensätze mit fester Breite handeln. Sie verwenden eine Baselinetemperatur und eine Reihe täglicher Temperaturdatensätze als Argumente für den primären Konstruktor:

:::code language="csharp" source="snippets/record-types/InterimSteps.cs" ID="DegreeDaysRecords":::

Der abstrakte Datensatz `DegreeDays` ist die gemeinsame Basisklasse für die beiden Datensätze `HeatingDegreeDays` und `CoolingDegreeDays`. Die primären Konstruktordeklarationen der abgeleiteten Datensätze zeigen, wie die Initialisierung des Basisdatensatzes verwaltet wird. Ihr abgeleiteter Datensatz deklariert Parameter für alle Parameter im primären Konstruktor des Basisdatensatzes. Der Basisdatensatz deklariert und initialisiert diese Eigenschaften. Der abgeleitete Datensatz blendet diese nicht aus. Stattdessen erstellt und initialisiert er nur Eigenschaften für Parameter, die nicht in seinem Basisdatensatz deklariert sind. In diesem Beispiel fügen die abgeleiteten Datensätze keine neuen primären Konstruktorparameter hinzu. Testen Sie Ihren Code, indem Sie den folgenden Code zu Ihrer `Main`-Methode hinzufügen:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="HeatingAndCooling":::

Daraufhin sollte eine Ausgabe ähnlich der folgenden angezeigt werden:

```dotnetcli
HeatingDegreeDays { BaseTemperature = 65, TempRecords = record_types.DailyTemperature[], DegreeDays = 85 }
CoolingDegreeDays { BaseTemperature = 65, TempRecords = record_types.DailyTemperature[], DegreeDays = 71.5 }
```

## <a name="define-compiler-synthesized-methods"></a>Definieren von durch den Compiler synthetisierten Methoden

Ihr Code berechnet die korrekte Anzahl von Wärme- und Kältesummen über den Zeitraum. Jedoch veranschaulicht dieses Beispiel, wieso Sie einige der synthetisierten Methoden durch Datensätze ersetzen sollten. Mit Ausnahme der Clone-Methode können Sie Ihre eigene Version von beliebigen durch den Compiler synthetisierten Methoden in einem Datensatztyp deklarieren. Die Clone-Methode verfügt über einen vom Compiler generierten Namen, und Sie können keine andere Implementierung bereitstellen. Die synthetisierten Methoden umfassen einen Kopierkonstruktor, die Member der <xref:System.IEquatable%601?displayProperty=nameWithType>-Schnittstelle, Gleichheits- und Ungleichheitstests sowie <xref:System.Object.GetHashCode>. Zu diesem Zweck synthetisieren Sie `PrintMembers`. Sie könnten auch Ihre eigene Version von `ToString` deklarieren, jedoch stellt `PrintMembers` eine bessere Option für Vererbungsszenarios dar. Die Signatur muss mit der synthetisierten Methode übereinstimmen, wenn Sie Ihre eigene Version einer synthetisierten Methode verwenden möchten.

Das Element `TempRecords` in der Konsolenausgabe ist nicht nützlich. Es zeigt den Typ an, erfüllt aber sonst keinen Zweck. Sie können dieses Verhalten ändern, indem Sie Ihre eigene Implementierung der synthetisierten `PrintMembers`-Methode angeben. Die Signatur hängt von den Modifizierern ab, die auf die `record`-Deklaration angewendet werden:

- Wenn ein Datensatztyp `sealed` ist, lautet die Signatur `private bool PrintMembers(StringBuilder builder);`.
- Wenn ein Datensatztyp nicht `sealed` ist und von `object` abgeleitet wird (d. h., er deklariert keinen Basisdatensatz), lautet die Signatur `protected virtual bool PrintMembers(StringBuilder builder);`.
- Wenn ein Datensatztyp nicht `sealed` ist und von einem anderen Datensatz abgeleitet wird, lautet die Signatur `protected override bool PrintMembers(StringBuilder builder);`.

Diese Regeln sind am einfachsten zu verstehen, wenn Sie den Zweck von `PrintMembers` verstehen. `PrintMembers` fügt Informationen zu jeder Eigenschaft in einem Datensatztyp zu einer Zeichenfolge hinzu. Der Vertrag erfordert, dass Basisdatensätze ihre Member zur Anzeige hinzufügen, und geht davon aus, dass abgeleitete Member ihre Member hinzufügen. Jeder Datensatztyp synthetisiert eine `ToString`-Überschreibung, die dem folgenden Beispiel für `HeatingDegreeDays` ähnelt:

```csharp
public override string ToString()
{
    StringBuilder stringBuilder = new StringBuilder();
    stringBuilder.Append("HeatingDegreeDays");
    stringBuilder.Append(" { ");
    if (PrintMembers(stringBuilder))
    {
        stringBuilder.Append(" ");
    }
    stringBuilder.Append("}");
    return stringBuilder.ToString();
}
```

Sie deklarieren eine `PrintMembers`-Methode im Datensatz `DegreeDays`, der den Typ der Sammlung nicht ausgibt:

:::code language="csharp" source="snippets/record-types/DegreeDays.cs" ID="AddPrintMembers":::

Die Signatur deklariert eine `virtual protected`-Methode entsprechend der Version des Compilers. Sie müssen sich keine Sorgen darüber machen, dass Sie die falschen Zugriffsmethoden verwenden, da die Sprache die richtige Signatur erzwingt. Wenn Sie die richtigen Modifizierer für synthetisierte Methoden vergessen, gibt der Compiler Warnungen oder Fehler aus, die Sie dabei unterstützen, die richtige Signatur zu verwenden.

## <a name="non-destructive-mutation"></a>Nicht destruktive Änderungen

Die synthetisierten Member in einem Datensatz mit fester Breite ändern den Zustand des Datensatzes nicht. Das Ziel besteht darin, dass Sie unveränderliche Datensätze einfacher erstellen können. Sehen Sie sich noch einmal die vorherigen Deklarationen für `HeatingDegreeDays` und `CoolingDegreeDays` an. Die hinzugefügten Member führen Berechnungen der Werte für den Datensatz durch, ändern aber nicht den Zustand. Datensätze mit fester Breite vereinfachen das Erstellen unveränderlicher Verweistypen.

Das Erstellen unveränderlicher Verweistypen impliziert, dass Sie nicht destruktive Änderungen verwenden sollten. Sie erstellen neue Datensatzinstanzen mit [`with`-Ausdrücken](../../language-reference/operators/with-expression.md), die den vorhandenen Datensatzinstanzen ähneln. Diese Ausdrücke sind eine Kopierkonstruktion mit zusätzlichen Zuweisungen, die die Kopie ändern. Das Ergebnis ist eine neue Datensatzinstanz, bei der alle Eigenschaften aus dem vorhandenen Datensatz kopiert und optional geändert wurden. Der ursprüngliche Datensatz bleibt unverändert.

Als Nächstes fügen Sie zur Veranschaulichung von `with`-Ausdrücken einige Features zu Ihrem Programm hinzu. Zuerst erstellen Sie einen neuen Datensatz zum Berechnen steigender Wärmesummen mithilfe derselben Daten. Für *steigende Wärmesummen* werden in der Regel 41 F als Baselinetemperatur verwendet und sie messen Temperaturen über der Baseline. Sie können einen neuen Datensatz erstellen, der `coolingDegreeDays` ähnelt, aber eine andere Baselinetemperatur verwendet, um dieselben Daten zu verwenden:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="GrowingDegreeDays":::

Sie können die Anzahl der berechneten Temperaturen mit den generierten Zahlen mit einer höheren Baselinetemperatur vergleichen. Denken Sie daran, dass Datensätze *Verweistypen* sind und dass es sich bei diesen Kopien um flache Kopien handelt. Das Array für die Daten wird nicht kopiert, aber beide Datensätze beziehen sich auf dieselben Daten. Dies ist in einem anderen Szenario von Vorteil. Bei steigenden Wärmesummen ist es nützlich, die Gesamtsumme der letzten fünf Tage zu überwachen. Mithilfe von `with`-Ausdrücken können Sie neue Datensätze mit anderen Quelldaten erstellen. Mit dem folgenden Code wird eine Sammlung dieser Akkumulationen erstellt, und anschließend werden die Werte angezeigt:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="RunningFiveDayTotal":::

Sie können auch `with`-Ausdrücke verwenden, um Kopien von Datensätzen zu erstellen. Geben Sie keine Eigenschaften zwischen den geschweiften Klammern für den `with`-Ausdruck an. Das bedeutet, eine Kopie wird erstellt und es werden keine Eigenschaften geändert:

```csharp
var growingDegreeDaysCopy = growingDegreeDays with { };
```

Führen Sie die fertiggestellte Anwendung aus, um die Ergebnisse anzuzeigen.

## <a name="summary"></a>Zusammenfassung

In diesem Tutorial wurden verschiedene Aspekte von Datensätzen vorgestellt. Datensätze bieten eine präzise Syntax für Verweistypen, bei dem der grundlegende Zweck das Speichern von Daten ist. Bei objektorientierten Klassen ist der grundlegende Zweck die Definition von Zuständigkeiten. Im Mittelpunkt dieses Tutorials standen *Datensätze mit fester Breite*, für die Sie eine präzise Syntax zum Deklarieren der init-only-Eigenschaften für einen Datensatz verwenden können. Der Compiler synthetisiert einige Member des Datensatzes zum Kopieren und Vergleichen der Datensätze. Sie können beliebige andere Member hinzufügen, die Sie für Ihre Datensatztypen benötigen. Sie können unveränderliche Datensatztypen erstellen und sich gewiss sein, das kein vom Compiler generierter Member den Zustand ändern würde. Für Datensätze mit fester Breite vereinfachen `with`-Ausdrücke die Unterstützung nicht destruktiver Änderungen.

Datensätze bieten eine weitere Möglichkeit zum Definieren von Typen. Sie können `class`-Definitionen zum Erstellen von objektorientierten Hierarchien verwenden, die sich auf die Zuständigkeiten und das Verhalten von Objekten konzentrieren. Sie können `struct`-Typen für Datenstrukturen erstellen, die Daten speichern und klein genug für effiziente Kopiervorgänge sind. Wenn Sie wertbasierte Gleichheit und Vergleiche sowie Verweisvariablen verwenden, aber keine Werte kopieren möchten, können Sie Datensätze erstellen.

Vollständige Beschreibungen der Datensätze finden Sie in der [Spezifikation empfohlener Datensatztypen](~/_csharplang/proposals/csharp-9.0/records.md).
