---
title: ''
description: Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.
ms.date: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords: []
ms.openlocfilehash: f1a5da448b08f9b4f1cf3fa6cba67fb376b00a6f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702267"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Serialisieren und Deserialisieren (Marshallen und Marshallen rückgängig machen) von JSON-Daten in .NET

Dieser Artikel veranschaulicht, wie Sie mithilfe des <xref:System.Text.Json>-Namespace Daten in das JSON-Format (JavaScript Object Notation) serialisiert und daraus deserialisiert werden. Wenn Sie vorhandenen Code aus `Newtonsoft.Json` portieren, finden Sie weitere Informationen unter [Migrieren zu `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).

Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework wie [ASP.NET Core](/aspnet/core/).

Im größten Teil des Serialisierungsbeispielcodes ist <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` festgelegt, um den JSON-Code übersichtlicher zu gestalten (mit Einzügen und Zwischenräumen für bessere Lesbarkeit). Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.

Die Codebeispiele verweisen auf die folgende Klasse und deren Varianten:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a>Namespaces

Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen. Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind. Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Anweisungen für einen oder beide Namespaces:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden zurzeit in `System.Text.Json` nicht unterstützt.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Schreiben von .NET-Objekten in JSON (Serialisieren)

Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, rufen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode auf.

Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

In den vorangehenden Beispielen wird Typrückschluss für den zu serialisierenden Typ verwendet. Eine Überladung von `Serialize()` akzeptiert einen generischen Typparameter:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Serialisierungsbeispiel

Im Folgenden finden Sie eine Beispielklasse, die Sammlungen und eine geschachtelte Klasse enthält:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus. Die JSON-Ausgabe wird standardmäßig verkleinert:

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

Im folgenden Beispiel wird derselbe JSON-Code dargestellt, allerdings formatiert (d. h. übersichtlich mit Zwischenräumen und Einzügen):

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

### <a name="serialize-to-utf-8"></a>Serialisieren in UTF-8

Um in UTF-8 zu serialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode auf:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A>-Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> akzeptiert, ist ebenfalls verfügbar.

Das Serialisieren in UTF-8 ist ungefähr 5–10 % schneller als die Verwendung von zeichenfolgenbasierten Methoden. Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.

## <a name="serialization-behavior"></a>Serialisierungsverhalten

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [auszuschließende Eigenschaften angeben](#exclude-properties-from-serialization).
* Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.
* JSON wird standardmäßig verkleinert. Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen. Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](#customize-json-names-and-values).
* Zirkelbezüge werden erkannt und daraufhin Ausnahmen ausgelöst.
* Felder sind aktuell ausgeschlossen.

Unter anderem unterstützte Typen:

* .NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.
* Benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).
* Eindimensionale und Jagged Arrays (`ArrayName[][]`).
* Ein `Dictionary<string,TValue>`, wobei `TValue` ein `object` ist, ein `JsonElement` oder ein POCO.
* Sammlungen aus den folgenden Namespaces.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Lesen von JSON in .NET-Objekte (Deserialisieren)

Um aus einer Zeichenfolge oder einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode auf.

Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecast`-Klasse erstellt, die schon zuvor im [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Um mithilfe von synchronem Code aus einer Datei zu deserialisieren, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode auf:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Deserialisieren aus UTF-8

Um aus UTF-8 zu deserialisieren, rufen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung auf, die einen `Utf8JsonReader` oder ein `ReadOnlySpan<byte>` akzeptiert, wie in den folgenden Beispielen gezeigt. In den Beispielen wird vorausgesetzt, dass sich das JSON in einem Bytearray namens „jsonUtf8Bytes“ befindet.

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Deserialisierungsverhalten

* Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet. Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](#case-insensitive-property-matching).
* Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Die Deserialisierung in Verweistypen ohne einen parameterlosen Konstruktor wird nicht unterstützt.
* Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.
* Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt. Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](#enums-as-strings).
* Felder werden nicht unterstützt.
* Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus. Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).
* Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.

Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="serialize-to-formatted-json"></a>Serialisieren in formatierten JSON-Code

Um die JSON-Ausgabe übersichtlich zu formatieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

Hier sehen Sie einen zu serialisierenden Beispieltyp und die übersichtlich formatierte JSON-Ausgabe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>Anpassen von JSON-Namen und -Werten

Standardmäßig bleiben Eigenschaftsnamen und Wörterbuchschlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung. Enumerationswerte werden als Zahlen dargestellt. In diesem Abschnitt wird Folgendes beschrieben:

* [Anpassen einzelner Eigenschaftsnamen](#customize-individual-property-names)
* [Konvertieren aller Eigenschaftsnamen in Camel-Case-Schreibweise](#use-camel-case-for-all-json-property-names)
* [Implementieren einer benutzerdefinierten Benennungsrichtlinie für Eigenschaften](#use-a-custom-json-property-naming-policy)
* [Konvertieren von Wörterbuchschlüsseln in Camel-Case-Schreibweise](#camel-case-dictionary-keys)
* [Konvertieren von Enumerationen in Zeichenfolgen und Camel-Case-Schreibweise](#enums-as-strings)

Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und -werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Anpassen einzelner Eigenschaftsnamen

Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das Attribut [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).

Hier finden Sie einen zu serialisierenden Beispieltyp und die daraus resultierende JSON-Ausgabe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Der über dieses Attribut festgelegte Eigenschaftsname:

* Dies gilt in beide Richtungen, für Serialisierung und Deserialisierung.
* Es hat Vorrang vor Benennungsrichtlinien für Eigenschaften.

### <a name="use-camel-case-for-all-json-property-names"></a>Verwenden der Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen

Um die Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen zu verwenden, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Die Camel-Case-Benennungsrichtlinie für Eigenschaften:

* Gilt für Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt. Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Camel-Case-Schreibweise.

### <a name="use-a-custom-json-property-naming-policy"></a>Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften

Um eine benutzerdefinierte Benennungsrichtlinie für JSON-Eigenschaften zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und setzen Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode außer Kraft, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihre Benennungsrichtlinienklasse fest:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Die Benennungsrichtlinie für JSON-Eigenschaften:

* Gilt für Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt. Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Großbuchstaben.

### <a name="camel-case-dictionary-keys"></a>Wörterbuchschlüssel in Camel-Case-Schreibweise

Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die Schlüssel vom Typ `string` in Camel-Case-Schreibweise konvertiert werden. Legen Sie hierzu <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

Das Serialisieren eines Objekts mit einem Wörterbuch namens `TemperatureRanges`, das die Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` enthält, würde zu einer JSON-Ausgabe wie im folgenden Beispiel führen:

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

Die Camel-Case-Benennungsrichtlinie für Wörterbuchschlüssel gilt nur für die Serialisierung. Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei auch dann, wenn Sie `JsonNamingPolicy.CamelCase` als `DictionaryKeyPolicy` angeben.

### <a name="enums-as-strings"></a>Enumerationen als Zeichenfolgen

Standardmäßig werden Enumerationen als Zahlen serialisiert. Um Enumerationen als Zeichenfolgen zu serialisieren, verwenden Sie <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Angenommen, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Wenn die Zusammenfassung `Hot` ist, hat das serialisierte JSON standardmäßig den numerischen Wert 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

Das resultierende JSON sieht wie im folgenden Beispiel aus:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Zeichenfolgennamen von Enumerationen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Ausschließen von Eigenschaften aus der Serialisierung

Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Wenn Sie möchten, dass einige von ihnen nicht in der JSON-Ausgabe vorkommen, haben Sie mehrere Möglichkeiten. In diesem Abschnitt wird erläutert, wie Sie Folgendes ausschließen können:

* [Einzelne Eigenschaften](#exclude-individual-properties)
* [ Alle schreibgeschützten Eigenschaften](#exclude-all-read-only-properties)
* [Alle Nullwert-Eigenschaften](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>Ausschließen einzelner Eigenschaften

Um einzelne Eigenschaften zu ignorieren, verwenden Sie das Attribut [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).

Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>Ausschließen aller schreibgeschützten Eigenschaften

Eine Eigenschaft ist schreibgeschützt, wenn sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält. Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Diese Option gilt nur für Serialisierung. Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.

### <a name="exclude-all-null-value-properties"></a>Ausschließen aller Nullwert-Eigenschaften

Um alle Nullwert-Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

Hier finden Sie ein zu serialisierendes Beispielobjekt und die JSON-Ausgabe:

|Eigenschaft |Wert  |
|---
title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-
title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-----|--- title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-
title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-----| | Date    | 8/1/2019 12:00:00 AM -07:00| | TemperatureCelsius| 25 | | Summary| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

Diese Einstellung gilt für Serialisierung und Deserialisierung. Informationen zu ihren Auswirkungen auf die Deserialisierung finden Sie unter [Ignorieren von Null beim Deserialisieren](#ignore-null-when-deserializing).

## <a name="customize-character-encoding"></a>Anpassen der Zeichencodierung

Standardmäßig escapet der Serialisierer alle Nicht-ASCII-Zeichen.  Das heißt, dass sie durch `\uxxxx` ersetzt werden, wobei `xxxx` der Unicode-Code des Zeichens ist.  Wenn die `Summary`-Eigenschaft beispielsweise auf Kyrillisch „жарко“ festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Serialisieren von Sprachzeichensätzen

Zum Serialisieren der Zeichensätze von mindestens einer Sprache ohne zu escapen geben Sie [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) an, wenn Sie eine Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> erstellen, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Mit diesem Code werden weder kyrillische noch griechische Zeichen escapet. Wenn die `Summary`-Eigenschaft auf Kyrillisch „жарко“ festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Um alle Sprachensätze ohne zu escapen zu serialisieren, verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

### <a name="serialize-specific-characters"></a>Serialisieren bestimmter Zeichen

Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne dass sie escapet werden. Im folgenden Beispiel werden nur die ersten zwei Zeichen von „жарко“ serialisiert:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Hier sehen Sie eine JSON-Beispiel, das vom vorangehenden Code erzeugt wird:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Serialisieren aller Zeichen

Um das Escapen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> verwenden, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> Im Vergleich zum Standardencoder ist der `UnsafeRelaxedJsonEscaping`-Encoder weniger streng beim Zulassen von Zeichen, ohne sie zu escapen:
>
> * Er escapet keine HTML-abhängigen Zeichen wie `<`, `>`, `&` und `'`.
> * Er bietet keine zusätzlichen, tief greifenden Abwehrmaßnahmen gegen solche Cross-Site Scripting (XSS)- oder Information-Disclosure-Angriffe (Veröffentlichung von Informationen), die von einem Client und Server, die sich nicht auf einen *Zeichensatz* einigen können, verursacht werden können.
>
> Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretieren wird. Beispielsweise können Sie ihn verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8` sendet. Gestatten Sie niemals, dass die `UnsafeRelaxedJsonEscaping`-Rohausgabe in eine HTML-Seite oder ein `<script>`-Element ausgegeben wird.

## <a name="serialize-properties-of-derived-classes"></a>Serialisieren von Eigenschaften abgeleiteter Klassen

Das Serialisieren einer polymorphen Typhierarchie wird nicht unterstützt. Wenn eine Eigenschaft beispielsweise als eine Schnittstelle oder eine abstrakte Klasse definiert wird, werden nur die für die Schnittstelle oder abstrakte Klasse definierten Eigenschaften serialisiert, auch wenn der Laufzeittyp über zusätzliche Eigenschaften verfügt. Die Ausnahmen bei diesem Verhalten werden in diesem Abschnitt erläutert.

Nehmen Sie beispielsweise an, Sie besitzen eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

Ferner sei angenommen, dass das Typargument der `Serialize`-Methode zur Kompilierzeit `WeatherForecast` ist:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch dann nicht, wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist. Nur die Basisklasseneigenschaften werden serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Dieses Verhalten soll die versehentliche Verfügbarmachung von Daten in einem abgeleiteten, zur Laufzeit erstellten Typ verhindern.

Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs im vorherigen Beispiel zu serialisieren:

* Rufen Sie eine Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A> auf, bei der Sie den Typ zur Laufzeit angeben können:

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Deklarieren Sie das zu serialisierende Objekt als `object`.

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in die JSON-Ausgabe aufgenommen wird:

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> Diese Ansätze bieten polymorphe Serialisierung nur für das Stammobjekt, das serialisiert werden soll, und nicht für die Eigenschaften dieses Stammobjekts.

Sie können polymorphe Serialisierung für Objekte auf niedrigerer Ebene erzielen, wenn Sie diese als `object`-Typ definieren. Angenommen, Ihre `WeatherForecast`-Klasse verfügt über eine Eigenschaft mit dem Namen `PreviousForecast`, die als `WeatherForecast`-Typ oder als `object`-Typ definiert werden kann:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

Wenn die Eigenschaft `PreviousForecast` eine Instanz von `WeatherForecastDerived` enthält:

* Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPrevious` **enthält keine** `WindSpeed`.
* Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPreviousAsObject` **enthält** `WindSpeed`.

Um `WeatherForecastWithPreviousAsObject` zu serialisieren, ist es nicht erforderlich, `Serialize<object>` oder `GetType` aufzurufen, da das Stammobjekt nicht das Objekt ist, das von einem abgeleiteten Typ sein darf. Im folgenden Codebeispiel wird weder `Serialize<object>` noch `GetType` aufgerufen:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

Der vorangehende Code serialisiert `WeatherForecastWithPreviousAsObject` korrekt:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

Derselbe Ansatz zum Definieren von Eigenschaften als `object` funktioniert mit Schnittstellen. Angenommen, Sie haben die folgende Schnittstelle und Implementierung, und Sie möchten eine Klasse mit Eigenschaften serialisieren, die Implementierungsinstanzen enthalten:

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

Wenn Sie eine Instanz von `Forecasts` serialisieren, zeigt nur `Tuesday` die `WindSpeed`-Eigenschaft an, da `Tuesday` als `object` definiert ist:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

Im folgenden Beispiel wird der JSON-Code gezeigt, der aus dem vorangehenden Code resultiert:

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

Weitere Informationen zur polymorphen **Serialisierung** sowie Informationen zur **Deserialisierung** finden Sie unter [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).

## <a name="allow-comments-and-trailing-commas"></a>Zulassen von Kommentaren und nachfolgenden Kommas

Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig. Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest.
Und um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest. Das folgende Beispiel veranschaulicht, wie Sie beides zulassen:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Im Folgenden finden Sie ein JSON-Beispiel mit Kommentaren und einem nachfolgenden Komma:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Eigenschaftenabgleich ohne Beachtung der Groß-/Kleinschreibung

Standardmäßig wird bei der Deserialisierung nach Übereinstimmungen von Eigenschaftsnamen zwischen JSON und den Zielobjekteigenschaften unter Berücksichtigung von Groß-/Kleinschreibung gesucht. Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Im Folgenden finden Sie ein JSON-Beispiel mit Eigenschaftsnamen in Camel-Case-Schreibweise. Es kann in den folgenden Typ deserialisiert werden, der Eigenschaftsnamen in Pascal-Schreibweise besitzt.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>Verarbeiten von Überlauf-JSON

Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, die nicht von Eigenschaften des Zieltyps dargestellt werden. Angenommen, Ihr Zieltyp ist folgender:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

Und der zu deserialisierende JSON-Code ist wie folgt:

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

Wenn Sie den angezeigten JSON-Code in den gezeigten Typ deserialisieren, gibt es keinen Ort mehr für die Eigenschaften `DatesAvailable` und `SummaryWords`, und sie gehen verloren. Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)-Attribut auf eine Eigenschaft des Typs `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:

|Eigenschaft |Wert  |Hinweise  |
|---
title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-
title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-----|--- title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-
title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-----|--- title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-
title: description: „Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.“
ms.date: no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json' helpviewer_keywords:
- 
- 
- 
- 

-----| | Date    | 8/1/2019 12:00:00 AM -07:00|| | TemperatureCelsius| 0 | Keine Übereinstimmung unter Berücksichtigung von Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die Eigenschaft nicht festgelegt wird. | | Summary | Hot || | ExtensionData | temperatureCelsius: 25 |Da die Groß-/Kleinschreibung nicht übereinstimmte, ist diese JSON-Eigenschaft ein zusätzliches Element und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.| || DatesAvailable:<br>  8/1/2019 12:00:00 AM -07:00<br>8/2/2019 12:00:00 AM -07:00 |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.| | |SummaryWords:<br>Toll<br>Windig<br>Humid |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|

Wenn das Zielobjekt serialisiert wird, werden die Schlüssel-Wert-Paare der Erweiterungsdaten zu genau solchen JSON-Eigenschaften, wie sie im eingehenden JSON-Code waren:

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

Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code vorkommt. Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert würden.

## <a name="ignore-null-when-deserializing"></a>Ignorieren von Null beim Deserialisieren

Wenn eine Eigenschaft in JSON Null ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf Null festgelegt. In einigen Szenarien kann die Zieleigenschaft möglicherweise einen Standardwert besitzen, und Sie möchten nicht, dass dieser Standardwert von einem Nullwert überschrieben wird.

Angenommen, der folgende Code stellt Ihr Zielobjekt dar:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Und ferner angenommen, der folgende JSON-Code wird deserialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Nach der Deserialisierung ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts Null.

Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> auf `true` fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

Bei dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts der Standardwert „Keine Zusammenfassung“ nach der Deserialisierung.

Nullwerte im JSON werden nur ignoriert, wenn Sie gültig sind. Nullwerte für Non-Nullable-Werttypen verursachen Ausnahmen.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>„Utf8JsonReader“, „Utf8JsonWriter“ und „JsonDocument“

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, rein vorwärtsgerichteter Reader mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der aus einem `ReadOnlySpan<byte>` oder `ReadOnlySequence<byte>` gelesen wird. Der `Utf8JsonReader` ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierungsprogrammen genutzt werden kann. Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` verdeckt.

Mit <xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell mit hohem Durchsatz schreiben. Der Writer ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen genutzt werden kann. Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` verdeckt.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mithilfe von `Utf8JsonReader` ein schreibgeschütztes Dokumentobjektmodell (DOM) zu erstellen. Das DOM bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast. Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den Typ <xref:System.Text.Json.JsonElement> zugegriffen werden. Der `JsonElement`-Typ stellt Array- und Objektenumeratoren sowie APIs zum Konvertieren von JSON-Text in gängige .NET-Typen bereit. `JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.

In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.

## <a name="use-jsondocument-for-access-to-data"></a>Verwenden von „JsonDocument“ für den Zugriff auf Daten

Das folgende Beispiel zeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

Der vorangehende Code:

* Setzt voraus, dass sich der zu analysierende JSON-Code in einer Zeichenfolge namens `jsonString` befindet.
* Berechnet eine durchschnittliche Note für Objekte in einem `Students`-Array, die eine `Grade`-Eigenschaft besitzen.
* Weist Kursteilnehmern, die keine Note haben, eine Standardnote von 70 zu.
* Zählt Kursteilnehmer durch Inkrementieren einer `count`-Variablen bei jeder Iteration. Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A> aufzurufen, wie im folgenden Beispiel gezeigt:

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Im Folgenden finden Sie ein Beispiel für das JSON, das von diesem Code verarbeitet wird:

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Verwenden von JsonDocument zum Schreiben von JSON

Das folgende Beispiel veranschaulicht, wie JSON aus einem <xref:System.Text.Json.JsonDocument> geschrieben wird:

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

Der vorangehende Code:

* Liest eine JSON-Datei, lädt die Daten in ein `JsonDocument` und schreibt (übersichtlich) formatierten JSON-Code in eine Datei.
* Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.
* Ruft nach Abschluss <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf. Eine Alternative besteht darin, den Writer automatisch zu leeren, wenn er entsorgt wird.

Im Folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die von dem Beispielcode verarbeitet werden soll:

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

Das Ergebnis ist die folgende, übersichtlich formatierte JSON-Ausgabe:

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Verwenden von „Utf8JsonWriter“

Im folgenden Beispiel wird die Verwendung der <xref:System.Text.Json.Utf8JsonWriter>-Klasse veranschaulicht:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Verwenden von „Utf8JsonReader“

Im folgenden Beispiel wird die Verwendung der <xref:System.Text.Json.Utf8JsonReader>-Klasse veranschaulicht:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

Der vorangehende Code setzt voraus, dass es sich bei der `jsonUtf8`-Variablen um ein Bytearray handelt, das gültigen, UTF-8-codierten JSON-Code enthält.

### <a name="filter-data-using-utf8jsonreader"></a>Filtern von Daten mithilfe von „Utf8JsonReader“

Das folgende Beispiel zeigt, wie Sie eine Datei synchron lesen und nach einem Wert suchen:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

Der vorangehende Code:

* Setzt voraus, dass der JSON-Code ein Array von Objekten enthält, und dass jedes Objekt eine Eigenschaft „name“ vom Typ „string“ (Zeichenfolge) enthalten kann.
* Zählt Objekte und „name“-Eigenschaftswerte, die auf „University“ enden.
* Setzt voraus, dass die Datei UTF-16-codiert ist und transcodiert sie in UTF-8. Eine UTF-8-codierte Datei kann mithilfe des folgenden Codes direkt in ein `ReadOnlySpan<byte>` gelesen werden:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Wenn die Datei eine UTF-8-Bytereihenfolge-Marke (BOM) enthält, entfernen Sie diese, bevor Sie die Bytes an den `Utf8JsonReader` übergeben, da der Reader Text erwartet. Andernfalls wird die BOM als ungültiges JSON betrachtet, und der Reader löst eine Ausnahme aus.

Im Folgenden finden Sie ein JSON-Beispiel, das der voranstehende Code lesen kann. Die resultierende Zusammenfassungsmeldung lautet „2 out of 2 have names that end with ‚University‘“ (2 von 4 besitzen Namen, die auf „University“ enden):

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a>Lesen aus einem Stream mithilfe von Utf8JsonReader

Wenn Sie eine große Datei (z. B. ein Gigabyte oder mehr) lesen, möchten Sie die gesamte Datei vielleicht nicht auf einmal in den Arbeitsspeicher laden müssen. In diesem Szenario können Sie einen <xref:System.IO.FileStream> verwenden.

Wenn Sie einen `Utf8JsonReader` zum Lesen aus einem Stream verwenden, gelten die folgenden Regeln:

* Der Puffer, der die partielle JSON-Nutzlast enthält, muss mindestens so groß wie das größte JSON-Token darin sein, damit der Reader vorankommen kann.
* Der Puffer muss mindestens so groß wie die größte Sequenz von Leerraum innerhalb der JSON-Nutzlast sein.
* Der Reader verfolgt die gelesenen Daten nicht nach, bis er den nächsten <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in der JSON-Nutzlast vollständig gelesen hat. Wenn im Puffer noch Bytes vorhanden sind, müssen Sie sie wieder dem Reader übergeben. Sie können <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> verwenden, um zu bestimmen, wie viele Bytes übrig bleiben.

Im folgenden Code wird veranschaulicht, wie aus einem Stream gelesen wird. Das Beispiel zeigt einen <xref:System.IO.MemoryStream>. Ähnlicher Code funktioniert mit einem <xref:System.IO.FileStream>, es sei denn, der `FileStream` enthält am Anfang eine UTF-8-BOM. In diesem Fall müssen Sie diese drei Bytes aus dem Puffer entfernen, bevor Sie die verbleibenden Bytes an den `Utf8JsonReader` übergeben. Andernfalls würde der Reader eine Ausnahme auslösen, da die BOM nicht als gültiger Teil des JSON-Codes angesehen wird.

Der Beispielcode beginnt mit einem 4-KB-Puffer und verdoppelt die Puffergröße jedes Mal, wenn festgestellt wird, dass die Größe nicht ausreicht, um einem kompletten JSON-Token zu entsprechen. Dies ist erforderlich, damit der Reader mit der JSON-Nutzlast vorankommt. Das JSON-Beispiel im Codeausschnitt löst nur dann eine Erhöhung der Puffergröße aus, wenn Sie eine sehr geringe Anfangspuffergröße festlegen, z. B. 10 Bytes. Die `Console.WriteLine`-Anweisungen zeigen Ursache und Auswirkung der Puffergrößenerhöhungen, wenn Sie die Anfangspuffergröße auf 10 festlegen. Bei der Anfangspuffergröße von 4 KB wird das gesamte JSON-Beispiel von jeder `Console.WriteLine` angezeigt, und die Puffergröße muss nie erhöht werden.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

Im vorherigen Beispiel wurde keine Pufferobergrenze festgelegt. Bei übermäßiger Tokengröße kann bei dem Code ein <xref:System.OutOfMemoryException>-Ausnahmefehler auftreten. Dies kann vorkommen, wenn der JSON-Code ein ungefähr 1 GB großes oder größeres Token enthält, da das Token bei Verdoppelung von 1 GB nicht mehr in einen `int32`-Puffer passt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md)
* [Migrieren von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
