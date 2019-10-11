---
title: Serialisieren und Deserialisieren von JSON mit C# -.net
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3c988a0151f57b67db19f41aeb88c6fb9b808cb3
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179200"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a>Serialisieren und Deserialisieren von JSON in .net

> [!IMPORTANT]
> Die JSON-serialisierungsdokumentation befindet sich in der Konstruktion. In diesem Artikel werden nicht alle Szenarien behandelt. Weitere Informationen finden Sie unter " [System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) "-Probleme im dotnet/corefx-Repository auf GitHub, insbesondere die mit der Bezeichnung " [JSON-funktionsdoc](https://github.com/dotnet/corefx/labels/json-functionality-doc)".

In diesem Artikel wird gezeigt, wie Sie den <xref:System.Text.Json>-Namespace zum Serialisieren und Deserialisieren in und aus JavaScript Object Notation (JSON) verwenden. Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework, wie z. b. [ASP.net Core](/aspnet/core/).

## <a name="namespaces"></a>Namespaces

Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen. Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind. Die in diesem Artikel gezeigten Codebeispiele erfordern daher mindestens eine der folgenden `using`-Direktiven:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden derzeit in `System.Text.Json` nicht unterstützt.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Schreiben von .NET-Objekten in JSON (Serialisieren)

Um JSON in eine Zeichenfolge zu schreiben, nennen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode. Im folgenden Beispiel wird eine-Überladung mit einem generischen Typparameter verwendet:

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

Sie können den generischen Typparameter weglassen und stattdessen einen generischen Typrückschluss verwenden:

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

Hier ist ein Beispieltyp, der serialisiert werden kann, der Auflistungen und Klassen enthält:

```csharp
public class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public IList<DateTimeOffset> DatesAvailable { get; set;}
    public Dictionary<string, HighLowTemperatures> TemperatureRanges { get; set; }
    public string [] SummaryWords { get; set; }
}

public class HighLowTemperatures
{
    public Temperature High { get; set; }
    public Temperature Low { get; set; }
}

public class Temperature
{
    public int DegreesCelsius { get; set; }
}
```

Die JSON-Ausgabe wird standardmäßig minimiert: 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

