---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
description: Hier erfahren Sie, wie Sie mithilfe des System.Text.Json-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Er enthält Beispielcode.
ms.date: 10/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 0fda248b7d2e5a7cfa748447d0265565cb160b7e
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997780"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="7996a-104">Serialisieren und Deserialisieren (Marshallen und Marshallen rückgängig machen) von JSON-Daten in .NET</span><span class="sxs-lookup"><span data-stu-id="7996a-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="7996a-105">Dieser Artikel veranschaulicht, wie Sie mithilfe des <xref:System.Text.Json?displayProperty=fullName>-Namespace Daten in das JSON-Format (JavaScript Object Notation) serialisieren und daraus deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="7996a-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="7996a-106">Wenn Sie vorhandenen Code aus `Newtonsoft.Json` portieren, finden Sie weitere Informationen unter [Migrieren zu `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="7996a-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="7996a-107">Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework wie [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="7996a-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="7996a-108">Im größten Teil des Serialisierungsbeispielcodes ist <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` festgelegt, um den JSON-Code übersichtlicher zu gestalten (mit Einzügen und Zwischenräumen für bessere Lesbarkeit).</span><span class="sxs-lookup"><span data-stu-id="7996a-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="7996a-109">Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7996a-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="7996a-110">Die Codebeispiele verweisen auf die folgende Klasse und deren Varianten:</span><span class="sxs-lookup"><span data-stu-id="7996a-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="7996a-111">Namespaces</span><span class="sxs-lookup"><span data-stu-id="7996a-111">Namespaces</span></span>

<span data-ttu-id="7996a-112">Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen.</span><span class="sxs-lookup"><span data-stu-id="7996a-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="7996a-113">Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7996a-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="7996a-114">Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Anweisungen für einen oder beide Namespaces:</span><span class="sxs-lookup"><span data-stu-id="7996a-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="7996a-115">Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden zurzeit in `System.Text.Json` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7996a-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="7996a-116">Schreiben von .NET-Objekten in JSON (Serialisieren)</span><span class="sxs-lookup"><span data-stu-id="7996a-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="7996a-117">Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, rufen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="7996a-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="7996a-118">Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="7996a-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-119">Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7996a-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-120">Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7996a-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-121">In den vorangehenden Beispielen wird Typrückschluss für den zu serialisierenden Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="7996a-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="7996a-122">Eine Überladung von `Serialize()` akzeptiert einen generischen Typparameter:</span><span class="sxs-lookup"><span data-stu-id="7996a-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="7996a-123">Serialisierungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="7996a-123">Serialization example</span></span>

<span data-ttu-id="7996a-124">Im Folgenden finden Sie eine Beispielklasse, die die Sammlungstypeigenschaften und einen benutzerdefinierten Typen enthält:</span><span class="sxs-lookup"><span data-stu-id="7996a-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> <span data-ttu-id="7996a-125">„POCO“ steht für [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="7996a-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="7996a-126">Ein POCO ist ein .NET-Typ, der von keinen frameworkspezifischen Typen abhängig ist (z. B. durch Vererbung oder Attribute).</span><span class="sxs-lookup"><span data-stu-id="7996a-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="7996a-127">Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="7996a-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="7996a-128">Die JSON-Ausgabe wird standardmäßig verkleinert:</span><span class="sxs-lookup"><span data-stu-id="7996a-128">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="7996a-129">Im folgenden Beispiel wird derselbe JSON-Code dargestellt, allerdings in formatierter Form (d. h. übersichtlich mit Zwischenräumen und Einzügen):</span><span class="sxs-lookup"><span data-stu-id="7996a-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="7996a-130">Serialisieren in UTF-8</span><span class="sxs-lookup"><span data-stu-id="7996a-130">Serialize to UTF-8</span></span>

<span data-ttu-id="7996a-131">Um in UTF-8 zu serialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="7996a-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-132">Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A>-Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> akzeptiert, ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7996a-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="7996a-133">Das Serialisieren in UTF-8 ist ungefähr 5–10 % schneller als die Verwendung von zeichenfolgenbasierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="7996a-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="7996a-134">Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7996a-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="7996a-135">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="7996a-135">Serialization behavior</span></span>

* <span data-ttu-id="7996a-136">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7996a-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="7996a-137">Sie können [auszuschließende Eigenschaften angeben](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="7996a-137">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="7996a-138">Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7996a-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="7996a-139">JSON wird standardmäßig verkleinert.</span><span class="sxs-lookup"><span data-stu-id="7996a-139">By default, JSON is minified.</span></span> <span data-ttu-id="7996a-140">Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="7996a-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="7996a-141">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen.</span><span class="sxs-lookup"><span data-stu-id="7996a-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="7996a-142">Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="7996a-142">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="7996a-143">Zirkelbezüge werden erkannt und daraufhin Ausnahmen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7996a-143">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="7996a-144">Aktuell werden [Felder](../../csharp/programming-guide/classes-and-structs/fields.md) ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7996a-144">Currently, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are excluded.</span></span>

<span data-ttu-id="7996a-145">Unter anderem unterstützte Typen:</span><span class="sxs-lookup"><span data-stu-id="7996a-145">Supported types include:</span></span>

* <span data-ttu-id="7996a-146">.NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="7996a-146">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="7996a-147">benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="7996a-147">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="7996a-148">Eindimensionale und Jagged Arrays (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="7996a-148">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="7996a-149">Ein `Dictionary<string,TValue>`, wobei `TValue` ein `object` ist, ein `JsonElement` oder ein POCO.</span><span class="sxs-lookup"><span data-stu-id="7996a-149">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="7996a-150">Sammlungen aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="7996a-150">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="7996a-151">Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-151">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="7996a-152">Lesen von JSON in .NET-Objekte (Deserialisieren)</span><span class="sxs-lookup"><span data-stu-id="7996a-152">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="7996a-153">Um aus einer Zeichenfolge oder einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="7996a-153">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="7996a-154">Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecastWithPOCOs`-Klasse erstellt, die schon zuvor im [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:</span><span class="sxs-lookup"><span data-stu-id="7996a-154">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="7996a-155">Um mithilfe von synchronem Code aus einer Datei zu deserialisieren, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-155">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="7996a-156">Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="7996a-156">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="7996a-157">Deserialisieren aus UTF-8</span><span class="sxs-lookup"><span data-stu-id="7996a-157">Deserialize from UTF-8</span></span>

<span data-ttu-id="7996a-158">Um aus UTF-8 zu deserialisieren, rufen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung auf, die einen `Utf8JsonReader` oder ein `ReadOnlySpan<byte>` akzeptiert, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7996a-158">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="7996a-159">In den Beispielen wird vorausgesetzt, dass sich das JSON in einem Bytearray namens „jsonUtf8Bytes“ befindet.</span><span class="sxs-lookup"><span data-stu-id="7996a-159">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="7996a-160">Deserialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="7996a-160">Deserialization behavior</span></span>

<span data-ttu-id="7996a-161">Beim Deserialisieren von JSON-Code gelten die folgenden Verhaltensweisen:</span><span class="sxs-lookup"><span data-stu-id="7996a-161">The following behaviors apply when deserializing JSON:</span></span>

* <span data-ttu-id="7996a-162">Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="7996a-162">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="7996a-163">Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="7996a-163">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="7996a-164">Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7996a-164">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="7996a-165">Konstruktoren für die Deserialisierung:</span><span class="sxs-lookup"><span data-stu-id="7996a-165">Constructors for deserialization:</span></span>
  - <span data-ttu-id="7996a-166">Im Zusammenhang mit .NET Core 3.0 und 3.1 wird ein parameterloser Konstruktor für die Deserialisierung verwendet, der öffentlich, intern oder privat sein kann.</span><span class="sxs-lookup"><span data-stu-id="7996a-166">On .NET Core 3.0 and 3.1, a parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
  - <span data-ttu-id="7996a-167">In .NET 5.0 und höher werden nicht öffentliche Konstruktoren vom Serialisierungsprogramm ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7996a-167">In .NET 5.0 and later, non-public constructors are ignored by the serializer.</span></span> <span data-ttu-id="7996a-168">Parametrisierte Konstruktoren können jedoch verwendet werden, wenn kein parameterloser Konstruktor verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7996a-168">However, parameterized constructors can be used if a parameterless constructor isn't available.</span></span>
* <span data-ttu-id="7996a-169">Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7996a-169">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="7996a-170">Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7996a-170">By default, enums are supported as numbers.</span></span> <span data-ttu-id="7996a-171">Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="7996a-171">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="7996a-172">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7996a-172">Fields aren't supported.</span></span>
* <span data-ttu-id="7996a-173">Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="7996a-173">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="7996a-174">Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="7996a-174">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="7996a-175">Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.</span><span class="sxs-lookup"><span data-stu-id="7996a-175">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="7996a-176">Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-176">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="7996a-177">Serialisieren in formatierten JSON-Code</span><span class="sxs-lookup"><span data-stu-id="7996a-177">Serialize to formatted JSON</span></span>

<span data-ttu-id="7996a-178">Um die JSON-Ausgabe übersichtlich zu formatieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="7996a-178">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="7996a-179">Hier sehen Sie einen zu serialisierenden Beispieltyp und die übersichtlich formatierte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7996a-179">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="7996a-180">Anpassen von JSON-Namen und -Werten</span><span class="sxs-lookup"><span data-stu-id="7996a-180">Customize JSON names and values</span></span>

<span data-ttu-id="7996a-181">Standardmäßig bleiben Eigenschaftsnamen und Wörterbuchschlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="7996a-181">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="7996a-182">Enumerationswerte werden als Zahlen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7996a-182">Enum values are represented as numbers.</span></span> <span data-ttu-id="7996a-183">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="7996a-183">This section explains how to:</span></span>

* [<span data-ttu-id="7996a-184">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="7996a-184">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="7996a-185">Konvertieren aller Eigenschaftsnamen in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="7996a-185">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="7996a-186">Implementieren einer benutzerdefinierten Benennungsrichtlinie für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7996a-186">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="7996a-187">Konvertieren von Wörterbuchschlüsseln in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="7996a-187">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="7996a-188">Konvertieren von Enumerationen in Zeichenfolgen und Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="7996a-188">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="7996a-189">Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und -werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="7996a-189">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="7996a-190">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="7996a-190">Customize individual property names</span></span>

<span data-ttu-id="7996a-191">Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das Attribut [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="7996a-191">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="7996a-192">Hier finden Sie einen zu serialisierenden Beispieltyp und die daraus resultierende JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7996a-192">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="7996a-193">Der über dieses Attribut festgelegte Eigenschaftsname:</span><span class="sxs-lookup"><span data-stu-id="7996a-193">The property name set by this attribute:</span></span>

* <span data-ttu-id="7996a-194">Dies gilt in beide Richtungen, für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="7996a-194">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="7996a-195">Es hat Vorrang vor Benennungsrichtlinien für Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7996a-195">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="7996a-196">Verwenden der Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="7996a-196">Use camel case for all JSON property names</span></span>

<span data-ttu-id="7996a-197">Um die Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen zu verwenden, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-197">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="7996a-198">Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7996a-198">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="7996a-199">Die Camel-Case-Benennungsrichtlinie für Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7996a-199">The camel case property naming policy:</span></span>

* <span data-ttu-id="7996a-200">Gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="7996a-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="7996a-201">Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="7996a-201">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="7996a-202">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="7996a-202">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="7996a-203">Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7996a-203">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="7996a-204">Um eine benutzerdefinierte Benennungsrichtlinie für JSON-Eigenschaften zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und setzen Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode außer Kraft, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-204">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="7996a-205">Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihre Benennungsrichtlinienklasse fest:</span><span class="sxs-lookup"><span data-stu-id="7996a-205">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-206">Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7996a-206">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="7996a-207">Die Benennungsrichtlinie für JSON-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7996a-207">The JSON property naming policy:</span></span>

* <span data-ttu-id="7996a-208">Gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="7996a-208">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="7996a-209">Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="7996a-209">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="7996a-210">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="7996a-210">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="7996a-211">Wörterbuchschlüssel in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="7996a-211">Camel case dictionary keys</span></span>

<span data-ttu-id="7996a-212">Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die Schlüssel vom Typ `string` in Camel-Case-Schreibweise konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-212">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="7996a-213">Legen Sie hierzu <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-213">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-214">Das Serialisieren eines Objekts mit einem Wörterbuch namens `TemperatureRanges`, das die Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` enthält, würde zu einer JSON-Ausgabe wie im folgenden Beispiel führen:</span><span class="sxs-lookup"><span data-stu-id="7996a-214">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="7996a-215">Die Camel-Case-Benennungsrichtlinie für Wörterbuchschlüssel gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="7996a-215">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="7996a-216">Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei auch dann, wenn Sie `JsonNamingPolicy.CamelCase` als `DictionaryKeyPolicy` angeben.</span><span class="sxs-lookup"><span data-stu-id="7996a-216">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="7996a-217">Enumerationen als Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="7996a-217">Enums as strings</span></span>

<span data-ttu-id="7996a-218">Standardmäßig werden Enumerationen als Zahlen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7996a-218">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="7996a-219">Um Enumerationen als Zeichenfolgen zu serialisieren, verwenden Sie <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="7996a-219">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="7996a-220">Angenommen, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:</span><span class="sxs-lookup"><span data-stu-id="7996a-220">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="7996a-221">Wenn die Zusammenfassung `Hot` ist, hat das serialisierte JSON standardmäßig den numerischen Wert 3:</span><span class="sxs-lookup"><span data-stu-id="7996a-221">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="7996a-222">Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:</span><span class="sxs-lookup"><span data-stu-id="7996a-222">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-223">Das resultierende JSON sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="7996a-223">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="7996a-224">Zeichenfolgennamen von Enumerationen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-224">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="7996a-225">Ausschließen von Eigenschaften aus der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="7996a-225">Exclude properties from serialization</span></span>

<span data-ttu-id="7996a-226">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7996a-226">By default, all public properties are serialized.</span></span> <span data-ttu-id="7996a-227">Wenn Sie möchten, dass einige von ihnen nicht in der JSON-Ausgabe vorkommen, haben Sie mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="7996a-227">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="7996a-228">In diesem Abschnitt wird erläutert, wie Sie Folgendes ausschließen können:</span><span class="sxs-lookup"><span data-stu-id="7996a-228">This section explains how to exclude:</span></span>

* [<span data-ttu-id="7996a-229">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7996a-229">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="7996a-230"> Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7996a-230">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="7996a-231">Alle Nullwert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7996a-231">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="7996a-232">Ausschließen einzelner Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7996a-232">Exclude individual properties</span></span>

<span data-ttu-id="7996a-233">Um einzelne Eigenschaften zu ignorieren, verwenden Sie das Attribut [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="7996a-233">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="7996a-234">Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7996a-234">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="7996a-235">Ausschließen aller schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7996a-235">Exclude all read-only properties</span></span>

<span data-ttu-id="7996a-236">Eine Eigenschaft ist schreibgeschützt, wenn sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.</span><span class="sxs-lookup"><span data-stu-id="7996a-236">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="7996a-237">Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-237">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-238">Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7996a-238">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="7996a-239">Diese Option gilt nur für Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="7996a-239">This option applies only to serialization.</span></span> <span data-ttu-id="7996a-240">Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7996a-240">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="7996a-241">Ausschließen aller Nullwert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7996a-241">Exclude all null value properties</span></span>

<span data-ttu-id="7996a-242">Um alle Nullwert-Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-242">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-243">Hier finden Sie ein zu serialisierendes Beispielobjekt und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7996a-243">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="7996a-244">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7996a-244">Property</span></span> |<span data-ttu-id="7996a-245">Wert</span><span class="sxs-lookup"><span data-stu-id="7996a-245">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="7996a-246">Datum</span><span class="sxs-lookup"><span data-stu-id="7996a-246">Date</span></span>    | <span data-ttu-id="7996a-247">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="7996a-247">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="7996a-248">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="7996a-248">TemperatureCelsius</span></span>| <span data-ttu-id="7996a-249">25</span><span class="sxs-lookup"><span data-stu-id="7996a-249">25</span></span> |
| <span data-ttu-id="7996a-250">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="7996a-250">Summary</span></span>| <span data-ttu-id="7996a-251">NULL</span><span class="sxs-lookup"><span data-stu-id="7996a-251">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="7996a-252">Diese Einstellung gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="7996a-252">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="7996a-253">Informationen zu ihren Auswirkungen auf die Deserialisierung finden Sie unter [Ignorieren von Null beim Deserialisieren](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="7996a-253">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="7996a-254">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="7996a-254">Customize character encoding</span></span>

<span data-ttu-id="7996a-255">Standardmäßig escapet der Serialisierer alle Nicht-ASCII-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="7996a-255">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="7996a-256">Das heißt, dass sie durch `\uxxxx` ersetzt werden, wobei `xxxx` der Unicode-Code des Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="7996a-256">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="7996a-257">Wenn die `Summary`-Eigenschaft beispielsweise auf Kyrillisch „жарко“ festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="7996a-257">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="7996a-258">Serialisieren von Sprachzeichensätzen</span><span class="sxs-lookup"><span data-stu-id="7996a-258">Serialize language character sets</span></span>

<span data-ttu-id="7996a-259">Zum Serialisieren der Zeichensätze von mindestens einer Sprache ohne zu escapen geben Sie [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) an, wenn Sie eine Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> erstellen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-259">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="7996a-260">Mit diesem Code werden weder kyrillische noch griechische Zeichen escapet.</span><span class="sxs-lookup"><span data-stu-id="7996a-260">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="7996a-261">Wenn die `Summary`-Eigenschaft auf Kyrillisch „жарко“ festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="7996a-261">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="7996a-262">Um alle Sprachensätze ohne zu escapen zu serialisieren, verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7996a-262">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="7996a-263">Serialisieren bestimmter Zeichen</span><span class="sxs-lookup"><span data-stu-id="7996a-263">Serialize specific characters</span></span>

<span data-ttu-id="7996a-264">Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne dass sie escapet werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-264">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="7996a-265">Im folgenden Beispiel werden nur die ersten zwei Zeichen von „жарко“ serialisiert:</span><span class="sxs-lookup"><span data-stu-id="7996a-265">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="7996a-266">Hier sehen Sie eine JSON-Beispiel, das vom vorangehenden Code erzeugt wird:</span><span class="sxs-lookup"><span data-stu-id="7996a-266">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="7996a-267">Serialisieren aller Zeichen</span><span class="sxs-lookup"><span data-stu-id="7996a-267">Serialize all characters</span></span>

<span data-ttu-id="7996a-268">Um das Escapen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-268">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="7996a-269">Im Vergleich zum Standardencoder ist der `UnsafeRelaxedJsonEscaping`-Encoder weniger streng beim Zulassen von Zeichen, ohne sie zu escapen:</span><span class="sxs-lookup"><span data-stu-id="7996a-269">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="7996a-270">Er escapet keine HTML-abhängigen Zeichen wie `<`, `>`, `&` und `'`.</span><span class="sxs-lookup"><span data-stu-id="7996a-270">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="7996a-271">Er bietet keine zusätzlichen, tief greifenden Abwehrmaßnahmen gegen solche Cross-Site Scripting (XSS)- oder Information-Disclosure-Angriffe (Veröffentlichung von Informationen), die von einem Client und Server, die sich nicht auf einen *Zeichensatz* einigen können, verursacht werden können.</span><span class="sxs-lookup"><span data-stu-id="7996a-271">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="7996a-272">Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretieren wird.</span><span class="sxs-lookup"><span data-stu-id="7996a-272">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="7996a-273">Beispielsweise können Sie ihn verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8` sendet.</span><span class="sxs-lookup"><span data-stu-id="7996a-273">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="7996a-274">Gestatten Sie niemals, dass die `UnsafeRelaxedJsonEscaping`-Rohausgabe in eine HTML-Seite oder ein `<script>`-Element ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7996a-274">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="7996a-275">Serialisieren von Eigenschaften abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="7996a-275">Serialize properties of derived classes</span></span>

<span data-ttu-id="7996a-276">Das Serialisieren einer polymorphen Typhierarchie wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7996a-276">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="7996a-277">Wenn eine Eigenschaft beispielsweise als eine Schnittstelle oder eine abstrakte Klasse definiert wird, werden nur die für die Schnittstelle oder abstrakte Klasse definierten Eigenschaften serialisiert, auch wenn der Laufzeittyp über zusätzliche Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="7996a-277">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="7996a-278">Die Ausnahmen bei diesem Verhalten werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="7996a-278">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="7996a-279">Nehmen Sie beispielsweise an, Sie besitzen eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="7996a-279">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="7996a-280">Ferner sei angenommen, dass das Typargument der `Serialize`-Methode zur Kompilierzeit `WeatherForecast` ist:</span><span class="sxs-lookup"><span data-stu-id="7996a-280">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="7996a-281">In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch dann nicht, wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="7996a-281">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="7996a-282">Nur die Basisklasseneigenschaften werden serialisiert:</span><span class="sxs-lookup"><span data-stu-id="7996a-282">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="7996a-283">Dieses Verhalten soll die versehentliche Verfügbarmachung von Daten in einem abgeleiteten, zur Laufzeit erstellten Typ verhindern.</span><span class="sxs-lookup"><span data-stu-id="7996a-283">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="7996a-284">Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs im vorherigen Beispiel zu serialisieren:</span><span class="sxs-lookup"><span data-stu-id="7996a-284">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="7996a-285">Rufen Sie eine Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A> auf, bei der Sie den Typ zur Laufzeit angeben können:</span><span class="sxs-lookup"><span data-stu-id="7996a-285">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="7996a-286">Deklarieren Sie das zu serialisierende Objekt als `object`.</span><span class="sxs-lookup"><span data-stu-id="7996a-286">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="7996a-287">Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in die JSON-Ausgabe aufgenommen wird:</span><span class="sxs-lookup"><span data-stu-id="7996a-287">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="7996a-288">Diese Ansätze bieten polymorphe Serialisierung nur für das Stammobjekt, das serialisiert werden soll, und nicht für die Eigenschaften dieses Stammobjekts.</span><span class="sxs-lookup"><span data-stu-id="7996a-288">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="7996a-289">Sie können polymorphe Serialisierung für Objekte auf niedrigerer Ebene erzielen, wenn Sie diese als `object`-Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="7996a-289">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="7996a-290">Angenommen, Ihre `WeatherForecast`-Klasse verfügt über eine Eigenschaft mit dem Namen `PreviousForecast`, die als `WeatherForecast`-Typ oder als `object`-Typ definiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="7996a-290">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="7996a-291">Wenn die Eigenschaft `PreviousForecast` eine Instanz von `WeatherForecastDerived` enthält:</span><span class="sxs-lookup"><span data-stu-id="7996a-291">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="7996a-292">Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPrevious` **enthält keine** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="7996a-292">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="7996a-293">Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPreviousAsObject` **enthält** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="7996a-293">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="7996a-294">Um `WeatherForecastWithPreviousAsObject` zu serialisieren, ist es nicht erforderlich, `Serialize<object>` oder `GetType` aufzurufen, da das Stammobjekt nicht das Objekt ist, das von einem abgeleiteten Typ sein darf.</span><span class="sxs-lookup"><span data-stu-id="7996a-294">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="7996a-295">Im folgenden Codebeispiel wird weder `Serialize<object>` noch `GetType` aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="7996a-295">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="7996a-296">Der vorangehende Code serialisiert `WeatherForecastWithPreviousAsObject` korrekt:</span><span class="sxs-lookup"><span data-stu-id="7996a-296">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="7996a-297">Derselbe Ansatz zum Definieren von Eigenschaften als `object` funktioniert mit Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="7996a-297">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="7996a-298">Angenommen, Sie haben die folgende Schnittstelle und Implementierung, und Sie möchten eine Klasse mit Eigenschaften serialisieren, die Implementierungsinstanzen enthalten:</span><span class="sxs-lookup"><span data-stu-id="7996a-298">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="7996a-299">Wenn Sie eine Instanz von `Forecasts` serialisieren, zeigt nur `Tuesday` die `WindSpeed`-Eigenschaft an, da `Tuesday` als `object` definiert ist:</span><span class="sxs-lookup"><span data-stu-id="7996a-299">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="7996a-300">Im folgenden Beispiel wird der JSON-Code gezeigt, der aus dem vorangehenden Code resultiert:</span><span class="sxs-lookup"><span data-stu-id="7996a-300">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="7996a-301">Weitere Informationen zur polymorphen **Serialisierung** sowie Informationen zur **Deserialisierung** finden Sie unter [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="7996a-301">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="7996a-302">Zulassen von Kommentaren und nachfolgenden Kommas</span><span class="sxs-lookup"><span data-stu-id="7996a-302">Allow comments and trailing commas</span></span>

<span data-ttu-id="7996a-303">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="7996a-303">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="7996a-304">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest.</span><span class="sxs-lookup"><span data-stu-id="7996a-304">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="7996a-305">Und um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="7996a-305">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="7996a-306">Das folgende Beispiel veranschaulicht, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="7996a-306">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="7996a-307">Im Folgenden finden Sie ein JSON-Beispiel mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="7996a-307">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="7996a-308">Eigenschaftenabgleich ohne Beachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="7996a-308">Case-insensitive property matching</span></span>

<span data-ttu-id="7996a-309">Standardmäßig wird bei der Deserialisierung nach Übereinstimmungen von Eigenschaftsnamen zwischen JSON und den Zielobjekteigenschaften unter Berücksichtigung von Groß-/Kleinschreibung gesucht.</span><span class="sxs-lookup"><span data-stu-id="7996a-309">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="7996a-310">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="7996a-310">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="7996a-311">Im Folgenden finden Sie ein JSON-Beispiel mit Eigenschaftsnamen in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="7996a-311">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="7996a-312">Es kann in den folgenden Typ deserialisiert werden, der Eigenschaftsnamen in Pascal-Schreibweise besitzt.</span><span class="sxs-lookup"><span data-stu-id="7996a-312">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="7996a-313">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="7996a-313">Handle overflow JSON</span></span>

<span data-ttu-id="7996a-314">Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, die nicht von Eigenschaften des Zieltyps dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-314">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="7996a-315">Angenommen, Ihr Zieltyp ist folgender:</span><span class="sxs-lookup"><span data-stu-id="7996a-315">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="7996a-316">Und der zu deserialisierende JSON-Code ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7996a-316">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="7996a-317">Wenn Sie den angezeigten JSON-Code in den gezeigten Typ deserialisieren, gibt es keinen Ort mehr für die Eigenschaften `DatesAvailable` und `SummaryWords`, und sie gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="7996a-317">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="7996a-318">Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)-Attribut auf eine Eigenschaft des Typs `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:</span><span class="sxs-lookup"><span data-stu-id="7996a-318">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="7996a-319">Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="7996a-319">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="7996a-320">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7996a-320">Property</span></span> |<span data-ttu-id="7996a-321">Wert</span><span class="sxs-lookup"><span data-stu-id="7996a-321">Value</span></span>  |<span data-ttu-id="7996a-322">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7996a-322">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="7996a-323">Datum</span><span class="sxs-lookup"><span data-stu-id="7996a-323">Date</span></span>    | <span data-ttu-id="7996a-324">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="7996a-324">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="7996a-325">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="7996a-325">TemperatureCelsius</span></span>| <span data-ttu-id="7996a-326">0</span><span class="sxs-lookup"><span data-stu-id="7996a-326">0</span></span> | <span data-ttu-id="7996a-327">Keine Übereinstimmung unter Berücksichtigung von Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die Eigenschaft nicht festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="7996a-327">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="7996a-328">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="7996a-328">Summary</span></span> | <span data-ttu-id="7996a-329">Heiß</span><span class="sxs-lookup"><span data-stu-id="7996a-329">Hot</span></span> ||
| <span data-ttu-id="7996a-330">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="7996a-330">ExtensionData</span></span> | <span data-ttu-id="7996a-331">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="7996a-331">temperatureCelsius: 25</span></span> |<span data-ttu-id="7996a-332">Da die Groß-/Kleinschreibung nicht übereinstimmte, ist diese JSON-Eigenschaft ein zusätzliches Element und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="7996a-332">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="7996a-333">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="7996a-333">DatesAvailable:</span></span><br>  <span data-ttu-id="7996a-334">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="7996a-334">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="7996a-335">8/2/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="7996a-335">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="7996a-336">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="7996a-336">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="7996a-337">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="7996a-337">SummaryWords:</span></span><br><span data-ttu-id="7996a-338">Toll</span><span class="sxs-lookup"><span data-stu-id="7996a-338">Cool</span></span><br><span data-ttu-id="7996a-339">Windig</span><span class="sxs-lookup"><span data-stu-id="7996a-339">Windy</span></span><br><span data-ttu-id="7996a-340">Feucht</span><span class="sxs-lookup"><span data-stu-id="7996a-340">Humid</span></span> |<span data-ttu-id="7996a-341">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="7996a-341">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="7996a-342">Wenn das Zielobjekt serialisiert wird, werden die Schlüssel-Wert-Paare der Erweiterungsdaten zu genau solchen JSON-Eigenschaften, wie sie im eingehenden JSON-Code waren:</span><span class="sxs-lookup"><span data-stu-id="7996a-342">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="7996a-343">Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code vorkommt.</span><span class="sxs-lookup"><span data-stu-id="7996a-343">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="7996a-344">Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert würden.</span><span class="sxs-lookup"><span data-stu-id="7996a-344">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="7996a-345">Ignorieren von Null beim Deserialisieren</span><span class="sxs-lookup"><span data-stu-id="7996a-345">Ignore null when deserializing</span></span>

<span data-ttu-id="7996a-346">Wenn eine Eigenschaft in JSON Null ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf Null festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7996a-346">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="7996a-347">In einigen Szenarien kann die Zieleigenschaft möglicherweise einen Standardwert besitzen, und Sie möchten nicht, dass dieser Standardwert von einem Nullwert überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="7996a-347">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="7996a-348">Angenommen, der folgende Code stellt Ihr Zielobjekt dar:</span><span class="sxs-lookup"><span data-stu-id="7996a-348">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="7996a-349">Und ferner angenommen, der folgende JSON-Code wird deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="7996a-349">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="7996a-350">Nach der Deserialisierung ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts Null.</span><span class="sxs-lookup"><span data-stu-id="7996a-350">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="7996a-351">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-351">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="7996a-352">Bei dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts der Standardwert „Keine Zusammenfassung“ nach der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="7996a-352">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="7996a-353">Nullwerte im JSON werden nur ignoriert, wenn Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="7996a-353">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="7996a-354">Nullwerte für Non-Nullable-Werttypen verursachen Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="7996a-354">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="7996a-355">„Utf8JsonReader“, „Utf8JsonWriter“ und „JsonDocument“</span><span class="sxs-lookup"><span data-stu-id="7996a-355">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="7996a-356"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, rein vorwärtsgerichteter Reader mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der aus einem `ReadOnlySpan<byte>` oder `ReadOnlySequence<byte>` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="7996a-356"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="7996a-357">Der `Utf8JsonReader` ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierungsprogrammen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7996a-357">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="7996a-358">Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` verdeckt.</span><span class="sxs-lookup"><span data-stu-id="7996a-358">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="7996a-359">Mit <xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell mit hohem Durchsatz schreiben.</span><span class="sxs-lookup"><span data-stu-id="7996a-359"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="7996a-360">Der Writer ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7996a-360">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="7996a-361">Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` verdeckt.</span><span class="sxs-lookup"><span data-stu-id="7996a-361">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="7996a-362"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mithilfe von `Utf8JsonReader` ein schreibgeschütztes Dokumentobjektmodell (DOM) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7996a-362"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="7996a-363">Das DOM bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="7996a-363">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="7996a-364">Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den Typ <xref:System.Text.Json.JsonElement> zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-364">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="7996a-365">Der `JsonElement`-Typ stellt Array- und Objektenumeratoren sowie APIs zum Konvertieren von JSON-Text in gängige .NET-Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="7996a-365">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="7996a-366">`JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7996a-366">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="7996a-367">In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-367">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="7996a-368">Verwenden von „JsonDocument“ für den Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="7996a-368">Use JsonDocument for access to data</span></span>

<span data-ttu-id="7996a-369">Das folgende Beispiel zeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:</span><span class="sxs-lookup"><span data-stu-id="7996a-369">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="7996a-370">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="7996a-370">The preceding code:</span></span>

* <span data-ttu-id="7996a-371">Setzt voraus, dass sich der zu analysierende JSON-Code in einer Zeichenfolge namens `jsonString` befindet.</span><span class="sxs-lookup"><span data-stu-id="7996a-371">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="7996a-372">Berechnet eine durchschnittliche Note für Objekte in einem `Students`-Array, die eine `Grade`-Eigenschaft besitzen.</span><span class="sxs-lookup"><span data-stu-id="7996a-372">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="7996a-373">Weist Kursteilnehmern, die keine Note haben, eine Standardnote von 70 zu.</span><span class="sxs-lookup"><span data-stu-id="7996a-373">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="7996a-374">Zählt Kursteilnehmer durch Inkrementieren einer `count`-Variablen bei jeder Iteration.</span><span class="sxs-lookup"><span data-stu-id="7996a-374">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="7996a-375">Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A> aufzurufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7996a-375">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="7996a-376">Im Folgenden finden Sie ein Beispiel für das JSON, das von diesem Code verarbeitet wird:</span><span class="sxs-lookup"><span data-stu-id="7996a-376">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="7996a-377">Verwenden von JsonDocument zum Schreiben von JSON</span><span class="sxs-lookup"><span data-stu-id="7996a-377">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="7996a-378">Das folgende Beispiel veranschaulicht, wie JSON aus einem <xref:System.Text.Json.JsonDocument> geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="7996a-378">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="7996a-379">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="7996a-379">The preceding code:</span></span>

* <span data-ttu-id="7996a-380">Liest eine JSON-Datei, lädt die Daten in ein `JsonDocument` und schreibt (übersichtlich) formatierten JSON-Code in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="7996a-380">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="7996a-381">Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-381">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="7996a-382">Ruft nach Abschluss <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf.</span><span class="sxs-lookup"><span data-stu-id="7996a-382">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="7996a-383">Eine Alternative besteht darin, den Writer automatisch zu leeren, wenn er entsorgt wird.</span><span class="sxs-lookup"><span data-stu-id="7996a-383">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="7996a-384">Im Folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die von dem Beispielcode verarbeitet werden soll:</span><span class="sxs-lookup"><span data-stu-id="7996a-384">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="7996a-385">Das Ergebnis ist die folgende, übersichtlich formatierte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7996a-385">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="7996a-386">Verwenden von „Utf8JsonWriter“</span><span class="sxs-lookup"><span data-stu-id="7996a-386">Use Utf8JsonWriter</span></span>

<span data-ttu-id="7996a-387">Im folgenden Beispiel wird die Verwendung der <xref:System.Text.Json.Utf8JsonWriter>-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="7996a-387">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="7996a-388">Verwenden von „Utf8JsonReader“</span><span class="sxs-lookup"><span data-stu-id="7996a-388">Use Utf8JsonReader</span></span>

<span data-ttu-id="7996a-389">Im folgenden Beispiel wird die Verwendung der <xref:System.Text.Json.Utf8JsonReader>-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="7996a-389">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="7996a-390">Der vorangehende Code setzt voraus, dass es sich bei der `jsonUtf8`-Variablen um ein Bytearray handelt, das gültigen, UTF-8-codierten JSON-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="7996a-390">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="7996a-391">Filtern von Daten mithilfe von „Utf8JsonReader“</span><span class="sxs-lookup"><span data-stu-id="7996a-391">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="7996a-392">Das folgende Beispiel zeigt, wie Sie eine Datei synchron lesen und nach einem Wert suchen:</span><span class="sxs-lookup"><span data-stu-id="7996a-392">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="7996a-393">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="7996a-393">The preceding code:</span></span>

* <span data-ttu-id="7996a-394">Setzt voraus, dass der JSON-Code ein Array von Objekten enthält, und dass jedes Objekt eine Eigenschaft „name“ vom Typ „string“ (Zeichenfolge) enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="7996a-394">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="7996a-395">Zählt Objekte und „name“-Eigenschaftswerte, die auf „University“ enden.</span><span class="sxs-lookup"><span data-stu-id="7996a-395">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="7996a-396">Setzt voraus, dass die Datei UTF-16-codiert ist und transcodiert sie in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="7996a-396">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="7996a-397">Eine UTF-8-codierte Datei kann mithilfe des folgenden Codes direkt in ein `ReadOnlySpan<byte>` gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="7996a-397">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="7996a-398">Wenn die Datei eine UTF-8-Bytereihenfolge-Marke (BOM) enthält, entfernen Sie diese, bevor Sie die Bytes an den `Utf8JsonReader` übergeben, da der Reader Text erwartet.</span><span class="sxs-lookup"><span data-stu-id="7996a-398">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="7996a-399">Andernfalls wird die BOM als ungültiges JSON betrachtet, und der Reader löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="7996a-399">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="7996a-400">Im Folgenden finden Sie ein JSON-Beispiel, das der voranstehende Code lesen kann.</span><span class="sxs-lookup"><span data-stu-id="7996a-400">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="7996a-401">Die resultierende Zusammenfassungsmeldung lautet „2 out of 2 have names that end with ‚University‘“ (2 von 4 besitzen Namen, die auf „University“ enden):</span><span class="sxs-lookup"><span data-stu-id="7996a-401">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="7996a-402">Lesen aus einem Stream mithilfe von Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="7996a-402">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="7996a-403">Wenn Sie eine große Datei (z. B. ein Gigabyte oder mehr) lesen, möchten Sie die gesamte Datei vielleicht nicht auf einmal in den Arbeitsspeicher laden müssen.</span><span class="sxs-lookup"><span data-stu-id="7996a-403">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="7996a-404">In diesem Szenario können Sie einen <xref:System.IO.FileStream> verwenden.</span><span class="sxs-lookup"><span data-stu-id="7996a-404">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="7996a-405">Wenn Sie einen `Utf8JsonReader` zum Lesen aus einem Stream verwenden, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="7996a-405">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="7996a-406">Der Puffer, der die partielle JSON-Nutzlast enthält, muss mindestens so groß wie das größte JSON-Token darin sein, damit der Reader vorankommen kann.</span><span class="sxs-lookup"><span data-stu-id="7996a-406">The buffer containing the partial JSON payload must be at least as big as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="7996a-407">Der Puffer muss mindestens so groß wie die größte Sequenz von Leerraum innerhalb der JSON-Nutzlast sein.</span><span class="sxs-lookup"><span data-stu-id="7996a-407">The buffer must be at least as big as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="7996a-408">Der Reader verfolgt die gelesenen Daten nicht nach, bis er den nächsten <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in der JSON-Nutzlast vollständig gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="7996a-408">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="7996a-409">Wenn im Puffer noch Bytes vorhanden sind, müssen Sie sie wieder dem Reader übergeben.</span><span class="sxs-lookup"><span data-stu-id="7996a-409">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="7996a-410">Sie können <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> verwenden, um zu bestimmen, wie viele Bytes übrig bleiben.</span><span class="sxs-lookup"><span data-stu-id="7996a-410">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="7996a-411">Im folgenden Code wird veranschaulicht, wie aus einem Stream gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="7996a-411">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="7996a-412">Das Beispiel zeigt einen <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="7996a-412">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="7996a-413">Ähnlicher Code funktioniert mit einem <xref:System.IO.FileStream>, es sei denn, der `FileStream` enthält am Anfang eine UTF-8-BOM.</span><span class="sxs-lookup"><span data-stu-id="7996a-413">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="7996a-414">In diesem Fall müssen Sie diese drei Bytes aus dem Puffer entfernen, bevor Sie die verbleibenden Bytes an den `Utf8JsonReader` übergeben.</span><span class="sxs-lookup"><span data-stu-id="7996a-414">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="7996a-415">Andernfalls würde der Reader eine Ausnahme auslösen, da die BOM nicht als gültiger Teil des JSON-Codes angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="7996a-415">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="7996a-416">Der Beispielcode beginnt mit einem 4-KB-Puffer und verdoppelt die Puffergröße jedes Mal, wenn festgestellt wird, dass die Größe nicht ausreicht, um einem kompletten JSON-Token zu entsprechen. Dies ist erforderlich, damit der Reader mit der JSON-Nutzlast vorankommt.</span><span class="sxs-lookup"><span data-stu-id="7996a-416">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not big enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="7996a-417">Das JSON-Beispiel im Codeausschnitt löst nur dann eine Erhöhung der Puffergröße aus, wenn Sie eine sehr geringe Anfangspuffergröße festlegen, z. B. 10 Bytes.</span><span class="sxs-lookup"><span data-stu-id="7996a-417">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="7996a-418">Die `Console.WriteLine`-Anweisungen zeigen Ursache und Auswirkung der Puffergrößenerhöhungen, wenn Sie die Anfangspuffergröße auf 10 festlegen.</span><span class="sxs-lookup"><span data-stu-id="7996a-418">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="7996a-419">Bei der Anfangspuffergröße von 4 KB wird das gesamte JSON-Beispiel von jeder `Console.WriteLine` angezeigt, und die Puffergröße muss nie erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="7996a-419">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="7996a-420">Im vorherigen Beispiel wurde keine Pufferobergrenze festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7996a-420">The preceding example sets no limit to how big the buffer can grow.</span></span> <span data-ttu-id="7996a-421">Bei übermäßiger Tokengröße kann bei dem Code ein <xref:System.OutOfMemoryException>-Ausnahmefehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="7996a-421">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="7996a-422">Dies kann vorkommen, wenn der JSON-Code ein ungefähr 1 GB großes oder größeres Token enthält, da das Token bei Verdoppelung von 1 GB nicht mehr in einen `int32`-Puffer passt.</span><span class="sxs-lookup"><span data-stu-id="7996a-422">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7996a-423">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7996a-423">Additional resources</span></span>

* [<span data-ttu-id="7996a-424">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="7996a-424">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="7996a-425">Schreiben von benutzerdefinierten Konvertern</span><span class="sxs-lookup"><span data-stu-id="7996a-425">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="7996a-426">Migrieren von Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="7996a-426">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="7996a-427">Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="7996a-427">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="7996a-428">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="7996a-428">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
