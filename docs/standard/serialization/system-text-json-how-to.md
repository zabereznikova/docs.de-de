---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
description: Hier erfahren Sie, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Enthält Beispielcode.
ms.date: 12/02/2020
ms.custom: contperfq2
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 1ea4ff71b9e21bd7c5b12598581b33e1e96ebb19
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008837"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Serialisieren und Deserialisieren (Marshallen und Marshallen rückgängig machen) von JSON-Daten in .NET

Dieser Artikel veranschaulicht, wie Sie mithilfe des <xref:System.Text.Json?displayProperty=fullName>-Namespace Daten in das JSON-Format (JavaScript Object Notation) serialisieren und daraus deserialisieren. Wenn Sie vorhandenen Code aus `Newtonsoft.Json` portieren, finden Sie weitere Informationen unter [Migrieren zu `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).

Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework wie [ASP.NET Core](/aspnet/core/).

Im größten Teil des Serialisierungsbeispielcodes ist <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` festgelegt, um den JSON-Code übersichtlicher zu gestalten (mit Einzügen und Zwischenräumen für bessere Lesbarkeit). Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.

Die Codebeispiele verweisen auf die folgende Klasse und deren Varianten:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a>Namespaces

Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen. Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind. Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Anweisungen für einen oder beide Namespaces:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> Attribute aus dem Namespace <xref:System.Runtime.Serialization> werden in `System.Text.Json` nicht unterstützt.

## <a name="how-to-write-net-objects-as-json-serialize"></a>Schreiben von .NET-Objekten in JSON (Serialisieren)

Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, rufen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode auf.

Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

In den vorangehenden Beispielen wird Typrückschluss für den zu serialisierenden Typ verwendet. Eine Überladung von `Serialize()` akzeptiert einen generischen Typparameter:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a>Serialisierungsbeispiel

Im Folgenden finden Sie eine Beispielklasse, die die Sammlungstypeigenschaften und einen benutzerdefinierten Typen enthält:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> „POCO“ steht für [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object). Ein POCO ist ein .NET-Typ, der von keinen frameworkspezifischen Typen abhängig ist (z. B. durch Vererbung oder Attribute).

Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus. Die JSON-Ausgabe wird standardmäßig minimiert (Zeichen für Leerraum, Einzug und Zeilenumbruch werden entfernt):

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

## <a name="serialize-to-utf-8"></a>Serialisieren in UTF-8

Um in UTF-8 zu serialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode auf:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A>-Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> akzeptiert, ist ebenfalls verfügbar.

Das Serialisieren in UTF-8 ist ungefähr 5–10 % schneller als die Verwendung von zeichenfolgenbasierten Methoden. Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.

## <a name="serialization-behavior"></a>Serialisierungsverhalten

::: zone pivot="dotnet-5-0"

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [zu ignorierende Eigenschaften angeben](system-text-json-ignore-properties.md).
* Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.
* JSON wird standardmäßig verkleinert. Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen. Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](system-text-json-customize-properties.md).
* Zirkelbezüge werden standardmäßig erkannt und entsprechende Ausnahmen ausgelöst. Sie können [Verweise beibehalten und Zirkelbezüge behandeln](system-text-json-preserve-references.md).
* [Felder](../../csharp/programming-guide/classes-and-structs/fields.md) werden standardmäßig ignoriert. Sie können [Felder einschließen](#include-fields).

Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen. Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [zu ignorierende Eigenschaften angeben](system-text-json-ignore-properties.md).
* Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.
* JSON wird standardmäßig verkleinert. Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen. Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](system-text-json-customize-properties.md).
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

## <a name="how-to-read-json-as-net-objects-deserialize"></a>Lesen von JSON als .NET-Objekte (Deserialisieren)

