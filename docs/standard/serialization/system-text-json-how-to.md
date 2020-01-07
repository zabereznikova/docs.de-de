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
ms.openlocfilehash: 32c78cc48dcd3d9f2c6e1d338bdbdd359f69879f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344505"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a>Serialisieren und Deserialisieren von JSON in .net

In diesem Artikel wird gezeigt, wie Sie den <xref:System.Text.Json>-Namespace zum Serialisieren und Deserialisieren in und aus JavaScript Object Notation (JSON) verwenden.

Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework, wie z. b. [ASP.net Core](/aspnet/core/).

Der größte Teil des serialisierungsbeispielcodes legt <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> fest, um die JSON-Datei zu `true` (mit einzügkeit und Leerraum für die Lesbarkeit des Menschen). Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.

## <a name="namespaces"></a>-Namespaces

Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen. Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind. Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Direktiven für einen oder beide Namespaces:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden derzeit in `System.Text.Json`nicht unterstützt.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Schreiben von .NET-Objekten in JSON (Serialisieren)

Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, müssen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode aufzurufen.

Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

In den vorangehenden Beispielen wird der Typrückschluss für den serialisierten Typ verwendet. Eine Überladung von `Serialize()` nimmt einen generischen Typparameter an:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Beispiel für die Serialisierung

Im folgenden finden Sie eine Beispiel Klasse, die Auflistungen und eine-Klasse enthält:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus. Die JSON-Ausgabe wird standardmäßig minimiert: 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

Im folgenden Beispiel wird derselbe JSON-Code dargestellt, der formatiert ist (d. h. mit Leerraum und Einzug):

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a>In UTF-8 serialisieren

Um zu UTF-8 zu serialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode aufzurufen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A> Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> annimmt, ist ebenfalls verfügbar.

Die Serialisierung in UTF-8 ist ungefähr 5-10% schneller als die Verwendung der Zeichen folgen basierten Methoden. Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichen folgen (UTF-16) konvertiert werden müssen.

