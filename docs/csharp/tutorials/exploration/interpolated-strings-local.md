---
title: Zeichenfolgeninterpolation – C#-Tutorial
description: Dieses Tutorial erläutert, wie Sie mit dem Zeichenfolgeninterpolations-Feature in C# formatierte Ausdrucksergebnisse in eine größere Zeichenfolge einfügen.
ms.date: 10/23/2018
ms.openlocfilehash: 22637895f241585bac4909479f225bf3cb581614
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738280"
---
# <a name="use-string-interpolation-to-construct-formatted-strings"></a>Erstellen formatierter Zeichenfolgen mit der Zeichenfolgeninterpolation

Dieses Tutorial erläutert, wie Sie die [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md) in C# verwenden, um Werte in eine einzelne Ergebniszeichenfolge einzufügen. Sie schreiben einen C#-Code und sehen dort die Ergebnisse der Kompilierung und Ausführung Ihres Codes. Dieses Tutorial enthält einige Lektionen, in denen Ihnen gezeigt wird, wie Werte in eine Zeichenfolge eingefügt und auf verschiedene Weisen formatiert werden.

Für dieses Tutorial wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können. Im .NET-Tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) (Hallo Welt in zehn Minuten) finden Sie eine Anleitung zum Einrichten Ihrer lokalen Entwicklungsumgebung unter Windows, Linux oder macOS. Sie können auch die [interaktive Version](interpolated-strings.yml) dieses Tutorials in Ihrem Browser durcharbeiten.

## <a name="create-an-interpolated-string"></a>Erstellen einer interpolierten Zeichenfolge

Erstellen Sie ein Verzeichnis namens *interpolated*. Legen Sie dieses als das aktuelle Verzeichnis fest, und führen Sie folgenden Befehl in einem Konsolenfenster aus:

```dotnetcli
dotnet new console
```

Dieser Befehl erstellt im aktuellen Verzeichnis eine neue .NET Core-Konsolenanwendung.

Öffnen Sie *Program.cs* in Ihrem bevorzugten Editor, und ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code, in dem Sie `<name>` durch Ihren Namen ersetzen:

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

Testen Sie diesen Code, indem Sie `dotnet run` in Ihr Konsolenfenster eingeben. Wenn Sie das Programm ausführen, wird eine einzelne Zeichenfolge angezeigt, die Ihren Namen in der Begrüßung enthält. Die im <xref:System.Console.WriteLine%2A>-Methodenaufruf enthaltene Zeichenfolge ist ein *interpolierter Zeichenfolgenausdruck*. Dabei handelt es sich um eine Vorlage, durch die Sie eine einzelne Zeichenfolge (als *Ergebniszeichenfolge* bezeichnet) aus einer Zeichenfolge erstellen können, die eingebetteten Code enthält. Interpolierte Zeichenfolgen sind besonders nützlich für das Einfügen von Werten in eine Zeichenfolge oder zum Verketten (bzw. Verknüpfen) von Zeichenfolgen.

Dieses einfache Beispiel enthält die zwei Elemente, über die jede interpolierte Zeichenfolge verfügen muss:

