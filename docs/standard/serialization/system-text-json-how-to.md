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
ms.openlocfilehash: 3d3dc0011562e25854938aff857f2832a5978b49
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283334"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="1d340-102">Serialisieren und Deserialisieren von JSON in .net</span><span class="sxs-lookup"><span data-stu-id="1d340-102">How to serialize and deserialize JSON in .NET</span></span>

<span data-ttu-id="1d340-103">In diesem Artikel wird gezeigt, wie Sie den <xref:System.Text.Json>-Namespace zum Serialisieren und Deserialisieren in und aus JavaScript Object Notation (JSON) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d340-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="1d340-104">Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework, wie z. b. [ASP.net Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="1d340-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="1d340-105">Der größte Teil des serialisierungsbeispielcodes legt <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> fest, um die JSON-Datei zu `true` (mit einzügkeit und Leerraum für die Lesbarkeit des Menschen).</span><span class="sxs-lookup"><span data-stu-id="1d340-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="1d340-106">Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="1d340-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="1d340-107">Namespaces</span><span class="sxs-lookup"><span data-stu-id="1d340-107">Namespaces</span></span>

<span data-ttu-id="1d340-108">Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen.</span><span class="sxs-lookup"><span data-stu-id="1d340-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="1d340-109">Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="1d340-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="1d340-110">Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Direktiven für einen oder beide Namespaces:</span><span class="sxs-lookup"><span data-stu-id="1d340-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="1d340-111">Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden derzeit in `System.Text.Json`nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d340-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="1d340-112">Schreiben von .NET-Objekten in JSON (Serialisieren)</span><span class="sxs-lookup"><span data-stu-id="1d340-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="1d340-113">Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, müssen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1d340-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1d340-114">Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="1d340-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-115">Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1d340-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-116">Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1d340-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-117">In den vorangehenden Beispielen wird der Typrückschluss für den serialisierten Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d340-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="1d340-118">Eine Überladung von `Serialize()` nimmt einen generischen Typparameter an:</span><span class="sxs-lookup"><span data-stu-id="1d340-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="1d340-119">Beispiel für die Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1d340-119">Serialization example</span></span>

<span data-ttu-id="1d340-120">Im folgenden finden Sie eine Beispiel Klasse, die Auflistungen und eine-Klasse enthält:</span><span class="sxs-lookup"><span data-stu-id="1d340-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="1d340-121">Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="1d340-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="1d340-122">Die JSON-Ausgabe wird standardmäßig minimiert:</span><span class="sxs-lookup"><span data-stu-id="1d340-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="1d340-123">Im folgenden Beispiel wird derselbe JSON-Code dargestellt, der formatiert ist (d. h. mit Leerraum und Einzug):</span><span class="sxs-lookup"><span data-stu-id="1d340-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="1d340-124">In UTF-8 serialisieren</span><span class="sxs-lookup"><span data-stu-id="1d340-124">Serialize to UTF-8</span></span>

<span data-ttu-id="1d340-125">Um zu UTF-8 zu serialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="1d340-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-126">Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A> Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> annimmt, ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1d340-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="1d340-127">Die Serialisierung in UTF-8 ist ungefähr 5-10% schneller als die Verwendung der Zeichen folgen basierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="1d340-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="1d340-128">Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichen folgen (UTF-16) konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1d340-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="1d340-129">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="1d340-129">Serialization behavior</span></span>

* <span data-ttu-id="1d340-130">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1d340-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="1d340-131">Sie können [Eigenschaften angeben, die ausgeschlossen werden sollen](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="1d340-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="1d340-132">Der [Standard Encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) schützt nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [der RFC 8259 JSON-Spezifikation](https://tools.ietf.org/html/rfc8259#section-7)mit Escapezeichen versehen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1d340-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1d340-133">Standardmäßig wird JSON minimiert.</span><span class="sxs-lookup"><span data-stu-id="1d340-133">By default, JSON is minified.</span></span> <span data-ttu-id="1d340-134">Sie können [den JSON-Code ziemlich ausdrucken](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="1d340-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1d340-135">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen den .net-Namen.</span><span class="sxs-lookup"><span data-stu-id="1d340-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1d340-136">Sie können die [JSON-namens](#customize-json-names-and-values)Schreibweise anpassen.</span><span class="sxs-lookup"><span data-stu-id="1d340-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="1d340-137">Zirkuläre Verweise werden erkannt, und Ausnahmen werden ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1d340-137">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="1d340-138">Weitere Informationen finden Sie unter [Issue 38579 on Zirkel References](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="1d340-138">For more information, see [issue 38579 on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="1d340-139">Derzeit werden Felder ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1d340-139">Currently, fields are excluded.</span></span>

<span data-ttu-id="1d340-140">Folgende Typen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1d340-140">Supported types include:</span></span>

* <span data-ttu-id="1d340-141">.Net-primitive, die JavaScript-primitiven zugeordnet sind, z. b. numerische Typen, Zeichen folgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="1d340-141">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1d340-142">Benutzerdefinierte [Plain Old CLR Objects (POCOS)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="1d340-142">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="1d340-143">Eindimensionales und verzweigte Arrays (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="1d340-143">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="1d340-144">`Dictionary<string,TValue>`, wo `TValue` `object`, `JsonElement`oder poco ist.</span><span class="sxs-lookup"><span data-stu-id="1d340-144">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="1d340-145">Sammlungen aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="1d340-145">Collections from the following namespaces.</span></span> <span data-ttu-id="1d340-146">Weitere Informationen finden Sie im [Thema zur Unterstützung von Sammlungen](https://github.com/dotnet/corefx/issues/36643) im dotnet/corefx-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="1d340-146">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="1d340-147">Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md) , um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-147">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="1d340-148">Lesen von JSON in .NET-Objekte (Deserialisieren)</span><span class="sxs-lookup"><span data-stu-id="1d340-148">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="1d340-149">Um eine Zeichenfolge oder eine Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1d340-149">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1d340-150">Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecast`-Klasse erstellt, die zuvor für das [serialisierungsbeispiel](#serialization-example)gezeigt wurde:</span><span class="sxs-lookup"><span data-stu-id="1d340-150">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d340-151">Wenn Sie aus einer Datei mithilfe von synchronem Code deserialisieren möchten, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-151">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d340-152">Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode abrufen:</span><span class="sxs-lookup"><span data-stu-id="1d340-152">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="1d340-153">Aus UTF-8 Deserialisieren</span><span class="sxs-lookup"><span data-stu-id="1d340-153">Deserialize from UTF-8</span></span>

<span data-ttu-id="1d340-154">Um von UTF-8 zu deserialisieren, müssen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> Überladung aufrufen, die eine `Utf8JsonReader` oder eine `ReadOnlySpan<byte>`annimmt, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d340-154">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="1d340-155">In den Beispielen wird davon ausgegangen, dass sich die JSON in einem Bytearray namens jsonUtf8Bytes</span><span class="sxs-lookup"><span data-stu-id="1d340-155">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="1d340-156">Deserialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="1d340-156">Deserialization behavior</span></span>

* <span data-ttu-id="1d340-157">Standardmäßig wird die Groß-/Kleinschreibung bei der Übereinstimmung von Eigenschaften Namen</span><span class="sxs-lookup"><span data-stu-id="1d340-157">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1d340-158">Sie können die [Groß-/Kleinschreibung](#case-insensitive-property-matching)nicht beachten.</span><span class="sxs-lookup"><span data-stu-id="1d340-158">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="1d340-159">Wenn der JSON-Wert einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1d340-159">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1d340-160">Die Deserialisierung für Verweis Typen ohne Parameter losen Konstruktor wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d340-160">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="1d340-161">Die Deserialisierung zu unveränderlichen Objekten oder schreibgeschützten Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d340-161">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="1d340-162">Weitere Informationen finden Sie unter GitHub- [Problem 38569 bei der Unterstützung für unveränderliche Objekte](https://github.com/dotnet/corefx/issues/38569) und [Problem 38163 bei der Unterstützung](https://github.com/dotnet/corefx/issues/38163) für schreibgeschützte Eigenschaften im dotnet/corefx-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="1d340-162">For more information, see GitHub [issue 38569 on immutable object support](https://github.com/dotnet/corefx/issues/38569) and [issue 38163 on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="1d340-163">Standardmäßig werden Enumerationen als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d340-163">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1d340-164">Enumerationsnamen können als Zeichen folgen [serialisiert](#enums-as-strings)werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-164">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="1d340-165">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d340-165">Fields aren't supported.</span></span>
* <span data-ttu-id="1d340-166">Standardmäßig lösen Kommentare oder nachfolgende Kommas in der JSON-Datei Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="1d340-166">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1d340-167">Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="1d340-167">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="1d340-168">Der Standardwert für die [Maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) ist 64.</span><span class="sxs-lookup"><span data-stu-id="1d340-168">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1d340-169">Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md) , um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-169">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="1d340-170">Serialisieren in formatierten JSON-Code</span><span class="sxs-lookup"><span data-stu-id="1d340-170">Serialize to formatted JSON</span></span>

<span data-ttu-id="1d340-171">Um die JSON-Ausgabe zu Recht drucken, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true`fest:</span><span class="sxs-lookup"><span data-stu-id="1d340-171">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="1d340-172">Hier ist ein Beispieltyp, der serialisiert und eine ziemlich gedruckte JSON-Ausgabe ist:</span><span class="sxs-lookup"><span data-stu-id="1d340-172">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="1d340-173">Anpassen von JSON-Namen und-Werten</span><span class="sxs-lookup"><span data-stu-id="1d340-173">Customize JSON names and values</span></span>

<span data-ttu-id="1d340-174">Standardmäßig sind Eigenschaftsnamen und Wörterbuch Schlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="1d340-174">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="1d340-175">Enumerationswerte werden als Zahlen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1d340-175">Enum values are represented as numbers.</span></span> <span data-ttu-id="1d340-176">In diesem Abschnitt wird Folgendes erläutert:</span><span class="sxs-lookup"><span data-stu-id="1d340-176">This section explains how to:</span></span>

* [<span data-ttu-id="1d340-177">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="1d340-177">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="1d340-178">Alle Eigenschaftsnamen in Camel-Case konvertieren</span><span class="sxs-lookup"><span data-stu-id="1d340-178">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="1d340-179">Implementieren einer benutzerdefinierten Benennungs Richtlinie für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1d340-179">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="1d340-180">Wörterbuch Schlüssel in Kamel-Schreibweise konvertieren</span><span class="sxs-lookup"><span data-stu-id="1d340-180">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="1d340-181">Enumerationszeichen in Zeichen folgen und Camel-Case konvertieren</span><span class="sxs-lookup"><span data-stu-id="1d340-181">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="1d340-182">Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und-Werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="1d340-182">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="1d340-183">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="1d340-183">Customize individual property names</span></span>

<span data-ttu-id="1d340-184">Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das [[jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) -Attribut.</span><span class="sxs-lookup"><span data-stu-id="1d340-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="1d340-185">Hier ist ein Beispiel für die Serialisierung und die daraus resultierende JSON-Datei:</span><span class="sxs-lookup"><span data-stu-id="1d340-185">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1d340-186">Der durch dieses Attribut festgelegte Eigenschaftsname:</span><span class="sxs-lookup"><span data-stu-id="1d340-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="1d340-187">Gilt für die Serialisierung und Deserialisierung in beide Richtungen.</span><span class="sxs-lookup"><span data-stu-id="1d340-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="1d340-188">Hat Vorrang vor Eigenschafts Benennungs Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="1d340-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="1d340-189">Bei allen JSON-Eigenschaftsnamen die Kamel-Schreibweise verwenden</span><span class="sxs-lookup"><span data-stu-id="1d340-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="1d340-190">Wenn Sie die Kamel-Schreibweise für alle JSON-Eigenschaftsnamen verwenden möchten, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="1d340-191">Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1d340-191">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1d340-192">Die Benennungs Richtlinie für die Camel-Case-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="1d340-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="1d340-193">Gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1d340-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="1d340-194">Wird von `[JsonPropertyName]` Attributen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d340-194">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="1d340-195">Aus diesem Grund ist der Name der JSON-Eigenschaft `Wind` im Beispiel nicht Camel Case.</span><span class="sxs-lookup"><span data-stu-id="1d340-195">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="1d340-196">Verwenden einer benutzerdefinierten JSON-Eigenschafts Benennungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="1d340-196">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="1d340-197">Um eine benutzerdefinierte JSON-Benennungs Richtlinie zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und überschreiben Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-197">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="1d340-198">Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihrer Benennungs Richtlinien Klasse fest:</span><span class="sxs-lookup"><span data-stu-id="1d340-198">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-199">Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1d340-199">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1d340-200">Die Benennungs Richtlinie für die JSON-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="1d340-200">The JSON property naming policy:</span></span>

* <span data-ttu-id="1d340-201">Gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1d340-201">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="1d340-202">Wird von `[JsonPropertyName]` Attributen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d340-202">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="1d340-203">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="1d340-203">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="1d340-204">Camel-Case-Wörterbuch Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1d340-204">Camel case dictionary keys</span></span>

<span data-ttu-id="1d340-205">Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>`ist, können die `string` Schlüssel in die Kamel-Schreibweise konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-205">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="1d340-206">Legen Sie zu diesem Zweck <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-206">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-207">Das Serialisieren eines Objekts mit einem Wörterbuch mit dem Namen `TemperatureRanges`, das Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` hat, führt zu einer JSON-Ausgabe wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1d340-207">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="1d340-208">Die Camel-Case-Benennungs Richtlinie für Wörterbuch Schlüssel gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1d340-208">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="1d340-209">Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei, auch wenn Sie `JsonNamingPolicy.CamelCase` für die `DictionaryKeyPolicy`angeben.</span><span class="sxs-lookup"><span data-stu-id="1d340-209">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="1d340-210">Enumerationszeichen als Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="1d340-210">Enums as strings</span></span>

<span data-ttu-id="1d340-211">Standardmäßig werden Enumerationen als Zahlen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1d340-211">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="1d340-212">Verwenden Sie die <xref:System.Text.Json.Serialization.JsonStringEnumConverter>, um Enumerationsnamen als Zeichen folgen zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="1d340-212">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="1d340-213">Nehmen Sie beispielsweise an, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:</span><span class="sxs-lookup"><span data-stu-id="1d340-213">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="1d340-214">Wenn die Zusammenfassung `Hot`ist, hat die serialisierte JSON standardmäßig den numerischen Wert 3:</span><span class="sxs-lookup"><span data-stu-id="1d340-214">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="1d340-215">Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Kamel-Schreibweise:</span><span class="sxs-lookup"><span data-stu-id="1d340-215">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-216">Der resultierende JSON-Code sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="1d340-216">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="1d340-217">Enum-Zeichen folgen Namen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-217">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="1d340-218">Ausschließen von Eigenschaften von der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1d340-218">Exclude properties from serialization</span></span>

<span data-ttu-id="1d340-219">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1d340-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="1d340-220">Wenn Sie nicht möchten, dass einige von Ihnen in der JSON-Ausgabe angezeigt werden, haben Sie mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="1d340-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="1d340-221">In diesem Abschnitt wird erläutert, wie Folgendes ausgeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="1d340-221">This section explains how to exclude:</span></span>

* [<span data-ttu-id="1d340-222">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1d340-222">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="1d340-223">Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1d340-223">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="1d340-224">Alle NULL-Wert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1d340-224">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="1d340-225">Einzelne Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="1d340-225">Exclude individual properties</span></span>

<span data-ttu-id="1d340-226">Verwenden Sie das Attribut [[jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) , um einzelne Eigenschaften zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="1d340-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="1d340-227">Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1d340-227">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="1d340-228">Alle schreibgeschützten Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="1d340-228">Exclude all read-only properties</span></span>

<span data-ttu-id="1d340-229">Eine Eigenschaft ist schreibgeschützt, wenn Sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.</span><span class="sxs-lookup"><span data-stu-id="1d340-229">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="1d340-230">Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-230">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-231">Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1d340-231">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="1d340-232">Diese Option gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1d340-232">This option applies only to serialization.</span></span> <span data-ttu-id="1d340-233">Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1d340-233">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="1d340-234">Alle NULL-Wert Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="1d340-234">Exclude all null value properties</span></span>

<span data-ttu-id="1d340-235">Um alle NULL-Wert Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-236">Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1d340-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="1d340-237">Die Eigenschaften-</span><span class="sxs-lookup"><span data-stu-id="1d340-237">Property</span></span> |<span data-ttu-id="1d340-238">Wert</span><span class="sxs-lookup"><span data-stu-id="1d340-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="1d340-239">Datum</span><span class="sxs-lookup"><span data-stu-id="1d340-239">Date</span></span>    | <span data-ttu-id="1d340-240">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="1d340-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="1d340-241">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="1d340-241">TemperatureCelsius</span></span>| <span data-ttu-id="1d340-242">25</span><span class="sxs-lookup"><span data-stu-id="1d340-242">25</span></span> |
| <span data-ttu-id="1d340-243">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1d340-243">Summary</span></span>| <span data-ttu-id="1d340-244">null</span><span class="sxs-lookup"><span data-stu-id="1d340-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="1d340-245">Diese Einstellung gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1d340-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="1d340-246">Informationen zu den Auswirkungen auf die Deserialisierung finden Sie unter [Ignorieren von NULL beim Deserialisieren](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="1d340-246">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="1d340-247">Zeichencodierung anpassen</span><span class="sxs-lookup"><span data-stu-id="1d340-247">Customize character encoding</span></span>

<span data-ttu-id="1d340-248">Standardmäßig schützt das Serialisierungsprogramm alle nicht-ASCII-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1d340-248">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="1d340-249">Das heißt, Sie ersetzt Sie durch `\uxxxx`, wobei `xxxx` der Unicode-Code des Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="1d340-249">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="1d340-250">Wenn die `Summary`-Eigenschaft z. b. auf Cyrillic-"-Eigenschaft" festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1d340-250">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="1d340-251">Serialisieren von sprach Zeichensätzen</span><span class="sxs-lookup"><span data-stu-id="1d340-251">Serialize language character sets</span></span>

<span data-ttu-id="1d340-252">Wenn Sie die Zeichensätze mindestens einer Sprache ohne Escapezeichen serialisieren möchten, müssen Sie beim Erstellen einer Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>[Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) angeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-252">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="1d340-253">Mit diesem Code werden keine kyrillischen oder griechischen Zeichen entfernt.</span><span class="sxs-lookup"><span data-stu-id="1d340-253">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="1d340-254">Wenn die `Summary`-Eigenschaft auf Cyrillic--,-festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1d340-254">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="1d340-255">Verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>, um alle sprach Sätze ohne Escapezeichen zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="1d340-255">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="1d340-256">Serialisieren bestimmter Zeichen</span><span class="sxs-lookup"><span data-stu-id="1d340-256">Serialize specific characters</span></span>

<span data-ttu-id="1d340-257">Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne mit Escapezeichen versehen zu werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-257">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="1d340-258">Im folgenden Beispiel werden nur die ersten zwei Zeichen von "..." serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1d340-258">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="1d340-259">Im folgenden finden Sie ein Beispiel für JSON, das durch den vorangehenden Code generiert wird:</span><span class="sxs-lookup"><span data-stu-id="1d340-259">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="1d340-260">Alle Zeichen serialisieren</span><span class="sxs-lookup"><span data-stu-id="1d340-260">Serialize all characters</span></span>

<span data-ttu-id="1d340-261">Um das Escapezeichen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-261">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="1d340-262">Im Vergleich zum Standard-Encoder ist der `UnsafeRelaxedJsonEscaping` Encoder eher für das Zulassen von Zeichen ohne Escapezeichen zulässig:</span><span class="sxs-lookup"><span data-stu-id="1d340-262">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="1d340-263">Es werden keine HTML-sensiblen Zeichen wie `<`, `>`, `&`und `'`mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="1d340-263">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="1d340-264">Er bietet keine zusätzlichen Schutzmaßnahmen vor XSS-oder Informations Offenlegungs Angriffen, wie z. b. solche, die sich aus dem Client und dem Server ergeben könnten, die auf dem *CharSet*nicht einverstanden sind.</span><span class="sxs-lookup"><span data-stu-id="1d340-264">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="1d340-265">Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1d340-265">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="1d340-266">Sie können Sie beispielsweise verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8`sendet.</span><span class="sxs-lookup"><span data-stu-id="1d340-266">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="1d340-267">Gestatten Sie niemals, dass die Roh`UnsafeRelaxedJsonEscaping` Ausgabe in eine HTML-Seite oder ein `<script>` Element ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1d340-267">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="1d340-268">Serialisieren von Eigenschaften abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="1d340-268">Serialize properties of derived classes</span></span>

<span data-ttu-id="1d340-269">Die polymorphe Serialisierung wird nicht unterstützt, wenn Sie zum Zeitpunkt der Kompilierung angeben, welcher Typ serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d340-269">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="1d340-270">Nehmen Sie beispielsweise an, Sie verfügen über eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastWithWind`:</span><span class="sxs-lookup"><span data-stu-id="1d340-270">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="1d340-271">Angenommen, das Typargument der `Serialize` Methode zum Zeitpunkt der Kompilierung ist `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="1d340-271">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="1d340-272">In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastWithWind`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="1d340-272">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="1d340-273">Es werden nur die Basisklassen Eigenschaften serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1d340-273">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="1d340-274">Dieses Verhalten soll das versehentliche verfügbar machen von Daten in einem abgeleiteten, von der Laufzeit erstellten Typ verhindern.</span><span class="sxs-lookup"><span data-stu-id="1d340-274">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="1d340-275">Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs zu serialisieren:</span><span class="sxs-lookup"><span data-stu-id="1d340-275">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="1d340-276">Aufrufen einer Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A>, mit der Sie den Typ zur Laufzeit angeben können:</span><span class="sxs-lookup"><span data-stu-id="1d340-276">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="1d340-277">Deklarieren Sie das Objekt, das als `object`serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d340-277">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="1d340-278">Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in der JSON-Ausgabe enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="1d340-278">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="1d340-279">Weitere Informationen zur polymorphen Deserialisierung finden Sie [unter Unterstützung der polymorphen Deserialisierung](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="1d340-279">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="1d340-280">Kommentare und nachfolgende Kommas zulassen</span><span class="sxs-lookup"><span data-stu-id="1d340-280">Allow comments and trailing commas</span></span>

<span data-ttu-id="1d340-281">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1d340-281">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="1d340-282">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip`fest.</span><span class="sxs-lookup"><span data-stu-id="1d340-282">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="1d340-283">Um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="1d340-283">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="1d340-284">Im folgenden Beispiel wird gezeigt, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="1d340-284">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d340-285">Im folgenden finden Sie ein Beispiel für JSON mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="1d340-285">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="1d340-286">Nichtbeachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="1d340-286">Case-insensitive property matching</span></span>

<span data-ttu-id="1d340-287">Standardmäßig wird bei der Deserialisierung nach Groß-/Kleinschreibung unterschieden, dass Eigenschaften Namen Übereinstimmungen zwischen JSON und den Zielobjekt Eigenschaften aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1d340-287">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="1d340-288">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true`fest:</span><span class="sxs-lookup"><span data-stu-id="1d340-288">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d340-289">Im folgenden finden Sie eine Beispiel-JSON-Datei mit den Namen der Kamel</span><span class="sxs-lookup"><span data-stu-id="1d340-289">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="1d340-290">Sie kann in den folgenden Typ deserialisiert werden, der über die Namen der Pascal-Großbuchstaben verfügt.</span><span class="sxs-lookup"><span data-stu-id="1d340-290">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="1d340-291">Handle für Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="1d340-291">Handle overflow JSON</span></span>

<span data-ttu-id="1d340-292">Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, der nicht durch Eigenschaften des Zieltyps dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1d340-292">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="1d340-293">Angenommen, Ihr Zieltyp lautet:</span><span class="sxs-lookup"><span data-stu-id="1d340-293">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="1d340-294">Der JSON-Code, der deserialisiert werden soll, lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1d340-294">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="1d340-295">Wenn Sie den JSON-Code deserialisieren, der in den angezeigten Typ angezeigt wird, sind die Eigenschaften `DatesAvailable` und `SummaryWords` nicht mehr vorhanden und gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="1d340-295">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="1d340-296">Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) -Attribut auf eine Eigenschaft vom Typ `Dictionary<string,object>` oder `Dictionary<string,JsonElement>`an:</span><span class="sxs-lookup"><span data-stu-id="1d340-296">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="1d340-297">Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="1d340-297">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="1d340-298">Die Eigenschaften-</span><span class="sxs-lookup"><span data-stu-id="1d340-298">Property</span></span> |<span data-ttu-id="1d340-299">Wert</span><span class="sxs-lookup"><span data-stu-id="1d340-299">Value</span></span>  |<span data-ttu-id="1d340-300">Notizen</span><span class="sxs-lookup"><span data-stu-id="1d340-300">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="1d340-301">Datum</span><span class="sxs-lookup"><span data-stu-id="1d340-301">Date</span></span>    | <span data-ttu-id="1d340-302">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="1d340-302">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="1d340-303">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="1d340-303">TemperatureCelsius</span></span>| <span data-ttu-id="1d340-304">0</span><span class="sxs-lookup"><span data-stu-id="1d340-304">0</span></span> | <span data-ttu-id="1d340-305">Unterscheidung nach Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die-Eigenschaft nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1d340-305">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="1d340-306">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1d340-306">Summary</span></span> | <span data-ttu-id="1d340-307">Luft</span><span class="sxs-lookup"><span data-stu-id="1d340-307">Hot</span></span> ||
| <span data-ttu-id="1d340-308">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="1d340-308">ExtensionData</span></span> | <span data-ttu-id="1d340-309">TemperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="1d340-309">temperatureCelsius: 25</span></span> |<span data-ttu-id="1d340-310">Da die Groß-/Kleinschreibung nicht entsprach, ist diese JSON-Eigenschaft ein zusätzliches und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="1d340-310">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="1d340-311">Datesavailable:</span><span class="sxs-lookup"><span data-stu-id="1d340-311">DatesAvailable:</span></span><br>  <span data-ttu-id="1d340-312">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="1d340-312">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="1d340-313">8/2/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="1d340-313">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="1d340-314">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="1d340-314">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="1d340-315">Summarywords:</span><span class="sxs-lookup"><span data-stu-id="1d340-315">SummaryWords:</span></span><br><span data-ttu-id="1d340-316">Toll</span><span class="sxs-lookup"><span data-stu-id="1d340-316">Cool</span></span><br><span data-ttu-id="1d340-317">Digen</span><span class="sxs-lookup"><span data-stu-id="1d340-317">Windy</span></span><br><span data-ttu-id="1d340-318">Feu</span><span class="sxs-lookup"><span data-stu-id="1d340-318">Humid</span></span> |<span data-ttu-id="1d340-319">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="1d340-319">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="1d340-320">Wenn das Zielobjekt serialisiert wird, werden die Erweiterungs-Datenschlüssel Wert-Paare zu JSON-Eigenschaften, genauso wie Sie im eingehenden JSON-Code waren:</span><span class="sxs-lookup"><span data-stu-id="1d340-320">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="1d340-321">Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1d340-321">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="1d340-322">Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-322">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="1d340-323">NULL beim Deserialisieren ignorieren</span><span class="sxs-lookup"><span data-stu-id="1d340-323">Ignore null when deserializing</span></span>

<span data-ttu-id="1d340-324">Wenn eine Eigenschaft in JSON NULL ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1d340-324">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="1d340-325">In einigen Szenarios hat die Ziel Eigenschaft möglicherweise einen Standardwert, und Sie möchten nicht, dass ein NULL-Wert den Standardwert überschreibt.</span><span class="sxs-lookup"><span data-stu-id="1d340-325">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="1d340-326">Nehmen Sie beispielsweise an, der folgende Code stellt das Zielobjekt dar:</span><span class="sxs-lookup"><span data-stu-id="1d340-326">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="1d340-327">Angenommen, der folgende JSON-Code wird deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="1d340-327">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="1d340-328">Nach der Deserialisierung ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts NULL.</span><span class="sxs-lookup"><span data-stu-id="1d340-328">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="1d340-329">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-329">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d340-330">Bei dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault` Objekts der Standardwert "keine Zusammenfassung" nach der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1d340-330">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="1d340-331">NULL-Werte in JSON werden nur ignoriert, wenn Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="1d340-331">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="1d340-332">NULL-Werte für Werttypen, die keine NULL-Werte zulassen, verursachen Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="1d340-332">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="1d340-333">Weitere Informationen finden Sie im dotnet/corefx-Repository auf GitHub unter [Problem 40922 für Werttypen, die keine NULL-Werte](https://github.com/dotnet/corefx/issues/40922) zulassen.</span><span class="sxs-lookup"><span data-stu-id="1d340-333">For more information, see [issue 40922 on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="1d340-334">Utf8JsonReader, Utf8JsonWriter und jsondocument</span><span class="sxs-lookup"><span data-stu-id="1d340-334">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="1d340-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, reiner Vorwärtsleser mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="1d340-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="1d340-336">Der `Utf8JsonReader` ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Parser und deserialisierern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d340-336">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="1d340-337">Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` unter dem Cover.</span><span class="sxs-lookup"><span data-stu-id="1d340-337">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="1d340-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ist eine hochleistungsfähige Methode zum Schreiben von UTF-8-codiertem JSON-Text aus gängigen .NET-Typen wie `String`, `Int32`und `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="1d340-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="1d340-339">Der Writer ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Serialisierern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d340-339">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="1d340-340">Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` unter dem Cover.</span><span class="sxs-lookup"><span data-stu-id="1d340-340">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="1d340-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mit `Utf8JsonReader`ein Schreib geschütztes Dokumentobjektmodell (DOM) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d340-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="1d340-342">Das Dom bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="1d340-342">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="1d340-343">Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den <xref:System.Text.Json.JsonElement> Typ zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-343">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="1d340-344">Der `JsonElement`-Typ stellt Array-und Objekt Enumeratoren zusammen mit APIs bereit, um JSON-Text in allgemeine .NET-Typen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1d340-344">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="1d340-345">`JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1d340-345">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="1d340-346">In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-346">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="1d340-347">Verwenden von jsondocument für den Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="1d340-347">Use JsonDocument for access to data</span></span>

<span data-ttu-id="1d340-348">Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:</span><span class="sxs-lookup"><span data-stu-id="1d340-348">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="1d340-349">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1d340-349">The preceding code:</span></span>

* <span data-ttu-id="1d340-350">Geht davon aus, dass der zu analysierende JSON-Code eine Zeichenfolge namens `jsonString`</span><span class="sxs-lookup"><span data-stu-id="1d340-350">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="1d340-351">Berechnet eine durchschnittliche Qualität für Objekte in einem `Students` Array mit einer `Grade`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1d340-351">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="1d340-352">Weist einen Standardwert von 70 für Studenten zu, die nicht über eine Qualität verfügen.</span><span class="sxs-lookup"><span data-stu-id="1d340-352">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="1d340-353">Zählt Schüler und Studenten durch Inkrementieren einer `count` Variablen bei jeder Iterationen.</span><span class="sxs-lookup"><span data-stu-id="1d340-353">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="1d340-354">Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A>aufzurufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d340-354">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="1d340-355">Im folgenden finden Sie ein Beispiel für die JSON, die von diesem Code verarbeitet wird:</span><span class="sxs-lookup"><span data-stu-id="1d340-355">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="1d340-356">Verwenden von jsondocument zum Schreiben von JSON</span><span class="sxs-lookup"><span data-stu-id="1d340-356">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="1d340-357">Im folgenden Beispiel wird gezeigt, wie JSON aus einem <xref:System.Text.Json.JsonDocument>geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="1d340-357">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="1d340-358">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1d340-358">The preceding code:</span></span>

* <span data-ttu-id="1d340-359">Liest eine JSON-Datei, lädt die Daten in eine `JsonDocument`und schreibt formatierte (hübsch gedruckte) JSON-Daten in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="1d340-359">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="1d340-360">Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="1d340-360">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="1d340-361">Wenn Sie fertig sind, ruft <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf.</span><span class="sxs-lookup"><span data-stu-id="1d340-361">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="1d340-362">Eine Alternative besteht darin, den Writer automatisch zu leeren, wenn er verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="1d340-362">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="1d340-363">Im folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die durch den Beispielcode verarbeitet werden soll:</span><span class="sxs-lookup"><span data-stu-id="1d340-363">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="1d340-364">Das Ergebnis ist die folgende ziemlich gedruckte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1d340-364">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="1d340-365">Utf8JsonWriter verwenden</span><span class="sxs-lookup"><span data-stu-id="1d340-365">Use Utf8JsonWriter</span></span>

<span data-ttu-id="1d340-366">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonWriter>-Klasse verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="1d340-366">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="1d340-367">Utf8JsonReader verwenden</span><span class="sxs-lookup"><span data-stu-id="1d340-367">Use Utf8JsonReader</span></span>

<span data-ttu-id="1d340-368">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonReader>-Klasse verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="1d340-368">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="1d340-369">Der vorangehende Code geht davon aus, dass es sich bei der `jsonUtf8` Variable um ein Bytearray handelt, das gültige JSON-Codierung als UTF-8 enthält</span><span class="sxs-lookup"><span data-stu-id="1d340-369">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="1d340-370">Filtern von Daten mithilfe von Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="1d340-370">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="1d340-371">Im folgenden Beispiel wird gezeigt, wie eine Datei synchron gelesen und nach einem Wert gesucht wird:</span><span class="sxs-lookup"><span data-stu-id="1d340-371">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="1d340-372">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1d340-372">The preceding code:</span></span>

* <span data-ttu-id="1d340-373">Geht davon aus, dass die Datei als UTF-16 codiert ist, und transcodiert Sie in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1d340-373">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="1d340-374">Eine Datei, die als UTF-8 codiert ist, kann mithilfe des folgenden Codes direkt in eine `ReadOnlySpan<byte>`gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="1d340-374">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="1d340-375">Geht davon aus, dass der JSON-Code ein Array von Objekten enthält und jedes Objekt eine "Name"-Eigenschaft vom Typ "String" enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="1d340-375">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="1d340-376">Zählt Objekte und `name` Eigenschaftswerte, die mit "University" enden.</span><span class="sxs-lookup"><span data-stu-id="1d340-376">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="1d340-377">Im folgenden finden Sie ein JSON-Beispiel, das der vorherige Code lesen kann.</span><span class="sxs-lookup"><span data-stu-id="1d340-377">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="1d340-378">Die resultierende Zusammenfassungs Meldung lautet: "2 von 4 haben Namen, die mit" University "enden:</span><span class="sxs-lookup"><span data-stu-id="1d340-378">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="1d340-379">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1d340-379">Additional resources</span></span>

* [<span data-ttu-id="1d340-380">Übersicht über System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="1d340-380">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1d340-381">System. Text. JSON-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="1d340-381">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="1d340-382">Schreiben von benutzerdefinierten Konvertern für "System. Text. JSON"</span><span class="sxs-lookup"><span data-stu-id="1d340-382">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="1d340-383">DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="1d340-383">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="1d340-384">GitHub-Probleme im dotnet/corefx-Repository mit der Bezeichnung JSON-funktion\doc</span><span class="sxs-lookup"><span data-stu-id="1d340-384">GitHub issues in the dotnet/corefx repository labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
