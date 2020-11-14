---
title: Serialisieren und Deserialisieren von JSON mit C# – .NET
description: Hier erfahren Sie, wie Sie mithilfe des :::no-loc(System.Text.Json):::-Namespace Daten vom JSON- in das .NET-Format serialisieren und daraus deserialisieren. Enthält Beispielcode.
ms.date: 11/05/2020
no-loc:
- ':::no-loc(System.Text.Json):::'
- ':::no-loc(Newtonsoft.Json):::'
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
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="1c2f0-104">Serialisieren und Deserialisieren (Marshallen und Marshallen rückgängig machen) von JSON-Daten in .NET</span><span class="sxs-lookup"><span data-stu-id="1c2f0-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="1c2f0-105">Dieser Artikel veranschaulicht, wie Sie mithilfe des <xref::::no-loc(System.Text.Json):::?displayProperty=fullName>-Namespace Daten in das JSON-Format (JavaScript Object Notation) serialisieren und daraus deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-105">This article shows how to use the <xref::::no-loc(System.Text.Json):::?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="1c2f0-106">Wenn Sie vorhandenen Code aus `:::no-loc(Newtonsoft.Json):::` portieren, finden Sie weitere Informationen unter [Migrieren zu `:::no-loc(System.Text.Json):::`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-106">If you're porting existing code from `:::no-loc(Newtonsoft.Json):::`, see [How to migrate to `:::no-loc(System.Text.Json):::`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="1c2f0-107">Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework wie [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="1c2f0-108">Im größten Teil des Serialisierungsbeispielcodes ist <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` festgelegt, um den JSON-Code übersichtlicher zu gestalten (mit Einzügen und Zwischenräumen für bessere Lesbarkeit).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-108">Most of the serialization sample code sets <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="1c2f0-109">Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="1c2f0-110">Die Codebeispiele verweisen auf die folgende Klasse und deren Varianten:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="1c2f0-111">Namespaces</span><span class="sxs-lookup"><span data-stu-id="1c2f0-111">Namespaces</span></span>

<span data-ttu-id="1c2f0-112">Der <xref::::no-loc(System.Text.Json):::>-Namespace enthält alle Einstiegspunkte und die Haupttypen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-112">The <xref::::no-loc(System.Text.Json):::> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="1c2f0-113">Der <xref::::no-loc(System.Text.Json):::.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-113">The <xref::::no-loc(System.Text.Json):::.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="1c2f0-114">Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Anweisungen für einen oder beide Namespaces:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using :::no-loc(System.Text.Json):::;
using :::no-loc(System.Text.Json):::.Serialization;
```

<span data-ttu-id="1c2f0-115">Attribute aus dem Namespace <xref:System.Runtime.Serialization> werden in `:::no-loc(System.Text.Json):::` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `:::no-loc(System.Text.Json):::`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="1c2f0-116">Schreiben von .NET-Objekten in JSON (Serialisieren)</span><span class="sxs-lookup"><span data-stu-id="1c2f0-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="1c2f0-117">Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, rufen Sie die <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-117">To write JSON to a string or to a file, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1c2f0-118">Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-119">Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-120">Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-121">In den vorangehenden Beispielen wird Typrückschluss für den zu serialisierenden Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="1c2f0-122">Eine Überladung von `Serialize()` akzeptiert einen generischen Typparameter:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="1c2f0-123">Serialisierungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="1c2f0-123">Serialization example</span></span>

<span data-ttu-id="1c2f0-124">Im Folgenden finden Sie eine Beispielklasse, die die Sammlungstypeigenschaften und einen benutzerdefinierten Typen enthält:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> <span data-ttu-id="1c2f0-125">„POCO“ steht für [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="1c2f0-126">Ein POCO ist ein .NET-Typ, der von keinen frameworkspezifischen Typen abhängig ist (z. B. durch Vererbung oder Attribute).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="1c2f0-127">Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="1c2f0-128">Die JSON-Ausgabe wird standardmäßig verkleinert:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-128">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="1c2f0-129">Im folgenden Beispiel wird derselbe JSON-Code dargestellt, allerdings in formatierter Form (d. h. übersichtlich mit Zwischenräumen und Einzügen):</span><span class="sxs-lookup"><span data-stu-id="1c2f0-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="1c2f0-130">Serialisieren in UTF-8</span><span class="sxs-lookup"><span data-stu-id="1c2f0-130">Serialize to UTF-8</span></span>

<span data-ttu-id="1c2f0-131">Um in UTF-8 zu serialisieren, rufen Sie die <xref::::no-loc(System.Text.Json):::.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-131">To serialize to UTF-8, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-132">Eine <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A>-Überladung, die einen <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> akzeptiert, ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-132">A <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A> overload that takes a <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="1c2f0-133">Das Serialisieren in UTF-8 ist ungefähr 5–10 % schneller als die Verwendung von zeichenfolgenbasierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="1c2f0-134">Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="1c2f0-135">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="1c2f0-135">Serialization behavior</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1c2f0-136">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="1c2f0-137">Sie können [zu ignorierende Eigenschaften angeben](#ignore-properties).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-137">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="1c2f0-138">Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1c2f0-139">JSON wird standardmäßig verkleinert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-139">By default, JSON is minified.</span></span> <span data-ttu-id="1c2f0-140">Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1c2f0-141">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1c2f0-142">Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-142">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="1c2f0-143">Zirkelbezüge werden standardmäßig erkannt und entsprechende Ausnahmen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="1c2f0-144">Sie können [Verweise beibehalten und Zirkelbezüge behandeln](#preserve-references-and-handle-circular-references).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-144">You can [preserve references and handle circular references](#preserve-references-and-handle-circular-references).</span></span>
* <span data-ttu-id="1c2f0-145">[Felder](../../csharp/programming-guide/classes-and-structs/fields.md) werden standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="1c2f0-146">Sie können [Felder einschließen](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="1c2f0-147">Wenn Sie :::no-loc(System.Text.Json)::: indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-147">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1c2f0-148">Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-148">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1c2f0-149">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="1c2f0-150">Sie können [zu ignorierende Eigenschaften angeben](#ignore-properties).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-150">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="1c2f0-151">Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1c2f0-152">JSON wird standardmäßig verkleinert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-152">By default, JSON is minified.</span></span> <span data-ttu-id="1c2f0-153">Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1c2f0-154">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1c2f0-155">Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-155">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="1c2f0-156">Zirkelbezüge werden erkannt und daraufhin Ausnahmen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="1c2f0-157">[Felder](../../csharp/programming-guide/classes-and-structs/fields.md) werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="1c2f0-158">Unter anderem unterstützte Typen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1c2f0-159">.NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1c2f0-160">benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="1c2f0-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="1c2f0-161">Eindimensionale und Jagged Arrays (`T[][]`).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="1c2f0-162">Sammlungen und Wörterbücher aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1c2f0-163">.NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1c2f0-164">benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="1c2f0-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="1c2f0-165">Eindimensionale und Jagged Arrays (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="1c2f0-166">Ein `Dictionary<string,TValue>`, wobei `TValue` ein `object` ist, ein `JsonElement` oder ein POCO.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="1c2f0-167">Sammlungen aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="1c2f0-168">Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="1c2f0-169">Lesen von JSON in .NET-Objekte (Deserialisieren)</span><span class="sxs-lookup"><span data-stu-id="1c2f0-169">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="1c2f0-170">Um aus einer Zeichenfolge oder einer Datei zu deserialisieren, rufen Sie die <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-170">To deserialize from a string or a file, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1c2f0-171">Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecastWithPOCOs`-Klasse erstellt, die schon zuvor im [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="1c2f0-172">Um mithilfe von synchronem Code aus einer Datei zu deserialisieren, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="1c2f0-173">Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, rufen Sie die <xref::::no-loc(System.Text.Json):::.JsonSerializer.DeserializeAsync%2A>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-173">To deserialize from a file by using asynchronous code, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="1c2f0-174">Deserialisieren aus UTF-8</span><span class="sxs-lookup"><span data-stu-id="1c2f0-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="1c2f0-175">Um aus UTF-8 zu deserialisieren, rufen Sie eine <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung auf, die einen `Utf8JsonReader` oder ein `ReadOnlySpan<byte>` akzeptiert, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-175">To deserialize from UTF-8, call a <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="1c2f0-176">In den Beispielen wird vorausgesetzt, dass sich das JSON in einem Bytearray namens „jsonUtf8Bytes“ befindet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="1c2f0-177">Deserialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="1c2f0-177">Deserialization behavior</span></span>

<span data-ttu-id="1c2f0-178">Beim Deserialisieren von JSON-Code gelten die folgenden Verhaltensweisen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1c2f0-179">Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1c2f0-180">Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-180">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="1c2f0-181">Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1c2f0-182">Nicht öffentliche Konstruktoren werden vom Serialisierungsmodul ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="1c2f0-183">Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="1c2f0-184">Weitere Informationen finden Sie unter [Unveränderliche Typen und Datensätze](#immutable-types-and-records).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-184">See [Immutable types and Records](#immutable-types-and-records).</span></span>
* <span data-ttu-id="1c2f0-185">Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1c2f0-186">Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-186">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="1c2f0-187">Felder werden standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-187">By default, fields are ignored.</span></span> <span data-ttu-id="1c2f0-188">Sie können [Felder einschließen](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="1c2f0-189">Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1c2f0-190">Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-190">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="1c2f0-191">Die [ standardmäßige maximale Tiefe](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) beträgt 64.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-191">The [default maximum depth](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1c2f0-192">Wenn Sie :::no-loc(System.Text.Json)::: indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-192">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1c2f0-193">Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-193">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1c2f0-194">Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1c2f0-195">Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-195">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span> <span data-ttu-id="1c2f0-196">ASP.NET Core-Apps [unterscheiden standardmäßig Groß-/Kleinschreibung nicht](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-196">ASP.NET Core apps [specify case-insensitivity by default](#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="1c2f0-197">Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1c2f0-198">Ein parameterloser Konstruktor, der öffentlich, intern oder privat sein kann, wird für die Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="1c2f0-199">Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="1c2f0-200">Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1c2f0-201">Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-201">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="1c2f0-202">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-202">Fields aren't supported.</span></span>
* <span data-ttu-id="1c2f0-203">Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1c2f0-204">Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-204">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="1c2f0-205">Die [ standardmäßige maximale Tiefe](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) beträgt 64.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-205">The [default maximum depth](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1c2f0-206">Wenn Sie :::no-loc(System.Text.Json)::: indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-206">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1c2f0-207">Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-207">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="1c2f0-208">Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="1c2f0-209">Serialisieren in formatierten JSON-Code</span><span class="sxs-lookup"><span data-stu-id="1c2f0-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="1c2f0-210">Um die JSON-Ausgabe übersichtlich zu formatieren, legen Sie <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-210">To pretty-print the JSON output, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="1c2f0-211">Hier sehen Sie einen zu serialisierenden Beispieltyp und die übersichtlich formatierte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a><span data-ttu-id="1c2f0-212">Einschließen von Feldern</span><span class="sxs-lookup"><span data-stu-id="1c2f0-212">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-213">Verwenden Sie die globale Einstellung <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> oder das Attribut [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute), um Felder bei der Serialisierung oder Deserialisierung einzuschließen (siehe folgendes Beispiel):</span><span class="sxs-lookup"><span data-stu-id="1c2f0-213">Use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="15,17,19,31":::

<span data-ttu-id="1c2f0-214">Verwenden Sie die globale Einstellung <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>, um schreibgeschützte Felder zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-214">To ignore read-only fields, use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-215">Felder werden in .NET Core 3.1 in :::no-loc(System.Text.Json)::: nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-215">Fields are not supported in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span> <span data-ttu-id="1c2f0-216">[Benutzerdefinierte Konverter](system-text-json-converters-how-to.md) können diese Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-216">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="customize-json-names-and-values"></a><span data-ttu-id="1c2f0-217">Anpassen von JSON-Namen und -Werten</span><span class="sxs-lookup"><span data-stu-id="1c2f0-217">Customize JSON names and values</span></span>

<span data-ttu-id="1c2f0-218">Standardmäßig bleiben Eigenschaftsnamen und Wörterbuchschlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-218">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="1c2f0-219">Enumerationswerte werden als Zahlen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-219">Enum values are represented as numbers.</span></span> <span data-ttu-id="1c2f0-220">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-220">This section explains how to:</span></span>

* [<span data-ttu-id="1c2f0-221">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-221">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="1c2f0-222">Konvertieren aller Eigenschaftsnamen in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="1c2f0-222">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="1c2f0-223">Implementieren einer benutzerdefinierten Benennungsrichtlinie für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-223">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="1c2f0-224">Konvertieren von Wörterbuchschlüsseln in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="1c2f0-224">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="1c2f0-225">Konvertieren von Enumerationen in Zeichenfolgen und Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="1c2f0-225">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="1c2f0-226">Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und -werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-226">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="1c2f0-227">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-227">Customize individual property names</span></span>

<span data-ttu-id="1c2f0-228">Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das Attribut [[JsonPropertyName]](xref::::no-loc(System.Text.Json):::.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-228">To set the name of individual properties, use the [[JsonPropertyName]](xref::::no-loc(System.Text.Json):::.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="1c2f0-229">Hier finden Sie einen zu serialisierenden Beispieltyp und die daraus resultierende JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-229">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1c2f0-230">Der über dieses Attribut festgelegte Eigenschaftsname:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-230">The property name set by this attribute:</span></span>

* <span data-ttu-id="1c2f0-231">Dies gilt in beide Richtungen, für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-231">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="1c2f0-232">Es hat Vorrang vor Benennungsrichtlinien für Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-232">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="1c2f0-233">Verwenden der Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-233">Use camel case for all JSON property names</span></span>

<span data-ttu-id="1c2f0-234">Um die Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen zu verwenden, legen Sie <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-234">To use camel case for all JSON property names, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="1c2f0-235">Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-235">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1c2f0-236">Die Camel-Case-Benennungsrichtlinie für Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-236">The camel case property naming policy:</span></span>

* <span data-ttu-id="1c2f0-237">Gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-237">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="1c2f0-238">Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-238">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="1c2f0-239">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-239">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="1c2f0-240">Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-240">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="1c2f0-241">Um eine benutzerdefinierte Benennungsrichtlinie für JSON-Eigenschaften zu verwenden, erstellen Sie eine Klasse, die von <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> abgeleitet ist, und setzen Sie die <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.ConvertName%2A>-Methode außer Kraft, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-241">To use a custom JSON property naming policy, create a class that derives from <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> and override the <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="1c2f0-242">Legen Sie dann die <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihre Benennungsrichtlinienklasse fest:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-242">Then set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-243">Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-243">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="1c2f0-244">Die Benennungsrichtlinie für JSON-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-244">The JSON property naming policy:</span></span>

* <span data-ttu-id="1c2f0-245">Gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-245">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="1c2f0-246">Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-246">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="1c2f0-247">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-247">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="1c2f0-248">Wörterbuchschlüssel in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="1c2f0-248">Camel case dictionary keys</span></span>

<span data-ttu-id="1c2f0-249">Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die Schlüssel vom Typ `string` in Camel-Case-Schreibweise konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-249">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="1c2f0-250">Legen Sie hierzu <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-250">To do that, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-251">Das Serialisieren eines Objekts mit einem Wörterbuch namens `TemperatureRanges`, das die Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` enthält, würde zu einer JSON-Ausgabe wie im folgenden Beispiel führen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-251">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="1c2f0-252">Die Camel-Case-Benennungsrichtlinie für Wörterbuchschlüssel gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-252">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="1c2f0-253">Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei auch dann, wenn Sie `JsonNamingPolicy.CamelCase` als `DictionaryKeyPolicy` angeben.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-253">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="1c2f0-254">Enumerationen als Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-254">Enums as strings</span></span>

<span data-ttu-id="1c2f0-255">Standardmäßig werden Enumerationen als Zahlen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-255">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="1c2f0-256">Um Enumerationen als Zeichenfolgen zu serialisieren, verwenden Sie <xref::::no-loc(System.Text.Json):::.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-256">To serialize enum names as strings, use the <xref::::no-loc(System.Text.Json):::.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="1c2f0-257">Angenommen, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-257">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="1c2f0-258">Wenn die Zusammenfassung `Hot` ist, hat das serialisierte JSON standardmäßig den numerischen Wert 3:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-258">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="1c2f0-259">Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-259">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-260">Das resultierende JSON sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-260">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="1c2f0-261">Zeichenfolgennamen von Enumerationen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-261">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="ignore-properties"></a><span data-ttu-id="1c2f0-262">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-262">Ignore properties</span></span>

<span data-ttu-id="1c2f0-263">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-263">By default, all public properties are serialized.</span></span> <span data-ttu-id="1c2f0-264">Wenn Sie möchten, dass einige von ihnen nicht in der JSON-Ausgabe vorkommen, haben Sie mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-264">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="1c2f0-265">In diesem Abschnitt wird erläutert, wie Sie Folgendes ignorieren können:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-265">This section explains how to ignore:</span></span>

::: zone pivot="dotnet-5-0"

* [<span data-ttu-id="1c2f0-266">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-266">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="1c2f0-267"> Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-267">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="1c2f0-268">Alle Nullwert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-268">All null-value properties</span></span>](#ignore-all-null-value-properties)
* [<span data-ttu-id="1c2f0-269">Alle Eigenschaften mit Standardwert</span><span class="sxs-lookup"><span data-stu-id="1c2f0-269">All default-value properties</span></span>](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [<span data-ttu-id="1c2f0-270">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-270">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="1c2f0-271"> Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-271">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="1c2f0-272">Alle Nullwert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-272">All null-value properties</span></span>](#ignore-all-null-value-properties)
::: zone-end

### <a name="ignore-individual-properties"></a><span data-ttu-id="1c2f0-273">Ignorieren einzelner Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-273">Ignore individual properties</span></span>

<span data-ttu-id="1c2f0-274">Um einzelne Eigenschaften zu ignorieren, verwenden Sie das Attribut [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-274">To ignore individual properties, use the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="1c2f0-275">Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-275">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-276">Sie können einen bedingten Ausschluss angeben, indem Sie die Eigenschaft `Condition` des Attributs [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) festlegen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-276">You can specify conditional exclusion by setting the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="1c2f0-277">Die Enumeration <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition> bietet die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-277">The <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="1c2f0-278">`Always`: Die Eigenschaft wird stets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-278">`Always` - The property is always ignored.</span></span> <span data-ttu-id="1c2f0-279">Wenn `Condition` nicht angegeben ist, wird diese Option angenommen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-279">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="1c2f0-280">`Never`: Die Eigenschaft wird stets serialisiert und deserialisiert, und zwar unabhängig von den globalen Einstellungen `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` und `IgnoreReadOnlyFields`.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-280">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="1c2f0-281">`WhenWritingDefault`: Die Eigenschaft wird bei der Serialisierung ignoriert, wenn es sich um den Verweistyp `null` oder den Werttyp `default` handelt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-281">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null` or a value type `default`.</span></span>
* <span data-ttu-id="1c2f0-282">`WhenWritingNull`: Die Eigenschaft wird bei der Serialisierung ignoriert, wenn es sich um den Verweistyp `null` handelt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-282">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`.</span></span>

<span data-ttu-id="1c2f0-283">Das folgende Beispiel veranschaulicht die Verwendung der Eigenschaft `Condition` des Attributs [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute):</span><span class="sxs-lookup"><span data-stu-id="1c2f0-283">The following example illustrates use of the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

### <a name="ignore-all-read-only-properties"></a><span data-ttu-id="1c2f0-284">Ignorieren aller schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1c2f0-284">Ignore all read-only properties</span></span>

<span data-ttu-id="1c2f0-285">Eine Eigenschaft ist schreibgeschützt, wenn sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-285">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="1c2f0-286">Um alle schreibgeschützten Eigenschaften bei der Serialisierung zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-286">To ignore all read-only properties when serializing, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-287">Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-287">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="1c2f0-288">Diese Option gilt nur für Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-288">This option applies only to serialization.</span></span> <span data-ttu-id="1c2f0-289">Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-289">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-290">Diese Option gilt nur für Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-290">This option applies only to properties.</span></span> <span data-ttu-id="1c2f0-291">Um schreibgeschützte Felder beim [Serialisieren von Feldern](#include-fields) zu ignorieren, verwenden Sie die globale Einstellung <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-291">To ignore read-only fields when [serializing fields](#include-fields), use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

### <a name="ignore-all-null-value-properties"></a><span data-ttu-id="1c2f0-292">Ignorieren aller Eigenschaften mit dem Wert NULL</span><span class="sxs-lookup"><span data-stu-id="1c2f0-292">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-293">Um alle Eigenschaften mit dem Wert NULL zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> auf <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingNull> fest:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-293">To ignore all null-value properties, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-294">Um bei der Serialisierung alle Eigenschaften mit dem Wert NULL zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreNullValues> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-294">To ignore all null-value properties when serializing, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-295">Hier finden Sie ein zu serialisierendes Beispielobjekt und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-295">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="1c2f0-296">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c2f0-296">Property</span></span> |<span data-ttu-id="1c2f0-297">Wert</span><span class="sxs-lookup"><span data-stu-id="1c2f0-297">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="1c2f0-298">Datum</span><span class="sxs-lookup"><span data-stu-id="1c2f0-298">Date</span></span>    | <span data-ttu-id="1c2f0-299">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="1c2f0-299">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="1c2f0-300">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="1c2f0-300">TemperatureCelsius</span></span>| <span data-ttu-id="1c2f0-301">25</span><span class="sxs-lookup"><span data-stu-id="1c2f0-301">25</span></span> |
| <span data-ttu-id="1c2f0-302">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1c2f0-302">Summary</span></span>| <span data-ttu-id="1c2f0-303">NULL</span><span class="sxs-lookup"><span data-stu-id="1c2f0-303">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

### <a name="ignore-all-default-value-properties"></a><span data-ttu-id="1c2f0-304">Ignorieren aller Eigenschaften mit Standardwert</span><span class="sxs-lookup"><span data-stu-id="1c2f0-304">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-305">Um die Serialisierung von Standardwerten in Werttypeigenschaften zu verhindern, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> auf <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingDefault> fest:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-305">To prevent serialization of default values in value type properties, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="1c2f0-306">Die Einstellung `WhenWritingDefault` verhindert auch die Serialisierung von Verweistypeigenschaften mit dem Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-306">The `WhenWritingDefault` setting also prevents serialization of null-value reference type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-307">Es gibt keine in . NET Core 3.1 integrierte Möglichkeit, die Serialisierung von Eigenschaften mit Standardwerttypen in :::no-loc(System.Text.Json)::: zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-307">There is no built-in way to prevent serialization of properties with value type defaults in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span>
::: zone-end

## <a name="customize-character-encoding"></a><span data-ttu-id="1c2f0-308">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="1c2f0-308">Customize character encoding</span></span>

<span data-ttu-id="1c2f0-309">Standardmäßig escapet der Serialisierer alle Nicht-ASCII-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-309">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="1c2f0-310">Das heißt, dass sie durch `\uxxxx` ersetzt werden, wobei `xxxx` der Unicode-Code des Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-310">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="1c2f0-311">Wenn die `Summary`-Eigenschaft beispielsweise auf Kyrillisch „жарко“ festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-311">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="1c2f0-312">Serialisieren von Sprachzeichensätzen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-312">Serialize language character sets</span></span>

<span data-ttu-id="1c2f0-313">Zum Serialisieren der Zeichensätze von mindestens einer Sprache ohne zu escapen geben Sie [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) an, wenn Sie eine Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> erstellen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-313">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="1c2f0-314">Mit diesem Code werden weder kyrillische noch griechische Zeichen escapet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-314">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="1c2f0-315">Wenn die `Summary`-Eigenschaft auf Kyrillisch „жарко“ festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-315">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="1c2f0-316">Um alle Sprachensätze ohne zu escapen zu serialisieren, verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-316">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="1c2f0-317">Serialisieren bestimmter Zeichen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-317">Serialize specific characters</span></span>

<span data-ttu-id="1c2f0-318">Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne dass sie escapet werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-318">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="1c2f0-319">Im folgenden Beispiel werden nur die ersten zwei Zeichen von „жарко“ serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-319">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="1c2f0-320">Hier sehen Sie eine JSON-Beispiel, das vom vorangehenden Code erzeugt wird:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-320">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="1c2f0-321">Serialisieren aller Zeichen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-321">Serialize all characters</span></span>

<span data-ttu-id="1c2f0-322">Um das Escapen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-322">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="1c2f0-323">Im Vergleich zum Standardencoder ist der `UnsafeRelaxedJsonEscaping`-Encoder weniger streng beim Zulassen von Zeichen, ohne sie zu escapen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-323">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="1c2f0-324">Er escapet keine HTML-abhängigen Zeichen wie `<`, `>`, `&` und `'`.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-324">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="1c2f0-325">Er bietet keine zusätzlichen, tief greifenden Abwehrmaßnahmen gegen solche Cross-Site Scripting (XSS)- oder Information-Disclosure-Angriffe (Veröffentlichung von Informationen), die von einem Client und Server, die sich nicht auf einen *Zeichensatz* einigen können, verursacht werden können.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-325">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="1c2f0-326">Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretieren wird.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-326">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="1c2f0-327">Beispielsweise können Sie ihn verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8` sendet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-327">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="1c2f0-328">Gestatten Sie niemals, dass die `UnsafeRelaxedJsonEscaping`-Rohausgabe in eine HTML-Seite oder ein `<script>`-Element ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-328">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="1c2f0-329">Serialisieren von Eigenschaften abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-329">Serialize properties of derived classes</span></span>

<span data-ttu-id="1c2f0-330">Das Serialisieren einer polymorphen Typhierarchie wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-330">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="1c2f0-331">Wenn eine Eigenschaft beispielsweise als eine Schnittstelle oder eine abstrakte Klasse definiert wird, werden nur die für die Schnittstelle oder abstrakte Klasse definierten Eigenschaften serialisiert, auch wenn der Laufzeittyp über zusätzliche Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-331">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="1c2f0-332">Die Ausnahmen bei diesem Verhalten werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-332">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="1c2f0-333">Nehmen Sie beispielsweise an, Sie besitzen eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-333">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="1c2f0-334">Ferner sei angenommen, dass das Typargument der `Serialize`-Methode zur Kompilierzeit `WeatherForecast` ist:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-334">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="1c2f0-335">In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch dann nicht, wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-335">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="1c2f0-336">Nur die Basisklasseneigenschaften werden serialisiert:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-336">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="1c2f0-337">Dieses Verhalten soll die versehentliche Verfügbarmachung von Daten in einem abgeleiteten, zur Laufzeit erstellten Typ verhindern.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-337">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="1c2f0-338">Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs im vorherigen Beispiel zu serialisieren:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-338">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="1c2f0-339">Rufen Sie eine Überladung von <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A> auf, bei der Sie den Typ zur Laufzeit angeben können:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-339">Call an overload of <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="1c2f0-340">Deklarieren Sie das zu serialisierende Objekt als `object`.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-340">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="1c2f0-341">Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in die JSON-Ausgabe aufgenommen wird:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-341">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="1c2f0-342">Diese Ansätze bieten polymorphe Serialisierung nur für das Stammobjekt, das serialisiert werden soll, und nicht für die Eigenschaften dieses Stammobjekts.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-342">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="1c2f0-343">Sie können polymorphe Serialisierung für Objekte auf niedrigerer Ebene erzielen, wenn Sie diese als `object`-Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-343">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="1c2f0-344">Angenommen, Ihre `WeatherForecast`-Klasse verfügt über eine Eigenschaft mit dem Namen `PreviousForecast`, die als `WeatherForecast`-Typ oder als `object`-Typ definiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-344">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="1c2f0-345">Wenn die Eigenschaft `PreviousForecast` eine Instanz von `WeatherForecastDerived` enthält:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-345">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="1c2f0-346">Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPrevious` **enthält keine** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-346">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="1c2f0-347">Die JSON-Ausgabe der Serialisierung von `WeatherForecastWithPreviousAsObject` **enthält** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-347">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="1c2f0-348">Um `WeatherForecastWithPreviousAsObject` zu serialisieren, ist es nicht erforderlich, `Serialize<object>` oder `GetType` aufzurufen, da das Stammobjekt nicht das Objekt ist, das von einem abgeleiteten Typ sein darf.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-348">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="1c2f0-349">Im folgenden Codebeispiel wird weder `Serialize<object>` noch `GetType` aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-349">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="1c2f0-350">Der vorangehende Code serialisiert `WeatherForecastWithPreviousAsObject` korrekt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-350">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="1c2f0-351">Derselbe Ansatz zum Definieren von Eigenschaften als `object` funktioniert mit Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-351">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="1c2f0-352">Angenommen, Sie haben die folgende Schnittstelle und Implementierung, und Sie möchten eine Klasse mit Eigenschaften serialisieren, die Implementierungsinstanzen enthalten:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-352">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="1c2f0-353">Wenn Sie eine Instanz von `Forecasts` serialisieren, zeigt nur `Tuesday` die `WindSpeed`-Eigenschaft an, da `Tuesday` als `object` definiert ist:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-353">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="1c2f0-354">Im folgenden Beispiel wird der JSON-Code gezeigt, der aus dem vorangehenden Code resultiert:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-354">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="1c2f0-355">Weitere Informationen zur polymorphen **Serialisierung** sowie Informationen zur **Deserialisierung** finden Sie unter [Migrieren von :::no-loc(Newtonsoft.Json)::: zu :::no-loc(System.Text.Json):::](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-355">For more information about polymorphic **serialization** , and for information about **deserialization** , see [How to migrate from :::no-loc(Newtonsoft.Json)::: to :::no-loc(System.Text.Json):::](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="1c2f0-356">Zulassen von Kommentaren und nachfolgenden Kommas</span><span class="sxs-lookup"><span data-stu-id="1c2f0-356">Allow comments and trailing commas</span></span>

<span data-ttu-id="1c2f0-357">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-357">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="1c2f0-358">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-358">To allow comments in the JSON, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="1c2f0-359">Und um nachfolgende Kommas zuzulassen, legen Sie die <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-359">And to allow trailing commas, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="1c2f0-360">Das folgende Beispiel veranschaulicht, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-360">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="1c2f0-361">Im Folgenden finden Sie ein JSON-Beispiel mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-361">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="1c2f0-362">Eigenschaftenabgleich ohne Beachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="1c2f0-362">Case-insensitive property matching</span></span>

<span data-ttu-id="1c2f0-363">Standardmäßig wird bei der Deserialisierung nach Übereinstimmungen von Eigenschaftsnamen zwischen JSON und den Zielobjekteigenschaften unter Berücksichtigung von Groß-/Kleinschreibung gesucht.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-363">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="1c2f0-364">Um dieses Verhalten zu ändern, legen Sie <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-364">To change that behavior, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="1c2f0-365">Im Folgenden finden Sie ein JSON-Beispiel mit Eigenschaftsnamen in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-365">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="1c2f0-366">Es kann in den folgenden Typ deserialisiert werden, der Eigenschaftsnamen in Pascal-Schreibweise besitzt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-366">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="1c2f0-367">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="1c2f0-367">Handle overflow JSON</span></span>

<span data-ttu-id="1c2f0-368">Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, die nicht von Eigenschaften des Zieltyps dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-368">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="1c2f0-369">Angenommen, Ihr Zieltyp ist folgender:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-369">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="1c2f0-370">Und der zu deserialisierende JSON-Code ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-370">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="1c2f0-371">Wenn Sie den angezeigten JSON-Code in den gezeigten Typ deserialisieren, gibt es keinen Ort mehr für die Eigenschaften `DatesAvailable` und `SummaryWords`, und sie gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-371">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="1c2f0-372">Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das Attribut [JsonExtensionData](xref::::no-loc(System.Text.Json):::.Serialization.JsonExtensionDataAttribute) auf eine Eigenschaft des Typs `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-372">To capture extra data such as these properties, apply the [[JsonExtensionData]](xref::::no-loc(System.Text.Json):::.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="1c2f0-373">Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-373">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="1c2f0-374">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c2f0-374">Property</span></span> |<span data-ttu-id="1c2f0-375">Wert</span><span class="sxs-lookup"><span data-stu-id="1c2f0-375">Value</span></span>  |<span data-ttu-id="1c2f0-376">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c2f0-376">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="1c2f0-377">Datum</span><span class="sxs-lookup"><span data-stu-id="1c2f0-377">Date</span></span>    | <span data-ttu-id="1c2f0-378">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="1c2f0-378">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="1c2f0-379">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="1c2f0-379">TemperatureCelsius</span></span>| <span data-ttu-id="1c2f0-380">0</span><span class="sxs-lookup"><span data-stu-id="1c2f0-380">0</span></span> | <span data-ttu-id="1c2f0-381">Keine Übereinstimmung unter Berücksichtigung von Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die Eigenschaft nicht festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-381">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="1c2f0-382">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1c2f0-382">Summary</span></span> | <span data-ttu-id="1c2f0-383">Heiß</span><span class="sxs-lookup"><span data-stu-id="1c2f0-383">Hot</span></span> ||
| <span data-ttu-id="1c2f0-384">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="1c2f0-384">ExtensionData</span></span> | <span data-ttu-id="1c2f0-385">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="1c2f0-385">temperatureCelsius: 25</span></span> |<span data-ttu-id="1c2f0-386">Da die Groß-/Kleinschreibung nicht übereinstimmte, ist diese JSON-Eigenschaft ein zusätzliches Element und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-386">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="1c2f0-387">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-387">DatesAvailable:</span></span><br>  <span data-ttu-id="1c2f0-388">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="1c2f0-388">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="1c2f0-389">8/2/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="1c2f0-389">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="1c2f0-390">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-390">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="1c2f0-391">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-391">SummaryWords:</span></span><br><span data-ttu-id="1c2f0-392">Toll</span><span class="sxs-lookup"><span data-stu-id="1c2f0-392">Cool</span></span><br><span data-ttu-id="1c2f0-393">Windig</span><span class="sxs-lookup"><span data-stu-id="1c2f0-393">Windy</span></span><br><span data-ttu-id="1c2f0-394">Feucht</span><span class="sxs-lookup"><span data-stu-id="1c2f0-394">Humid</span></span> |<span data-ttu-id="1c2f0-395">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-395">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="1c2f0-396">Wenn das Zielobjekt serialisiert wird, werden die Schlüssel-Wert-Paare der Erweiterungsdaten zu genau solchen JSON-Eigenschaften, wie sie im eingehenden JSON-Code waren:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-396">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="1c2f0-397">Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code vorkommt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-397">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="1c2f0-398">Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert würden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-398">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="preserve-references-and-handle-circular-references"></a><span data-ttu-id="1c2f0-399">Beibehalten von Verweisen und Behandeln von Zirkelbezügen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-399">Preserve references and handle circular references</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="1c2f0-400">Um Verweise beizubehalten und Zirkelbezüge zu behandeln, legen Sie <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReferenceHandler%2A> auf <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-400">To preserve references and handle circular references, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReferenceHandler%2A> to <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="1c2f0-401">Diese Einstellung bewirkt folgendes Verhalten:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-401">This setting causes the following behavior:</span></span>

* <span data-ttu-id="1c2f0-402">Beim Serialisieren:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-402">On serialize:</span></span>

  <span data-ttu-id="1c2f0-403">Beim Schreiben komplexer Typen schreibt das Serialisierungsmodul auch Metadateneigenschaften (`$id`, `$values` und `$ref`).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-403">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="1c2f0-404">Beim Deserialisieren:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-404">On deserialize:</span></span>

  <span data-ttu-id="1c2f0-405">Metadaten werden erwartet (obwohl nicht zwingend erforderlich), und der Deserialisierer versucht, sie zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-405">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="1c2f0-406">Der folgende Code veranschaulicht die Verwendung der Einstellung `Preserve`.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-406">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="1c2f0-407">Dieses Feature kann nicht verwendet werden, um Wert- oder unveränderliche Typen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-407">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="1c2f0-408">Bei der Deserialisierung wird die Instanz eines unveränderlichen Typs erstellt, nachdem die gesamten Nutzdaten gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-408">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="1c2f0-409">Daher wäre es unmöglich, dieselbe Instanz zu deserialisieren, wenn ein Verweis darauf in den JSON-Nutzdaten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-409">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="1c2f0-410">Für Werttypen, unveränderliche Typen und Arrays werden keine Verweismetadaten serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-410">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="1c2f0-411">Bei der Deserialisierung wird eine Ausnahme ausgelöst, wenn `$ref` oder `$id` gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-411">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="1c2f0-412">Werttypen ignorieren jedoch `$id` (und `$values` im Falle von Sammlungen), um die Deserialisierung von Nutzdaten zu ermöglichen, die mit :::no-loc(Newtonsoft.Json)::: serialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-412">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using :::no-loc(Newtonsoft.Json):::.</span></span>  <span data-ttu-id="1c2f0-413">:::no-loc(Newtonsoft.Json)::: serialisiert die Metadaten für solche Typen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-413">:::no-loc(Newtonsoft.Json)::: does serialize metadata for such types.</span></span>

<span data-ttu-id="1c2f0-414">Um festzustellen, ob Objekte gleich sind, wird <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType> von :::no-loc(System.Text.Json)::: verwendet. Dabei wird beim Vergleich zweier Objektinstanzen die Verweisgleichheit (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) anstelle der Wertgleichheit (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>) verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-414">To determine if objects are equal, :::no-loc(System.Text.Json)::: uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="1c2f0-415">Weitere Informationen zur Serialisierung und Deserialisierung von Verweisen finden Sie unter <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-415">For more information about how references are serialized and deserialized, see <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1c2f0-416">Die <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceResolver>-Klasse definiert das Verhalten bei Beibehaltung von Verweisen für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-416">The <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="1c2f0-417">Erstellen Sie eine abgeleitete Klasse, um benutzerdefiniertes Verhalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-417">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="1c2f0-418">Ein Beispiel finden Sie unter [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-418">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-419">:::no-loc(System.Text.Json)::: in .NET Core 3.1 unterstützt nur die Serialisierung nach Wert und löst bei Zirkelbezügen eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-419">:::no-loc(System.Text.Json)::: in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="1c2f0-420">Zulassen oder Schreiben von Zahlen in Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-420">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="1c2f0-421">Einige Serialisierungsmodule codieren Zahlen als (in Anführungszeichen eingeschlossene) JSON-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-421">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="1c2f0-422">Beispiel: `{"DegreesCelsius":"23"}` statt `{"DegreesCelsius":23}`.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-422">For example: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="1c2f0-423">Um Zahlen in Anführungszeichen zu serialisieren oder Zahlen in Anführungszeichen im gesamten Graphen des Eingabeobjekts zu akzeptieren, legen Sie <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> wie im folgenden Beispiel gezeigt fest:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-423">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-28":::

<span data-ttu-id="1c2f0-424">Wenn Sie :::no-loc(System.Text.Json)::: indirekt über ASP.NET Core verwenden, sind beim Deserialisieren Zahlen in Anführungszeichen erlaubt, da ASP.NET Core [Webstandardoptionen](xref::::no-loc(System.Text.Json):::.JsonSerializerDefaults.Web) angibt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-424">When you use :::no-loc(System.Text.Json)::: indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref::::no-loc(System.Text.Json):::.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="1c2f0-425">Um Zahlen in Anführungszeichen für bestimmte Eigenschaften, Felder oder Typen zuzulassen oder zu schreiben, verwenden Sie das Attribut [[JsonNumberHandling]](xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandlingAttribute).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-425">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-426">:::no-loc(System.Text.Json)::: in .NET Core 3.1 unterstützt keine Serialisierung oder Deserialisierung von Zahlen in Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-426">:::no-loc(System.Text.Json)::: in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="1c2f0-427">Weitere Informationen finden Sie unter [Zulassen oder Schreiben von Zahlen in Anführungszeichen](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-427">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="immutable-types-and-records"></a><span data-ttu-id="1c2f0-428">Unveränderliche Typen und Datensätze</span><span class="sxs-lookup"><span data-stu-id="1c2f0-428">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-429">:::no-loc(System.Text.Json)::: kann einen parametrisierten Konstruktor verwenden, der es ermöglicht, eine unveränderliche Klasse oder Struktur zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-429">:::no-loc(System.Text.Json)::: can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="1c2f0-430">Wenn für eine Klasse der einzige Konstruktor ein parametrisierter ist, wird dieser Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-430">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="1c2f0-431">Geben Sie für eine Struktur oder Klasse mit mehreren Konstruktoren den zu verwendenden Konstruktor an, indem Sie das Attribut [[JsonConstructor]](xref::::no-loc(System.Text.Json):::.Serialization.JsonConstructorAttribute.%23ctor%2A) anwenden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-431">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref::::no-loc(System.Text.Json):::.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="1c2f0-432">Wenn das Attribut nicht verwendet wird, wird, sofern vorhanden, stets ein öffentlicher parameterloser Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-432">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="1c2f0-433">Das Attribut kann nur mit öffentlichen Konstruktoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-433">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="1c2f0-434">Im folgenden Beispiel wird das Attribut `[JsonConstructor]` hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-434">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="1c2f0-435">Datensätze in C# 9 werden, wie im folgenden Beispiel gezeigt, ebenfalls unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-435">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="1c2f0-436">Informationen zu Typen, die unveränderlich sind, weil alle ihre Eigenschaftssetter nicht öffentlich sind, finden Sie im folgenden Abschnitt über [nicht öffentliche Eigenschaftenaccessoren](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-436">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-437">`JsonConstructorAttribute` und C# 9-Datensätze werden in .NET Core 3.1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-437">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="1c2f0-438">Nicht öffentliche Eigenschaftenaccessoren</span><span class="sxs-lookup"><span data-stu-id="1c2f0-438">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-439">Um die Verwendung eines nicht öffentlichen Eigenschaftenaccessors zu aktivieren, verwenden Sie das Attribut [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute), wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-439">To enable use of a non-public property accessor, use the [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-440">Nicht öffentliche Eigenschaftenaccessoren werden in .NET Core 3.1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-440">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="1c2f0-441">Weitere Informationen finden Sie im Artikel [Migration von :::no-loc(Newtonsoft.Json):::](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-441">For more information, see [the Migrate from :::no-loc(Newtonsoft.Json)::: article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="1c2f0-442">Kopieren von JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="1c2f0-442">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-443">Es gibt einen [JsonSerializerOptions-Konstruktor](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerOptions)), mit dem Sie eine neue Instanz mit den Optionen einer vorhandenen Instanz erstellen können, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-443">There is a [JsonSerializerOptions constructor](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-444">Ein Konstruktor des Typs `JsonSerializerOptions`, der eine vorhandene Instanz verwendet, steht in .NET Core 3.1 nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-444">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="1c2f0-445">Webstandardwerte für JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="1c2f0-445">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1c2f0-446">Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-446">Here are the options that have different defaults for web apps:</span></span>

* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> = <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.CamelCase>
* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A> = <xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="1c2f0-447">Es gibt einen [JsonSerializerOptions-Konstruktor](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerDefaults)?view=net-5.0&preserve-view=true), mit dem Sie eine neue Instanz mit den Standardoptionen erstellen können, die ASP.NET Core für Web-Apps verwendet (siehe folgendes Beispiel):</span><span class="sxs-lookup"><span data-stu-id="1c2f0-447">There's a [JsonSerializerOptions constructor](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-448">Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-448">Here are the options that have different defaults for web apps:</span></span>

* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> = <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.CamelCase>

<span data-ttu-id="1c2f0-449">Ein Konstruktor des Typs `JsonSerializerOptions`, der eine Gruppe von Standardwerten angibt, steht in .NET Core 3.1 nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-449">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="1c2f0-450">Erweiterungsmethoden für HttpClient und HttpContent</span><span class="sxs-lookup"><span data-stu-id="1c2f0-450">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="1c2f0-451">Das Serialisieren und Deserialisieren von aus dem Netzwerk stammenden JSON-Nutzdaten sind gängige Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-451">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="1c2f0-452">Erweiterungsmethoden für [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) und [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) ermöglichen Ihnen das Ausführen dieser Vorgänge in einer einzelnen Codezeile.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-452">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="1c2f0-453">Diese Erweiterungsmethoden verwenden [Webstandardwerte für JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-453">These extension methods use [web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="1c2f0-454">Im folgenden Beispiel wird die Verwendung von <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> und <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-454">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="23,30":::

<span data-ttu-id="1c2f0-455">Es gibt auch Erweiterungsmethoden für :::no-loc(System.Text.Json)::: für [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span><span class="sxs-lookup"><span data-stu-id="1c2f0-455">There are also extension methods for :::no-loc(System.Text.Json)::: on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1c2f0-456">Erweiterungsmethoden für `HttpClient` und `HttpContent` sind in :::no-loc(System.Text.Json)::: in .NET Core 3.1 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-456">Extension methods on `HttpClient` and `HttpContent` are not available in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span>
::: zone-end

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="1c2f0-457">„Utf8JsonReader“, „Utf8JsonWriter“ und „JsonDocument“</span><span class="sxs-lookup"><span data-stu-id="1c2f0-457">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="1c2f0-458"><xref::::no-loc(System.Text.Json):::.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, rein vorwärtsgerichteter Reader mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der aus einem `ReadOnlySpan<byte>` oder `ReadOnlySequence<byte>` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-458"><xref::::no-loc(System.Text.Json):::.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="1c2f0-459">Der `Utf8JsonReader` ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierungsprogrammen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-459">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="1c2f0-460">Die <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` verdeckt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-460">The <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="1c2f0-461">Mit <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter?displayProperty=fullName> lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell mit hohem Durchsatz schreiben.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-461"><xref::::no-loc(System.Text.Json):::.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="1c2f0-462">Der Writer ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-462">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="1c2f0-463">Die <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` verdeckt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-463">The <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="1c2f0-464"><xref::::no-loc(System.Text.Json):::.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mithilfe von `Utf8JsonReader` ein schreibgeschütztes Dokumentobjektmodell (DOM) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-464"><xref::::no-loc(System.Text.Json):::.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="1c2f0-465">Das DOM bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-465">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="1c2f0-466">Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den Typ <xref::::no-loc(System.Text.Json):::.JsonElement> zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-466">The JSON elements that compose the payload can be accessed via the <xref::::no-loc(System.Text.Json):::.JsonElement> type.</span></span> <span data-ttu-id="1c2f0-467">Der `JsonElement`-Typ stellt Array- und Objektenumeratoren sowie APIs zum Konvertieren von JSON-Text in gängige .NET-Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-467">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="1c2f0-468">`JsonDocument` macht eine <xref::::no-loc(System.Text.Json):::.JsonDocument.RootElement>-Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-468">`JsonDocument` exposes a <xref::::no-loc(System.Text.Json):::.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="1c2f0-469">In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-469">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="1c2f0-470">Verwenden von „JsonDocument“ für den Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="1c2f0-470">Use JsonDocument for access to data</span></span>

<span data-ttu-id="1c2f0-471">Das folgende Beispiel zeigt, wie Sie die <xref::::no-loc(System.Text.Json):::.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-471">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="1c2f0-472">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-472">The preceding code:</span></span>

* <span data-ttu-id="1c2f0-473">Setzt voraus, dass sich der zu analysierende JSON-Code in einer Zeichenfolge namens `jsonString` befindet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-473">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="1c2f0-474">Berechnet eine durchschnittliche Note für Objekte in einem `Students`-Array, die eine `Grade`-Eigenschaft besitzen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-474">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="1c2f0-475">Weist Kursteilnehmern, die keine Note haben, eine Standardnote von 70 zu.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-475">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="1c2f0-476">Zählt Kursteilnehmer durch Inkrementieren einer `count`-Variablen bei jeder Iteration.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-476">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="1c2f0-477">Eine Alternative besteht darin, <xref::::no-loc(System.Text.Json):::.JsonElement.GetArrayLength%2A> aufzurufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-477">An alternative is to call <xref::::no-loc(System.Text.Json):::.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="1c2f0-478">Im Folgenden finden Sie ein Beispiel für das JSON, das von diesem Code verarbeitet wird:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-478">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="1c2f0-479">Verwenden von JsonDocument zum Schreiben von JSON</span><span class="sxs-lookup"><span data-stu-id="1c2f0-479">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="1c2f0-480">Das folgende Beispiel veranschaulicht, wie JSON aus einem <xref::::no-loc(System.Text.Json):::.JsonDocument> geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-480">The following example shows how to write JSON from a <xref::::no-loc(System.Text.Json):::.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="1c2f0-481">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-481">The preceding code:</span></span>

* <span data-ttu-id="1c2f0-482">Liest eine JSON-Datei, lädt die Daten in ein `JsonDocument` und schreibt (übersichtlich) formatierten JSON-Code in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-482">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="1c2f0-483">Verwendet <xref::::no-loc(System.Text.Json):::.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-483">Uses <xref::::no-loc(System.Text.Json):::.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="1c2f0-484">Ruft nach Abschluss <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter.Flush%2A> für den Writer auf.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-484">When finished, calls <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="1c2f0-485">Eine Alternative besteht darin, den Writer automatisch zu leeren, wenn er entsorgt wird.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-485">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="1c2f0-486">Im Folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die von dem Beispielcode verarbeitet werden soll:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-486">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="1c2f0-487">Das Ergebnis ist die folgende, übersichtlich formatierte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-487">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="1c2f0-488">Verwenden von „Utf8JsonWriter“</span><span class="sxs-lookup"><span data-stu-id="1c2f0-488">Use Utf8JsonWriter</span></span>

<span data-ttu-id="1c2f0-489">Im folgenden Beispiel wird die Verwendung der <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter>-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-489">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="1c2f0-490">Verwenden von „Utf8JsonReader“</span><span class="sxs-lookup"><span data-stu-id="1c2f0-490">Use Utf8JsonReader</span></span>

<span data-ttu-id="1c2f0-491">Im folgenden Beispiel wird die Verwendung der <xref::::no-loc(System.Text.Json):::.Utf8JsonReader>-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-491">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="1c2f0-492">Der vorangehende Code setzt voraus, dass es sich bei der `jsonUtf8`-Variablen um ein Bytearray handelt, das gültigen, UTF-8-codierten JSON-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-492">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="1c2f0-493">Filtern von Daten mithilfe von „Utf8JsonReader“</span><span class="sxs-lookup"><span data-stu-id="1c2f0-493">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="1c2f0-494">Das folgende Beispiel zeigt, wie Sie eine Datei synchron lesen und nach einem Wert suchen:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-494">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="1c2f0-495">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-495">The preceding code:</span></span>

* <span data-ttu-id="1c2f0-496">Setzt voraus, dass der JSON-Code ein Array von Objekten enthält, und dass jedes Objekt eine Eigenschaft „name“ vom Typ „string“ (Zeichenfolge) enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-496">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="1c2f0-497">Zählt Objekte und „name“-Eigenschaftswerte, die auf „University“ enden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-497">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="1c2f0-498">Setzt voraus, dass die Datei UTF-16-codiert ist und transcodiert sie in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-498">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="1c2f0-499">Eine UTF-8-codierte Datei kann mithilfe des folgenden Codes direkt in ein `ReadOnlySpan<byte>` gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-499">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="1c2f0-500">Wenn die Datei eine UTF-8-Bytereihenfolge-Marke (BOM) enthält, entfernen Sie diese, bevor Sie die Bytes an den `Utf8JsonReader` übergeben, da der Reader Text erwartet.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-500">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="1c2f0-501">Andernfalls wird die BOM als ungültiges JSON betrachtet, und der Reader löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-501">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="1c2f0-502">Im Folgenden finden Sie ein JSON-Beispiel, das der voranstehende Code lesen kann.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-502">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="1c2f0-503">Die resultierende Zusammenfassungsmeldung lautet „2 out of 2 have names that end with ‚University‘“ (2 von 4 besitzen Namen, die auf „University“ enden):</span><span class="sxs-lookup"><span data-stu-id="1c2f0-503">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="1c2f0-504">Lesen aus einem Stream mithilfe von Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="1c2f0-504">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="1c2f0-505">Wenn Sie eine große Datei (z. B. ein Gigabyte oder mehr) lesen, möchten Sie die gesamte Datei vielleicht nicht auf einmal in den Arbeitsspeicher laden müssen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-505">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="1c2f0-506">In diesem Szenario können Sie einen <xref:System.IO.FileStream> verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-506">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="1c2f0-507">Wenn Sie einen `Utf8JsonReader` zum Lesen aus einem Stream verwenden, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="1c2f0-507">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="1c2f0-508">Der Puffer, der die partielle JSON-Nutzlast enthält, muss mindestens so groß wie das größte JSON-Token darin sein, damit der Reader vorankommen kann.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-508">The buffer containing the partial JSON payload must be at least as large as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="1c2f0-509">Der Puffer muss mindestens so groß wie die größte Sequenz von Leerraum innerhalb der JSON-Nutzdaten sein.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-509">The buffer must be at least as large as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="1c2f0-510">Der Reader verfolgt die gelesenen Daten nicht nach, bis er den nächsten <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.TokenType%2A> in der JSON-Nutzlast vollständig gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-510">The reader doesn't keep track of the data it has read until it completely reads the next <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="1c2f0-511">Wenn im Puffer noch Bytes vorhanden sind, müssen Sie sie wieder dem Reader übergeben.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-511">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="1c2f0-512">Sie können <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.BytesConsumed%2A> verwenden, um zu bestimmen, wie viele Bytes übrig bleiben.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-512">You can use <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="1c2f0-513">Im folgenden Code wird veranschaulicht, wie aus einem Stream gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-513">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="1c2f0-514">Das Beispiel zeigt einen <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-514">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="1c2f0-515">Ähnlicher Code funktioniert mit einem <xref:System.IO.FileStream>, es sei denn, der `FileStream` enthält am Anfang eine UTF-8-BOM.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-515">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="1c2f0-516">In diesem Fall müssen Sie diese drei Bytes aus dem Puffer entfernen, bevor Sie die verbleibenden Bytes an den `Utf8JsonReader` übergeben.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-516">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="1c2f0-517">Andernfalls würde der Reader eine Ausnahme auslösen, da die BOM nicht als gültiger Teil des JSON-Codes angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-517">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="1c2f0-518">Der Beispielcode beginnt mit einem 4 KB großen Puffer und verdoppelt die Puffergröße jedes Mal, wenn festgestellt wird, dass die Größe nicht ausreicht, um ein komplettes JSON-Token aufzunehmen. Dies ist erforderlich, damit der Reader mit den JSON-Nutzdaten vorankommt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-518">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not large enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="1c2f0-519">Das JSON-Beispiel im Codeausschnitt löst nur dann eine Erhöhung der Puffergröße aus, wenn Sie eine sehr geringe Anfangspuffergröße festlegen, z. B. 10 Bytes.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-519">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="1c2f0-520">Die `Console.WriteLine`-Anweisungen zeigen Ursache und Auswirkung der Puffergrößenerhöhungen, wenn Sie die Anfangspuffergröße auf 10 festlegen.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-520">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="1c2f0-521">Bei der Anfangspuffergröße von 4 KB wird das gesamte JSON-Beispiel von jeder `Console.WriteLine` angezeigt, und die Puffergröße muss nie erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-521">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="1c2f0-522">Im vorherigen Beispiel wurde keine Pufferobergrenze festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-522">The preceding example sets no limit to how large the buffer can grow.</span></span> <span data-ttu-id="1c2f0-523">Bei übermäßiger Tokengröße kann bei dem Code ein <xref:System.OutOfMemoryException>-Ausnahmefehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-523">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="1c2f0-524">Dies kann vorkommen, wenn der JSON-Code ein ungefähr 1 GB großes oder größeres Token enthält, da das Token bei Verdoppelung von 1 GB nicht mehr in einen `int32`-Puffer passt.</span><span class="sxs-lookup"><span data-stu-id="1c2f0-524">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c2f0-525">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1c2f0-525">Additional resources</span></span>

* [<span data-ttu-id="1c2f0-526">:::no-loc(System.Text.Json)::: – Übersicht</span><span class="sxs-lookup"><span data-stu-id="1c2f0-526">:::no-loc(System.Text.Json)::: overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1c2f0-527">Schreiben von benutzerdefinierten Konvertern</span><span class="sxs-lookup"><span data-stu-id="1c2f0-527">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="1c2f0-528">Migrieren von :::no-loc(Newtonsoft.Json):::</span><span class="sxs-lookup"><span data-stu-id="1c2f0-528">How to migrate from :::no-loc(Newtonsoft.Json):::</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="1c2f0-529">Unterstützung von „DateTime“ und „DateTimeOffset“ in :::no-loc(System.Text.Json):::</span><span class="sxs-lookup"><span data-stu-id="1c2f0-529">DateTime and DateTimeOffset support in :::no-loc(System.Text.Json):::</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="1c2f0-530">[:::no-loc(System.Text.Json):::-API-Referenz](xref::::no-loc(System.Text.Json):::)</span><span class="sxs-lookup"><span data-stu-id="1c2f0-530">[:::no-loc(System.Text.Json)::: API reference](xref::::no-loc(System.Text.Json):::)</span></span>
<!-- * [:::no-loc(System.Text.Json)::: roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::/roadmap/README.md)-->