- Ein Zeichenfolgenliteral, das ein `$`-Zeichen vor dem öffnenden Anführungszeichen enthält. Zwischen dem `$`-Symbol und dem Anführungszeichen darf kein Leerraum vorhanden sein. (Wenn Sie testen möchten, was andernfalls geschieht, fügen Sie einen Leerraum nach dem `$`-Zeichen ein, speichern Sie die Datei, und führen Sie das Programm erneut aus, indem Sie `dotnet run` im Konsolenfenster eingeben. Der C#-Compiler zeigt dann die Fehlermeldung „Fehler CS1056: Unerwartetes Zeichen '$'“ an.)

- Mindestens ein *Interpolationsausdruck*. Ein Interpolationsausdruck wird durch eine öffnende und eine schließende geschweifte Klammer (`{` und `}`) angegeben. Sie können jeden C#-Ausdruck in die Klammern einfügen, der einen Wert (einschließlich `null`) zurückgibt.

Im Folgenden finden Sie weitere Beispiele für die Zeichenfolgeninterpolation mit einigen anderen Datentypen.

## <a name="include-different-data-types"></a>Einschließen verschiedener Datentypen

Im vorherigen Abschnitt haben Sie die Zeichenfolgeninterpolation verwendet, um eine Zeichenfolge in eine andere einzufügen. Das Ergebnis eines Interpolationsausdrucks kann jedoch jeden Datentyp aufweisen. Im Folgenden werden mehrere Datentypen in eine interpolierte Zeichenfolge einbezogen.

Im folgenden Beispiel wird zunächst ein [Klassen](../../programming-guide/classes-and-structs/classes.md)-Datentyp `Vegetable` definiert, der über die [Eigenschaft](../../properties.md)`Name` und die [Methode](../../methods.md) `ToString` verfügt. Diese Methode [überschreibt](../../language-reference/keywords/override.md) das Verhalten der <xref:System.Object.ToString?displayProperty=nameWithType>-Methode. Der [`public`-Zugriffsmodifizierer](../../language-reference/keywords/public.md) stellt diese Methode jedem Clientcode zur Verfügung, um die Zeichenfolgendarstellung einer `Vegetable`-Instanz abzurufen. Im Beispiel gibt die Methode `Vegetable.ToString` den Wert der Eigenschaft `Name` zurück, die beim [Konstruktor](../../programming-guide/classes-and-structs/constructors.md) `Vegetable` initialisiert wird:

```csharp
public Vegetable(string name) => Name = name;
```

Dann wird eine Instanz der Klasse `Vegetable` mit dem Namen `item` mithilfe des [`new`Operators](../../language-reference/operators/new-operator.md) erstellt und ein Name für den Konstruktor `Vegetable` angegeben:

```csharp
var item = new Vegetable("eggplant");
```

Zum Schluss wird die Variable `item` in eine interpolierte Zeichenfolge einbezogen, die auch einen <xref:System.DateTime>-Wert, <xref:System.Decimal>-Wert und einen [Enumerationswert](../../language-reference/builtin-types/enum.md) `Unit` enthält. Ersetzen Sie sämtlichen C#-Code in Ihrem Editor durch folgenden Code, und verwenden Sie dann den `dotnet run`-Befehl, um diesen auszuführen:

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;

   public string Name { get; }

   public override string ToString() => Name;
}