## <a name="serialization-behavior"></a>Serialisierungsverhalten

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [Eigenschaften angeben, die ausgeschlossen werden sollen](#exclude-properties-from-serialization).
* Der [Standard Encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) schützt nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [der RFC 8259 JSON-Spezifikation](https://tools.ietf.org/html/rfc8259#section-7)mit Escapezeichen versehen werden müssen.
* Standardmäßig wird JSON minimiert. Sie können [den JSON-Code ziemlich ausdrucken](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen den .net-Namen. Sie können die [JSON-namens](#customize-json-names-and-values)Schreibweise anpassen.
* Zirkuläre Verweise werden erkannt, und Ausnahmen werden ausgelöst. Weitere Informationen finden Sie unter [Issue 38579 on Zirkel References](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx Repository auf GitHub.
* Derzeit werden Felder ausgeschlossen.

Folgende Typen werden unterstützt:

* .Net-primitive, die JavaScript-primitiven zugeordnet sind, z. b. numerische Typen, Zeichen folgen und boolesche Werte.
* Benutzerdefinierte [Plain Old CLR Objects (POCOS)](https://stackoverflow.com/questions/250001/poco-definition).
* Eindimensionales und verzweigte Arrays (`ArrayName[][]`).
* `Dictionary<string,TValue>`, wo `TValue` `object`, `JsonElement`oder poco ist.
* Sammlungen aus den folgenden Namespaces. Weitere Informationen finden Sie im [Thema zur Unterstützung von Sammlungen](https://github.com/dotnet/corefx/issues/36643) im dotnet/corefx-Repository auf GitHub.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md) , um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Lesen von JSON in .NET-Objekte (Deserialisieren)

Um eine Zeichenfolge oder eine Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode aufzurufen.

Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecast`-Klasse erstellt, die zuvor für das [serialisierungsbeispiel](#serialization-example)gezeigt wurde:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Wenn Sie aus einer Datei mithilfe von synchronem Code deserialisieren möchten, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode abrufen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Aus UTF-8 Deserialisieren

Um von UTF-8 zu deserialisieren, müssen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> Überladung aufrufen, die eine `Utf8JsonReader` oder eine `ReadOnlySpan<byte>`annimmt, wie in den folgenden Beispielen gezeigt. In den Beispielen wird davon ausgegangen, dass sich die JSON in einem Bytearray namens jsonUtf8Bytes

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Deserialisierungsverhalten

* Standardmäßig wird die Groß-/Kleinschreibung bei der Übereinstimmung von Eigenschaften Namen Sie können die [Groß-/Kleinschreibung](#case-insensitive-property-matching)nicht beachten.
* Wenn der JSON-Wert einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Die Deserialisierung für Verweis Typen ohne Parameter losen Konstruktor wird nicht unterstützt.
* Die Deserialisierung zu unveränderlichen Objekten oder schreibgeschützten Eigenschaften wird nicht unterstützt. Weitere Informationen finden Sie unter GitHub- [Problem 38569 bei der Unterstützung für unveränderliche Objekte](https://github.com/dotnet/corefx/issues/38569) und [Problem 38163 bei der Unterstützung](https://github.com/dotnet/corefx/issues/38163) für schreibgeschützte Eigenschaften im dotnet/corefx-Repository auf GitHub.
* Standardmäßig werden Enumerationen als Zahlen unterstützt. Enumerationsnamen können als Zeichen folgen [serialisiert](#enums-as-strings)werden.
* Felder werden nicht unterstützt.
* Standardmäßig lösen Kommentare oder nachfolgende Kommas in der JSON-Datei Ausnahmen aus. Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).
* Der Standardwert für die [Maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) ist 64.

Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md) , um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="serialize-to-formatted-json"></a>Serialisieren in formatierten JSON-Code

Um die JSON-Ausgabe zu Recht drucken, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true`fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

Hier ist ein Beispieltyp, der serialisiert und eine ziemlich gedruckte JSON-Ausgabe ist:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>Anpassen von JSON-Namen und-Werten

Standardmäßig sind Eigenschaftsnamen und Wörterbuch Schlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung. Enumerationswerte werden als Zahlen dargestellt. In diesem Abschnitt wird Folgendes beschrieben:

* [Anpassen einzelner Eigenschaftsnamen](#customize-individual-property-names)
* [Alle Eigenschaftsnamen in Camel-Case konvertieren](#use-camel-case-for-all-json-property-names)
* [Implementieren einer benutzerdefinierten Benennungs Richtlinie für Eigenschaften](#use-a-custom-json-property-naming-policy)
* [Wörterbuch Schlüssel in Kamel-Schreibweise konvertieren](#camel-case-dictionary-keys)
* [Enumerationszeichen in Zeichen folgen und Camel-Case konvertieren](#enums-as-strings) 

Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und-Werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Anpassen einzelner Eigenschaftsnamen

Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das [[jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) -Attribut.

Hier ist ein Beispiel für die Serialisierung und die daraus resultierende JSON-Datei:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Der durch dieses Attribut festgelegte Eigenschaftsname:

* Gilt für die Serialisierung und Deserialisierung in beide Richtungen.
* Hat Vorrang vor Eigenschafts Benennungs Richtlinien.

### <a name="use-camel-case-for-all-json-property-names"></a>Bei allen JSON-Eigenschaftsnamen die Kamel-Schreibweise verwenden

Wenn Sie die Kamel-Schreibweise für alle JSON-Eigenschaftsnamen verwenden möchten, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Die Benennungs Richtlinie für die Camel-Case-Eigenschaft:

* Gilt für die Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]` Attributen überschrieben. Aus diesem Grund ist der Name der JSON-Eigenschaft `Wind` im Beispiel nicht Camel Case.

### <a name="use-a-custom-json-property-naming-policy"></a>Verwenden einer benutzerdefinierten JSON-Eigenschafts Benennungs Richtlinie

Um eine benutzerdefinierte JSON-Benennungs Richtlinie zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und überschreiben Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihrer Benennungs Richtlinien Klasse fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Die Benennungs Richtlinie für die JSON-Eigenschaft:

* Gilt für die Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]` Attributen überschrieben. Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht Großbuchstaben.

### <a name="camel-case-dictionary-keys"></a>Camel-Case-Wörterbuch Schlüssel

Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>`ist, können die `string` Schlüssel in die Kamel-Schreibweise konvertiert werden. Legen Sie zu diesem Zweck <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

Das Serialisieren eines Objekts mit einem Wörterbuch mit dem Namen `TemperatureRanges`, das Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` hat, führt zu einer JSON-Ausgabe wie im folgenden Beispiel:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

Die Camel-Case-Benennungs Richtlinie für Wörterbuch Schlüssel gilt nur für die Serialisierung. Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei, auch wenn Sie `JsonNamingPolicy.CamelCase` für die `DictionaryKeyPolicy`angeben.

### <a name="enums-as-strings"></a>Enumerationszeichen als Zeichen folgen

Standardmäßig werden Enumerationen als Zahlen serialisiert. Verwenden Sie die <xref:System.Text.Json.Serialization.JsonStringEnumConverter>, um Enumerationsnamen als Zeichen folgen zu serialisieren.

Nehmen Sie beispielsweise an, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Wenn die Zusammenfassung `Hot`ist, hat die serialisierte JSON standardmäßig den numerischen Wert 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Kamel-Schreibweise:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

Der resultierende JSON-Code sieht wie im folgenden Beispiel aus:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Enum-Zeichen folgen Namen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Ausschließen von Eigenschaften von der Serialisierung

Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Wenn Sie nicht möchten, dass einige von Ihnen in der JSON-Ausgabe angezeigt werden, haben Sie mehrere Möglichkeiten. In diesem Abschnitt wird erläutert, wie Folgendes ausgeschlossen wird:

* [Einzelne Eigenschaften](#exclude-individual-properties)
* [Alle schreibgeschützten Eigenschaften](#exclude-all-read-only-properties)
* [Alle NULL-Wert-Eigenschaften](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>Einzelne Eigenschaften ausschließen

Verwenden Sie das Attribut [[jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) , um einzelne Eigenschaften zu ignorieren.

Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>Alle schreibgeschützten Eigenschaften ausschließen

Eine Eigenschaft ist schreibgeschützt, wenn Sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält. Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Diese Option gilt nur für die Serialisierung. Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.

### <a name="exclude-all-null-value-properties"></a>Alle NULL-Wert Eigenschaften ausschließen

Um alle NULL-Wert Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:

|Die Eigenschaften- |{2&gt;Wert&lt;2}  |
|---------|---------|
| Datum    | 8/1/2019 12:00:00 Uhr-07:00|
| TemperatureCelsius| 25 |
| Summary| NULL|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

Diese Einstellung gilt für die Serialisierung und Deserialisierung. Informationen zu den Auswirkungen auf die Deserialisierung finden Sie unter [Ignorieren von NULL beim Deserialisieren](#ignore-null-when-deserializing).

## <a name="customize-character-encoding"></a>Zeichencodierung anpassen

Standardmäßig schützt das Serialisierungsprogramm alle nicht-ASCII-Zeichen.  Das heißt, Sie ersetzt Sie durch `\uxxxx`, wobei `xxxx` der Unicode-Code des Zeichens ist.  Wenn die `Summary`-Eigenschaft z. b. auf Cyrillic-"-Eigenschaft" festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Serialisieren von sprach Zeichensätzen

Wenn Sie die Zeichensätze mindestens einer Sprache ohne Escapezeichen serialisieren möchten, müssen Sie beim Erstellen einer Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>[Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) angeben, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Mit diesem Code werden keine kyrillischen oder griechischen Zeichen entfernt. Wenn die `Summary`-Eigenschaft auf Cyrillic--,-festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>, um alle sprach Sätze ohne Escapezeichen zu serialisieren.

### <a name="serialize-specific-characters"></a>Serialisieren bestimmter Zeichen

Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne mit Escapezeichen versehen zu werden. Im folgenden Beispiel werden nur die ersten zwei Zeichen von "..." serialisiert:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Im folgenden finden Sie ein Beispiel für JSON, das durch den vorangehenden Code generiert wird:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Alle Zeichen serialisieren

Um das Escapezeichen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>verwenden, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> Im Vergleich zum Standard-Encoder ist der `UnsafeRelaxedJsonEscaping` Encoder eher für das Zulassen von Zeichen ohne Escapezeichen zulässig:
>
> * Es werden keine HTML-sensiblen Zeichen wie `<`, `>`, `&`und `'`mit Escapezeichen versehen.
> * Er bietet keine zusätzlichen Schutzmaßnahmen vor XSS-oder Informations Offenlegungs Angriffen, wie z. b. solche, die sich aus dem Client und dem Server ergeben könnten, die auf dem *CharSet*nicht einverstanden sind.
>
> Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretiert. Sie können Sie beispielsweise verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8`sendet. Gestatten Sie niemals, dass die Roh`UnsafeRelaxedJsonEscaping` Ausgabe in eine HTML-Seite oder ein `<script>` Element ausgegeben wird.

## <a name="serialize-properties-of-derived-classes"></a>Serialisieren von Eigenschaften abgeleiteter Klassen

Die polymorphe Serialisierung wird nicht unterstützt, wenn Sie zum Zeitpunkt der Kompilierung angeben, welcher Typ serialisiert werden soll. Nehmen Sie beispielsweise an, Sie verfügen über eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

Angenommen, das Typargument der `Serialize` Methode zum Zeitpunkt der Kompilierung ist `WeatherForecast`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist. Es werden nur die Basisklassen Eigenschaften serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Dieses Verhalten soll das versehentliche verfügbar machen von Daten in einem abgeleiteten, von der Laufzeit erstellten Typ verhindern.

Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs zu serialisieren:

* Aufrufen einer Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A>, mit der Sie den Typ zur Laufzeit angeben können:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Deklarieren Sie das Objekt, das als `object`serialisiert werden soll.

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in der JSON-Ausgabe enthalten ist:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

Weitere Informationen zur polymorphen Deserialisierung finden Sie [unter Unterstützung der polymorphen Deserialisierung](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

## <a name="allow-comments-and-trailing-commas"></a>Kommentare und nachfolgende Kommas zulassen

Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig. Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip`fest.
Um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true`fest. Im folgenden Beispiel wird gezeigt, wie Sie beides zulassen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Im folgenden finden Sie ein Beispiel für JSON mit Kommentaren und einem nachfolgenden Komma:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Nichtbeachtung der Groß-/Kleinschreibung

Standardmäßig wird bei der Deserialisierung nach Groß-/Kleinschreibung unterschieden, dass Eigenschaften Namen Übereinstimmungen zwischen JSON und den Zielobjekt Eigenschaften aufweisen. Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true`fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Im folgenden finden Sie eine Beispiel-JSON-Datei mit den Namen der Kamel Sie kann in den folgenden Typ deserialisiert werden, der über die Namen der Pascal-Großbuchstaben verfügt.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>Handle für Überlauf-JSON

Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, der nicht durch Eigenschaften des Zieltyps dargestellt wird. Angenommen, Ihr Zieltyp lautet:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Der JSON-Code, der deserialisiert werden soll, lautet wie folgt:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
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

Wenn Sie den JSON-Code deserialisieren, der in den angezeigten Typ angezeigt wird, sind die Eigenschaften `DatesAvailable` und `SummaryWords` nicht mehr vorhanden und gehen verloren. Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) -Attribut auf eine Eigenschaft vom Typ `Dictionary<string,object>` oder `Dictionary<string,JsonElement>`an:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:

|Die Eigenschaften- |{2&gt;Wert&lt;2}  |Hinweise  |
|---------|---------|---------|
| Datum    | 8/1/2019 12:00:00 Uhr-07:00||
| TemperatureCelsius| 0 | Unterscheidung nach Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die-Eigenschaft nicht festgelegt ist. |
| Summary | Hohe Auslastung ||
| ExtensionData | TemperatureCelsius: 25 |Da die Groß-/Kleinschreibung nicht entsprach, ist diese JSON-Eigenschaft ein zusätzliches und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.|
|| Datesavailable:<br>  8/1/2019 12:00:00 Uhr-07:00<br>8/2/2019 12:00:00 Uhr-07:00 |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|
| |Summarywords:<br>Toll<br>Windig<br>Feu |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|

Wenn das Zielobjekt serialisiert wird, werden die Erweiterungs-Datenschlüssel Wert-Paare zu JSON-Eigenschaften, genauso wie Sie im eingehenden JSON-Code waren:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
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

## <a name="ignore-null-when-deserializing"></a>NULL beim Deserialisieren ignorieren

Wenn eine Eigenschaft in JSON NULL ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf NULL festgelegt. In einigen Szenarios hat die Ziel Eigenschaft möglicherweise einen Standardwert, und Sie möchten nicht, dass ein NULL-Wert den Standardwert überschreibt.

Nehmen Sie beispielsweise an, der folgende Code stellt das Zielobjekt dar:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Angenommen, der folgende JSON-Code wird deserialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Nach der Deserialisierung ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts NULL.

Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

Bei dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault` Objekts der Standardwert "keine Zusammenfassung" nach der Deserialisierung.

NULL-Werte in JSON werden nur ignoriert, wenn Sie gültig sind. NULL-Werte für Werttypen, die keine NULL-Werte zulassen, verursachen Ausnahmen. Weitere Informationen finden Sie im dotnet/corefx-Repository auf GitHub unter [Problem 40922 für Werttypen, die keine NULL-Werte](https://github.com/dotnet/corefx/issues/40922) zulassen.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter und jsondocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, reiner Vorwärtsleser mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird. Der `Utf8JsonReader` ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Parser und deserialisierern verwendet werden kann. Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` unter dem Cover.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ist eine hochleistungsfähige Methode zum Schreiben von UTF-8-codiertem JSON-Text aus gängigen .NET-Typen wie `String`, `Int32`und `DateTime`. Der Writer ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Serialisierern verwendet werden kann. Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` unter dem Cover.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mit `Utf8JsonReader`ein Schreib geschütztes Dokumentobjektmodell (DOM) zu erstellen. Das Dom bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast. Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den <xref:System.Text.Json.JsonElement> Typ zugegriffen werden. Der `JsonElement`-Typ stellt Array-und Objekt Enumeratoren zusammen mit APIs bereit, um JSON-Text in allgemeine .NET-Typen zu konvertieren. `JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.

In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.

## <a name="use-jsondocument-for-access-to-data"></a>Verwenden von jsondocument für den Zugriff auf Daten

Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

Der vorangehende Code:

* Geht davon aus, dass der zu analysierende JSON-Code eine Zeichenfolge namens `jsonString`
* Berechnet eine durchschnittliche Qualität für Objekte in einem `Students` Array mit einer `Grade`-Eigenschaft. 
* Weist einen Standardwert von 70 für Studenten zu, die nicht über eine Qualität verfügen.
* Zählt Schüler und Studenten durch Inkrementieren einer `count` Variablen bei jeder Iterationen. Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A>aufzurufen, wie im folgenden Beispiel gezeigt:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Im folgenden finden Sie ein Beispiel für die JSON, die von diesem Code verarbeitet wird:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Verwenden von jsondocument zum Schreiben von JSON

Im folgenden Beispiel wird gezeigt, wie JSON aus einem <xref:System.Text.Json.JsonDocument>geschrieben wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

Der vorangehende Code:

* Liest eine JSON-Datei, lädt die Daten in eine `JsonDocument`und schreibt formatierte (hübsch gedruckte) JSON-Daten in eine Datei.
* Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.
* Wenn Sie fertig sind, ruft <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf. Eine Alternative besteht darin, den Writer automatisch zu leeren, wenn er verworfen wird. 

Im folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die durch den Beispielcode verarbeitet werden soll:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

Das Ergebnis ist die folgende ziemlich gedruckte JSON-Ausgabe:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Utf8JsonWriter verwenden

Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonWriter>-Klasse verwendet wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Utf8JsonReader verwenden

Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonReader>-Klasse verwendet wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

Der vorangehende Code geht davon aus, dass es sich bei der `jsonUtf8` Variable um ein Bytearray handelt, das gültige JSON-Codierung als UTF-8 enthält

### <a name="filter-data-using-utf8jsonreader"></a>Filtern von Daten mithilfe von Utf8JsonReader

Im folgenden Beispiel wird gezeigt, wie eine Datei synchron gelesen und nach einem Wert gesucht wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

Der vorangehende Code:

* Geht davon aus, dass die Datei als UTF-16 codiert ist, und transcodiert Sie in UTF-8. Eine Datei, die als UTF-8 codiert ist, kann mithilfe des folgenden Codes direkt in eine `ReadOnlySpan<byte>`gelesen werden:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* Geht davon aus, dass der JSON-Code ein Array von Objekten enthält und jedes Objekt eine "Name"-Eigenschaft vom Typ "String" enthalten kann.
* Zählt Objekte und `name` Eigenschaftswerte, die mit "University" enden.

Im folgenden finden Sie ein JSON-Beispiel, das der vorherige Code lesen kann. Die resultierende Zusammenfassungs Meldung lautet: "2 von 4 haben Namen, die mit" University "enden:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a>Weitere Ressourcen

* [Übersicht über System. Text. JSON](system-text-json-overview.md)
* [System. Text. JSON-API-Referenz](xref:System.Text.Json)
* [Schreiben von benutzerdefinierten Konvertern für "System. Text. JSON"](system-text-json-converters-how-to.md)
* [DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON](../datetime/system-text-json-support.md)
* [GitHub-Probleme im dotnet/corefx-Repository mit der Bezeichnung JSON-funktion\doc](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
