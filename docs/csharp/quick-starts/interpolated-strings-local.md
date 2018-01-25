---
title: 'Schnellstart: Interpolierte Zeichenfolgen (C#-Handbuch)'
description: "In diesem Schnellstart über interpolierte Zeichenfolgen schreiben Sie C#-Code, um das Ergebnis eines Ausdrucks in eine größere Zeichenfolge einzufügen."
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 14185dd4e364f12756541ac6401d1c6ff3206fe9
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2018
---
# <a name="interpolated-strings"></a>Interpolierte Zeichenfolgen

In diesem Schnellstart wird erläutert, wie Sie interpolierte Zeichenfolgen in C# verwenden können, um Werte in eine einzige Ausgabezeichenfolge einzufügen. Sie schreiben einen C#-Code und sehen dort die Ergebnisse der Kompilierung und Ausführung Ihres Codes. In diesem Schnellstart sind einige Lektionen enthalten, bei denen Werte in Zeichenfolgen eingefügt und auf verschiedene Arten formatiert werden.

Für diesen Schnellstart wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können. Das .NET-Thema [Erste Schritte in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten Ihrer lokalen Entwicklungsumgebung auf einem Mac-, Windows- oder Linux-PC. Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie in den [Schnellstarts mit der Einführung zu lokalen Umgebungen](local-environment.md), die Links mit weiteren Einzelheiten enthalten. 

## <a name="create-an-interpolated-string"></a>Erstellen einer interpolierten Zeichenfolge

Erstellen Sie ein Verzeichnis namens **interpolated-quickstart**. Legen Sie dieses als das aktuelle Verzeichnis fest, und führen Sie folgenden Befehl in einem Konsolenfenster aus:

```console
dotnet new console -n interpolated -o .
```

Dieser Befehl erstellt im aktuellen Verzeichnis eine neue .NET Core-Konsolenanwendung.

Öffnen Sie **Program.cs** in Ihrem bevorzugten Editor, und ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code, in dem Sie `<name>` durch Ihren Namen ersetzen:

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
Testen Sie diesen Code, indem Sie `dotnet run` in Ihr Konsolenfenster eingeben. Wenn Sie das Programm ausführen, wird eine einzelne Zeichenfolge angezeigt, die Ihren Namen in der Begrüßung enthält. Die Zeichenfolge, die in den <xref:System.Console.WriteLine%2A>-Methodenaufruf eingefügt wird, ist eine *interpolierte Zeichenfolge*. Dabei handelt es sich um eine Vorlage, durch die Sie eine einzelne Zeichenfolge (als *Ergebniszeichenfolge* bezeichnet) aus einer Zeichenfolge erstellen können, die eingebetteten Code enthält. Interpolierte Zeichenfolgen sind besonders nützlich für das Einfügen von Werten in eine Zeichenfolge oder zum Verketten (bzw. Verknüpfen) von Zeichenfolgen. 
    
Dieses einfache Beispiel enthält die zwei Elemente, über die jede interpolierte Zeichenfolge verfügen muss: 

- Ein Zeichenfolgenliteral, das ein `$`-Zeichen vor dem öffnenden Anführungszeichen enthält. Zwischen dem `$`-Symbol und dem Anführungszeichen darf kein Leerraum vorhanden sein. (Wenn Sie testen möchten, was andernfalls geschieht, fügen Sie einen Leerraum nach dem `$`-Zeichen ein, speichern Sie die Datei, und führen Sie das Programm erneut aus, indem Sie `dotnet run` im Konsolenfenster eingeben. Der C#-Compiler zeigt dann die Fehlermeldung „Fehler CS1056: Unerwartetes Zeichen ‚$‘.“ an.) 

- Mindestens ein *interpolierter Ausdruck*. Ein interpolierter Ausdruck wird durch eine öffnende und eine schließende Klammer (`{` und `}`) angegeben. Sie können jeden C#-Ausdruck in die Klammern einfügen, der einen Wert (einschließlich `null`) zurückgibt. 

Im Folgenden finden Sie weitere Beispiele für interpolierte Zeichenfolgen mit anderen Datentypen.
    
## <a name="include-different-data-types"></a>Einschließen verschiedener Datentypen

Im vorherigen Abschnitt haben Sie eine interpolierte Zeichenfolge verwendet, um eine Zeichenfolge in eine andere einzufügen. Ein interpolierter Zeichenfolgenausdruck kann jedoch jeden Datentyp aufweisen. Im Folgenden wird eine interpolierte Zeichenfolge dargestellt, die Werte mehrerer Datentypen enthält. 
    
Im folgenden Beispiel sind interpolierte Ausdrücke enthalten, die über ein `Vegetable`-Objekt, einen Member der `Unit`-Enumeration, einen <xref:System.DateTime>-Wert und einen <xref:System.Decimal>-Wert verfügen. Ersetzen Sie sämtlichen C#-Code in Ihrem Editor durch folgenden Code, und verwenden Sie dann den `console run`-Befehl, um diesen auszuführen:

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Example
{
   public enum Unit { item, pound, ounce, dozen };
   
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
    
Beachten Sie, dass der zweite interpolierte Ausdruck das `item`-Objekt in der Ergebniszeichenfolge enthält, die in der Konsole angezeigt wird. In diesem Fall wird die Zeichenfolge „eggplant“ in die Ergebniszeichenfolge eingefügt. Dies liegt daran, dass der C#-Compiler Folgendes durchführt, wenn der Typ eines interpolierten Ausdrucks keine Zeichenfolge ist:

- Wenn der interpolierte Ausdruck `null` ist, gibt dieser eine leere Zeichenfolge ("" oder <xref:System.String.Empty?displayProperty=nameWithType>) zurück.

- Wenn der interpolierte Ausdruck nicht `null` ist, wird die `ToString`-Methode des Typs des interpolierten Ausdrucks aufgerufen. Sie können dies testen, indem Sie die Definition der `Vegetable.ToString`-Methode im Beispiel auskommentieren, indem Sie ein Kommentarsymbol (`//`) davor einfügen. In der Ausgabe wird die Zeichenfolge „eggplant“ durch den Typnamen „Vegetable“ ersetzt. Dies stellt das Standardverhalten der <xref:System.Object.ToString?displayProperty=nameWithType>-Methode dar.   

Bei der Ausgabe dieses Beispielcodes ist das Datum zu genau angegeben (der Preis von Auberginen ändert sich nicht sekündlich), und der Wert der Variablen „price“ gibt keine Währungsinformation an. Im nächsten Abschnitt erfahren Sie, wie Sie diese Probleme beheben, indem Sie das Format der Zeichenfolgen steuern, die von interpolierten Ausdrücken zurückgegeben werden.

## <a name="control-the-formatting-of-interpolated-expressions"></a>Steuern der Formatierung von interpolierten Ausdrücken

Im vorherigen Abschnitt wurden zwei fehlerhaft formatierte Zeichenfolgen in die Ergebniszeichenfolge eingefügt. Bei einer davon handelte es sich um einen Datums- und Uhrzeitwert, bei dem nur das Datum relevant war. Bei der zweiten handelte es sich um einen Preis, bei dem keine Währungseinheit angegeben wurde. Beide Probleme sind einfach zu beheben. Interpolierte Ausdrücke können *Formatzeichenfolgen* enthalten, die die Formatierung von bestimmten Typen steuern. Ändern Sie den Aufruf von `Console.WriteLine` im vorherigen Beispiel, damit der Formatbezeichner für die Felder „date“ und „price“ wie in der folgenden Zeile dargestellt enthalten ist:

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
Sie können eine Formatzeichenfolge angeben, indem Sie dem interpolierten Ausdruck einen Doppelpunkt und die Formatzeichenfolge anfügen. Bei „d“ handelt es sich um eine [Zeichenfolge für das Standardformat für Datum und Uhrzeit](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier), die das kurze Datumsformat darstellt. Bei „C2“ handelt es sich um eine [Zeichenfolge für das numerische Standardformat](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier), die eine Zahl als Währungswert mit zwei Ziffern nach dem Dezimaltrennzeichen darstellt.

Einige Typen in den .NET Standard-Bibliotheken unterstützen einen vordefinierten Satz von Formatzeichenfolgen. Darin sind alle numerischen Typen sowie alle Datums- und Uhrzeittypen enthalten. Eine vollständige Liste der Typen, die Formatzeichenfolgen unterstützen, finden Sie im Artikel [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) unter [Format Strings and .NET Class Library Types (Formatzeichenfolgen und .NET-Klassenbibliothekstypen)](../../standard/base-types/formatting-types.md#stringRef). Jeder dieser Typen kann bestimmte Formatzeichenfolgen unterstützen. Sie können jedoch ebenfalls benutzerdefinierte Formatierungserweiterungen entwickeln, um benutzerdefinierte Formatierungen für vorhandene Typen bereitzustellen. Weitere Informationen zur benutzerdefinierten Formatierung durch die Bereitstellung einer <xref:System.ICustomFormatter>-Implementierung finden Sie im Artikel [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) unter [Benutzerdefinierte Formatierung mit ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).

Versuchen Sie, die Formatzeichenfolgen in Ihrem Text-Editor zu ändern, und führen Sie das Programm jedes Mal erneut aus, wenn Sie eine Änderung vornehmen. So können Sie feststellen, wie sich die Änderungen auf die Formatierung des Datums, der Uhrzeit und des numerischen Werts auswirken. Ändern Sie „d“ in `{date:d}` in „t“ (um das kurze Uhrzeitformat anzuzeigen) sowie in „y“ (um das Jahr und den Monat anzuzeigen) und in „yyyy“ (um das Jahr als vierstellige Zahl anzuzeigen). Ändern Sie „C2“ in `{price:C2}` in „e“ (für die Exponentialschreibweise) und in „F3“ (für einen numerischen Wert mit drei Ziffern nach dem Dezimaltrennzeichen).

Sie können zusätzlich zum Steuern der Formatierung auch die Feldbreite und die Ausrichtung der Zeichenfolgen steuern, die von einem interpolierten Ausdruck zurückgegeben werden. Im nächsten Abschnitt erfahren Sie mehr zu diesem Thema.

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a>Steuern der Feldbreite und der Ausrichtung von interpolierten Ausdrücken

Wenn die von einem interpolierten Ausdruck zurückgegebene Zeichenfolge in eine Ergebniszeichenfolge eingefügt wird, enthält diese normalerweise keine führenden oder nachgestellten Leerräume. Insbesondere bei Instanzen, bei denen Sie mit einem Datensatz arbeiten, können Sie durch interpolierte Ausdrücke die Breite und Ausrichtung eines Felds angeben. Ersetzen Sie zur Veranschaulichung den gesamten Code in Ihrem Text-Editor durch folgenden Code, und geben Sie dann `console run` ein, um das Programm auszuführen:
    
```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>();
      titles.Add("Doyle, Arthur Conan", "Hound of the Baskervilles, The");
      titles.Add("London, Jack", "Call of the Wild, The");
      titles.Add("Shakespeare, William", "Tempest, The");

      Console.WriteLine("Author and Title List");
      Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
      foreach (var title in titles)
         Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
   }
}
```
    
Die Namen der Autoren sind linksbündig ausgerichtet, während deren Werke rechtsbündig ausgerichtet sind. Sie können die Ausrichtung festlegen, indem Sie dem Ausdruck ein Komma („,“) anfügen und die Feldbreite angeben. Wenn Sie eine positive Zahl für die Feldbreite eingeben, wird das Feld rechtsbündig ausgerichtet:

```text
{expression, width}
```

Wenn Sie eine negative Zahl für die Feldbreite eingeben, wird das Feld linksbündig ausgerichtet:

```text
{expression, -width}
```

Entfernen Sie die negativen Vorzeichen der interpolierten Ausdrücke `{"Author",-25}` und `{title.Key,-25}`, und führen Sie das Beispiel erneut aus.

```csharp
Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
```

Diesmal sind die Informationen zum Autor rechtsbündig ausgerichtet.

Sie können eine Feldbreite und eine Formatzeichenfolge in einem einzigen interpolierten Ausdruck kombinieren. Die Feldbreite wird zuerst angegeben, gefolgt von einem Doppelpunkt und der Formatzeichenfolge. Ersetzen Sie sämtlichen Code innerhalb der `Main`-Methode durch folgenden Code, der drei formatierte Zeichenfolgen mit definierten Feldbreiten anzeigt. Führen Sie das Programm anschließend aus, indem Sie den Befehl `dotnet run` eingeben.

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
Die Ausgabe sieht in etwa folgendermaßen aus:

```console
1/11/2018            Hour 09                1,063.34 feet
```

Sie haben den Schnellstart für interpolierte Zeichenfolgen abgeschlossen. 
    
Sie können mit dem Schnellstart [Arrays und Sammlungen](arrays-and-collections.md) in Ihrer eigenen Entwicklungsumgebung fortfahren.

Weitere Informationen zum Arbeiten mit interpolierten Zeichenfolgen finden Sie im Artikel [Interpolierte Zeichenfolgen](../language-reference/keywords/interpolated-strings.md) in der C#-Referenz.

