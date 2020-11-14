---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
description: Hier erfahren Sie, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Enthält Beispielcode.
ms.date: 11/05/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2c1358b2b63a92cb50b853043adbfaae23ccd897
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329871"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Serialisieren und Deserialisieren (Marshallen und Marshallen rückgängig machen) von JSON-Daten in .NET

Dieser Artikel veranschaulicht, wie Sie mithilfe des <xref:System.Text.Json?displayProperty=fullName>-Namespace Daten in das JSON-Format (JavaScript Object Notation) serialisieren und daraus deserialisieren. Wenn Sie vorhandenen Code aus `Newtonsoft.Json` portieren, finden Sie weitere Informationen unter [Migrieren zu `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).

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

Attribute aus dem Namespace <xref:System.Runtime.Serialization> werden in `System.Text.Json` nicht unterstützt.

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

Im Folgenden finden Sie eine Beispielklasse, die die Sammlungstypeigenschaften und einen benutzerdefinierten Typen enthält:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> „POCO“ steht für [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object). Ein POCO ist ein .NET-Typ, der von keinen frameworkspezifischen Typen abhängig ist (z. B. durch Vererbung oder Attribute).

Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus. Die JSON-Ausgabe wird standardmäßig verkleinert:

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

Im folgenden Beispiel wird derselbe JSON-Code dargestellt, allerdings in formatierter Form (d. h. übersichtlich mit Zwischenräumen und Einzügen):

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
::: zone pivot="dotnet-5-0"

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [zu ignorierende Eigenschaften angeben](#ignore-properties).
* Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.
* JSON wird standardmäßig verkleinert. Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen. Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](#customize-json-names-and-values).
* Zirkelbezüge werden standardmäßig erkannt und entsprechende Ausnahmen ausgelöst. Sie können [Verweise beibehalten und Zirkelbezüge behandeln](#preserve-references-and-handle-circular-references).
* [Felder](../../csharp/programming-guide/classes-and-structs/fields.md) werden standardmäßig ignoriert. Sie können [Felder einschließen](#include-fields).

Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen. Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [zu ignorierende Eigenschaften angeben](#ignore-properties).
* Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.
* JSON wird standardmäßig verkleinert. Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen. Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](#customize-json-names-and-values).
* Zirkelbezüge werden erkannt und daraufhin Ausnahmen ausgelöst.
* [Felder](../../csharp/programming-guide/classes-and-structs/fields.md) werden ignoriert.
::: zone-end

Unter anderem unterstützte Typen:
::: zone pivot="dotnet-5-0"

* .NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.
* benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)
* Eindimensionale und Jagged Arrays (`T[][]`).
* Sammlungen und Wörterbücher aus den folgenden Namespaces.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* .NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.
* benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)
* Eindimensionale und Jagged Arrays (`ArrayName[][]`).
* Ein `Dictionary<string,TValue>`, wobei `TValue` ein `object` ist, ein `JsonElement` oder ein POCO.
* Sammlungen aus den folgenden Namespaces.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Lesen von JSON in .NET-Objekte (Deserialisieren)

Um aus einer Zeichenfolge oder einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode auf.

Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecastWithPOCOs`-Klasse erstellt, die schon zuvor im [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:

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

Beim Deserialisieren von JSON-Code gelten die folgenden Verhaltensweisen:

::: zone pivot="dotnet-5-0"

* Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet. Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](#case-insensitive-property-matching).
* Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Nicht öffentliche Konstruktoren werden vom Serialisierungsmodul ignoriert.
* Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt. Weitere Informationen finden Sie unter [Unveränderliche Typen und Datensätze](#immutable-types-and-records).
* Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt. Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](#enums-as-strings).
* Felder werden standardmäßig ignoriert. Sie können [Felder einschließen](#include-fields).
* Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus. Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).
* Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.

Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen. Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet. Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](#case-insensitive-property-matching). ASP.NET Core-Apps [unterscheiden standardmäßig Groß-/Kleinschreibung nicht](#web-defaults-for-jsonserializeroptions).
* Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Ein parameterloser Konstruktor, der öffentlich, intern oder privat sein kann, wird für die Deserialisierung verwendet.
* Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.
* Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt. Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](#enums-as-strings).
* Felder werden nicht unterstützt.
* Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus. Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).
* Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.

Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen. Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).
::: zone-end

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

## <a name="include-fields"></a>Einschließen von Feldern

::: zone pivot="dotnet-5-0"
Verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> oder das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), um Felder bei der Serialisierung oder Deserialisierung einzuschließen (siehe folgendes Beispiel):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="15,17,19,31":::

Verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>, um schreibgeschützte Felder zu ignorieren.
::: zone-end

::: zone pivot="dotnet-core-3-1"
Felder werden in .NET Core 3.1 in System.Text.Json nicht unterstützt. [Benutzerdefinierte Konverter](system-text-json-converters-how-to.md) können diese Funktionalität bereitstellen.
::: zone-end

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

## <a name="ignore-properties"></a>Ignorieren von Eigenschaften

Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Wenn Sie möchten, dass einige von ihnen nicht in der JSON-Ausgabe vorkommen, haben Sie mehrere Möglichkeiten. In diesem Abschnitt wird erläutert, wie Sie Folgendes ignorieren können:

::: zone pivot="dotnet-5-0"

* [Einzelne Eigenschaften](#ignore-individual-properties)
* [ Alle schreibgeschützten Eigenschaften](#ignore-all-read-only-properties)
* [Alle Nullwert-Eigenschaften](#ignore-all-null-value-properties)
* [Alle Eigenschaften mit Standardwert](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [Einzelne Eigenschaften](#ignore-individual-properties)
* [ Alle schreibgeschützten Eigenschaften](#ignore-all-read-only-properties)
* [Alle Nullwert-Eigenschaften](#ignore-all-null-value-properties)
::: zone-end

### <a name="ignore-individual-properties"></a>Ignorieren einzelner Eigenschaften

Um einzelne Eigenschaften zu ignorieren, verwenden Sie das Attribut [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).

Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
Sie können einen bedingten Ausschluss angeben, indem Sie die Eigenschaft `Condition` des Attributs [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) festlegen. Die Enumeration <xref:System.Text.Json.Serialization.JsonIgnoreCondition> bietet die folgenden Optionen:

* `Always`: Die Eigenschaft wird stets ignoriert. Wenn `Condition` nicht angegeben ist, wird diese Option angenommen.
* `Never`: Die Eigenschaft wird stets serialisiert und deserialisiert, und zwar unabhängig von den globalen Einstellungen `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` und `IgnoreReadOnlyFields`.
* `WhenWritingDefault`: Die Eigenschaft wird bei der Serialisierung ignoriert, wenn es sich um den Verweistyp `null` oder den Werttyp `default` handelt.
* `WhenWritingNull`: Die Eigenschaft wird bei der Serialisierung ignoriert, wenn es sich um den Verweistyp `null` handelt.

Das folgende Beispiel veranschaulicht die Verwendung der Eigenschaft `Condition` des Attributs [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

### <a name="ignore-all-read-only-properties"></a>Ignorieren aller schreibgeschützten Eigenschaften

Eine Eigenschaft ist schreibgeschützt, wenn sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält. Um alle schreibgeschützten Eigenschaften bei der Serialisierung zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest:

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

::: zone pivot="dotnet-5-0"
Diese Option gilt nur für Eigenschaften. Um schreibgeschützte Felder beim [Serialisieren von Feldern](#include-fields) zu ignorieren, verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.
::: zone-end

### <a name="ignore-all-null-value-properties"></a>Ignorieren aller Eigenschaften mit dem Wert NULL

::: zone pivot="dotnet-5-0"
Um alle Eigenschaften mit dem Wert NULL zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> auf <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull> fest:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
Um bei der Serialisierung alle Eigenschaften mit dem Wert NULL zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> auf `true` fest:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

Hier finden Sie ein zu serialisierendes Beispielobjekt und die JSON-Ausgabe:

|Eigenschaft |Wert  |
|---------|---------|
| Datum    | 8/1/2019 12:00:00 AM -07:00|
| TemperatureCelsius| 25 |
| Zusammenfassung| NULL|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

### <a name="ignore-all-default-value-properties"></a>Ignorieren aller Eigenschaften mit Standardwert

::: zone pivot="dotnet-5-0"
Um die Serialisierung von Standardwerten in Werttypeigenschaften zu verhindern, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> auf <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> fest:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

Die Einstellung `WhenWritingDefault` verhindert auch die Serialisierung von Verweistypeigenschaften mit dem Wert NULL.

::: zone pivot="dotnet-core-3-1"
Es gibt keine in . NET Core 3.1 integrierte Möglichkeit, die Serialisierung von Eigenschaften mit Standardwerttypen in System.Text.Json zu verhindern.
::: zone-end

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

Wenn Sie den angezeigten JSON-Code in den gezeigten Typ deserialisieren, gibt es keinen Ort mehr für die Eigenschaften `DatesAvailable` und `SummaryWords`, und sie gehen verloren. Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das Attribut [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) auf eine Eigenschaft des Typs `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:

|Eigenschaft |Wert  |Hinweise  |
|---------|---------|---------|
| Datum    | 8/1/2019 12:00:00 AM -07:00||
| TemperatureCelsius| 0 | Keine Übereinstimmung unter Berücksichtigung von Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die Eigenschaft nicht festgelegt wird. |
| Zusammenfassung | Heiß ||
| ExtensionData | temperatureCelsius: 25 |Da die Groß-/Kleinschreibung nicht übereinstimmte, ist diese JSON-Eigenschaft ein zusätzliches Element und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.|
|| DatesAvailable:<br>  8/1/2019 12:00:00 AM -07:00<br>8/2/2019 12:00:00 AM -07:00 |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|
| |SummaryWords:<br>Toll<br>Windig<br>Feucht |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|

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

## <a name="preserve-references-and-handle-circular-references"></a>Beibehalten von Verweisen und Behandeln von Zirkelbezügen

::: zone pivot="dotnet-5-0"

Um Verweise beizubehalten und Zirkelbezüge zu behandeln, legen Sie <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> auf <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A> fest. Diese Einstellung bewirkt folgendes Verhalten:

* Beim Serialisieren:

  Beim Schreiben komplexer Typen schreibt das Serialisierungsmodul auch Metadateneigenschaften (`$id`, `$values` und `$ref`).

* Beim Deserialisieren:

  Metadaten werden erwartet (obwohl nicht zwingend erforderlich), und der Deserialisierer versucht, sie zu verstehen.

Der folgende Code veranschaulicht die Verwendung der Einstellung `Preserve`.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

Dieses Feature kann nicht verwendet werden, um Wert- oder unveränderliche Typen beizubehalten. Bei der Deserialisierung wird die Instanz eines unveränderlichen Typs erstellt, nachdem die gesamten Nutzdaten gelesen wurden. Daher wäre es unmöglich, dieselbe Instanz zu deserialisieren, wenn ein Verweis darauf in den JSON-Nutzdaten vorhanden ist.

Für Werttypen, unveränderliche Typen und Arrays werden keine Verweismetadaten serialisiert. Bei der Deserialisierung wird eine Ausnahme ausgelöst, wenn `$ref` oder `$id` gefunden wird. Werttypen ignorieren jedoch `$id` (und `$values` im Falle von Sammlungen), um die Deserialisierung von Nutzdaten zu ermöglichen, die mit Newtonsoft.Json serialisiert wurden.  Newtonsoft.Json serialisiert die Metadaten für solche Typen.

Um festzustellen, ob Objekte gleich sind, wird <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType> von System.Text.Json verwendet. Dabei wird beim Vergleich zweier Objektinstanzen die Verweisgleichheit (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) anstelle der Wertgleichheit (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>) verwendet.

Weitere Informationen zur Serialisierung und Deserialisierung von Verweisen finden Sie unter <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.

Die <xref:System.Text.Json.Serialization.ReferenceResolver>-Klasse definiert das Verhalten bei Beibehaltung von Verweisen für Serialisierung und Deserialisierung. Erstellen Sie eine abgeleitete Klasse, um benutzerdefiniertes Verhalten anzugeben. Ein Beispiel finden Sie unter [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).

::: zone-end

::: zone pivot="dotnet-core-3-1"
System.Text.Json in .NET Core 3.1 unterstützt nur die Serialisierung nach Wert und löst bei Zirkelbezügen eine Ausnahme aus.
::: zone-end

## <a name="allow-or-write-numbers-in-quotes"></a>Zulassen oder Schreiben von Zahlen in Anführungszeichen

::: zone pivot="dotnet-5-0"

Einige Serialisierungsmodule codieren Zahlen als (in Anführungszeichen eingeschlossene) JSON-Zeichenfolgen. Beispiel: `{"DegreesCelsius":"23"}` statt `{"DegreesCelsius":23}`. Um Zahlen in Anführungszeichen zu serialisieren oder Zahlen in Anführungszeichen im gesamten Graphen des Eingabeobjekts zu akzeptieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> wie im folgenden Beispiel gezeigt fest:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-28":::

Wenn Sie System.Text.Json indirekt über ASP.NET Core verwenden, sind beim Deserialisieren Zahlen in Anführungszeichen erlaubt, da ASP.NET Core [Webstandardoptionen](xref:System.Text.Json.JsonSerializerDefaults.Web) angibt.

Um Zahlen in Anführungszeichen für bestimmte Eigenschaften, Felder oder Typen zuzulassen oder zu schreiben, verwenden Sie das Attribut [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).
::: zone-end

::: zone pivot="dotnet-core-3-1"
System.Text.Json in .NET Core 3.1 unterstützt keine Serialisierung oder Deserialisierung von Zahlen in Anführungszeichen. Weitere Informationen finden Sie unter [Zulassen oder Schreiben von Zahlen in Anführungszeichen](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).
::: zone-end

## <a name="immutable-types-and-records"></a>Unveränderliche Typen und Datensätze

::: zone pivot="dotnet-5-0"
System.Text.Json kann einen parametrisierten Konstruktor verwenden, der es ermöglicht, eine unveränderliche Klasse oder Struktur zu deserialisieren. Wenn für eine Klasse der einzige Konstruktor ein parametrisierter ist, wird dieser Konstruktor verwendet. Geben Sie für eine Struktur oder Klasse mit mehreren Konstruktoren den zu verwendenden Konstruktor an, indem Sie das Attribut [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) anwenden. Wenn das Attribut nicht verwendet wird, wird, sofern vorhanden, stets ein öffentlicher parameterloser Konstruktor verwendet. Das Attribut kann nur mit öffentlichen Konstruktoren verwendet werden. Im folgenden Beispiel wird das Attribut `[JsonConstructor]` hinzugefügt:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

Datensätze in C# 9 werden, wie im folgenden Beispiel gezeigt, ebenfalls unterstützt:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

Informationen zu Typen, die unveränderlich sind, weil alle ihre Eigenschaftssetter nicht öffentlich sind, finden Sie im folgenden Abschnitt über [nicht öffentliche Eigenschaftenaccessoren](#non-public-property-accessors).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`JsonConstructorAttribute` und C# 9-Datensätze werden in .NET Core 3.1 nicht unterstützt.
::: zone-end

## <a name="non-public-property-accessors"></a>Nicht öffentliche Eigenschaftenaccessoren

::: zone pivot="dotnet-5-0"
Um die Verwendung eines nicht öffentlichen Eigenschaftenaccessors zu aktivieren, verwenden Sie das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Nicht öffentliche Eigenschaftenaccessoren werden in .NET Core 3.1 nicht unterstützt. Weitere Informationen finden Sie im Artikel [Migration von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).
::: zone-end

## <a name="copy-jsonserializeroptions"></a>Kopieren von JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Es gibt einen [JsonSerializerOptions-Konstruktor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)), mit dem Sie eine neue Instanz mit den Optionen einer vorhandenen Instanz erstellen können, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Ein Konstruktor des Typs `JsonSerializerOptions`, der eine vorhandene Instanz verwendet, steht in .NET Core 3.1 nicht zur Verfügung.
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a>Webstandardwerte für JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

Es gibt einen [JsonSerializerOptions-Konstruktor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true), mit dem Sie eine neue Instanz mit den Standardoptionen erstellen können, die ASP.NET Core für Web-Apps verwendet (siehe folgendes Beispiel):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

Ein Konstruktor des Typs `JsonSerializerOptions`, der eine Gruppe von Standardwerten angibt, steht in .NET Core 3.1 nicht zur Verfügung.
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a>Erweiterungsmethoden für HttpClient und HttpContent

::: zone pivot="dotnet-5-0"

Das Serialisieren und Deserialisieren von aus dem Netzwerk stammenden JSON-Nutzdaten sind gängige Vorgänge. Erweiterungsmethoden für [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) und [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) ermöglichen Ihnen das Ausführen dieser Vorgänge in einer einzelnen Codezeile. Diese Erweiterungsmethoden verwenden [Webstandardwerte für JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).

Im folgenden Beispiel wird die Verwendung von <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> und <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> veranschaulicht:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="23,30":::

Es gibt auch Erweiterungsmethoden für System.Text.Json für [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).
::: zone-end

::: zone pivot="dotnet-core-3-1"
Erweiterungsmethoden für `HttpClient` und `HttpContent` sind in System.Text.Json in .NET Core 3.1 nicht verfügbar.
::: zone-end

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
* Der Puffer muss mindestens so groß wie die größte Sequenz von Leerraum innerhalb der JSON-Nutzdaten sein.
* Der Reader verfolgt die gelesenen Daten nicht nach, bis er den nächsten <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in der JSON-Nutzlast vollständig gelesen hat. Wenn im Puffer noch Bytes vorhanden sind, müssen Sie sie wieder dem Reader übergeben. Sie können <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> verwenden, um zu bestimmen, wie viele Bytes übrig bleiben.

Im folgenden Code wird veranschaulicht, wie aus einem Stream gelesen wird. Das Beispiel zeigt einen <xref:System.IO.MemoryStream>. Ähnlicher Code funktioniert mit einem <xref:System.IO.FileStream>, es sei denn, der `FileStream` enthält am Anfang eine UTF-8-BOM. In diesem Fall müssen Sie diese drei Bytes aus dem Puffer entfernen, bevor Sie die verbleibenden Bytes an den `Utf8JsonReader` übergeben. Andernfalls würde der Reader eine Ausnahme auslösen, da die BOM nicht als gültiger Teil des JSON-Codes angesehen wird.

Der Beispielcode beginnt mit einem 4 KB großen Puffer und verdoppelt die Puffergröße jedes Mal, wenn festgestellt wird, dass die Größe nicht ausreicht, um ein komplettes JSON-Token aufzunehmen. Dies ist erforderlich, damit der Reader mit den JSON-Nutzdaten vorankommt. Das JSON-Beispiel im Codeausschnitt löst nur dann eine Erhöhung der Puffergröße aus, wenn Sie eine sehr geringe Anfangspuffergröße festlegen, z. B. 10 Bytes. Die `Console.WriteLine`-Anweisungen zeigen Ursache und Auswirkung der Puffergrößenerhöhungen, wenn Sie die Anfangspuffergröße auf 10 festlegen. Bei der Anfangspuffergröße von 4 KB wird das gesamte JSON-Beispiel von jeder `Console.WriteLine` angezeigt, und die Puffergröße muss nie erhöht werden.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

Im vorherigen Beispiel wurde keine Pufferobergrenze festgelegt. Bei übermäßiger Tokengröße kann bei dem Code ein <xref:System.OutOfMemoryException>-Ausnahmefehler auftreten. Dies kann vorkommen, wenn der JSON-Code ein ungefähr 1 GB großes oder größeres Token enthält, da das Token bei Verdoppelung von 1 GB nicht mehr in einen `int32`-Puffer passt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md)
* [Migrieren von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
