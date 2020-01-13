---
title: Serialisieren und Deserialisieren von JSON mit C# -.NET
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 047d5b5c6fa339089d2054eb6bfe8b3066c1d00c
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904657"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="1ac5c-102">Serialisieren und Deserialisieren (Mars Hallen und Unmarshalling) von JSON in .net</span><span class="sxs-lookup"><span data-stu-id="1ac5c-102">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="1ac5c-103">In diesem Artikel wird gezeigt, wie Sie den <xref:System.Text.Json>-Namespace zum Serialisieren und Deserialisieren in und aus JavaScript Object Notation (JSON) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="1ac5c-104">Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework, wie z. b. [ASP.net Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="1ac5c-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="1ac5c-105">Der größte Teil des Serialisierungsbeispielcodes legt <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest, um die JSON-Datei formatiert auszugeben (mit Einzügen und Leerraum für bessere Lesbarkeit).</span><span class="sxs-lookup"><span data-stu-id="1ac5c-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="1ac5c-106">In der produktiven Umgebung würden Sie für diese Einstellung in der Regel den Standardwert `false` beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="1ac5c-107">-Namespaces</span><span class="sxs-lookup"><span data-stu-id="1ac5c-107">Namespaces</span></span>

<span data-ttu-id="1ac5c-108">Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="1ac5c-109">Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="1ac5c-110">Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Direktiven für einen oder beide Namespaces:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="1ac5c-111">Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden derzeit in `System.Text.Json` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="1ac5c-112">Schreiben von .NET-Objekten in JSON (Serialisieren)</span><span class="sxs-lookup"><span data-stu-id="1ac5c-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="1ac5c-113">Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, müssen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1ac5c-114">Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-115">Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-116">Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-117">In den vorangehenden Beispielen wird der Typrückschluss für den serialisierten Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="1ac5c-118">Eine Überladung von `Serialize()` nimmt einen generischen Typparameter an:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="1ac5c-119">Beispiel für die Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1ac5c-119">Serialization example</span></span>

<span data-ttu-id="1ac5c-120">Im Folgenden finden Sie eine Beispiel-Klasse, die Auflistungen und eine geschachtelte Klasse enthält:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="1ac5c-121">Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="1ac5c-122">Die JSON-Ausgabe wird standardmäßig minimiert:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="1ac5c-123">Im folgenden Beispiel wird derselbe JSON-Code dargestellt, der formatiert ist (d. h. mit Leerraum und Einzug):</span><span class="sxs-lookup"><span data-stu-id="1ac5c-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="1ac5c-124">In UTF-8 serialisieren</span><span class="sxs-lookup"><span data-stu-id="1ac5c-124">Serialize to UTF-8</span></span>

<span data-ttu-id="1ac5c-125">Um zu UTF-8 zu serialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode aufrufen:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-126">Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A> Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> annimmt, ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="1ac5c-127">Die Serialisierung in UTF-8 ist ungefähr 5-10 % schneller als die Verwendung der auf Zeichenfolgen basierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="1ac5c-128">Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="1ac5c-129">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="1ac5c-129">Serialization behavior</span></span>

