---
title: Verwenden von Features für den Musterabgleich, um Datentypen zu erweitern
description: Dieses fortgeschrittene Tutorial veranschaulicht die Verwendung von Musterabgleichverfahren zum Erstellen von Funktionen mit Daten und Algorithmen, die separat erstellt werden.
ms.date: 03/13/2019
ms-technology: csharp-whats-new
ms.custom: mvc
ms.openlocfilehash: df1054d8e0ec2b2539e6a1d00bf353d8ca927397
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156531"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a>Tutorial: Verwenden von Features für den Musterabgleich, um Datentypen zu erweitern

Mit C# 7 wurden einfache Funktionen für den Musterabgleich eingeführt. Diese Funktionen werden in C# 8 mit neuen Ausdrücken und Mustern erweitert. Sie können Funktionen schreiben, die sich verhalten, als würden Sie Typen erweitern, die sich möglicherweise in anderen Bibliotheken befinden. Ein weiterer Verwendungszweck für Muster ist die Erstellung von Funktionalität, die Ihre Anwendung erfordert, und die keine grundlegende Funktion des erweiterten Typs ist.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> - Erkennen von Situationen, in denen ein Musterabgleich verwendet werden soll.
> - Verwenden von Musterabgleichausdrücken, um Verhalten auf Grundlage von Typen und Eigenschaftswerten zu implementieren.
> - Kombinieren des Musterabgleichs mit anderen Verfahren, um vollständige Algorithmen zu erstellen.

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0-Compilers. Der C# 8-Compiler steht ab [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder mit dem [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) zur Verfügung.

In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.

## <a name="scenarios-for-pattern-matching"></a>Szenarien für den Musterabgleich

Moderne Entwicklung umfasst häufig die Integration von Daten aus mehreren Quellen und die Darstellung von aus diesen Daten gewonnenen Informationen und Einblicken in einer einzelnen zusammenhängenden Anwendung. Sie und Ihr Team haben nicht die Kontrolle über oder den Zugriff auf alle Typen, die die eingehenden Daten darstellen.

Der klassische objektorientierte Entwurf würde das Erstellen von Typen in Ihrer Anwendung fordern, die alle Datentypen aus diesen unterschiedlichen Quellen darstellen. Dann würde Ihre Anwendung mit diesen neuen Typen arbeiten, Vererbungshierarchien erstellen, virtuelle Methoden erstellen und Abstraktionen implementieren. Diese Verfahren funktionieren, und manchmal sind sie die besten Tools. In anderen Fällen können Sie weniger Code schreiben. Sie können mehr klaren Code mithilfe von Verfahren schreiben, die die Daten von den Vorgängen trennen, die diese Daten bearbeiten.

In diesem Tutorial erstellen und untersuchen Sie eine Anwendung, die eingehende Daten aus mehreren externen Quellen für ein einzelnes Szenario entgegennimmt. Sie sehen, wie **Musterabgleich** eine effiziente Möglichkeit bietet, diese Daten auf Arten zu nutzen und zu verarbeiten, die nicht Teil des ursprünglichen Systems waren.

Stellen Sie sich eine bedeutende Metropolenregion vor, die für die Verwaltung des Verkehrs Mautgebühren und spezielle Preise für Spitzenzeiten verwendet. Sie schreiben eine Anwendung, die Mautgebühren für ein Fahrzeug basierend auf seinem Typ berechnet. In späteren Verbesserungen wird die Preisgestaltung auf Basis der Anzahl der Fahrzeuginsassen integriert. Bei weiteren Verbesserungen kommt die Preisgestaltung auf Basis der Tageszeit und des Wochentages hinzu.

Vielleicht haben Sie aufgrund dieser kurzen Beschreibung schnell eine Objekthierarchie skizziert, mit der Sie ein Modell dieses System erstellen würden. Allerdings kommen Ihre Daten aus mehreren Quellen, z.B. anderen Verwaltungssystemen zur Fahrzeugregistrierung. Diese Systeme bieten verschiedene Klassen zum Erstellen eines Modells aus diesen Daten, und Sie haben kein einzelnes Objektmodell, das Sie verwenden können. In diesem Tutorial werden Sie mit diesen vereinfachten Klassen ein Modell für die Fahrzeugdaten aus diesen externen Systemen erstellen, wie im folgenden Code gezeigt:

[!code-csharp[ExternalSystems](~/samples/snippets/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

Sie können den Startercode aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) auf GitHub herunterladen. Sie sehen, dass die Fahrzeugklassen aus verschiedenen Systemen stammen und sich in verschiedenen Namespaces befinden. Keine gemeinsame Basisklasse außer `System.Object` kann genutzt werden.

## <a name="pattern-matching-designs"></a>Musterabgleichentwürfe

Das Szenario in diesem Tutorial hebt die Arten von Problemen hervor, für deren Lösung Musterabgleiche gut geeignet sind:

- Die Objekte, mit denen Sie arbeiten müssen, befinden sich nicht in einer Objekthierarchie, die Ihren Zielen entspricht. Sie arbeiten möglicherweise mit Klassen, die zu nicht verbundenen Systemen gehören.
- Die Funktionalität, die Sie hinzufügen, ist nicht Teil der Kernabstraktion für diese Klassen. Die für ein Fahrzeug gezahlte Maut *ändert sich* für verschiedene Arten von Fahrzeugen, aber die Maut ist keine Kernfunktion des Fahrzeugs.

Wenn die *Form* der Daten und die mit diesen Daten durchgeführten *Vorgänge* nicht zusammen beschrieben werden, erleichtern die Musterabgleichfunktionen in C# die Arbeit mit ihnen.

## <a name="implement-the-basic-toll-calculations"></a>Implementieren der grundlegenden Mautberechnungen

Die grundlegendsten Mautberechnungen basieren nur auf dem Fahrzeugtyp:

- Ein `Car` zahlt 2,00 US-Dollar.
- Ein `Taxi` zahlt 3,50 US-Dollar.
- Ein `Bus` zahlt 5,00 US-Dollar.
- Ein `DeliveryTruck` zahlt 10,00 US-Dollar.

Erstellen Sie eine neue `TollCalculator`-Klasse, und implementieren Sie einen Musterabgleich nach dem Fahrzeugtyp, um den Mautbetrag zu ermitteln. Im folgenden Codebeispiel wird die ursprüngliche Implementierung der `TollCalculator`-Klasse veranschaulicht.

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    public class TollCalculator
    {
        public decimal CalculateToll(object vehicle) =>
            vehicle switch
        {
            Car c           => 2.00m,
            Taxi t          => 3.50m,
            Bus b           => 5.00m,
            DeliveryTruck t => 10.00m,
            { }             => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
            null            => throw new ArgumentNullException(nameof(vehicle))
        };
    }
}
```

Der vorherige Code verwendet einen **Switch-Ausdruck** (nicht zu verwechseln mit einer [`switch`](../language-reference/keywords/switch.md)-Anweisung), der das **Typmuster** testet. Ein **Switch-Ausdruck** beginnt mit der Variablen – `vehicle` im vorangehenden Code – gefolgt vom `switch`-Schlüsselwort. Als Nächstes folgen alle **Switch-Arme** in geschweiften Klammern. Der `switch`-Ausdruck nimmt andere Überarbeitungen an der Syntax vor, die die `switch`-Anweisung umgibt. Das `case`-Schlüsselwort wird ausgelassen, und das Ergebnis jedes einzelnen Arms ist ein Ausdruck. Die letzten beiden Arme zeigen eine neue Sprachfunktion. Der `{ }`-Fall entspricht jedem Objekt ungleich NULL, das nicht mit einem früheren Arm übereinstimmte. Diese Arm fängt alle an diese Methode übergebenen falschen Typen ab.  Der `{ }`-Fall muss den Fällen für jeden Fahrzeugtyp folgen. Wenn die Reihenfolge umgekehrt werden würde, hätte der `{ }`-Fall Vorrang. Zum Schluss erkennt das `null`-Muster die Übergabe von `null` an diese Methode. Das `null`-Muster kann an letzter Stelle stehen, da die anderen Typmuster nur mit einem Objekt ungleich NULL des richtigen Typs übereinstimmen.

Sie können diesen Code mit folgendem Code in `Program.cs` testen:

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    class Program
    {
        static void Main(string[] args)
        {
            var tollCalc = new TollCalculator();

            var car = new Car();
            var taxi = new Taxi();
            var bus = new Bus();
            var truck = new DeliveryTruck();

            Console.WriteLine($"The toll for a car is {tollCalc.CalculateToll(car)}");
            Console.WriteLine($"The toll for a taxi is {tollCalc.CalculateToll(taxi)}");
            Console.WriteLine($"The toll for a bus is {tollCalc.CalculateToll(bus)}");
            Console.WriteLine($"The toll for a truck is {tollCalc.CalculateToll(truck)}");

            try
            {
                tollCalc.CalculateToll("this will fail");
            }
            catch (ArgumentException e)
            {
                Console.WriteLine("Caught an argument exception when using the wrong type");
            }
            try
            {
                tollCalc.CalculateToll(null);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

Dieser Code befindet sich im Startprojekt, ist aber auskommentiert. Entfernen Sie die Kommentarmarkierungen, und Sie können testen, was Sie geschrieben haben.

Sie sehen jetzt, wie Muster Ihnen helfen können, Algorithmen zu erstellen, bei denen Code und Daten getrennt sind. Der `switch`-Ausdruck testet den Typ und produziert auf der Grundlage der Ergebnisse unterschiedliche Werte. Aber das ist nur der Anfang.

## <a name="add-occupancy-pricing"></a>Hinzufügen der Preisgestaltung nach Belegung

Die Mautbehörde möchte, dass die Fahrzeuge maximal ausgelastet werden. Sie hat entschieden, mehr zu verlangen, wenn sich weniger Fahrgäste in Fahrzeugen befinden, und bei vollständig gefüllten Fahrzeugen reduzierte Preise zu bieten:

- PKWs und Taxis ohne Fahrgäste zahlen einen Aufschlag von 0,50 US-Dollar.
- PKWs und Taxis mit zwei Fahrgästen erhalten einen Rabatt von 0,50 US-Dollar.
- PKWs und Taxis mit mindestens drei Fahrgästen erhalten einen Rabatt von 1,00 US-Dollar.
- Busse, die zu weniger als 50% gefüllt sind, zahlen einen Aufschlag von 2,00 US-Dollar.
- Busse, die zu mehr als 90% ausgelastet sind, erhalten einen Rabatt von 1,00 US-Dollar.

Diese Regeln können mit dem **Eigenschaftenmuster** im gleichen Switch-Ausdruck implementiert werden. Das Eigenschaftenmuster untersucht Eigenschaften des Objekts, nachdem der Typ bestimmt wurde. Der einzelne Fall eines `Car` wird auf vier verschiedene Fälle erweitert:

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1 }       => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    // ...
};
```