Im folgenden Beispiel wird derselbe JSON-Code dargestellt, der formatiert ist (d. h. mit Leerraum und Einzug):

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": {
        "DegreesCelsius": 20
      },
      "Low": {
        "DegreesCelsius": -10
      }
    },
    "Hot": {
      "High": {
        "DegreesCelsius": 60
      },
      "Low": {
        "DegreesCelsius": 20
      }
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

Über Ladungen von <xref:System.Text.Json.JsonSerializer.Serialize%2A> können Sie zu einer <xref:System.IO.Stream> serialisieren. Async-Versionen der `Stream`-über Ladungen sind verfügbar.

### <a name="serialize-to-utf-8"></a>In UTF-8 serialisieren

Um zu UTF-8 zu serialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode aufzurufen:

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

Als Alternative steht eine <xref:System.Text.Json.JsonSerializer.Serialize%2A>-Überladung, die eine <xref:System.Text.Json.Utf8JsonWriter> annimmt, zur Verfügung.

Die Serialisierung in UTF-8 ist ungefähr 5-10% schneller als die Verwendung der Zeichen folgen basierten Methoden. Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichen folgen (UTF-16) konvertiert werden müssen.

## <a name="serialization-behavior"></a>Serialisierungsverhalten

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [Eigenschaften angeben, die ausgeschlossen werden sollen](#exclude-properties).
* Der [standardcodierer](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) schützt nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die entsprechend [der JSON-Spezifikation](https://tools.ietf.org/html/rfc8259#section-7)mit Escapezeichen versehen werden müssen.
* Standardmäßig wird JSON minimiert. Sie können [den JSON-Code ziemlich ausdrucken](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen den .net-Namen. Sie können die [JSON-namens](#customize-json-names)Schreibweise anpassen.
* Zirkuläre Verweise werden erkannt, und Ausnahmen werden ausgelöst. Weitere Informationen finden Sie unter dem [Problem für zirkuläre Verweise](https://github.com/dotnet/corefx/issues/38579) im dotnet/corefx-Repository auf GitHub.
* Derzeit werden Felder ausgeschlossen.

Folgende Typen werden unterstützt:

* .Net-primitive, die JavaScript-primitiven zugeordnet sind, z. b. numerische Typen, Zeichen folgen und boolesche Werte.
* Benutzerdefinierte [Plain Old CLR Objects (POCOS)](https://stackoverflow.com/questions/250001/poco-definition).
* Eindimensionales und verzweigte Arrays (`ArrayName[][]`).
* `Dictionary<string,TValue>`, wobei `TValue` `object`, `JsonElement` oder ein poco ist.
* Sammlungen aus den folgenden Namespaces. Weitere Informationen finden Sie im [Thema zur Unterstützung von Sammlungen](https://github.com/dotnet/corefx/issues/36643) im dotnet/corefx-Repository auf GitHub.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Lesen von JSON in .NET-Objekte (Deserialisieren)

Um eine Zeichenfolge zu deserialisieren, nennen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode, wie im folgenden Beispiel gezeigt:

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

Ein Beispiel finden Sie im Abschnitt zum [serialisieren](#how-to-write-net-objects-to-json-serialize) . Das JSON-und .NET-Objekt sind identisch, aber die Richtung ist umgekehrt.

Über Ladungen von <xref:System.Text.Json.JsonSerializer.Deserialize*> können von einem `Stream` deserialisiert werden.  Async-Versionen der `Stream`-über Ladungen sind verfügbar.

### <a name="deserialize-from-utf-8"></a>Aus UTF-8 Deserialisieren

Um von UTF-8 zu deserialisieren, müssen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung aufrufen, die eine `Utf8JsonReader` oder eine `ReadOnlySpan<byte>` annimmt, wie in den folgenden Beispielen gezeigt:

```csharp
byte[] utf8Json;
//...
var readOnlySpan = new ReadOnlySpan<byte>(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
byte[] utf8Json;
//...
var utf8Reader = new Utf8JsonReader(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a>Deserialisierungsverhalten

* Standardmäßig wird die Groß-/Kleinschreibung bei der Übereinstimmung von Eigenschaften Namen Sie können die [Groß-/Kleinschreibung](#case-insensitive-property-matching)nicht beachten.
* Wenn der JSON-Wert einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Die Deserialisierung für Verweis Typen ohne Parameter losen Konstruktor wird nicht unterstützt.
* Die Deserialisierung zu unveränderlichen Objekten oder schreibgeschützten Eigenschaften wird nicht unterstützt. Weitere Informationen finden Sie im GitHub- [Problem bei der Unterstützung für unveränderliche Objekte](https://github.com/dotnet/corefx/issues/38569) und im Repository "dotnet/corefx" auf GitHub Unterstützung für schreibgeschützte [Eigenschaften](https://github.com/dotnet/corefx/issues/38163) .
* Standardmäßig werden Enumerationen als Zahlen unterstützt.
* Felder werden nicht unterstützt.
* Standardmäßig lösen Kommentare oder nachfolgende Kommas in der JSON-Datei Ausnahmen aus. Sie können bei Bedarf [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas) .
* Der Standardwert für die [Maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) ist 64.

## <a name="serialize-to-formatted-json"></a>Serialisieren in formatierten JSON-Code

Um die JSON-Ausgabe zu Recht drucken, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Hier ist ein Beispieltyp, der serialisiert werden soll, und die JSON-Ausgabe:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

## <a name="allow-comments-and-trailing-commas"></a>Kommentare und nachfolgende Kommas zulassen

Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig. Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest. Um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest. Im folgenden Beispiel wird gezeigt, wie Sie beides zulassen:

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

Im folgenden finden Sie ein Beispiel für JSON mit Kommentaren und einem nachfolgenden Komma:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a>Anpassen von JSON-Namen

Standardmäßig sind Eigenschaftsnamen und Wörterbuch Schlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung. In diesem Abschnitt wird Folgendes erläutert:

* Anpassen einzelner Eigenschaftsnamen
* Alle Eigenschaftsnamen in Camel-Case konvertieren
* Implementieren einer benutzerdefinierten Benennungs Richtlinie für Eigenschaften
* Wörterbuch Schlüssel in Kamel-Schreibweise konvertieren

Derzeit gibt es keine Unterstützung für das automatische Umrechnen von aufruten in Kamel Buchstaben. Weitere Informationen finden Sie im Repository "dotnet/corefx" auf GitHub [unter "Problem bei der Unterstützung von Unterstützung](https://github.com/dotnet/corefx/issues/37725) in der Groß-/Kleinschreibung.

### <a name="customize-individual-property-names"></a>Anpassen einzelner Eigenschaftsnamen

Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das [[jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) -Attribut.

Hier ist ein Beispiel für die Serialisierung und die daraus resultierende JSON-Datei:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Der durch dieses Attribut festgelegte Eigenschaftsname:

* Gilt für die Serialisierung und Deserialisierung in beide Richtungen.
* Hat Vorrang vor Eigenschafts Benennungs Richtlinien.

### <a name="use-camel-case-for-all-json-property-names"></a>Bei allen JSON-Eigenschaftsnamen die Kamel-Schreibweise verwenden

Wenn Sie die Kamel-Schreibweise für alle JSON-Eigenschaftsnamen verwenden möchten, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Die Benennungs Richtlinie für die Camel-Case-Eigenschaft:

* Gilt für die Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]`-Attributen überschrieben.

### <a name="use-a-custom-json-property-naming-policy"></a>Verwenden einer benutzerdefinierten JSON-Eigenschafts Benennungs Richtlinie

Um eine benutzerdefinierte JSON-Eigenschafts Benennungs Richtlinie zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und überschreiben Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode, wie im folgenden Beispiel gezeigt:

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihrer Benennungs Richtlinien Klasse fest:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATUREC": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Die Benennungs Richtlinie für die JSON-Eigenschaft:

* Gilt für die Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]`-Attributen überschrieben.

### <a name="camel-case-dictionary-keys"></a>Camel-Case-Wörterbuch Schlüssel

Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die `string`-Schlüssel in die Kamel-Schreibweise konvertiert werden. Legen Sie zu diesem Zweck <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:

|Eigenschaft |Wert  |
|---------|---------|
| date    | 8/1/2019 12:00:00 UHR-07:00|
| Temperatur| 25 |
| Zusammenfassung| Luft|
| Temperatureranges | Kalt, 20<br>Heiß, 40|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "cold": 20,
    "hot": 40
  }
}
```

Die Camel Case Naming-Richtlinie gilt nur für die Serialisierung.

## <a name="exclude-properties"></a>Eigenschaften ausschließen

Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Wenn Sie nicht möchten, dass einige von Ihnen in der JSON-Ausgabe angezeigt werden, haben Sie mehrere Möglichkeiten. In diesem Abschnitt wird erläutert, wie Folgendes ausgeschlossen wird:

* Einzelne Eigenschaften
* Alle schreibgeschützten Eigenschaften
* Alle NULL-Wert-Eigenschaften 

### <a name="exclude-individual-properties"></a>Einzelne Eigenschaften ausschließen

Verwenden Sie das Attribut [[jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) , um einzelne Eigenschaften zu ignorieren.

Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonIgnore]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

### <a name="exclude-all-read-only-properties"></a>Alle schreibgeschützten Eigenschaften ausschließen

Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest, wie im folgenden Beispiel gezeigt:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public int WindSpeed { get; private set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

Diese Option gilt nur für die Serialisierung. Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert. Eine Eigenschaft ist schreibgeschützt, wenn Sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.

### <a name="exclude-all-null-value-properties"></a>Alle NULL-Wert Eigenschaften ausschließen

Um alle NULL-Wert Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:

|Eigenschaft |Wert  |
|---------|---------|
| date    | 8/1/2019 12:00:00 UHR-07:00|
| Temperatur| 25 |
| Zusammenfassung| NULL|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

Diese Einstellung gilt für die Serialisierung und Deserialisierung. Während der Deserialisierung werden NULL-Werte in JSON nur ignoriert, wenn Sie gültig sind. NULL-Werte für Werttypen, die keine NULL-Werte zulassen, verursachen Ausnahmen. Weitere Informationen finden Sie im Repository dotnet/corefx auf GitHub unter dem [Problem für Werttypen, die keine NULL-Werte](https://github.com/dotnet/corefx/issues/40922) zulassen.

## <a name="case-insensitive-property-matching"></a>Nichtbeachtung der Groß-/Kleinschreibung

Standardmäßig wird bei der Deserialisierung nach Groß-/Kleinschreibung unterschieden, dass Eigenschaften Namen Übereinstimmungen zwischen JSON und den Zielobjekt Eigenschaften aufweisen. Um dieses Verhalten zu ändern, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

Im folgenden finden Sie eine Beispiel-JSON-Datei mit den Namen der Kamel Sie kann in den folgenden Typ deserialisiert werden, der über die Namen der Pascal-Großbuchstaben verfügt.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
}
```

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="include-properties-of-derived-classes"></a>Einschließen von Eigenschaften abgeleiteter Klassen

Die polymorphe Serialisierung wird nicht unterstützt, wenn Sie zum Zeitpunkt der Kompilierung angeben, welcher Typ serialisiert werden soll. Nehmen Sie beispielsweise an, Sie verfügen über eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastWithWind`:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
class WeatherForecastWithWind : WeatherForecast
{
    public int WindSpeed { get; set; }
}
```

Und nehmen wir an, dass der Typ, der zur Kompilierzeit an die `Serialize`-Methode geleitet oder von diesem abgeleitet wurde, `WeatherForecast` ist:

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastWithWind`-Objekt ist. Es werden nur die Basisklassen Eigenschaften serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

Dieses Verhalten soll das versehentliche verfügbar machen von Daten in einem abgeleiteten, von der Laufzeit erstellten Typ verhindern.

Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs zu serialisieren:

* Aufrufen einer Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A>, mit der Sie den Typ zur Laufzeit angeben können:

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* Deklarieren Sie das zu serialisierende Objekt als `object`.

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

Im vorangehenden Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in der JSON-Ausgabe enthalten ist:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a>Handle für Überlauf-JSON

Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, der nicht durch Eigenschaften des Zieltyps dargestellt wird. Angenommen, Ihr Zieltyp lautet:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

Der JSON-Code, der deserialisiert werden soll, lautet wie folgt:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

Wenn Sie den JSON-Code deserialisieren, der in den angezeigten Typ angezeigt wird, sind die Eigenschaften "`DatesAvailable`" und "`SummaryWords`" nicht mehr vorhanden und gehen verloren. Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) -Attribut auf eine Eigenschaft vom Typ `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonExtensionData]
    public Dictionary<string, object> ExtensionData { get; set; }
}
```

Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:

|Eigenschaft |Wert  |Hinweise  |
|---------|---------|---------|
| date    | 8/1/2019 12:00:00 UHR-07:00||
| Temperatur| 0 | Unterscheidung nach Groß-/Kleinschreibung (`temperatureC` im JSON-Code), sodass die-Eigenschaft nicht festgelegt ist. |
| Zusammenfassung | Luft ||
| ExtensionData | Temperatur: 25 |Da die Groß-/Kleinschreibung nicht entsprach, ist diese JSON-Eigenschaft ein zusätzliches und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.|
|| Datesavailable:<br>  8/1/2019 12:00:00 UHR-07:00<br>8/2/2019 12:00:00 UHR-07:00 |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|
| |Summarywords:<br>Toll<br>Digen<br>Feu |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|

Wenn das Zielobjekt serialisiert wird, werden die Erweiterungs-Datenschlüssel Wert-Paare zu JSON-Eigenschaften, genauso wie Sie im eingehenden JSON-Code waren:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 0,
  "Summary": "Hot",
  "temperatureC": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code angezeigt wird. Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert werden.

## <a name="use-utf8jsonwriter-directly"></a>Verwenden Sie Utf8JsonWriter direkt.

Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.Utf8JsonWriter>-Klasse direkt verwenden.

```csharp
var options = new JsonWriterOptions
{
    Indented = true
};

using (var stream = new MemoryStream())
{
    using (var writer = new Utf8JsonWriter(stream, options))
    {
        writer.WriteStartObject();
        writer.WriteString("date", DateTimeOffset.UtcNow);
        writer.WriteNumber("temp", 42);
        writer.WriteEndObject();
    }

    string json = Encoding.UTF8.GetString(stream.ToArray());
    Console.WriteLine(json);
}
```

## <a name="use-utf8jsonreader-directly"></a>Verwenden Sie Utf8JsonReader direkt.

Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.Utf8JsonReader>-Klasse direkt verwenden. Der Code geht davon aus, dass die `jsonUtf8`-Variable ein Bytearray ist, das gültige JSON-codierte JSON-Codierung enthält.

```csharp
var options = new JsonReaderOptions
{
    AllowTrailingCommas = true,
    CommentHandling = JsonCommentHandling.Skip
};
Utf8JsonReader reader = new Utf8JsonReader(jsonUtf8, options);

while (reader.Read())
{
    Console.Write(reader.TokenType);

    switch (reader.TokenType)
    {
        case JsonTokenType.PropertyName:
        case JsonTokenType.String:
            {
                string text = reader.GetString();
                Console.Write(" ");
                Console.Write(text);
                break;
            }

        case JsonTokenType.Number:
            {
                int value = reader.GetInt32();
                Console.Write(" ");
                Console.Write(value);
                break;
            }

            // Other token types elided for brevity
    }

    Console.WriteLine();
}
```

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Übersicht über System. Text. JSON](system-text-json-overview.md)
* [System. Text. JSON-API-Referenz](xref:System.Text.Json)
* [DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON](../datetime/system-text-json-support.md)
