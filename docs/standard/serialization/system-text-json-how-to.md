---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
description: Dieser Artikel veranschaulicht, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.
ms.date: 05/13/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 72ba79784d3eb1beb43eab8db0a448a7e3b18eb6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557839"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="9db7a-104">Serialisieren und Deserialisieren (Marshallen und Marshallen rückgängig machen) von JSON-Daten in .NET</span><span class="sxs-lookup"><span data-stu-id="9db7a-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="9db7a-105">Dieser Artikel veranschaulicht, wie Sie mithilfe des <xref:System.Text.Json>-Namespace Daten in das JSON-Format (JavaScript Object Notation) serialisiert und daraus deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-105">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="9db7a-106">Wenn Sie vorhandenen Code aus `Newtonsoft.Json` portieren, finden Sie weitere Informationen unter [Migrieren zu `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9db7a-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="9db7a-107">Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework wie [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="9db7a-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="9db7a-108">Im größten Teil des Serialisierungsbeispielcodes ist <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` festgelegt, um den JSON-Code übersichtlicher zu gestalten (mit Einzügen und Zwischenräumen für bessere Lesbarkeit).</span><span class="sxs-lookup"><span data-stu-id="9db7a-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="9db7a-109">Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="9db7a-110">Die Codebeispiele verweisen auf die folgende Klasse und deren Varianten:</span><span class="sxs-lookup"><span data-stu-id="9db7a-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="9db7a-111">Namespaces</span><span class="sxs-lookup"><span data-stu-id="9db7a-111">Namespaces</span></span>

<span data-ttu-id="9db7a-112">Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="9db7a-113">Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="9db7a-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="9db7a-114">Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Anweisungen für einen oder beide Namespaces:</span><span class="sxs-lookup"><span data-stu-id="9db7a-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="9db7a-115">Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden zurzeit in `System.Text.Json` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="9db7a-116">Schreiben von .NET-Objekten in JSON (Serialisieren)</span><span class="sxs-lookup"><span data-stu-id="9db7a-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="9db7a-117">Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, rufen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="9db7a-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9db7a-118">Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-119">Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9db7a-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-120">Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9db7a-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-121">In den vorangehenden Beispielen wird Typrückschluss für den zu serialisierenden Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="9db7a-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="9db7a-122">Eine Überladung von `Serialize()` akzeptiert einen generischen Typparameter:</span><span class="sxs-lookup"><span data-stu-id="9db7a-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="9db7a-123">Serialisierungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="9db7a-123">Serialization example</span></span>

<span data-ttu-id="9db7a-124">Im Folgenden finden Sie eine Beispielklasse, die Sammlungen und eine geschachtelte Klasse enthält:</span><span class="sxs-lookup"><span data-stu-id="9db7a-124">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="9db7a-125">Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="9db7a-125">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="9db7a-126">Die JSON-Ausgabe wird standardmäßig verkleinert:</span><span class="sxs-lookup"><span data-stu-id="9db7a-126">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="9db7a-127">Im folgenden Beispiel wird derselbe JSON-Code dargestellt, allerdings formatiert (d. h. übersichtlich mit Zwischenräumen und Einzügen):</span><span class="sxs-lookup"><span data-stu-id="9db7a-127">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="9db7a-128">Serialisieren in UTF-8</span><span class="sxs-lookup"><span data-stu-id="9db7a-128">Serialize to UTF-8</span></span>

<span data-ttu-id="9db7a-129">Um in UTF-8 zu serialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="9db7a-129">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-130">Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A>-Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> akzeptiert, ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9db7a-130">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="9db7a-131">Das Serialisieren in UTF-8 ist ungefähr 5–10 % schneller als die Verwendung von zeichenfolgenbasierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-131">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="9db7a-132">Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-132">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="9db7a-133">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="9db7a-133">Serialization behavior</span></span>

* <span data-ttu-id="9db7a-134">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9db7a-134">By default, all public properties are serialized.</span></span> <span data-ttu-id="9db7a-135">Sie können [auszuschließende Eigenschaften angeben](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="9db7a-135">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="9db7a-136">Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-136">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="9db7a-137">JSON wird standardmäßig verkleinert.</span><span class="sxs-lookup"><span data-stu-id="9db7a-137">By default, JSON is minified.</span></span> <span data-ttu-id="9db7a-138">Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="9db7a-138">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="9db7a-139">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-139">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="9db7a-140">Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="9db7a-140">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="9db7a-141">Zirkelbezüge werden erkannt und daraufhin Ausnahmen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9db7a-141">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="9db7a-142">Aktuell werden [Felder](../../csharp/programming-guide/classes-and-structs/fields.md) ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-142">Currently, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are excluded.</span></span>

<span data-ttu-id="9db7a-143">Unter anderem unterstützte Typen:</span><span class="sxs-lookup"><span data-stu-id="9db7a-143">Supported types include:</span></span>

* <span data-ttu-id="9db7a-144">.NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="9db7a-144">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="9db7a-145">Benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="9db7a-145">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="9db7a-146">Eindimensionale und Jagged Arrays (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="9db7a-146">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="9db7a-147">Ein `Dictionary<string,TValue>`, wobei `TValue` ein `object` ist, ein `JsonElement` oder ein POCO.</span><span class="sxs-lookup"><span data-stu-id="9db7a-147">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="9db7a-148">Sammlungen aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="9db7a-148">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="9db7a-149">Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-149">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="9db7a-150">Lesen von JSON in .NET-Objekte (Deserialisieren)</span><span class="sxs-lookup"><span data-stu-id="9db7a-150">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="9db7a-151">Um aus einer Zeichenfolge oder einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="9db7a-151">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9db7a-152">Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecast`-Klasse erstellt, die schon zuvor im [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:</span><span class="sxs-lookup"><span data-stu-id="9db7a-152">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="9db7a-153">Um mithilfe von synchronem Code aus einer Datei zu deserialisieren, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-153">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="9db7a-154">Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="9db7a-154">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="9db7a-155">Deserialisieren aus UTF-8</span><span class="sxs-lookup"><span data-stu-id="9db7a-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="9db7a-156">Um aus UTF-8 zu deserialisieren, rufen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung auf, die einen `Utf8JsonReader` oder ein `ReadOnlySpan<byte>` akzeptiert, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="9db7a-157">In den Beispielen wird vorausgesetzt, dass sich das JSON in einem Bytearray namens „jsonUtf8Bytes“ befindet.</span><span class="sxs-lookup"><span data-stu-id="9db7a-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="9db7a-158">Deserialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="9db7a-158">Deserialization behavior</span></span>

* <span data-ttu-id="9db7a-159">Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="9db7a-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="9db7a-160">Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="9db7a-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="9db7a-161">Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9db7a-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="9db7a-162">Die Deserialisierung in Verweistypen ohne einen parameterlosen Konstruktor wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="9db7a-163">Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="9db7a-164">Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-164">By default, enums are supported as numbers.</span></span> <span data-ttu-id="9db7a-165">Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="9db7a-165">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="9db7a-166">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-166">Fields aren't supported.</span></span>
* <span data-ttu-id="9db7a-167">Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="9db7a-167">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="9db7a-168">Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="9db7a-168">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="9db7a-169">Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.</span><span class="sxs-lookup"><span data-stu-id="9db7a-169">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="9db7a-170">Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-170">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="9db7a-171">Serialisieren in formatierten JSON-Code</span><span class="sxs-lookup"><span data-stu-id="9db7a-171">Serialize to formatted JSON</span></span>

<span data-ttu-id="9db7a-172">Um die JSON-Ausgabe übersichtlich zu formatieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="9db7a-172">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="9db7a-173">Hier sehen Sie einen zu serialisierenden Beispieltyp und die übersichtlich formatierte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9db7a-173">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="9db7a-174">Anpassen von JSON-Namen und -Werten</span><span class="sxs-lookup"><span data-stu-id="9db7a-174">Customize JSON names and values</span></span>

<span data-ttu-id="9db7a-175">Standardmäßig bleiben Eigenschaftsnamen und Wörterbuchschlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="9db7a-176">Enumerationswerte werden als Zahlen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-176">Enum values are represented as numbers.</span></span> <span data-ttu-id="9db7a-177">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="9db7a-177">This section explains how to:</span></span>

* [<span data-ttu-id="9db7a-178">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="9db7a-178">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="9db7a-179">Konvertieren aller Eigenschaftsnamen in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="9db7a-179">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="9db7a-180">Implementieren einer benutzerdefinierten Benennungsrichtlinie für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9db7a-180">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="9db7a-181">Konvertieren von Wörterbuchschlüsseln in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="9db7a-181">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="9db7a-182">Konvertieren von Enumerationen in Zeichenfolgen und Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="9db7a-182">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="9db7a-183">Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und -werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9db7a-183">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="9db7a-184">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="9db7a-184">Customize individual property names</span></span>

<span data-ttu-id="9db7a-185">Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das Attribut [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="9db7a-185">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="9db7a-186">Hier finden Sie einen zu serialisierenden Beispieltyp und die daraus resultierende JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9db7a-186">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9db7a-187">Der über dieses Attribut festgelegte Eigenschaftsname:</span><span class="sxs-lookup"><span data-stu-id="9db7a-187">The property name set by this attribute:</span></span>

* <span data-ttu-id="9db7a-188">Dies gilt in beide Richtungen, für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-188">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="9db7a-189">Es hat Vorrang vor Benennungsrichtlinien für Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9db7a-189">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="9db7a-190">Verwenden der Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="9db7a-190">Use camel case for all JSON property names</span></span>

<span data-ttu-id="9db7a-191">Um die Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen zu verwenden, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-191">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="9db7a-192">Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9db7a-192">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9db7a-193">Die Camel-Case-Benennungsrichtlinie für Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9db7a-193">The camel case property naming policy:</span></span>

* <span data-ttu-id="9db7a-194">Gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-194">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="9db7a-195">Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-195">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="9db7a-196">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="9db7a-196">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="9db7a-197">Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9db7a-197">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="9db7a-198">Um eine benutzerdefinierte Benennungsrichtlinie für JSON-Eigenschaften zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und setzen Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode außer Kraft, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-198">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="9db7a-199">Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihre Benennungsrichtlinienklasse fest:</span><span class="sxs-lookup"><span data-stu-id="9db7a-199">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-200">Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9db7a-200">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9db7a-201">Die Benennungsrichtlinie für JSON-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9db7a-201">The JSON property naming policy:</span></span>

* <span data-ttu-id="9db7a-202">Gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-202">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="9db7a-203">Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-203">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="9db7a-204">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="9db7a-204">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="9db7a-205">Wörterbuchschlüssel in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="9db7a-205">Camel case dictionary keys</span></span>

<span data-ttu-id="9db7a-206">Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die Schlüssel vom Typ `string` in Camel-Case-Schreibweise konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-206">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="9db7a-207">Legen Sie hierzu <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-207">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-208">Das Serialisieren eines Objekts mit einem Wörterbuch namens `TemperatureRanges`, das die Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` enthält, würde zu einer JSON-Ausgabe wie im folgenden Beispiel führen:</span><span class="sxs-lookup"><span data-stu-id="9db7a-208">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="9db7a-209">Die Camel-Case-Benennungsrichtlinie für Wörterbuchschlüssel gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-209">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="9db7a-210">Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei auch dann, wenn Sie `JsonNamingPolicy.CamelCase` als `DictionaryKeyPolicy` angeben.</span><span class="sxs-lookup"><span data-stu-id="9db7a-210">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="9db7a-211">Enumerationen als Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9db7a-211">Enums as strings</span></span>

<span data-ttu-id="9db7a-212">Standardmäßig werden Enumerationen als Zahlen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9db7a-212">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="9db7a-213">Um Enumerationen als Zeichenfolgen zu serialisieren, verwenden Sie <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="9db7a-213">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="9db7a-214">Angenommen, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-214">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="9db7a-215">Wenn die Zusammenfassung `Hot` ist, hat das serialisierte JSON standardmäßig den numerischen Wert 3:</span><span class="sxs-lookup"><span data-stu-id="9db7a-215">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="9db7a-216">Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:</span><span class="sxs-lookup"><span data-stu-id="9db7a-216">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-217">Das resultierende JSON sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="9db7a-217">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="9db7a-218">Zeichenfolgennamen von Enumerationen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-218">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="9db7a-219">Ausschließen von Eigenschaften aus der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="9db7a-219">Exclude properties from serialization</span></span>

<span data-ttu-id="9db7a-220">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9db7a-220">By default, all public properties are serialized.</span></span> <span data-ttu-id="9db7a-221">Wenn Sie möchten, dass einige von ihnen nicht in der JSON-Ausgabe vorkommen, haben Sie mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="9db7a-221">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="9db7a-222">In diesem Abschnitt wird erläutert, wie Sie Folgendes ausschließen können:</span><span class="sxs-lookup"><span data-stu-id="9db7a-222">This section explains how to exclude:</span></span>

* [<span data-ttu-id="9db7a-223">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9db7a-223">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="9db7a-224"> Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9db7a-224">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="9db7a-225">Alle Nullwert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9db7a-225">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="9db7a-226">Ausschließen einzelner Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9db7a-226">Exclude individual properties</span></span>

<span data-ttu-id="9db7a-227">Um einzelne Eigenschaften zu ignorieren, verwenden Sie das Attribut [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="9db7a-227">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="9db7a-228">Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9db7a-228">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="9db7a-229">Ausschließen aller schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9db7a-229">Exclude all read-only properties</span></span>

<span data-ttu-id="9db7a-230">Eine Eigenschaft ist schreibgeschützt, wenn sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.</span><span class="sxs-lookup"><span data-stu-id="9db7a-230">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="9db7a-231">Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-231">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-232">Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9db7a-232">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="9db7a-233">Diese Option gilt nur für Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-233">This option applies only to serialization.</span></span> <span data-ttu-id="9db7a-234">Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9db7a-234">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="9db7a-235">Ausschließen aller Nullwert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9db7a-235">Exclude all null value properties</span></span>

<span data-ttu-id="9db7a-236">Um alle Nullwert-Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-236">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-237">Hier finden Sie ein zu serialisierendes Beispielobjekt und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9db7a-237">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="9db7a-238">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9db7a-238">Property</span></span> |<span data-ttu-id="9db7a-239">Wert</span><span class="sxs-lookup"><span data-stu-id="9db7a-239">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="9db7a-240">Datum</span><span class="sxs-lookup"><span data-stu-id="9db7a-240">Date</span></span>    | <span data-ttu-id="9db7a-241">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="9db7a-241">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="9db7a-242">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="9db7a-242">TemperatureCelsius</span></span>| <span data-ttu-id="9db7a-243">25</span><span class="sxs-lookup"><span data-stu-id="9db7a-243">25</span></span> |
| <span data-ttu-id="9db7a-244">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="9db7a-244">Summary</span></span>| <span data-ttu-id="9db7a-245">NULL</span><span class="sxs-lookup"><span data-stu-id="9db7a-245">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="9db7a-246">Diese Einstellung gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-246">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="9db7a-247">Informationen zu ihren Auswirkungen auf die Deserialisierung finden Sie unter [Ignorieren von Null beim Deserialisieren](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="9db7a-247">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="9db7a-248">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="9db7a-248">Customize character encoding</span></span>

<span data-ttu-id="9db7a-249">Standardmäßig escapet der Serialisierer alle Nicht-ASCII-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-249">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="9db7a-250">Das heißt, dass sie durch `\uxxxx` ersetzt werden, wobei `xxxx` der Unicode-Code des Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="9db7a-250">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="9db7a-251">Wenn die `Summary`-Eigenschaft beispielsweise auf Kyrillisch „жарко“ festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="9db7a-251">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="9db7a-252">Serialisieren von Sprachzeichensätzen</span><span class="sxs-lookup"><span data-stu-id="9db7a-252">Serialize language character sets</span></span>

<span data-ttu-id="9db7a-253">Zum Serialisieren der Zeichensätze von mindestens einer Sprache ohne zu escapen geben Sie [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) an, wenn Sie eine Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> erstellen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-253">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="9db7a-254">Mit diesem Code werden weder kyrillische noch griechische Zeichen escapet.</span><span class="sxs-lookup"><span data-stu-id="9db7a-254">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="9db7a-255">Wenn die `Summary`-Eigenschaft auf Kyrillisch „жарко“ festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="9db7a-255">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="9db7a-256">Um alle Sprachensätze ohne zu escapen zu serialisieren, verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9db7a-256">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="9db7a-257">Serialisieren bestimmter Zeichen</span><span class="sxs-lookup"><span data-stu-id="9db7a-257">Serialize specific characters</span></span>

<span data-ttu-id="9db7a-258">Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne dass sie escapet werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-258">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="9db7a-259">Im folgenden Beispiel werden nur die ersten zwei Zeichen von „жарко“ serialisiert:</span><span class="sxs-lookup"><span data-stu-id="9db7a-259">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="9db7a-260">Hier sehen Sie eine JSON-Beispiel, das vom vorangehenden Code erzeugt wird:</span><span class="sxs-lookup"><span data-stu-id="9db7a-260">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="9db7a-261">Serialisieren aller Zeichen</span><span class="sxs-lookup"><span data-stu-id="9db7a-261">Serialize all characters</span></span>

<span data-ttu-id="9db7a-262">Um das Escapen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-262">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="9db7a-263">Im Vergleich zum Standardencoder ist der `UnsafeRelaxedJsonEscaping`-Encoder weniger streng beim Zulassen von Zeichen, ohne sie zu escapen:</span><span class="sxs-lookup"><span data-stu-id="9db7a-263">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="9db7a-264">Er escapet keine HTML-abhängigen Zeichen wie `<`, `>`, `&` und `'`.</span><span class="sxs-lookup"><span data-stu-id="9db7a-264">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="9db7a-265">Er bietet keine zusätzlichen, tief greifenden Abwehrmaßnahmen gegen solche Cross-Site Scripting (XSS)- oder Information-Disclosure-Angriffe (Veröffentlichung von Informationen), die von einem Client und Server, die sich nicht auf einen *Zeichensatz* einigen können, verursacht werden können.</span><span class="sxs-lookup"><span data-stu-id="9db7a-265">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="9db7a-266">Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretieren wird.</span><span class="sxs-lookup"><span data-stu-id="9db7a-266">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="9db7a-267">Beispielsweise können Sie ihn verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8` sendet.</span><span class="sxs-lookup"><span data-stu-id="9db7a-267">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="9db7a-268">Gestatten Sie niemals, dass die `UnsafeRelaxedJsonEscaping`-Rohausgabe in eine HTML-Seite oder ein `<script>`-Element ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9db7a-268">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="9db7a-269">Serialisieren von Eigenschaften abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="9db7a-269">Serialize properties of derived classes</span></span>

<span data-ttu-id="9db7a-270">Das Serialisieren einer polymorphen Typhierarchie wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-270">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="9db7a-271">Wenn eine Eigenschaft beispielsweise als eine Schnittstelle oder eine abstrakte Klasse definiert wird, werden nur die für die Schnittstelle oder abstrakte Klasse definierten Eigenschaften serialisiert, auch wenn der Laufzeittyp über zusätzliche Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-271">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="9db7a-272">Die Ausnahmen bei diesem Verhalten werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="9db7a-272">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="9db7a-273">Nehmen Sie beispielsweise an, Sie besitzen eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="9db7a-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="9db7a-274">Ferner sei angenommen, dass das Typargument der `Serialize`-Methode zur Kompilierzeit `WeatherForecast` ist:</span><span class="sxs-lookup"><span data-stu-id="9db7a-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="9db7a-275">In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch dann nicht, wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="9db7a-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="9db7a-276">Nur die Basisklasseneigenschaften werden serialisiert:</span><span class="sxs-lookup"><span data-stu-id="9db7a-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="9db7a-277">Dieses Verhalten soll die versehentliche Verfügbarmachung von Daten in einem abgeleiteten, zur Laufzeit erstellten Typ verhindern.</span><span class="sxs-lookup"><span data-stu-id="9db7a-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="9db7a-278">Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs im vorherigen Beispiel zu serialisieren:</span><span class="sxs-lookup"><span data-stu-id="9db7a-278">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="9db7a-279">Rufen Sie eine Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A> auf, bei der Sie den Typ zur Laufzeit angeben können:</span><span class="sxs-lookup"><span data-stu-id="9db7a-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="9db7a-280">Deklarieren Sie das zu serialisierende Objekt als `object`.</span><span class="sxs-lookup"><span data-stu-id="9db7a-280">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="9db7a-281">Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in die JSON-Ausgabe aufgenommen wird:</span><span class="sxs-lookup"><span data-stu-id="9db7a-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="9db7a-282">Diese Ansätze bieten polymorphe Serialisierung nur für das Stammobjekt, das serialisiert werden soll, und nicht für die Eigenschaften dieses Stammobjekts.</span><span class="sxs-lookup"><span data-stu-id="9db7a-282">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="9db7a-283">Sie können polymorphe Serialisierung für Objekte auf niedrigerer Ebene erzielen, wenn Sie diese als `object`-Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="9db7a-283">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="9db7a-284">Angenommen, Ihre `WeatherForecast`-Klasse verfügt über eine Eigenschaft mit dem Namen `PreviousForecast`, die als `WeatherForecast`-Typ oder als `object`-Typ definiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="9db7a-284">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="9db7a-285">Wenn die Eigenschaft `PreviousForecast` eine Instanz von `WeatherForecastDerived` enthält:</span><span class="sxs-lookup"><span data-stu-id="9db7a-285">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="9db7a-286">Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPrevious` **enthält keine** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="9db7a-286">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="9db7a-287">Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPreviousAsObject` **enthält** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="9db7a-287">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="9db7a-288">Um `WeatherForecastWithPreviousAsObject` zu serialisieren, ist es nicht erforderlich, `Serialize<object>` oder `GetType` aufzurufen, da das Stammobjekt nicht das Objekt ist, das von einem abgeleiteten Typ sein darf.</span><span class="sxs-lookup"><span data-stu-id="9db7a-288">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="9db7a-289">Im folgenden Codebeispiel wird weder `Serialize<object>` noch `GetType` aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="9db7a-289">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="9db7a-290">Der vorangehende Code serialisiert `WeatherForecastWithPreviousAsObject` korrekt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-290">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="9db7a-291">Derselbe Ansatz zum Definieren von Eigenschaften als `object` funktioniert mit Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-291">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="9db7a-292">Angenommen, Sie haben die folgende Schnittstelle und Implementierung, und Sie möchten eine Klasse mit Eigenschaften serialisieren, die Implementierungsinstanzen enthalten:</span><span class="sxs-lookup"><span data-stu-id="9db7a-292">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="9db7a-293">Wenn Sie eine Instanz von `Forecasts` serialisieren, zeigt nur `Tuesday` die `WindSpeed`-Eigenschaft an, da `Tuesday` als `object` definiert ist:</span><span class="sxs-lookup"><span data-stu-id="9db7a-293">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="9db7a-294">Im folgenden Beispiel wird der JSON-Code gezeigt, der aus dem vorangehenden Code resultiert:</span><span class="sxs-lookup"><span data-stu-id="9db7a-294">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="9db7a-295">Weitere Informationen zur polymorphen **Serialisierung** sowie Informationen zur **Deserialisierung** finden Sie unter [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="9db7a-295">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="9db7a-296">Zulassen von Kommentaren und nachfolgenden Kommas</span><span class="sxs-lookup"><span data-stu-id="9db7a-296">Allow comments and trailing commas</span></span>

<span data-ttu-id="9db7a-297">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9db7a-297">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="9db7a-298">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest.</span><span class="sxs-lookup"><span data-stu-id="9db7a-298">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="9db7a-299">Und um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="9db7a-299">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="9db7a-300">Das folgende Beispiel veranschaulicht, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="9db7a-300">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="9db7a-301">Im Folgenden finden Sie ein JSON-Beispiel mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="9db7a-301">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="9db7a-302">Eigenschaftenabgleich ohne Beachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="9db7a-302">Case-insensitive property matching</span></span>

<span data-ttu-id="9db7a-303">Standardmäßig wird bei der Deserialisierung nach Übereinstimmungen von Eigenschaftsnamen zwischen JSON und den Zielobjekteigenschaften unter Berücksichtigung von Groß-/Kleinschreibung gesucht.</span><span class="sxs-lookup"><span data-stu-id="9db7a-303">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="9db7a-304">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="9db7a-304">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="9db7a-305">Im Folgenden finden Sie ein JSON-Beispiel mit Eigenschaftsnamen in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="9db7a-305">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="9db7a-306">Es kann in den folgenden Typ deserialisiert werden, der Eigenschaftsnamen in Pascal-Schreibweise besitzt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-306">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="9db7a-307">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="9db7a-307">Handle overflow JSON</span></span>

<span data-ttu-id="9db7a-308">Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, die nicht von Eigenschaften des Zieltyps dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-308">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="9db7a-309">Angenommen, Ihr Zieltyp ist folgender:</span><span class="sxs-lookup"><span data-stu-id="9db7a-309">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="9db7a-310">Und der zu deserialisierende JSON-Code ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-310">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="9db7a-311">Wenn Sie den angezeigten JSON-Code in den gezeigten Typ deserialisieren, gibt es keinen Ort mehr für die Eigenschaften `DatesAvailable` und `SummaryWords`, und sie gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="9db7a-311">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="9db7a-312">Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)-Attribut auf eine Eigenschaft des Typs `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:</span><span class="sxs-lookup"><span data-stu-id="9db7a-312">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="9db7a-313">Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="9db7a-313">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="9db7a-314">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9db7a-314">Property</span></span> |<span data-ttu-id="9db7a-315">Wert</span><span class="sxs-lookup"><span data-stu-id="9db7a-315">Value</span></span>  |<span data-ttu-id="9db7a-316">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9db7a-316">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="9db7a-317">Datum</span><span class="sxs-lookup"><span data-stu-id="9db7a-317">Date</span></span>    | <span data-ttu-id="9db7a-318">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="9db7a-318">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="9db7a-319">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="9db7a-319">TemperatureCelsius</span></span>| <span data-ttu-id="9db7a-320">0</span><span class="sxs-lookup"><span data-stu-id="9db7a-320">0</span></span> | <span data-ttu-id="9db7a-321">Keine Übereinstimmung unter Berücksichtigung von Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die Eigenschaft nicht festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9db7a-321">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="9db7a-322">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="9db7a-322">Summary</span></span> | <span data-ttu-id="9db7a-323">Heiß</span><span class="sxs-lookup"><span data-stu-id="9db7a-323">Hot</span></span> ||
| <span data-ttu-id="9db7a-324">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="9db7a-324">ExtensionData</span></span> | <span data-ttu-id="9db7a-325">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="9db7a-325">temperatureCelsius: 25</span></span> |<span data-ttu-id="9db7a-326">Da die Groß-/Kleinschreibung nicht übereinstimmte, ist diese JSON-Eigenschaft ein zusätzliches Element und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="9db7a-326">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="9db7a-327">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="9db7a-327">DatesAvailable:</span></span><br>  <span data-ttu-id="9db7a-328">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="9db7a-328">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="9db7a-329">8/2/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="9db7a-329">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="9db7a-330">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="9db7a-330">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="9db7a-331">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="9db7a-331">SummaryWords:</span></span><br><span data-ttu-id="9db7a-332">Toll</span><span class="sxs-lookup"><span data-stu-id="9db7a-332">Cool</span></span><br><span data-ttu-id="9db7a-333">Windig</span><span class="sxs-lookup"><span data-stu-id="9db7a-333">Windy</span></span><br><span data-ttu-id="9db7a-334">Feucht</span><span class="sxs-lookup"><span data-stu-id="9db7a-334">Humid</span></span> |<span data-ttu-id="9db7a-335">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="9db7a-335">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="9db7a-336">Wenn das Zielobjekt serialisiert wird, werden die Schlüssel-Wert-Paare der Erweiterungsdaten zu genau solchen JSON-Eigenschaften, wie sie im eingehenden JSON-Code waren:</span><span class="sxs-lookup"><span data-stu-id="9db7a-336">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="9db7a-337">Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code vorkommt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-337">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="9db7a-338">Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert würden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-338">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="9db7a-339">Ignorieren von Null beim Deserialisieren</span><span class="sxs-lookup"><span data-stu-id="9db7a-339">Ignore null when deserializing</span></span>

<span data-ttu-id="9db7a-340">Wenn eine Eigenschaft in JSON Null ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf Null festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-340">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="9db7a-341">In einigen Szenarien kann die Zieleigenschaft möglicherweise einen Standardwert besitzen, und Sie möchten nicht, dass dieser Standardwert von einem Nullwert überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="9db7a-341">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="9db7a-342">Angenommen, der folgende Code stellt Ihr Zielobjekt dar:</span><span class="sxs-lookup"><span data-stu-id="9db7a-342">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="9db7a-343">Und ferner angenommen, der folgende JSON-Code wird deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="9db7a-343">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="9db7a-344">Nach der Deserialisierung ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts Null.</span><span class="sxs-lookup"><span data-stu-id="9db7a-344">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="9db7a-345">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-345">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="9db7a-346">Bei dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts der Standardwert „Keine Zusammenfassung“ nach der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="9db7a-346">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="9db7a-347">Nullwerte im JSON werden nur ignoriert, wenn Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="9db7a-347">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="9db7a-348">Nullwerte für Non-Nullable-Werttypen verursachen Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-348">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="9db7a-349">„Utf8JsonReader“, „Utf8JsonWriter“ und „JsonDocument“</span><span class="sxs-lookup"><span data-stu-id="9db7a-349">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="9db7a-350"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, rein vorwärtsgerichteter Reader mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der aus einem `ReadOnlySpan<byte>` oder `ReadOnlySequence<byte>` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="9db7a-350"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="9db7a-351">Der `Utf8JsonReader` ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierungsprogrammen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9db7a-351">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="9db7a-352">Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` verdeckt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-352">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="9db7a-353">Mit <xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell mit hohem Durchsatz schreiben.</span><span class="sxs-lookup"><span data-stu-id="9db7a-353"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="9db7a-354">Der Writer ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9db7a-354">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="9db7a-355">Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` verdeckt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-355">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="9db7a-356"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mithilfe von `Utf8JsonReader` ein schreibgeschütztes Dokumentobjektmodell (DOM) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-356"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="9db7a-357">Das DOM bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="9db7a-357">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="9db7a-358">Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den Typ <xref:System.Text.Json.JsonElement> zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-358">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="9db7a-359">Der `JsonElement`-Typ stellt Array- und Objektenumeratoren sowie APIs zum Konvertieren von JSON-Text in gängige .NET-Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="9db7a-359">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="9db7a-360">`JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9db7a-360">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="9db7a-361">In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-361">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="9db7a-362">Verwenden von „JsonDocument“ für den Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="9db7a-362">Use JsonDocument for access to data</span></span>

<span data-ttu-id="9db7a-363">Das folgende Beispiel zeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:</span><span class="sxs-lookup"><span data-stu-id="9db7a-363">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="9db7a-364">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="9db7a-364">The preceding code:</span></span>

* <span data-ttu-id="9db7a-365">Setzt voraus, dass sich der zu analysierende JSON-Code in einer Zeichenfolge namens `jsonString` befindet.</span><span class="sxs-lookup"><span data-stu-id="9db7a-365">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="9db7a-366">Berechnet eine durchschnittliche Note für Objekte in einem `Students`-Array, die eine `Grade`-Eigenschaft besitzen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-366">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="9db7a-367">Weist Kursteilnehmern, die keine Note haben, eine Standardnote von 70 zu.</span><span class="sxs-lookup"><span data-stu-id="9db7a-367">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="9db7a-368">Zählt Kursteilnehmer durch Inkrementieren einer `count`-Variablen bei jeder Iteration.</span><span class="sxs-lookup"><span data-stu-id="9db7a-368">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="9db7a-369">Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A> aufzurufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9db7a-369">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="9db7a-370">Im Folgenden finden Sie ein Beispiel für das JSON, das von diesem Code verarbeitet wird:</span><span class="sxs-lookup"><span data-stu-id="9db7a-370">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="9db7a-371">Verwenden von JsonDocument zum Schreiben von JSON</span><span class="sxs-lookup"><span data-stu-id="9db7a-371">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="9db7a-372">Das folgende Beispiel veranschaulicht, wie JSON aus einem <xref:System.Text.Json.JsonDocument> geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="9db7a-372">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="9db7a-373">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="9db7a-373">The preceding code:</span></span>

* <span data-ttu-id="9db7a-374">Liest eine JSON-Datei, lädt die Daten in ein `JsonDocument` und schreibt (übersichtlich) formatierten JSON-Code in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="9db7a-374">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="9db7a-375">Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-375">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="9db7a-376">Ruft nach Abschluss <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf.</span><span class="sxs-lookup"><span data-stu-id="9db7a-376">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="9db7a-377">Eine Alternative besteht darin, den Writer automatisch zu leeren, wenn er entsorgt wird.</span><span class="sxs-lookup"><span data-stu-id="9db7a-377">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="9db7a-378">Im Folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die von dem Beispielcode verarbeitet werden soll:</span><span class="sxs-lookup"><span data-stu-id="9db7a-378">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="9db7a-379">Das Ergebnis ist die folgende, übersichtlich formatierte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9db7a-379">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="9db7a-380">Verwenden von „Utf8JsonWriter“</span><span class="sxs-lookup"><span data-stu-id="9db7a-380">Use Utf8JsonWriter</span></span>

<span data-ttu-id="9db7a-381">Im folgenden Beispiel wird die Verwendung der <xref:System.Text.Json.Utf8JsonWriter>-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="9db7a-381">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="9db7a-382">Verwenden von „Utf8JsonReader“</span><span class="sxs-lookup"><span data-stu-id="9db7a-382">Use Utf8JsonReader</span></span>

<span data-ttu-id="9db7a-383">Im folgenden Beispiel wird die Verwendung der <xref:System.Text.Json.Utf8JsonReader>-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="9db7a-383">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="9db7a-384">Der vorangehende Code setzt voraus, dass es sich bei der `jsonUtf8`-Variablen um ein Bytearray handelt, das gültigen, UTF-8-codierten JSON-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="9db7a-384">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="9db7a-385">Filtern von Daten mithilfe von „Utf8JsonReader“</span><span class="sxs-lookup"><span data-stu-id="9db7a-385">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="9db7a-386">Das folgende Beispiel zeigt, wie Sie eine Datei synchron lesen und nach einem Wert suchen:</span><span class="sxs-lookup"><span data-stu-id="9db7a-386">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="9db7a-387">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="9db7a-387">The preceding code:</span></span>

* <span data-ttu-id="9db7a-388">Setzt voraus, dass der JSON-Code ein Array von Objekten enthält, und dass jedes Objekt eine Eigenschaft „name“ vom Typ „string“ (Zeichenfolge) enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="9db7a-388">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="9db7a-389">Zählt Objekte und „name“-Eigenschaftswerte, die auf „University“ enden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-389">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="9db7a-390">Setzt voraus, dass die Datei UTF-16-codiert ist und transcodiert sie in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9db7a-390">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="9db7a-391">Eine UTF-8-codierte Datei kann mithilfe des folgenden Codes direkt in ein `ReadOnlySpan<byte>` gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="9db7a-391">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="9db7a-392">Wenn die Datei eine UTF-8-Bytereihenfolge-Marke (BOM) enthält, entfernen Sie diese, bevor Sie die Bytes an den `Utf8JsonReader` übergeben, da der Reader Text erwartet.</span><span class="sxs-lookup"><span data-stu-id="9db7a-392">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="9db7a-393">Andernfalls wird die BOM als ungültiges JSON betrachtet, und der Reader löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="9db7a-393">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="9db7a-394">Im Folgenden finden Sie ein JSON-Beispiel, das der voranstehende Code lesen kann.</span><span class="sxs-lookup"><span data-stu-id="9db7a-394">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="9db7a-395">Die resultierende Zusammenfassungsmeldung lautet „2 out of 2 have names that end with ‚University‘“ (2 von 4 besitzen Namen, die auf „University“ enden):</span><span class="sxs-lookup"><span data-stu-id="9db7a-395">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="9db7a-396">Lesen aus einem Stream mithilfe von Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="9db7a-396">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="9db7a-397">Wenn Sie eine große Datei (z. B. ein Gigabyte oder mehr) lesen, möchten Sie die gesamte Datei vielleicht nicht auf einmal in den Arbeitsspeicher laden müssen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-397">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="9db7a-398">In diesem Szenario können Sie einen <xref:System.IO.FileStream> verwenden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-398">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="9db7a-399">Wenn Sie einen `Utf8JsonReader` zum Lesen aus einem Stream verwenden, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="9db7a-399">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="9db7a-400">Der Puffer, der die partielle JSON-Nutzlast enthält, muss mindestens so groß wie das größte JSON-Token darin sein, damit der Reader vorankommen kann.</span><span class="sxs-lookup"><span data-stu-id="9db7a-400">The buffer containing the partial JSON payload must be at least as big as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="9db7a-401">Der Puffer muss mindestens so groß wie die größte Sequenz von Leerraum innerhalb der JSON-Nutzlast sein.</span><span class="sxs-lookup"><span data-stu-id="9db7a-401">The buffer must be at least as big as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="9db7a-402">Der Reader verfolgt die gelesenen Daten nicht nach, bis er den nächsten <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in der JSON-Nutzlast vollständig gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="9db7a-402">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="9db7a-403">Wenn im Puffer noch Bytes vorhanden sind, müssen Sie sie wieder dem Reader übergeben.</span><span class="sxs-lookup"><span data-stu-id="9db7a-403">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="9db7a-404">Sie können <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> verwenden, um zu bestimmen, wie viele Bytes übrig bleiben.</span><span class="sxs-lookup"><span data-stu-id="9db7a-404">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="9db7a-405">Im folgenden Code wird veranschaulicht, wie aus einem Stream gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="9db7a-405">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="9db7a-406">Das Beispiel zeigt einen <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="9db7a-406">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="9db7a-407">Ähnlicher Code funktioniert mit einem <xref:System.IO.FileStream>, es sei denn, der `FileStream` enthält am Anfang eine UTF-8-BOM.</span><span class="sxs-lookup"><span data-stu-id="9db7a-407">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="9db7a-408">In diesem Fall müssen Sie diese drei Bytes aus dem Puffer entfernen, bevor Sie die verbleibenden Bytes an den `Utf8JsonReader` übergeben.</span><span class="sxs-lookup"><span data-stu-id="9db7a-408">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="9db7a-409">Andernfalls würde der Reader eine Ausnahme auslösen, da die BOM nicht als gültiger Teil des JSON-Codes angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="9db7a-409">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="9db7a-410">Der Beispielcode beginnt mit einem 4-KB-Puffer und verdoppelt die Puffergröße jedes Mal, wenn festgestellt wird, dass die Größe nicht ausreicht, um einem kompletten JSON-Token zu entsprechen. Dies ist erforderlich, damit der Reader mit der JSON-Nutzlast vorankommt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-410">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not big enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="9db7a-411">Das JSON-Beispiel im Codeausschnitt löst nur dann eine Erhöhung der Puffergröße aus, wenn Sie eine sehr geringe Anfangspuffergröße festlegen, z. B. 10 Bytes.</span><span class="sxs-lookup"><span data-stu-id="9db7a-411">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="9db7a-412">Die `Console.WriteLine`-Anweisungen zeigen Ursache und Auswirkung der Puffergrößenerhöhungen, wenn Sie die Anfangspuffergröße auf 10 festlegen.</span><span class="sxs-lookup"><span data-stu-id="9db7a-412">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="9db7a-413">Bei der Anfangspuffergröße von 4 KB wird das gesamte JSON-Beispiel von jeder `Console.WriteLine` angezeigt, und die Puffergröße muss nie erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="9db7a-413">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="9db7a-414">Im vorherigen Beispiel wurde keine Pufferobergrenze festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-414">The preceding example sets no limit to how big the buffer can grow.</span></span> <span data-ttu-id="9db7a-415">Bei übermäßiger Tokengröße kann bei dem Code ein <xref:System.OutOfMemoryException>-Ausnahmefehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="9db7a-415">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="9db7a-416">Dies kann vorkommen, wenn der JSON-Code ein ungefähr 1 GB großes oder größeres Token enthält, da das Token bei Verdoppelung von 1 GB nicht mehr in einen `int32`-Puffer passt.</span><span class="sxs-lookup"><span data-stu-id="9db7a-416">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9db7a-417">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9db7a-417">Additional resources</span></span>

* [<span data-ttu-id="9db7a-418">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="9db7a-418">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="9db7a-419">Schreiben von benutzerdefinierten Konvertern</span><span class="sxs-lookup"><span data-stu-id="9db7a-419">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="9db7a-420">Migrieren von Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="9db7a-420">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="9db7a-421">Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="9db7a-421">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="9db7a-422">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="9db7a-422">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
