---
title: Serialisieren und Deserialisieren von JSON mit C# -.NET
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344505"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a>Serialisieren und Deserialisieren von JSON in .NET

In diesem Artikel wird gezeigt, wie Sie den <xref:System.Text.Json>-Namespace zum Serialisieren und Deserialisieren in und aus JavaScript Object Notation (JSON) verwenden.

Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt, nicht über ein Framework wie z. B. [ASP.NET Core](/aspnet/core/).

Der größte Teil des Serialisierungsbeispielcodes legt <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest, um die JSON-Datei formatiert auszugeben (mit Einzügen und Leerraum für bessere Lesbarkeit). In der produktiven Umgebung würden Sie für diese Einstellung in der Regel den Standardwert `false` beibehalten.

## <a name="namespaces"></a>-Namespaces

Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen. Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind. Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Direktiven für einen oder beide Namespaces:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden derzeit in `System.Text.Json` nicht unterstützt.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Schreiben von .NET-Objekten in JSON (Serialisieren)

Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, müssen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode aufrufen.

Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

In den vorangehenden Beispielen wird der Typrückschluss für den serialisierten Typ verwendet. Eine Überladung von `Serialize()` nimmt einen generischen Typparameter an:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Beispiel für die Serialisierung

Im folgenden finden Sie eine Beispiel-Klasse, die Auflistungen und eine geschachtelte Klasse enthält:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus. Die JSON-Ausgabe wird standardmäßig minimiert: 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

Im folgenden Beispiel wird derselbe JSON-Code formatiert dargestellt (d. h. mit Leerraum und Einzug):

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

Um zu UTF-8 zu serialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode aufrufen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A> Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> annimmt, ist ebenfalls verfügbar.

Die Serialisierung in UTF-8 ist ungefähr 5-10% schneller als die Verwendung der Zeichenfolgen-basierten Methoden. Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.