Die ersten drei Fällen testen den Typ als `Car` und überprüfen dann den Wert der `Passengers`-Eigenschaft. Wenn beide übereinstimmen, wird dieser Ausdruck ausgewertet und zurückgegeben.

Sie würden auch die Fälle für Taxis auf ähnliche Weise erweitern:

```csharp
vehicle switch
{
    // ...

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    // ...
};
```

Im vorherigen Beispiel wurde die `when`-Klausel im letzten Fall weggelassen.

Implementieren Sie als Nächstes die Belegungsregeln durch Erweitern der Fälle für Busse, wie im folgenden Beispiel gezeigt:

```csharp
vehicle switch
{
    // ...

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    // ...
};
```

Die Mautbehörde interessiert sich nicht für die Anzahl der Fahrgäste in Lieferwagen. Stattdessen passt sie die Mauthöhe basierend auf der Gewichtsklasse der Lieferwagen wie folgt an:

- Lieferwagen über 2,3 t wird ein Aufschlag von 5,00 US-Dollar berechnet.
- Leichte Lieferwagen unter 1,35 t (3.000 Pfund) erhalten einen Rabatt von 2,00 USD.

Diese Regel wird mit folgendem Code implementiert:

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

Im vorherigen Code sehen Sie die `when`-Klausel eines switch-Arms. Mit der `when`-Klausel testen Sie andere Bedingungen einer Eigenschaft als Gleichheit. Wenn Sie damit fertig sind, haben Sie eine Methode, die der folgenden ähnelt:

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1}        => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,

    { }     => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
    null    => throw new ArgumentNullException(nameof(vehicle))
};
```

Viele dieser Switch-Arme sind Beispiele für **rekursive Muster**. `Car { Passengers: 1}` zeigt z.B. ein konstantes Muster in einem Eigenschaftenmuster an.

Sie können mit geschachtelten Switches die Wiederholungen in diesem Code reduzieren. `Car` und `Taxi` weisen in den vorherigen Beispielen jeweils vier verschiedene Arme auf. In beiden Fällen können Sie ein Typmuster erstellen, das in einem Eigenschaftenmuster mündet. Dieses Verfahren wird im folgenden Code dargestellt:

```csharp
public decimal CalculateToll(object vehicle) =>
    vehicle switch
    {
        Car c => c.Passengers switch
        {
            0 => 2.00m + 0.5m,
            1 => 2.0m,
            2 => 2.0m - 0.5m,
            _ => 2.00m - 1.0m
        },

        Taxi t => t.Fares switch
        {
            0 => 3.50m + 1.00m,
            1 => 3.50m,
            2 => 3.50m - 0.50m,
            _ => 3.50m - 1.00m
        },

        Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
        Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
        Bus b => 5.00m,

        DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
        DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
        DeliveryTruck t => 10.00m,

        { }  => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
        null => throw new ArgumentNullException(nameof(vehicle))
    };