* <span data-ttu-id="1ac5c-130">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="1ac5c-131">Sie können [Eigenschaften angeben, die ausgeschlossen werden sollen](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="1ac5c-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="1ac5c-132">Der [Standard-Encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) schützt Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [der RFC 8259 JSON-Spezifikation](https://tools.ietf.org/html/rfc8259#section-7) mit Escapezeichen versehen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1ac5c-133">Standardmäßig wird JSON minimiert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-133">By default, JSON is minified.</span></span> <span data-ttu-id="1ac5c-134">Sie können [JSON formatiert ausgeben](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="1ac5c-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1ac5c-135">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen den .NET-Namen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1ac5c-136">Sie können die [Schreibweise der JSON-Namen anpassen](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="1ac5c-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="1ac5c-137">Zirkuläre Verweise werden erkannt, und Ausnahmen werden ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-137">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="1ac5c-138">Felder werden derzeit ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-138">Currently, fields are excluded.</span></span>

<span data-ttu-id="1ac5c-139">Folgende Typen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-139">Supported types include:</span></span>

* <span data-ttu-id="1ac5c-140">.Net-primitive, die JavaScript-primitiven zugeordnet sind, z. b. numerische Typen, Zeichen folgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-140">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1ac5c-141">Benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition)</span><span class="sxs-lookup"><span data-stu-id="1ac5c-141">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="1ac5c-142">Eindimensionale und verzweigte Arrays (`ArrayName[][]`)</span><span class="sxs-lookup"><span data-stu-id="1ac5c-142">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="1ac5c-143">`Dictionary<string,TValue>`, wo `TValue` ein `object`, `JsonElement` oder ein POCO ist</span><span class="sxs-lookup"><span data-stu-id="1ac5c-143">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="1ac5c-144">Sammlungen aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-144">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="1ac5c-145">Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md), um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-145">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="1ac5c-146">Lesen von JSON in .NET-Objekte (Deserialisieren)</span><span class="sxs-lookup"><span data-stu-id="1ac5c-146">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="1ac5c-147">Um eine Zeichenfolge oder eine Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-147">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1ac5c-148">Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecast`-Klasse erstellt, die zuvor für das [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-148">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="1ac5c-149">Wenn Sie aus einer Datei mithilfe von synchronem Code deserialisieren möchten, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-149">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="1ac5c-150">Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode aufrufen:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-150">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="1ac5c-151">Aus UTF-8 deserialisieren</span><span class="sxs-lookup"><span data-stu-id="1ac5c-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="1ac5c-152">Um aus UTF-8 zu deserialisieren, müssen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung aufrufen, die einen `Utf8JsonReader` oder eine `ReadOnlySpan<byte>` annimmt, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="1ac5c-153">In den Beispielen wird davon ausgegangen, dass sich JSON in einem Bytearray namens jsonUtf8Bytes befindet.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-153">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="1ac5c-154">Deserialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="1ac5c-154">Deserialization behavior</span></span>

* <span data-ttu-id="1ac5c-155">Standardmäßig wird die Groß-/Kleinschreibung bei der Übereinstimmung von Eigenschaften Namen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-155">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1ac5c-156">Sie können die [Groß-/Kleinschreibung](#case-insensitive-property-matching)nicht beachten.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-156">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="1ac5c-157">Wenn der JSON-Wert einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-157">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1ac5c-158">Die Deserialisierung für Verweis Typen ohne Parameter losen Konstruktor wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-158">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="1ac5c-159">Die Deserialisierung zu unveränderlichen Objekten oder schreibgeschützten Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-159">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="1ac5c-160">Standardmäßig werden Enumerationen als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-160">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1ac5c-161">Enumerationsnamen können als Zeichen folgen [serialisiert](#enums-as-strings)werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-161">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="1ac5c-162">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-162">Fields aren't supported.</span></span>
* <span data-ttu-id="1ac5c-163">Standardmäßig lösen Kommentare oder nachfolgende Kommas in der JSON-Datei Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-163">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1ac5c-164">Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="1ac5c-164">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="1ac5c-165">Der Standardwert für die [maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) ist 64.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-165">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1ac5c-166">Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md), um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-166">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="1ac5c-167">Serialisieren in formatierten JSON-Code</span><span class="sxs-lookup"><span data-stu-id="1ac5c-167">Serialize to formatted JSON</span></span>

<span data-ttu-id="1ac5c-168">Um die JSON-Ausgabe zu formatieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-168">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="1ac5c-169">Im Folgenden finden Sie eine Beispielklasse, die serialisiert werden soll, und die formatierte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-169">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="1ac5c-170">Anpassen von JSON-Namen und -Werten</span><span class="sxs-lookup"><span data-stu-id="1ac5c-170">Customize JSON names and values</span></span>

<span data-ttu-id="1ac5c-171">Standardmäßig sind Eigenschaftsnamen und Wörterbuchschlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-171">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="1ac5c-172">Enumerationswerte werden als Zahlen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-172">Enum values are represented as numbers.</span></span> <span data-ttu-id="1ac5c-173">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-173">This section explains how to:</span></span>

* [<span data-ttu-id="1ac5c-174">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-174">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="1ac5c-175">Alle Eigenschaftsnamen in Camel-Case konvertieren</span><span class="sxs-lookup"><span data-stu-id="1ac5c-175">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="1ac5c-176">Implementieren einer benutzerdefinierten Benennungsrichtlinie für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ac5c-176">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="1ac5c-177">Wörterbuchschlüssel in Camel-Case konvertieren</span><span class="sxs-lookup"><span data-stu-id="1ac5c-177">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="1ac5c-178">Enumerationen in Zeichenfolgen und Camel-Case konvertieren</span><span class="sxs-lookup"><span data-stu-id="1ac5c-178">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="1ac5c-179">Für andere Szenarios, die eine besondere Behandlung von JSON-Eigenschaftsnamen und -Werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="1ac5c-179">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="1ac5c-180">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-180">Customize individual property names</span></span>

<span data-ttu-id="1ac5c-181">Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)-Attribut.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-181">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="1ac5c-182">Hier ist ein Beispiel für die Serialisierung und die daraus resultierende JSON-Datei:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-182">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1ac5c-183">Der durch dieses Attribut festgelegte Eigenschaftsname:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-183">The property name set by this attribute:</span></span>

* <span data-ttu-id="1ac5c-184">Gilt in beide Richtungen, für die Serialisierung und Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="1ac5c-184">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="1ac5c-185">Hat Vorrang vor Benennungsrichtlinien für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ac5c-185">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="1ac5c-186">Camel-Case für alle JSON-Eigenschaftsnamen verwenden</span><span class="sxs-lookup"><span data-stu-id="1ac5c-186">Use camel case for all JSON property names</span></span>

<span data-ttu-id="1ac5c-187">Wenn Sie die Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen verwenden möchten, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-187">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="1ac5c-188">Im Folgenden finden Sie eine Beispielklasse zum Serialisieren und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-188">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1ac5c-189">Die Camel-Case-Benennungsrichtlinie für Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-189">The camel case property naming policy:</span></span>

* <span data-ttu-id="1ac5c-190">Gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-190">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="1ac5c-191">Wird von `[JsonPropertyName]`-Attributen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-191">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="1ac5c-192">Aus diesem Grund ist der Name der JSON-Eigenschaft `Wind` im Beispiel nicht Camel-Case.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-192">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="1ac5c-193">Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ac5c-193">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="1ac5c-194">Um eine benutzerdefinierte Benennungsrichtlinie für JSON-Eigenschaften zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und überschreiben Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-194">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="1ac5c-195">Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihrer Benennungsrichtlinienklasse fest:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-195">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-196">Im Folgenden finden Sie eine Beispielklasse zum Serialisieren und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-196">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1ac5c-197">Die Benennungsrichtlinie für JSON-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-197">The JSON property naming policy:</span></span>

* <span data-ttu-id="1ac5c-198">Gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-198">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="1ac5c-199">Wird von `[JsonPropertyName]`-Attributen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-199">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="1ac5c-200">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-200">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="1ac5c-201">Camel-Case Wörterbuchschlüssel</span><span class="sxs-lookup"><span data-stu-id="1ac5c-201">Camel case dictionary keys</span></span>

<span data-ttu-id="1ac5c-202">Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die `string`-Schlüssel in die Camel-Case-Schreibweise konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-202">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="1ac5c-203">Legen Sie dazu die <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-203">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-204">Das Serialisieren eines Objekts mit einem Wörterbuch mit dem Namen `TemperatureRanges`, das Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` hat, führt zu einer JSON-Ausgabe wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-204">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="1ac5c-205">Die Camel-Case-Benennungsrichtlinie für Wörterbuchschlüssel gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-205">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="1ac5c-206">Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel denen in der JSON-Datei, auch wenn Sie `JsonNamingPolicy.CamelCase` als `DictionaryKeyPolicy` angeben.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-206">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="1ac5c-207">Enumerationen als Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-207">Enums as strings</span></span>

<span data-ttu-id="1ac5c-208">Standardmäßig werden Enumerationen als Zahlen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-208">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="1ac5c-209">Verwenden Sie den <xref:System.Text.Json.Serialization.JsonStringEnumConverter>, um Enumerationsnamen als Zeichenfolgen zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-209">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="1ac5c-210">Nehmen Sie beispielsweise an, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-210">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="1ac5c-211">Wenn die Summary-Eigenschaft `Hot` ist, hat die serialisierte JSON standardmäßig den numerischen Wert 3:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-211">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="1ac5c-212">Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-212">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-213">Der resultierende JSON-Code sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-213">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="1ac5c-214">Enumerationsnamen-Zeichenfolgen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-214">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="1ac5c-215">Eigenschaften von der Serialisierung ausschließen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-215">Exclude properties from serialization</span></span>

<span data-ttu-id="1ac5c-216">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-216">By default, all public properties are serialized.</span></span> <span data-ttu-id="1ac5c-217">Wenn Sie möchten, dass einige von ihnen nicht in der JSON-Ausgabe angezeigt werden, haben Sie mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-217">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="1ac5c-218">In diesem Abschnitt wird erläutert, wie verschiedene Dinge ausgeschlossen werden können:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-218">This section explains how to exclude:</span></span>

* [<span data-ttu-id="1ac5c-219">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ac5c-219">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="1ac5c-220">Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ac5c-220">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="1ac5c-221">Alle NULL-Wert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ac5c-221">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="1ac5c-222">Einzelne Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-222">Exclude individual properties</span></span>

<span data-ttu-id="1ac5c-223">Verwenden Sie das [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)-Attribut, um einzelne Eigenschaften zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-223">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="1ac5c-224">Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-224">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="1ac5c-225">Alle schreibgeschützten Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-225">Exclude all read-only properties</span></span>

<span data-ttu-id="1ac5c-226">Eine Eigenschaft ist schreibgeschützt, wenn Sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-226">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="1ac5c-227">Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-227">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-228">Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-228">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="1ac5c-229">Diese Option gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-229">This option applies only to serialization.</span></span> <span data-ttu-id="1ac5c-230">Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-230">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="1ac5c-231">Alle Eigenschaften mit NULL-Wert ausschließen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-231">Exclude all null value properties</span></span>

<span data-ttu-id="1ac5c-232">Um alle Eigenschaften mit NULL-Werten auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-232">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-233">Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-233">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="1ac5c-234">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1ac5c-234">Property</span></span> |<span data-ttu-id="1ac5c-235">Wert</span><span class="sxs-lookup"><span data-stu-id="1ac5c-235">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="1ac5c-236">date</span><span class="sxs-lookup"><span data-stu-id="1ac5c-236">Date</span></span>    | <span data-ttu-id="1ac5c-237">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="1ac5c-237">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="1ac5c-238">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="1ac5c-238">TemperatureCelsius</span></span>| <span data-ttu-id="1ac5c-239">25</span><span class="sxs-lookup"><span data-stu-id="1ac5c-239">25</span></span> |
| <span data-ttu-id="1ac5c-240">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1ac5c-240">Summary</span></span>| <span data-ttu-id="1ac5c-241">NULL</span><span class="sxs-lookup"><span data-stu-id="1ac5c-241">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="1ac5c-242">Diese Einstellung gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-242">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="1ac5c-243">Informationen zu den Auswirkungen auf die Deserialisierung finden Sie unter [Ignorieren von NULL beim Deserialisieren](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="1ac5c-243">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="1ac5c-244">Zeichencodierung anpassen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-244">Customize character encoding</span></span>

<span data-ttu-id="1ac5c-245">Standardmäßig schützt das Serialisierungsprogramm alle nicht-ASCII-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-245">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="1ac5c-246">Das heißt, Sie ersetzt Sie durch `\uxxxx`, wobei `xxxx` der Unicode-Code des Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-246">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="1ac5c-247">Wenn die `Summary`-Eigenschaft z. b. auf Cyrillic-"-Eigenschaft" festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-247">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="1ac5c-248">Serialisieren von Sprachzeichensätzen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-248">Serialize language character sets</span></span>

<span data-ttu-id="1ac5c-249">Wenn Sie die Zeichensätze mindestens einer Sprache ohne Escapezeichen serialisieren möchten, geben Sie einen oder mehrere [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) beim Erstellen einer <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>-Instanz an, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-249">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="1ac5c-250">Mit diesem Code werden kyrillische und griechische Zeichen nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-250">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="1ac5c-251">Wenn die `Summary`-Eigenschaft auf kyrillisch жарко festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-251">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="1ac5c-252">Verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>, um alle Sprachzeichensätze ungeschützt zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-252">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="1ac5c-253">Serialisieren bestimmter Zeichen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-253">Serialize specific characters</span></span>

<span data-ttu-id="1ac5c-254">Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne mit Escapezeichen versehen zu werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-254">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="1ac5c-255">Im folgenden Beispiel werden nur die ersten zwei Zeichen von "..." serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-255">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="1ac5c-256">Im Folgenden finden Sie ein Beispiel für die JSON-Ausgabe, die durch den vorangehenden Code generiert wird:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-256">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="1ac5c-257">Alle Zeichen serialisieren</span><span class="sxs-lookup"><span data-stu-id="1ac5c-257">Serialize all characters</span></span>

<span data-ttu-id="1ac5c-258">Um das Escapezeichen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-258">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="1ac5c-259">Im Vergleich zum Standard-Encoder ist der `UnsafeRelaxedJsonEscaping` Encoder eher für das Zulassen von Zeichen ohne Escapezeichen zulässig:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-259">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="1ac5c-260">Es werden keine HTML-sensiblen Zeichen wie `<`, `>`, `&`und `'`mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-260">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="1ac5c-261">Er bietet keine zusätzlichen Schutzmaßnahmen vor XSS-oder Informations Offenlegungs Angriffen, wie z. b. solche, die sich aus dem Client und dem Server ergeben könnten, die auf dem *CharSet*nicht einverstanden sind.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-261">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="1ac5c-262">Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-262">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="1ac5c-263">Sie können Sie beispielsweise verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8`sendet.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-263">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="1ac5c-264">Gestatten Sie niemals, dass die Roh`UnsafeRelaxedJsonEscaping` Ausgabe in eine HTML-Seite oder ein `<script>` Element ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-264">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="1ac5c-265">Serialisieren von Eigenschaften abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-265">Serialize properties of derived classes</span></span>

<span data-ttu-id="1ac5c-266">Die Serialisierung einer polymorphen Typhierarchie wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-266">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="1ac5c-267">Wenn eine Eigenschaft beispielsweise als eine Schnittstelle oder eine abstrakte Klasse definiert ist, werden nur die Eigenschaften, die für die Schnittstelle oder die abstrakte Klasse definiert sind, serialisiert, auch wenn der Lauf Zeittyp über zusätzliche Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-267">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="1ac5c-268">Die Ausnahmen für dieses Verhalten werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-268">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="1ac5c-269">Nehmen Sie beispielsweise an, Sie verfügen über eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-269">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="1ac5c-270">Angenommen, das Typargument der `Serialize` Methode zum Zeitpunkt der Kompilierung ist `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-270">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="1ac5c-271">In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-271">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="1ac5c-272">Es werden nur die Basisklassen Eigenschaften serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-272">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="1ac5c-273">Dieses Verhalten soll das versehentliche verfügbar machen von Daten in einem abgeleiteten, von der Laufzeit erstellten Typ verhindern.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-273">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="1ac5c-274">Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs im vorherigen Beispiel zu serialisieren:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-274">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="1ac5c-275">Aufrufen einer Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A>, mit der Sie den Typ zur Laufzeit angeben können:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-275">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="1ac5c-276">Deklarieren Sie das Objekt, das als `object`serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-276">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="1ac5c-277">Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in der JSON-Ausgabe enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-277">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="1ac5c-278">Diese Ansätze bieten polymorphe Serialisierung nur für das Stamm Objekt, das serialisiert werden soll, und nicht für die Eigenschaften dieses Stamm Objekts.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-278">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span> 

<span data-ttu-id="1ac5c-279">Sie können die polymorphe Serialisierung für Objekte auf niedrigerer Ebene erhalten, wenn Sie Sie als Typ `object`definieren.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-279">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="1ac5c-280">Angenommen, die `WeatherForecast`-Klasse verfügt über eine Eigenschaft mit dem Namen `PreviousForecast`, die als Typ `WeatherForecast` oder `object`definiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-280">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="1ac5c-281">Wenn die `PreviousForecast`-Eigenschaft eine Instanz von `WeatherForecastDerived`enthält:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-281">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="1ac5c-282">Die JSON-Ausgabe der Serialisierung `WeatherForecastWithPrevious` **enthält keine** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-282">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="1ac5c-283">Die JSON-Ausgabe der Serialisierung `WeatherForecastWithPreviousAsObject` **enthält** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-283">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="1ac5c-284">Um `WeatherForecastWithPreviousAsObject`zu serialisieren, ist es nicht erforderlich, `Serialize<object>` oder `GetType` aufzurufen, da das Stamm Objekt nicht das Objekt ist, das möglicherweise ein abgeleiteter Typ ist.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-284">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="1ac5c-285">Im folgenden Codebeispiel wird weder `Serialize<object>` noch `GetType`aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-285">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="1ac5c-286">Der vorangehende Code serialisiert `WeatherForecastWithPreviousAsObject`ordnungsgemäß:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-286">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="1ac5c-287">Der gleiche Ansatz zum Definieren von Eigenschaften als `object` funktioniert mit Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-287">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="1ac5c-288">Angenommen, Sie haben die folgende Schnittstelle und Implementierung, und Sie möchten eine Klasse mit Eigenschaften serialisieren, die Implementierungs Instanzen enthalten:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-288">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

<span data-ttu-id="1ac5c-289">Wenn Sie eine Instanz von `Forecasts`serialisieren, zeigt nur `Tuesday` die `WindSpeed`-Eigenschaft an, da `Tuesday` als `object`definiert ist:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-289">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="1ac5c-290">Das folgende Beispiel zeigt die JSON-Datei, die sich aus dem vorangehenden Code ergibt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-290">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="1ac5c-291">Weitere Informationen zur polymorphen **Serialisierung**und Informationen zur **Deserialisierung**finden [Sie unter Migrieren von "newtonsoft. JSON" zu "System. Text. JSON](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)".</span><span class="sxs-lookup"><span data-stu-id="1ac5c-291">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="1ac5c-292">Kommentare und nachfolgende Kommas zulassen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-292">Allow comments and trailing commas</span></span>

<span data-ttu-id="1ac5c-293">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-293">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="1ac5c-294">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip`fest.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-294">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="1ac5c-295">Um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-295">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="1ac5c-296">Im folgenden Beispiel wird gezeigt, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-296">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="1ac5c-297">Im folgenden finden Sie ein Beispiel für JSON mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-297">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="1ac5c-298">Nichtbeachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="1ac5c-298">Case-insensitive property matching</span></span>

<span data-ttu-id="1ac5c-299">Standardmäßig wird bei der Deserialisierung nach Groß-/Kleinschreibung unterschieden, dass Eigenschaften Namen Übereinstimmungen zwischen JSON und den Zielobjekt Eigenschaften aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-299">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="1ac5c-300">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true`fest:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-300">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="1ac5c-301">Im folgenden finden Sie eine Beispiel-JSON-Datei mit den Namen der Kamel</span><span class="sxs-lookup"><span data-stu-id="1ac5c-301">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="1ac5c-302">Sie kann in den folgenden Typ deserialisiert werden, der über die Namen der Pascal-Großbuchstaben verfügt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-302">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="1ac5c-303">Handle für Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="1ac5c-303">Handle overflow JSON</span></span>

<span data-ttu-id="1ac5c-304">Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, der nicht durch Eigenschaften des Zieltyps dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-304">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="1ac5c-305">Angenommen, Ihr Zieltyp lautet:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-305">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="1ac5c-306">Der JSON-Code, der deserialisiert werden soll, lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-306">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="1ac5c-307">Wenn Sie den JSON-Code deserialisieren, der in den angezeigten Typ angezeigt wird, sind die Eigenschaften `DatesAvailable` und `SummaryWords` nicht mehr vorhanden und gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-307">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="1ac5c-308">Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) -Attribut auf eine Eigenschaft vom Typ `Dictionary<string,object>` oder `Dictionary<string,JsonElement>`an:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-308">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="1ac5c-309">Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-309">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="1ac5c-310">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1ac5c-310">Property</span></span> |<span data-ttu-id="1ac5c-311">Wert</span><span class="sxs-lookup"><span data-stu-id="1ac5c-311">Value</span></span>  |<span data-ttu-id="1ac5c-312">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ac5c-312">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="1ac5c-313">date</span><span class="sxs-lookup"><span data-stu-id="1ac5c-313">Date</span></span>    | <span data-ttu-id="1ac5c-314">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="1ac5c-314">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="1ac5c-315">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="1ac5c-315">TemperatureCelsius</span></span>| <span data-ttu-id="1ac5c-316">0</span><span class="sxs-lookup"><span data-stu-id="1ac5c-316">0</span></span> | <span data-ttu-id="1ac5c-317">Unterscheidung nach Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die-Eigenschaft nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-317">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="1ac5c-318">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1ac5c-318">Summary</span></span> | <span data-ttu-id="1ac5c-319">Heiße Ebene</span><span class="sxs-lookup"><span data-stu-id="1ac5c-319">Hot</span></span> ||
| <span data-ttu-id="1ac5c-320">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="1ac5c-320">ExtensionData</span></span> | <span data-ttu-id="1ac5c-321">TemperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="1ac5c-321">temperatureCelsius: 25</span></span> |<span data-ttu-id="1ac5c-322">Da die Groß-/Kleinschreibung nicht entsprach, ist diese JSON-Eigenschaft ein zusätzliches und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-322">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="1ac5c-323">Datesavailable:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-323">DatesAvailable:</span></span><br>  <span data-ttu-id="1ac5c-324">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="1ac5c-324">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="1ac5c-325">8/2/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="1ac5c-325">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="1ac5c-326">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-326">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="1ac5c-327">Summarywords:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-327">SummaryWords:</span></span><br><span data-ttu-id="1ac5c-328">Kalte Ebene</span><span class="sxs-lookup"><span data-stu-id="1ac5c-328">Cool</span></span><br><span data-ttu-id="1ac5c-329">Windig</span><span class="sxs-lookup"><span data-stu-id="1ac5c-329">Windy</span></span><br><span data-ttu-id="1ac5c-330">Feu</span><span class="sxs-lookup"><span data-stu-id="1ac5c-330">Humid</span></span> |<span data-ttu-id="1ac5c-331">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-331">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="1ac5c-332">Wenn das Zielobjekt serialisiert wird, werden die Erweiterungs-Datenschlüssel Wert-Paare zu JSON-Eigenschaften, genauso wie Sie im eingehenden JSON-Code waren:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-332">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="1ac5c-333">Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-333">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="1ac5c-334">Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-334">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="1ac5c-335">NULL beim Deserialisieren ignorieren</span><span class="sxs-lookup"><span data-stu-id="1ac5c-335">Ignore null when deserializing</span></span>

<span data-ttu-id="1ac5c-336">Wenn eine Eigenschaft in JSON NULL ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-336">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="1ac5c-337">In einigen Szenarios hat die Ziel Eigenschaft möglicherweise einen Standardwert, und Sie möchten nicht, dass ein NULL-Wert den Standardwert überschreibt.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-337">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="1ac5c-338">Nehmen Sie beispielsweise an, der folgende Code stellt das Zielobjekt dar:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-338">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="1ac5c-339">Angenommen, der folgende JSON-Code wird deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-339">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="1ac5c-340">Nach der Deserialisierung ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts NULL.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-340">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="1ac5c-341">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-341">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="1ac5c-342">Bei dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault` Objekts der Standardwert "keine Zusammenfassung" nach der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-342">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="1ac5c-343">NULL-Werte in JSON werden nur ignoriert, wenn Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-343">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="1ac5c-344">NULL-Werte für Werttypen, die keine NULL-Werte zulassen, verursachen Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-344">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="1ac5c-345">Utf8JsonReader, Utf8JsonWriter und jsondocument</span><span class="sxs-lookup"><span data-stu-id="1ac5c-345">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="1ac5c-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist eine leistungsstarke, niedrige und vorwärts gerichtete Funktion für UTF-8-codierten JSON-Text, der aus einem `ReadOnlySpan<byte>` oder `ReadOnlySequence<byte>`gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="1ac5c-347">Der `Utf8JsonReader` ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Parser und deserialisierern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-347">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="1ac5c-348">Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` unter dem Cover.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-348">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="1ac5c-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ist eine hochleistungsfähige Methode zum Schreiben von UTF-8-codiertem JSON-Text aus gängigen .NET-Typen wie `String`, `Int32`und `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="1ac5c-350">Der Writer ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Serialisierern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-350">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="1ac5c-351">Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` unter dem Cover.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-351">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="1ac5c-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mit `Utf8JsonReader`ein Schreib geschütztes Dokumentobjektmodell (DOM) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="1ac5c-353">Das Dom bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-353">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="1ac5c-354">Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den <xref:System.Text.Json.JsonElement> Typ zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-354">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="1ac5c-355">Der `JsonElement`-Typ stellt Array-und Objekt Enumeratoren zusammen mit APIs bereit, um JSON-Text in allgemeine .NET-Typen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-355">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="1ac5c-356">`JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-356">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="1ac5c-357">In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-357">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="1ac5c-358">Verwenden von jsondocument für den Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="1ac5c-358">Use JsonDocument for access to data</span></span>

<span data-ttu-id="1ac5c-359">Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-359">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="1ac5c-360">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-360">The preceding code:</span></span>

* <span data-ttu-id="1ac5c-361">Geht davon aus, dass der zu analysierende JSON-Code eine Zeichenfolge namens `jsonString`</span><span class="sxs-lookup"><span data-stu-id="1ac5c-361">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="1ac5c-362">Berechnet eine durchschnittliche Qualität für Objekte in einem `Students` Array mit einer `Grade`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-362">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="1ac5c-363">Weist einen Standardwert von 70 für Studenten zu, die nicht über eine Qualität verfügen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-363">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="1ac5c-364">Zählt Schüler und Studenten durch Inkrementieren einer `count` Variablen bei jeder Iterationen.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-364">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="1ac5c-365">Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A>aufzurufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-365">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="1ac5c-366">Im folgenden finden Sie ein Beispiel für die JSON, die von diesem Code verarbeitet wird:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-366">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="1ac5c-367">Verwenden von jsondocument zum Schreiben von JSON</span><span class="sxs-lookup"><span data-stu-id="1ac5c-367">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="1ac5c-368">Im folgenden Beispiel wird gezeigt, wie JSON aus einem <xref:System.Text.Json.JsonDocument>geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-368">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="1ac5c-369">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-369">The preceding code:</span></span>

* <span data-ttu-id="1ac5c-370">Liest eine JSON-Datei, lädt die Daten in eine `JsonDocument`und schreibt formatierte (hübsch gedruckte) JSON-Daten in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-370">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="1ac5c-371">Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-371">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="1ac5c-372">Wenn Sie fertig sind, ruft <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-372">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="1ac5c-373">Eine Alternative besteht darin, den Writer automatisch zu leeren, wenn er verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-373">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="1ac5c-374">Im folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die durch den Beispielcode verarbeitet werden soll:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-374">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="1ac5c-375">Das Ergebnis ist die folgende ziemlich gedruckte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-375">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="1ac5c-376">Utf8JsonWriter verwenden</span><span class="sxs-lookup"><span data-stu-id="1ac5c-376">Use Utf8JsonWriter</span></span>

<span data-ttu-id="1ac5c-377">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonWriter>-Klasse verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-377">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="1ac5c-378">Utf8JsonReader verwenden</span><span class="sxs-lookup"><span data-stu-id="1ac5c-378">Use Utf8JsonReader</span></span>

<span data-ttu-id="1ac5c-379">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonReader>-Klasse verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-379">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="1ac5c-380">Der vorangehende Code geht davon aus, dass es sich bei der `jsonUtf8` Variable um ein Bytearray handelt, das gültige JSON-Codierung als UTF-8 enthält</span><span class="sxs-lookup"><span data-stu-id="1ac5c-380">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="1ac5c-381">Filtern von Daten mithilfe von Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="1ac5c-381">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="1ac5c-382">Im folgenden Beispiel wird gezeigt, wie eine Datei synchron gelesen und nach einem Wert gesucht wird:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-382">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="1ac5c-383">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-383">The preceding code:</span></span>

* <span data-ttu-id="1ac5c-384">Geht davon aus, dass der JSON-Code ein Array von Objekten enthält und jedes Objekt eine "Name"-Eigenschaft vom Typ "String" enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-384">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="1ac5c-385">Zählt Objekte und "Name"-Eigenschaftswerte, die mit "University" enden.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-385">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="1ac5c-386">Geht davon aus, dass die Datei als UTF-16 codiert ist, und transcodiert Sie in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-386">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="1ac5c-387">Eine Datei, die als UTF-8 codiert ist, kann mithilfe des folgenden Codes direkt in eine `ReadOnlySpan<byte>`gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-387">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

  <span data-ttu-id="1ac5c-388">Wenn die Datei eine UTF-8-Byte Reihenfolge-Marke (BOM) enthält, entfernen Sie diese, bevor Sie die Bytes an den `Utf8JsonReader`übergeben, da der Reader Text erwartet.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-388">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="1ac5c-389">Andernfalls wird die BOM als ungültige JSON betrachtet, und der Reader löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-389">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="1ac5c-390">Im folgenden finden Sie ein JSON-Beispiel, das der vorherige Code lesen kann.</span><span class="sxs-lookup"><span data-stu-id="1ac5c-390">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="1ac5c-391">Die resultierende Zusammenfassungs Meldung lautet: "2 von 4 haben Namen, die mit" University "enden:</span><span class="sxs-lookup"><span data-stu-id="1ac5c-391">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="1ac5c-392">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1ac5c-392">Additional resources</span></span>

* [<span data-ttu-id="1ac5c-393">Übersicht über System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="1ac5c-393">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1ac5c-394">Schreiben von benutzerdefinierten Konvertern</span><span class="sxs-lookup"><span data-stu-id="1ac5c-394">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="1ac5c-395">Vorgehensweise beim Migrieren von "newtonsoft. JSON"</span><span class="sxs-lookup"><span data-stu-id="1ac5c-395">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="1ac5c-396">DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="1ac5c-396">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="1ac5c-397">System. Text. JSON-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="1ac5c-397">System.Text.Json API reference</span></span>](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