## <a name="serialization-behavior"></a>Serialisierungsverhalten

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [Eigenschaften angeben, die ausgeschlossen werden sollen](#exclude-properties-from-serialization).
* Der [Standard Encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) schützt nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [der RFC 8259 JSON-Spezifikation](https://tools.ietf.org/html/rfc8259#section-7) mit Escapezeichen versehen werden müssen.
* Standardmäßig wird JSON minimiert. Sie können [JSON formatiert ausgeben](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen den .NET-Namen. Sie können die [Schreibweise der JSON-Namen anpassen](#customize-json-names-and-values).
* Zirkuläre Verweise werden erkannt, und Ausnahmen werden ausgelöst. Weitere Informationen finden Sie unter [Problem 38579 zu zirkulären Verweisen](https://github.com/dotnet/corefx/issues/38579) im dotnet/corefx-Repository auf GitHub.
* Felder werden derzeit ausgeschlossen.

Folgende Typen werden unterstützt:

* Primitive .NET-Typen, die primitiven JavaScript-Typen zugeordnet sind, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.
* Benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).
* Eindimensionale und verzweigte Arrays (`ArrayName[][]`).
* `Dictionary<string,TValue>`, wo `TValue` ein `object`, `JsonElement` oder ein POCO ist.
* Sammlungen aus den folgenden Namespaces. Weitere Informationen finden Sie im [Problem 36643 zur Unterstützung von Sammlungen](https://github.com/dotnet/corefx/issues/36643) im dotnet/corefx-Repository auf GitHub.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md), um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Lesen von JSON in .NET-Objekte (Deserialisieren)

Um eine Zeichenfolge oder eine Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode aufrufen.

Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecast`-Klasse erstellt, die zuvor für das [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Wenn Sie aus einer Datei mithilfe von synchronem Code deserialisieren möchten, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode aufrufen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Aus UTF-8 deserialisieren

Um aus UTF-8 zu deserialisieren, müssen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> Überladung aufrufen, die einen `Utf8JsonReader` oder eine `ReadOnlySpan<byte>` annimmt, wie in den folgenden Beispielen gezeigt. In den Beispielen wird davon ausgegangen, dass sich die JSON in einem Bytearray namens jsonUtf8Bytes befindet.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Deserialisierungsverhalten

* Standardmäßig wird die Groß-/Kleinschreibung bei der Zuordnung von Eigenschaftsnamen beachtet. Sie können [festlegen, dass die Groß-/Kleinschreibung ignoriert werden soll](#case-insensitive-property-matching).
* Wenn das JSON einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Die Deserialisierung für Verweistypen ohne parameterlosen Konstruktor wird nicht unterstützt.
* Die Deserialisierung zu unveränderlichen Objekten oder schreibgeschützten Eigenschaften wird nicht unterstützt. Weitere Informationen finden Sie im [Problem 38569 zur Unterstützung für unveränderliche Objekte](https://github.com/dotnet/corefx/issues/38569) und [Problem 38163 zur Unterstützung schreibgeschützte Eigenschaften](https://github.com/dotnet/corefx/issues/38163) im dotnet/corefx-Repository auf GitHub.
* Standardmäßig werden Enumerationen als Zahlen unterstützt. Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](#enums-as-strings).
* Felder werden nicht unterstützt.
* Standardmäßig lösen Kommentare oder nachfolgende Kommas in der JSON-Datei Ausnahmen aus. Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).
* Der Standardwert für die [maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) ist 64.

Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md), um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="serialize-to-formatted-json"></a>Serialisieren in formatierten JSON-Code

Um die JSON-Ausgabe zu formatieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

Im Folgenden finden Sie eine Beispielklasse, die serialisiert werden soll und die formatierte JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>Anpassen von JSON-Namen und -Werten

Standardmäßig sind Eigenschaftsnamen und Wörterbuch-Schlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung. Enumerationswerte werden als Zahlen dargestellt. In diesem Abschnitt wird Folgendes beschrieben:

* [Anpassen einzelner Eigenschaftsnamen](#customize-individual-property-names)
* [Alle Eigenschaftsnamen in Camel-Case konvertieren](#use-camel-case-for-all-json-property-names)
* [Implementieren einer benutzerdefinierten Benennungsrichtlinie für Eigenschaften](#use-a-custom-json-property-naming-policy)
* [Wörterbuch-Schlüssel in Camel-Case konvertieren](#camel-case-dictionary-keys)
* [Enumerationen in Zeichenfolgen und Camel-Case konvertieren](#enums-as-strings) 

Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und -Werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Anpassen einzelner Eigenschaftsnamen

Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)-Attribut.

Hier ist ein Beispiel für die Serialisierung und das resultierende JSON:

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

* Gilt in beide Richtungen, für die Serialisierung und Deserialisierung.
* Hat Vorrang vor Benennungsrichtlinien für Eigenschaften.

### <a name="use-camel-case-for-all-json-property-names"></a>Camel-Case für alle JSON-Eigenschaftsnamen verwenden

Wenn Sie die Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen verwenden möchten, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

Im Folgenden finden Sie eine Beispielklasse zum Serialisieren und die JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Die Camel-Case-Benennungsrichtlinie für Eigenschaften:

* Gilt für die Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]`-Attributen überschrieben. Aus diesem Grund ist der Name der JSON-Eigenschaft `Wind` im Beispiel nicht Camel-Case.

### <a name="use-a-custom-json-property-naming-policy"></a>Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften

Um eine benutzerdefinierte Benennungsrichtlinie für JSON-Eigenschaften zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und überschreiben Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihrer Benennungsrichtlinien-Klasse fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

Im Folgenden finden Sie eine Beispielklasse zum Serialisieren und die JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Die Benennungsrichtlinie für JSON-Eigenschaften:

* Gilt für die Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]`-Attributen überschrieben. Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Großbuchstaben.

### <a name="camel-case-dictionary-keys"></a>Camel-Case Wörterbuch-Schlüssel

Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die `string` Schlüssel in die Camel-Case-Schreibweise konvertiert werden. Legen Sie dazu die <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:

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

Die Camel-Case-Benennungsrichtlinie für Wörterbuch-Schlüssel gilt nur für die Serialisierung. Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel denen in der JSON-Datei, auch wenn Sie `JsonNamingPolicy.CamelCase` als `DictionaryKeyPolicy` angeben.

### <a name="enums-as-strings"></a>Enumerationen als Zeichenfolgen

Standardmäßig werden Enumerationen als Zahlen serialisiert. Verwenden Sie den <xref:System.Text.Json.Serialization.JsonStringEnumConverter>, um Enumerationsnamen als Zeichenfolgen zu serialisieren.

Nehmen Sie beispielsweise an, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Wenn die Summary-Eigenschaft `Hot` ist, hat die serialisierte JSON standardmäßig den numerischen Wert 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

Der resultierende JSON-Code sieht wie im folgenden Beispiel aus:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Enumerationsnamen-Zeichenfolgen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Eigenschaften von der Serialisierung ausschließen

Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Wenn Sie möchten, dass einige von ihnen nicht in der JSON-Ausgabe angezeigt werden, haben Sie mehrere Möglichkeiten. In diesem Abschnitt wird erläutert, wie verschiedene Dinge ausgeschlossen werden können:

* [Einzelne Eigenschaften](#exclude-individual-properties)
* [Alle schreibgeschützten Eigenschaften](#exclude-all-read-only-properties)
* [Alle NULL-Wert-Eigenschaften](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>Einzelne Eigenschaften ausschließen

Verwenden Sie das [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)-Attribut, um einzelne Eigenschaften zu ignorieren.

Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>Alle schreibgeschützten Eigenschaften ausschließen

Eine Eigenschaft ist schreibgeschützt, wenn Sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält. Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:

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

### <a name="exclude-all-null-value-properties"></a>Alle Eigenschaften mit NULL-Wert ausschließen

Um alle Eigenschaften mit NULL-Werten auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:

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

Standardmäßig schützt der Serialisierer alle nicht-ASCII-Zeichen. Das heißt, er ersetzt sie durch `\uxxxx`, wobei `xxxx` der Unicode-Code des Zeichens ist. Wenn die `Summary`-Eigenschaft z. B. auf kyrillisch жарко festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Serialisieren von Sprachzeichensätzen

Wenn Sie die Zeichensätze mindestens einer Sprache ohne Escapezeichen serialisieren möchten, geben Sie einen oder mehrere [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) beim Erstellen einer <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>-Instanz an, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Mit diesem Code werden kyrillische und griechische Zeichen nicht geschützt. Wenn die `Summary`-Eigenschaft auf kyrillisch жарко festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>, um alle Sprachzeichensätze ungeschützt zu serialisieren.

### <a name="serialize-specific-characters"></a>Serialisieren bestimmter Zeichen

Alternativ können Sie einzelne Zeichen angeben, die Sie zulassen möchten, ohne geschützt zu werden. Im folgenden Beispiel werden nur die ersten zwei Zeichen von "жарко" serialisiert:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Im Folgenden finden Sie ein Beispiel für das JSON, das durch den vorangehenden Code generiert wird:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Alle Zeichen serialisieren

Um das Schützen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> verwenden, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> Im Vergleich zum Standard-Encoder lässt der `UnsafeRelaxedJsonEscaping` Encoder mehr Zeichen ohne Escapezeichen durch:
>
> * Es werden keine HTML-sensiblen Zeichen wie `<`, `>`, `&`und `'` mit Escapezeichen versehen.
> * Er bietet keine zusätzlichen Schutzmaßnahmen vor XSS- oder Informationsoffenlegungsangriffen, wie z. B. solche, die sich aus einer Uneinigkeit zwischen dem Client und dem Server bezüglich des *charset* ergeben könnten.
>
> Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretiert. Sie können ihn beispielsweise verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8` sendet. Erlauben Sie niemals, dass eine rohe `UnsafeRelaxedJsonEscaping`-Ausgabe in eine HTML-Seite oder ein `<script>` Element ausgegeben wird.

## <a name="serialize-properties-of-derived-classes"></a>Serialisieren von Eigenschaften abgeleiteter Klassen

Die polymorphe Serialisierung wird nicht unterstützt, wenn Sie zum Zeitpunkt der Kompilierung angeben, welcher Typ serialisiert werden soll. Nehmen Sie beispielsweise an, Sie verfügen über eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

Angenommen, das Typargument der `Serialize` Methode zum Zeitpunkt der Kompilierung ist `WeatherForecast`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist. Es werden nur die Eigenschaften der Basisklasse serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Dieses Verhalten soll dabei helfen, das versehentliche Verfügbarmachen von Daten in einem abgeleiteten, von der Laufzeit erstellten Typ zu verhindern.

Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs zu serialisieren:

* Aufrufen einer Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A>, mit der Sie den Typ zur Laufzeit angeben können:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Deklarieren Sie das Objekt, das serialisiert werden soll, als `object`.

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

Weitere Informationen zur polymorphen Deserialisierung finden Sie unter [Unterstützung der polymorphen Deserialisierung](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

## <a name="allow-comments-and-trailing-commas"></a>Kommentare und nachfolgende Kommas zulassen

Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig. Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest. Und um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest. Im folgenden Beispiel wird gezeigt, wie Sie beides zulassen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Im Folgenden finden Sie ein Beispiel für JSON mit Kommentaren und einem nachfolgenden Komma:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Groß-/Kleinschreibung bei Eigenschaftsnamen ignorieren

Standardmäßig wird bei der Deserialisierung darauf geachtet, dass die Groß-/Kleinschreibung der Eigenschaftsnamen zwischen JSON und dem Zielobjekt übereinstimmt. Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Im Folgenden finden Sie eine Beispiel-JSON-Datei mit Camel-Case Namen. Sie kann in den folgenden Typ deserialisiert werden, der über Pascal-Case Eigenschaftsnamen verfügt.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>Überflüssiges JSON behandeln

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

Wenn Sie den obenstehenden JSON-Code in den angezeigten Typ deserialisieren, sind die Eigenschaften `DatesAvailable` und `SummaryWords` nicht mehr vorhanden und gehen verloren. Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)-Attribut auf eine Eigenschaft vom Typ `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:

|Eigenschaft |Wert |Hinweise |
|---------|---------|---------|
| Date    | 01.08.2019 00:00:00 -07:00||
| TemperatureCelsius| 0 | Abweichende Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die Eigenschaft nicht festgelegt ist. |
| Summary | Hot ||
| ExtensionData | TemperatureCelsius: 25 |Da die Groß-/Kleinschreibung nicht übereinstimmte, ist diese JSON-Eigenschaft ein Extra und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.|
|| DatesAvailable:<br>  01.08.2019 00:00:00 -07:00<br>02.08.2019 00:00:00 -07:00 |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar mit einem Array als Wertobjekt.|
| |SummaryWords:<br>Cool<br>Windy<br>Humid |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar mit einem Array als Wertobjekt.|

Wenn das Zielobjekt serialisiert wird, werden die Schlüssel-Wert-Paare der Erweiterungsdaten zu JSON-Eigenschaften, genauso wie sie im eingelesenen JSON-Code waren:

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

Wenn eine Eigenschaft in JSON NULL ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf NULL festgelegt. In einigen Szenarios hat die Zieleigenschaft möglicherweise einen Standardwert, und Sie möchten nicht, dass ein NULL-Wert den Standardwert überschreibt.

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

Um dieses Verhalten zu ändern, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

Mit dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault` Objekts nach der Deserialisierung der Standardwert "No summary".

NULL-Werte in JSON werden nur ignoriert, wenn sie gültig sind. NULL-Werte für Werttypen, die keine NULL-Werte zulassen, verursachen Ausnahmen. Weitere Informationen finden Sie im [Problem 40922 zu Werttypen, die keine NULL-Werte zulassen](https://github.com/dotnet/corefx/issues/40922) im dotnet/corefx-Repository auf GitHub.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter und JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, reiner Vorwärtsleser mit geringem Speicherbedarf für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird. Der `Utf8JsonReader` ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierern verwendet werden kann. Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet intern einen `Utf8JsonReader`.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ist eine leistungsstarke Methode zum Schreiben von UTF-8-codiertem JSON-Text aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime`. Der Writer ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Serialisierern verwendet werden kann. Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet intern einen `Utf8JsonWriter`.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mit `Utf8JsonReader` ein schreibgeschütztes Dokumentobjektmodell (DOM) zu erstellen. Das DOM bietet wahlfreien Zugriff auf Daten in einer JSON-Nutzlast. Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den <xref:System.Text.Json.JsonElement>-Typ zugegriffen werden. Der `JsonElement`-Typ stellt Array- und Objekt-Enumeratoren bereit zusammen mit APIs, um JSON-Text in allgemeine .NET-Typen zu konvertieren. `JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.

In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.

## <a name="use-jsondocument-for-access-to-data"></a>Verwenden von JsonDocument für den Zugriff auf Daten

Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den wahlfreien Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

Der vorangehende Code:

* Geht davon aus, dass der zu analysierende JSON-Code einer Zeichenfolge namens `jsonString` ist.
* Berechnet eine durchschnittliche Note für Objekte in einem `Students` Array mit einer `Grade`-Eigenschaft. 
* Weist eine Standardnote von 70 für Studenten zu, die keine Note haben.
* Zählt Schüler und Studenten durch Inkrementieren einer `count` Variablen bei jeder Iteration. Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A> aufzurufen, wie im folgenden Beispiel gezeigt:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Im Folgenden finden Sie ein Beispiel für das JSON, das von diesem Code verarbeitet wird:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Verwenden von jsondocument zum Schreiben von JSON

Im folgenden Beispiel wird gezeigt, wie JSON aus einem <xref:System.Text.Json.JsonDocument>geschrieben wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

Der vorangehende Code:

* Liest eine JSON-Datei, lädt die Daten in ein `JsonDocument` und schreibt die JSON-Daten formatiert in eine Datei.
* Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.
* Ruft zum Abschluss <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf. Eine Alternative besteht darin, den Writer automatisch flushen zu lassen, wenn er verworfen wird. 

Im Folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die durch den Beispielcode verarbeitet werden soll:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

Das Ergebnis ist die folgende formatierte JSON-Ausgabe:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Utf8JsonWriter verwenden

Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonWriter>-Klasse verwendet wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Utf8JsonReader verwenden

Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonReader>-Klasse verwendet wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

Der vorangehende Code geht davon aus, dass es sich bei der `jsonUtf8` Variable um ein Bytearray handelt, das gültiges JSON in UTF-8-Codierung enthält.

### <a name="filter-data-using-utf8jsonreader"></a>Filtern von Daten mithilfe von Utf8JsonReader

Im folgenden Beispiel wird gezeigt, wie eine Datei synchron gelesen und nach einem Wert gesucht wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

Der vorangehende Code:

* Geht davon aus, dass die Datei UTF-16-codiert ist, und transcodiert sie in UTF-8. Eine Datei, die als UTF-8 codiert ist, kann mithilfe des folgenden Codes direkt in eine `ReadOnlySpan<byte>` gelesen werden:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* Geht davon aus, dass der JSON-Code ein Array von Objekten enthält und jedes Objekt eine "name"-Eigenschaft vom Typ "String" enthalten kann.
* Zählt Objekte und `name` Eigenschaftswerte, die mit "University" enden.

Im Folgenden finden Sie ein JSON-Beispiel, das der vorherige Code lesen kann. Die resultierende Zusammenfassungsmeldung lautet: "2 out of 4 have names that end with 'University'":

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a>Weitere Ressourcen

* [Übersicht über System.Text.Json](system-text-json-overview.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [Schreiben von benutzerdefinierten Konvertern für System.Text.Json](system-text-json-converters-how-to.md)
* [DateTime- und DateTimeOffset-Unterstützung in System.Text.Json](../datetime/system-text-json-support.md)
* [GitHub-Probleme im dotnet/corefx-Repository mit dem Label json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