```

Im vorherigen Beispiel folgt aus der Verwendung eines rekursiven Ausdrucks, dass Sie nicht die Arme `Car` und `Taxi` wiederholen, die untergeordnete Arme enthalten, die den Wert der Eigenschaft testen. Dieses Verfahren wird nicht für die Arme `Bus` und `DeliveryTruck` verwendet, da diese Arme Bereiche für die Eigenschaft testen, nicht diskrete Werte.

## <a name="add-peak-pricing"></a>Hinzufügen der Preisgestaltung für Spitzenzeiten

Für das letzte Feature möchte die Mautbehörde die zeitabhängige Preisgestaltung für Spitzenzeiten hinzufügen. Während der morgendlichen und abendlichen Hauptverkehrszeiten werden die Mautgebühren verdoppelt. Diese Regel betrifft nur den Verkehr in einer Richtung: am Morgen den stadteinwärts und am Abend den stadtauswärts gehenden Verkehr. Während anderer Zeiten werden die Mautgebühren werktags um 50% heraufgesetzt. Am späten Abend und frühen Morgen werden die Mautgebühren um 25% verringert. Am Wochenende gelten unabhängig von der Zeit die normalen Gebühren.

Sie verwenden den Musterabgleich für dieses Feature, aber Sie integrieren es mit anderen Verfahren. Sie könnten einen einzelnen Musterabgleichausdruck erstellen, der alle Kombinationen von Richtung, Wochentag und Zeit berücksichtigen würde. Das Ergebnis wäre ein komplizierter Ausdruck. Er wäre schwierig zu lesen und schwer zu verstehen. Dies erschwert, die Richtigkeit zu gewährleisten. Kombinieren Sie stattdessen diese Methoden, um ein Tupel von Werten zu erstellen, das alle diese Zustände präzise beschreibt. Berechnen Sie mithilfe des Musterabgleichs einen Multiplikator für die Maut. Das Tupel enthält drei diskrete Bedingungen:

- Der Tag ist entweder ein Wochentag oder fällt auf ein Wochenende.
- Der Zeitbereich, in dem die Maut erhoben wird.
- Die Richtung – stadteinwärts oder stadtauswärts.

Die folgende Tabelle zeigt die Kombinationen von Eingabewerten und des Multiplikators für die Preisgestaltung für Spitzenzeiten:

| Day        | zeit         | Richtung | Aufschlag/Rabatt |
| ---------- | ------------ | --------- |--------:|
| Wochentag    | morgendliche Hauptverkehrszeit | stadteinwärts   | x 2,00  |
| Wochentag    | morgendliche Hauptverkehrszeit | stadtauswärts  | x 1,00  |
| Wochentag    | tagsüber      | stadteinwärts   | x 1,50  |
| Wochentag    | tagsüber      | stadtauswärts  | x 1,50  |
| Wochentag    | abendliche Hauptverkehrszeit | stadteinwärts   | x 1,00  |
| Wochentag    | abendliche Hauptverkehrszeit | stadtauswärts  | x 2,00  |
| Wochentag    | nachts    | stadteinwärts   | x 0,75  |
| Wochentag    | nachts    | stadtauswärts  | x 0,75  |
| Wochenende    | morgendliche Hauptverkehrszeit | stadteinwärts   | x 1,00  |
| Wochenende    | morgendliche Hauptverkehrszeit | stadtauswärts  | x 1,00  |
| Wochenende    | tagsüber      | stadteinwärts   | x 1,00  |
| Wochenende    | tagsüber      | stadtauswärts  | x 1,00  |
| Wochenende    | abendliche Hauptverkehrszeit | stadteinwärts   | x 1,00  |
| Wochenende    | abendliche Hauptverkehrszeit | stadtauswärts  | x 1,00  |
| Wochenende    | nachts    | stadteinwärts   | x 1,00  |
| Wochenende    | nachts    | stadtauswärts  | x 1,00  |

Es gibt 16 verschiedene Kombinationen der drei Variablen. Durch Kombinieren einiger Bedingungen vereinfachen Sie den endgültigen Switch-Ausdruck.

Das System, das die Maut erhebt, verwendet eine <xref:System.DateTime>-Struktur für die Uhrzeit, zu der die Maut erhoben wurde. Erstellen Sie die Membermethoden, die die Variablen aus der obigen Tabelle erstellen. Die folgende Funktion verwendet einen switch-Ausdruck für den Musterabgleich, um auszudrücken, ob eine <xref:System.DateTime>-Struktur ein Wochenende oder einen Wochentag darstellt:

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Monday    => true,
        DayOfWeek.Tuesday   => true,
        DayOfWeek.Wednesday => true,
        DayOfWeek.Thursday  => true,
        DayOfWeek.Friday    => true,
        DayOfWeek.Saturday  => false,
        DayOfWeek.Sunday    => false
    };
```