public class Program
{
   public enum Unit { item, kilogram, gram, dozen };

   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```

Beachten Sie, dass der Interpolationsausdruck `item` der interpolierten Zeichenfolge in der Ergebniszeichenfolge zu dem Text „eggplant“ aufgelöst wird. Dies liegt daran, dass der Ausdruckergebnistyp keine Zeichenfolge ist. Daher wird das Ergebnis auf folgende Weise zu einer Zeichenfolge aufgelöst:

- Wenn der Interpolationsausdruck zu `null` ausgewertet wird, wird eine leere Zeichenfolge („“ oder <xref:System.String.Empty?displayProperty=nameWithType>) verwendet.

- Wenn der Interpolationsausdruck nicht zu `null` ausgewertet wird, wird in der Regel die Methode `ToString` des Ergebnistyps aufgerufen. Sie können dies testen, indem Sie die Implementierung der Methode `Vegetable.ToString` aktualisieren. Sie müssen die Methode `ToString` nicht einmal implementieren, da jeder Typ auf die eine oder andere Art über eine Implementierung dieser Methode verfügt. Sie können dies testen, indem Sie die Definition der Methode `Vegetable.ToString` im Beispiel auskommentieren (fügen Sie hierzu davor ein Kommentarsymbol `//` ein). In der Ausgabe wird die Zeichenfolge „eggplant“ durch den vollqualifizierten Typnamen ersetzt (in diesem Beispiel „Vegetable“). Dies stellt das Standardverhalten der <xref:System.Object.ToString?displayProperty=nameWithType>-Methode dar. Das Standardverhalten der Methode `ToString` für einen Enumerationswert besteht darin, die Zeichenfolgendarstellung eines Werts zurückzugeben.

Bei der Ausgabe dieses Beispielcodes ist das Datum zu genau angegeben (der Preis von Auberginen ändert sich nicht sekündlich), und der Wert der Variablen „price“ gibt keine Währungsinformation an. Im nächsten Abschnitt erfahren Sie, wie Sie diese Probleme beheben, indem Sie das Format der Zeichenfolgendarstellung der Ergebnisse des Ausdrucks steuern.

## <a name="control-the-formatting-of-interpolation-expressions"></a>Steuern der Formatierung von Interpolationsausdrücken

Im vorherigen Abschnitt wurden zwei fehlerhaft formatierte Zeichenfolgen in die Ergebniszeichenfolge eingefügt. Bei einer davon handelte es sich um einen Datums- und Uhrzeitwert, bei dem nur das Datum relevant war. Bei der zweiten handelte es sich um einen Preis, bei dem keine Währungseinheit angegeben wurde. Beide Probleme sind einfach zu beheben. Mithilfe der Zeichenfolgeninterpolation können Sie *Formatzeichenfolgen* angeben, die die Formatierung bestimmter Typen steuern. Ändern Sie den Aufruf von `Console.WriteLine` im vorherigen Beispiel, damit die Formatzeichenfolgen für die Ausdrücke „date“ und „price,“ wie in der folgenden Zeile dargestellt, enthalten sind:

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

Sie können eine Formatzeichenfolge angeben, indem Sie dem Interpolationsausdruck einen Doppelpunkt („:“) und die Formatzeichenfolge anfügen. Bei „d“ handelt es sich um eine [Zeichenfolge für das Standardformat für Datum und Uhrzeit](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier), die das kurze Datumsformat darstellt. Bei „C2“ handelt es sich um eine [Zeichenfolge für das numerische Standardformat](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier), die eine Zahl als Währungswert mit zwei Ziffern nach dem Dezimaltrennzeichen darstellt.

Einige Typen in den .NET-Bibliotheken unterstützen einen vordefinierten Satz von Formatzeichenfolgen. Darin sind alle numerischen Typen sowie alle Datums- und Uhrzeittypen enthalten. Eine vollständige Liste der Typen, die Formatzeichenfolgen unterstützen, finden Sie im Artikel [Formatieren von Typen in .NET](../../../standard/base-types/formatting-types.md) unter [Format Strings and .NET Class Library Types (Formatzeichenfolgen und .NET-Klassenbibliothekstypen)](../../../standard/base-types/formatting-types.md#format-strings-and-net-types).

Versuchen Sie, die Formatzeichenfolgen in Ihrem Text-Editor zu ändern, und führen Sie das Programm jedes Mal erneut aus, wenn Sie eine Änderung vornehmen. So können Sie feststellen, wie sich die Änderungen auf die Formatierung des Datums, der Uhrzeit und des numerischen Werts auswirken. Ändern Sie „d“ in `{date:d}` in „t“ (um das kurze Uhrzeitformat anzuzeigen) sowie in „y“ (um das Jahr und den Monat anzuzeigen) und in „yyyy“ (um das Jahr als vierstellige Zahl anzuzeigen). Ändern Sie „C2“ in `{price:C2}` in „e“ (für die Exponentialschreibweise) und in „F3“ (für einen numerischen Wert mit drei Ziffern nach dem Dezimaltrennzeichen).

Sie können zusätzlich zum Steuern der Formatierung auch die Feldbreite und die Ausrichtung der formatierten Zeichenfolgen steuern, die in der Ergebniszeichenfolge enthalten sind. Im nächsten Abschnitt erfahren Sie mehr zu diesem Thema.

## <a name="control-the-field-width-and-alignment-of-interpolation-expressions"></a>Steuern der Feldbreite und der Ausrichtung von Interpolationsausdrücken

Wenn das Ergebnis eines Interpolationsausdrucks als Zeichenfolge formatiert wird, wird diese Zeichenfolge normalerweise in eine Ergebniszeichenfolge ohne führende oder nachgestellte Leerzeichen einbezogen. Die Feldbreite und Ausrichtung des Texts steuern zu können, ist insbesondere bei der Arbeit mit Daten hilfreich, um eine besser lesbare Ausgabe zu erzeugen. Ersetzen Sie zur Veranschaulichung den gesamten Code in Ihrem Text-Editor durch folgenden Code, und geben Sie dann `dotnet run` ein, um das Programm auszuführen:

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

Die Namen der Autoren sind linksbündig ausgerichtet, während deren Werke rechtsbündig ausgerichtet sind. Sie können die Ausrichtung festlegen, indem Sie einem Interpolationsausdruck ein Komma („,“) anfügen und die *minimale* Feldbreite angeben. Wenn der angegebene Wert eine positive Zahl ist, wird das Feld rechtsbündig ausgerichtet. Wenn er eine negative Zahl ist, wird das Feld linksbündig ausgerichtet.

Versuchen Sie die negativen Vorzeichen aus dem Code `{"Author",-25}` und `{title.Key,-25}` wie im folgenden Code zu entfernen, und führen Sie das Beispiel erneut aus:

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

Diesmal sind die Informationen zum Autor rechtsbündig ausgerichtet.

Sie können einen Ausrichtungsspezifizierer und eine Formatzeichenfolge für einen einzigen Interpolationsausdruck kombinieren. Geben Sie dazu zunächst die Ausrichtung gefolgt von einem Doppelpunkt und der Formatzeichenfolge an. Ersetzen Sie sämtlichen Code innerhalb der `Main`-Methode durch folgenden Code, der drei formatierte Zeichenfolgen mit definierten Feldbreiten anzeigt. Führen Sie das Programm anschließend aus, indem Sie den Befehl `dotnet run` eingeben.

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

Die Ausgabe sieht in etwa folgendermaßen aus:

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

Sie haben da Tutorial für die Zeichenfolgeninterpolation abgeschlossen.

Weitere Informationen finden Sie im Artikel zur [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md) und dem Tutorial [Zeichenfolgeninterpolation in C#](../../tutorials/string-interpolation.md).