Um aus einer Zeichenfolge oder einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode auf.

Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecastWithPOCOs`-Klasse erstellt, die schon zuvor im [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

Um mithilfe von synchronem Code aus einer Datei zu deserialisieren, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode auf:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a>Deserialisieren aus UTF-8

Um aus UTF-8 zu deserialisieren, rufen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung auf, die einen `ReadOnlySpan<byte>` oder ein `Utf8JsonReader` akzeptiert, wie in den folgenden Beispielen gezeigt. In den Beispielen wird vorausgesetzt, dass sich das JSON in einem Bytearray namens „jsonUtf8Bytes“ befindet.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a>Deserialisierungsverhalten

Beim Deserialisieren von JSON-Code gelten die folgenden Verhaltensweisen:

::: zone pivot="dotnet-5-0"

* Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet. Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](system-text-json-character-casing.md).
* Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Nicht öffentliche Konstruktoren werden vom Serialisierungsmodul ignoriert.
* Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt. Weitere Informationen finden Sie unter [Unveränderliche Typen und Datensätze](system-text-json-immutability.md).
* Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt. Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](system-text-json-customize-properties.md#enums-as-strings).
* Felder werden standardmäßig ignoriert. Sie können [Felder einschließen](#include-fields).
* Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus. Sie können [Kommentare und nachfolgende Kommas zulassen](system-text-json-invalid-json.md).
* Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.

Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen. Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet. Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](system-text-json-character-casing.md). ASP.NET Core-Apps [unterscheiden standardmäßig Groß-/Kleinschreibung nicht](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
* Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Ein parameterloser Konstruktor, der öffentlich, intern oder privat sein kann, wird für die Deserialisierung verwendet.
* Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.
* Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt. Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](system-text-json-customize-properties.md#enums-as-strings).
* Felder werden nicht unterstützt.
* Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus. Sie können [Kommentare und nachfolgende Kommas zulassen](system-text-json-invalid-json.md).
* Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.

Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen. Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="serialize-to-formatted-json"></a>Serialisieren in formatierten JSON-Code

Um die JSON-Ausgabe übersichtlich zu formatieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

Hier sehen Sie einen zu serialisierenden Beispieltyp und die übersichtlich formatierte JSON-Ausgabe:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Wenn Sie `JsonSerializerOptions` wiederholt mit den gleichen Optionen verwenden, sollten Sie nicht bei jeder Verwendung eine neue `JsonSerializerOptions`-Instanz erstellen. Verwenden Sie für jeden Aufruf dieselbe Instanz. Weitere Informationen finden Sie unter [Wiederverwenden von JsonSerializerOptions-Instanzen](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).

## <a name="include-fields"></a>Einschließen von Feldern

::: zone pivot="dotnet-5-0"
Verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> oder das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), um Felder bei der Serialisierung oder Deserialisierung einzuschließen (siehe folgendes Beispiel):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

Verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>, um schreibgeschützte Felder zu ignorieren.
::: zone-end

::: zone pivot="dotnet-core-3-1"
Felder werden in .NET Core 3.1 in System.Text.Json nicht unterstützt. [Benutzerdefinierte Konverter](system-text-json-converters-how-to.md) können diese Funktionalität bereitstellen.
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a>Erweiterungsmethoden für HttpClient und HttpContent

::: zone pivot="dotnet-5-0"

Das Serialisieren und Deserialisieren von aus dem Netzwerk stammenden JSON-Nutzdaten sind gängige Vorgänge. Erweiterungsmethoden für [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) und [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) ermöglichen Ihnen das Ausführen dieser Vorgänge in einer einzelnen Codezeile. Diese Erweiterungsmethoden verwenden [Webstandardwerte für JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).

Im folgenden Beispiel wird die Verwendung von <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> und <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> veranschaulicht:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

Es gibt auch Erweiterungsmethoden für System.Text.Json für [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).
::: zone-end

::: zone pivot="dotnet-core-3-1"
Erweiterungsmethoden für `HttpClient` und `HttpContent` sind in System.Text.Json in .NET Core 3.1 nicht verfügbar.
::: zone-end

## <a name="see-also"></a>Weitere Informationen

* [System.Text.Json – Übersicht](system-text-json-overview.md)
* [Instanziieren von JsonSerializerOptions-Instanzen](system-text-json-configure-options.md)
* [Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung](system-text-json-character-casing.md)
* [Anpassen von Eigenschaftsnamen und -werten](system-text-json-customize-properties.md)
* [Ignorieren von Eigenschaften](system-text-json-ignore-properties.md)
* [Zulassen von ungültigem JSON-Code](system-text-json-invalid-json.md)
* [Verarbeiten von Überlauf-JSON](system-text-json-handle-overflow.md)
* [Beibehalten von Verweisen](system-text-json-preserve-references.md)
* [Unveränderliche Typen und nicht öffentliche Zugriffsmethoden](system-text-json-immutability.md)
* [Polymorphe Serialisierung](system-text-json-polymorphism.md)
* [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Anpassen der Zeichencodierung](system-text-json-character-encoding.md)
* [Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer](write-custom-serializer-deserializer.md)
* [Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung](system-text-json-converters-how-to.md)
* [Unterstützung von DateTime und DateTimeOffset](../datetime/system-text-json-support.md)
* [System.Text.Json-API-Referenz](xref:System.Text.Json)
* [System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)