Diese Methode funktioniert, aber sie enthält Wiederholungen. Sie können sie vereinfachen, wie im folgenden Code gezeigt:

[!code-csharp[IsWeekDay](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

Fügen Sie als Nächstes eine ähnliche Funktion hinzu, um die Zeit in den Blöcken zu kategorisieren:

[!code-csharp[GetTimeBand](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

Die vorherige Methode verwendet den Musterabgleich nicht. Es ist klarer, eine vertraute Kaskade von `if`-Anweisungen zu verwenden. Sie fügen eine private `enum`-Variable hinzu, um jeden Zeitbereich in einen diskreten Wert zu konvertieren.

Nachdem Sie diese Methoden erstellt haben, können Sie einen anderen `switch`-Ausdruck mit dem **Tupelmuster** zum Berechnen des Aufschlags bzw. Rabatts auf den Preis verwenden. Sie könnten einen `switch`-Ausdruck mit allen 16 Armen erstellen:

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

Der obige Code funktioniert, aber er kann vereinfacht werden. Alle acht Kombinationen für das Wochenende haben die gleiche Maut. Sie können alle acht mit der folgenden Zeile ersetzen:

```csharp
(false, _, _) => 1.0m,
```

Sowohl stadteinwärts als auch stadtauswärts gehender Verkehr haben an Wochentagen tagsüber und nachts den gleichen Multiplikator. Diese vier switch-Arme können durch die folgenden zwei Zeilen ersetzt werden:

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

Der Code sollte nach diesen beiden Änderungen folgendermaßen aussehen:

```csharp
public decimal PeakTimePremium(DateTime timeOfToll, bool inbound) =>
    (IsWeekDay(timeOfToll), GetTimeBand(timeOfToll), inbound) switch
    {
        (true, TimeBand.MorningRush, true)  => 2.00m,
        (true, TimeBand.MorningRush, false) => 1.00m,
        (true, TimeBand.Daytime,     _)     => 1.50m,
        (true, TimeBand.EveningRush, true)  => 1.00m,
        (true, TimeBand.EveningRush, false) => 2.00m,
        (true, TimeBand.Overnight,   _)     => 0.75m,
        (false, _,                   _)     => 1.00m,
    };
```

Schließlich können Sie die zwei Hauptverkehrszeiten entfernen, zu denen der reguläre Preis gezahlt wird. Wenn Sie diese Arme entfernen, können Sie im letzten Switch-Arm `false` mit einem Verwerfen (`_`) ersetzen. So sieht die abgeschlossene Methode aus:

[!code-csharp[SimplifiedTuplePattern](../../../samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

Dieses Beispiel verdeutlicht einen der Vorteile von Musterabgleich: Die Musterverzweigungen werden der Reihe nach ausgewertet. Wenn Sie sie neu anordnen, sodass eine frühere Verzweigung einen Ihrer späteren Fälle verarbeitet, gibt der Compiler einen Warnhinweis zum unerreichbaren Code aus. Diese Sprachregeln haben die Durchführung der vorherigen Vereinfachungen erleichtert mit der Zuversicht, dass der Code sich nicht geändert hat.

Ein Musterabgleich führt dazu, dass einige Codetypen leichter lesbar sind, und bietet eine Alternative zu objektorientierten Verfahren, wenn Ihren Klassen kein Code hinzugefügt werden kann. Die Cloud sorgt dafür, dass Daten und Funktionen getrennt bleiben. Die *Form* der Daten und die daran ausgeführten *Vorgänge* werden nicht notwendigerweise zusammen beschrieben. In diesem Tutorial haben Sie vorhandene Daten auf von ihrer ursprünglichen Funktion völlig unterschiedliche Arten verwendet. Der Musterabgleich ermöglichte Ihnen, Funktionalitäten zu erstellen, die diese Typen überschrieben haben, obwohl Sie sie nicht erweitern konnten.

## <a name="next-steps"></a>Nächste Schritte

Sie können den fertig gestellten Code aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) auf GitHub herunterladen. Untersuchen Sie Muster auf eigene Faust, und nehmen Sie dieses Verfahren in Ihre Codierungsgewohnheiten auf. Wenn Sie diese Verfahren lernen, eröffnet sich Ihnen ein anderer Weg, Probleme anzugehen und neue Funktionalität zu erstellen.
