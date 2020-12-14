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
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="c1a36-104">Serialisieren und Deserialisieren (Marshallen und Marshallen rückgängig machen) von JSON-Daten in .NET</span><span class="sxs-lookup"><span data-stu-id="c1a36-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="c1a36-105">Dieser Artikel veranschaulicht, wie Sie mithilfe des <xref:System.Text.Json?displayProperty=fullName>-Namespace Daten in das JSON-Format (JavaScript Object Notation) serialisieren und daraus deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="c1a36-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="c1a36-106">Wenn Sie vorhandenen Code aus `Newtonsoft.Json` portieren, finden Sie weitere Informationen unter [Migrieren zu `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="c1a36-107">Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework wie [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="c1a36-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="c1a36-108">Im größten Teil des Serialisierungsbeispielcodes ist <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` festgelegt, um den JSON-Code übersichtlicher zu gestalten (mit Einzügen und Zwischenräumen für bessere Lesbarkeit).</span><span class="sxs-lookup"><span data-stu-id="c1a36-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="c1a36-109">Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c1a36-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="c1a36-110">Die Codebeispiele verweisen auf die folgende Klasse und deren Varianten:</span><span class="sxs-lookup"><span data-stu-id="c1a36-110">The code examples refer to the following class and variants of it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a><span data-ttu-id="c1a36-111">Namespaces</span><span class="sxs-lookup"><span data-stu-id="c1a36-111">Namespaces</span></span>

<span data-ttu-id="c1a36-112">Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="c1a36-113">Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="c1a36-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="c1a36-114">Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Anweisungen für einen oder beide Namespaces:</span><span class="sxs-lookup"><span data-stu-id="c1a36-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> <span data-ttu-id="c1a36-115">Attribute aus dem Namespace <xref:System.Runtime.Serialization> werden in `System.Text.Json` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1a36-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-as-json-serialize"></a><span data-ttu-id="c1a36-116">Schreiben von .NET-Objekten in JSON (Serialisieren)</span><span class="sxs-lookup"><span data-stu-id="c1a36-116">How to write .NET objects as JSON (serialize)</span></span>

<span data-ttu-id="c1a36-117">Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, rufen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="c1a36-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c1a36-118">Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="c1a36-118">The following example creates JSON as a string:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

<span data-ttu-id="c1a36-119">Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c1a36-119">The following example uses synchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

<span data-ttu-id="c1a36-120">Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c1a36-120">The following example uses asynchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

<span data-ttu-id="c1a36-121">In den vorangehenden Beispielen wird Typrückschluss für den zu serialisierenden Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1a36-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="c1a36-122">Eine Überladung von `Serialize()` akzeptiert einen generischen Typparameter:</span><span class="sxs-lookup"><span data-stu-id="c1a36-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a><span data-ttu-id="c1a36-123">Serialisierungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="c1a36-123">Serialization example</span></span>

<span data-ttu-id="c1a36-124">Im Folgenden finden Sie eine Beispielklasse, die die Sammlungstypeigenschaften und einen benutzerdefinierten Typen enthält:</span><span class="sxs-lookup"><span data-stu-id="c1a36-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> <span data-ttu-id="c1a36-125">„POCO“ steht für [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="c1a36-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="c1a36-126">Ein POCO ist ein .NET-Typ, der von keinen frameworkspezifischen Typen abhängig ist (z. B. durch Vererbung oder Attribute).</span><span class="sxs-lookup"><span data-stu-id="c1a36-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="c1a36-127">Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="c1a36-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="c1a36-128">Die JSON-Ausgabe wird standardmäßig minimiert (Zeichen für Leerraum, Einzug und Zeilenumbruch werden entfernt):</span><span class="sxs-lookup"><span data-stu-id="c1a36-128">The JSON output is minified (whitespace, indentation, and new-line characters are removed) by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="c1a36-129">Im folgenden Beispiel wird derselbe JSON-Code dargestellt, allerdings in formatierter Form (d. h. übersichtlich mit Zwischenräumen und Einzügen):</span><span class="sxs-lookup"><span data-stu-id="c1a36-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

## <a name="serialize-to-utf-8"></a><span data-ttu-id="c1a36-130">Serialisieren in UTF-8</span><span class="sxs-lookup"><span data-stu-id="c1a36-130">Serialize to UTF-8</span></span>

<span data-ttu-id="c1a36-131">Um in UTF-8 zu serialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="c1a36-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

<span data-ttu-id="c1a36-132">Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A>-Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> akzeptiert, ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c1a36-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="c1a36-133">Das Serialisieren in UTF-8 ist ungefähr 5–10 % schneller als die Verwendung von zeichenfolgenbasierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="c1a36-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="c1a36-134">Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="c1a36-135">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="c1a36-135">Serialization behavior</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="c1a36-136">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="c1a36-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="c1a36-137">Sie können [zu ignorierende Eigenschaften angeben](system-text-json-ignore-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-137">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="c1a36-138">Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="c1a36-139">JSON wird standardmäßig verkleinert.</span><span class="sxs-lookup"><span data-stu-id="c1a36-139">By default, JSON is minified.</span></span> <span data-ttu-id="c1a36-140">Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="c1a36-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="c1a36-141">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="c1a36-142">Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](system-text-json-customize-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-142">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="c1a36-143">Zirkelbezüge werden standardmäßig erkannt und entsprechende Ausnahmen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c1a36-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="c1a36-144">Sie können [Verweise beibehalten und Zirkelbezüge behandeln](system-text-json-preserve-references.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-144">You can [preserve references and handle circular references](system-text-json-preserve-references.md).</span></span>
* <span data-ttu-id="c1a36-145">[Felder](../../csharp/programming-guide/classes-and-structs/fields.md) werden standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c1a36-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="c1a36-146">Sie können [Felder einschließen](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="c1a36-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="c1a36-147">Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-147">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="c1a36-148">Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="c1a36-148">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="c1a36-149">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="c1a36-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="c1a36-150">Sie können [zu ignorierende Eigenschaften angeben](system-text-json-ignore-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-150">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="c1a36-151">Der [Standardencoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapet Nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [JSON-Spezifikation RFC 8259](https://tools.ietf.org/html/rfc8259#section-7) escapet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="c1a36-152">JSON wird standardmäßig verkleinert.</span><span class="sxs-lookup"><span data-stu-id="c1a36-152">By default, JSON is minified.</span></span> <span data-ttu-id="c1a36-153">Sie können den [JSON-Code übersichtlich formatieren](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="c1a36-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="c1a36-154">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen der von .NET-Namen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="c1a36-155">Sie können die [Groß-/Kleinschreibung von JSON-Namen anpassen](system-text-json-customize-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-155">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="c1a36-156">Zirkelbezüge werden erkannt und daraufhin Ausnahmen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c1a36-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="c1a36-157">[Felder](../../csharp/programming-guide/classes-and-structs/fields.md) werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c1a36-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="c1a36-158">Unter anderem unterstützte Typen:</span><span class="sxs-lookup"><span data-stu-id="c1a36-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="c1a36-159">.NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="c1a36-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="c1a36-160">benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="c1a36-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="c1a36-161">Eindimensionale und Jagged Arrays (`T[][]`).</span><span class="sxs-lookup"><span data-stu-id="c1a36-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="c1a36-162">Sammlungen und Wörterbücher aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="c1a36-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="c1a36-163">.NET-Primitive, die JavaScript-Primitiven entsprechen, z. B. numerische Typen, Zeichenfolgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="c1a36-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="c1a36-164">benutzerdefinierte [Plain Old CLR Objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="c1a36-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="c1a36-165">Eindimensionale und Jagged Arrays (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="c1a36-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="c1a36-166">Ein `Dictionary<string,TValue>`, wobei `TValue` ein `object` ist, ein `JsonElement` oder ein POCO.</span><span class="sxs-lookup"><span data-stu-id="c1a36-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="c1a36-167">Sammlungen aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="c1a36-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="c1a36-168">Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c1a36-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-as-net-objects-deserialize"></a><span data-ttu-id="c1a36-169">Lesen von JSON als .NET-Objekte (Deserialisieren)</span><span class="sxs-lookup"><span data-stu-id="c1a36-169">How to read JSON as .NET objects (deserialize)</span></span>

<span data-ttu-id="c1a36-170">Um aus einer Zeichenfolge oder einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="c1a36-170">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c1a36-171">Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecastWithPOCOs`-Klasse erstellt, die schon zuvor im [Serialisierungsbeispiel](#serialization-example) gezeigt wurde:</span><span class="sxs-lookup"><span data-stu-id="c1a36-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

<span data-ttu-id="c1a36-172">Um mithilfe von synchronem Code aus einer Datei zu deserialisieren, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c1a36-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

<span data-ttu-id="c1a36-173">Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, rufen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="c1a36-173">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a><span data-ttu-id="c1a36-174">Deserialisieren aus UTF-8</span><span class="sxs-lookup"><span data-stu-id="c1a36-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="c1a36-175">Um aus UTF-8 zu deserialisieren, rufen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung auf, die einen `ReadOnlySpan<byte>` oder ein `Utf8JsonReader` akzeptiert, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c1a36-175">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `ReadOnlySpan<byte>` or a `Utf8JsonReader`, as shown in the following examples.</span></span> <span data-ttu-id="c1a36-176">In den Beispielen wird vorausgesetzt, dass sich das JSON in einem Bytearray namens „jsonUtf8Bytes“ befindet.</span><span class="sxs-lookup"><span data-stu-id="c1a36-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a><span data-ttu-id="c1a36-177">Deserialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="c1a36-177">Deserialization behavior</span></span>

<span data-ttu-id="c1a36-178">Beim Deserialisieren von JSON-Code gelten die folgenden Verhaltensweisen:</span><span class="sxs-lookup"><span data-stu-id="c1a36-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="c1a36-179">Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="c1a36-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="c1a36-180">Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](system-text-json-character-casing.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-180">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span>
* <span data-ttu-id="c1a36-181">Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c1a36-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="c1a36-182">Nicht öffentliche Konstruktoren werden vom Serialisierungsmodul ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c1a36-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="c1a36-183">Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1a36-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="c1a36-184">Weitere Informationen finden Sie unter [Unveränderliche Typen und Datensätze](system-text-json-immutability.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-184">See [Immutable types and Records](system-text-json-immutability.md).</span></span>
* <span data-ttu-id="c1a36-185">Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1a36-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="c1a36-186">Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](system-text-json-customize-properties.md#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="c1a36-186">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="c1a36-187">Felder werden standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c1a36-187">By default, fields are ignored.</span></span> <span data-ttu-id="c1a36-188">Sie können [Felder einschließen](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="c1a36-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="c1a36-189">Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="c1a36-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="c1a36-190">Sie können [Kommentare und nachfolgende Kommas zulassen](system-text-json-invalid-json.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-190">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="c1a36-191">Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.</span><span class="sxs-lookup"><span data-stu-id="c1a36-191">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="c1a36-192">Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-192">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="c1a36-193">Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="c1a36-193">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="c1a36-194">Beim Abgleichen der Eigenschaftsnamen wird standardmäßig die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="c1a36-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="c1a36-195">Sie können [angeben, dass Groß-/Kleinschreibung nicht berücksichtigt wird](system-text-json-character-casing.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-195">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span> <span data-ttu-id="c1a36-196">ASP.NET Core-Apps [unterscheiden standardmäßig Groß-/Kleinschreibung nicht](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="c1a36-196">ASP.NET Core apps [specify case-insensitivity by default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="c1a36-197">Wenn der JSON-Code einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c1a36-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="c1a36-198">Ein parameterloser Konstruktor, der öffentlich, intern oder privat sein kann, wird für die Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1a36-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="c1a36-199">Die Deserialisierung in unveränderliche Objekte oder schreibgeschützte Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1a36-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="c1a36-200">Standardmäßig werden Enumerationen (Aufzählungen) als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1a36-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="c1a36-201">Sie können [Enumerationsnamen als Zeichenfolgen serialisieren](system-text-json-customize-properties.md#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="c1a36-201">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="c1a36-202">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1a36-202">Fields aren't supported.</span></span>
* <span data-ttu-id="c1a36-203">Standardmäßig lösen Kommentare oder nachfolgende Kommas im JSON-Code Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="c1a36-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="c1a36-204">Sie können [Kommentare und nachfolgende Kommas zulassen](system-text-json-invalid-json.md).</span><span class="sxs-lookup"><span data-stu-id="c1a36-204">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="c1a36-205">Die [ standardmäßige maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) beträgt 64.</span><span class="sxs-lookup"><span data-stu-id="c1a36-205">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="c1a36-206">Wenn Sie System.Text.Json indirekt in einer ASP.NET Core-App verwenden, unterscheiden sich einige Standardverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-206">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="c1a36-207">Weitere Informationen finden Sie unter [Webstandardwerte für JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="c1a36-207">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="c1a36-208">Sie können [benutzerdefinierte Konverter](system-text-json-converters-how-to.md) implementieren, um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c1a36-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="c1a36-209">Serialisieren in formatierten JSON-Code</span><span class="sxs-lookup"><span data-stu-id="c1a36-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="c1a36-210">Um die JSON-Ausgabe übersichtlich zu formatieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="c1a36-210">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

<span data-ttu-id="c1a36-211">Hier sehen Sie einen zu serialisierenden Beispieltyp und die übersichtlich formatierte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c1a36-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="c1a36-212">Wenn Sie `JsonSerializerOptions` wiederholt mit den gleichen Optionen verwenden, sollten Sie nicht bei jeder Verwendung eine neue `JsonSerializerOptions`-Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-212">If you use `JsonSerializerOptions` repeatedly with the same options, don't create a new `JsonSerializerOptions` instance each time you use it.</span></span> <span data-ttu-id="c1a36-213">Verwenden Sie für jeden Aufruf dieselbe Instanz.</span><span class="sxs-lookup"><span data-stu-id="c1a36-213">Reuse the same instance for every call.</span></span> <span data-ttu-id="c1a36-214">Weitere Informationen finden Sie unter [Wiederverwenden von JsonSerializerOptions-Instanzen](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span><span class="sxs-lookup"><span data-stu-id="c1a36-214">For more information, see [Reuse JsonSerializerOptions instances](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span></span>

## <a name="include-fields"></a><span data-ttu-id="c1a36-215">Einschließen von Feldern</span><span class="sxs-lookup"><span data-stu-id="c1a36-215">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="c1a36-216">Verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> oder das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), um Felder bei der Serialisierung oder Deserialisierung einzuschließen (siehe folgendes Beispiel):</span><span class="sxs-lookup"><span data-stu-id="c1a36-216">Use the <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

<span data-ttu-id="c1a36-217">Verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>, um schreibgeschützte Felder zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="c1a36-217">To ignore read-only fields, use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="c1a36-218">Felder werden in .NET Core 3.1 in System.Text.Json nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1a36-218">Fields are not supported in System.Text.Json in .NET Core 3.1.</span></span> <span data-ttu-id="c1a36-219">[Benutzerdefinierte Konverter](system-text-json-converters-how-to.md) können diese Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c1a36-219">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="c1a36-220">Erweiterungsmethoden für HttpClient und HttpContent</span><span class="sxs-lookup"><span data-stu-id="c1a36-220">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="c1a36-221">Das Serialisieren und Deserialisieren von aus dem Netzwerk stammenden JSON-Nutzdaten sind gängige Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="c1a36-221">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="c1a36-222">Erweiterungsmethoden für [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) und [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) ermöglichen Ihnen das Ausführen dieser Vorgänge in einer einzelnen Codezeile.</span><span class="sxs-lookup"><span data-stu-id="c1a36-222">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="c1a36-223">Diese Erweiterungsmethoden verwenden [Webstandardwerte für JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="c1a36-223">These extension methods use [web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="c1a36-224">Im folgenden Beispiel wird die Verwendung von <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> und <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c1a36-224">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

<span data-ttu-id="c1a36-225">Es gibt auch Erweiterungsmethoden für System.Text.Json für [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span><span class="sxs-lookup"><span data-stu-id="c1a36-225">There are also extension methods for System.Text.Json on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="c1a36-226">Erweiterungsmethoden für `HttpClient` und `HttpContent` sind in System.Text.Json in .NET Core 3.1 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c1a36-226">Extension methods on `HttpClient` and `HttpContent` are not available in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="c1a36-227">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1a36-227">See also</span></span>

* [<span data-ttu-id="c1a36-228">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="c1a36-228">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="c1a36-229">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="c1a36-229">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="c1a36-230">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="c1a36-230">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="c1a36-231">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="c1a36-231">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="c1a36-232">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c1a36-232">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="c1a36-233">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="c1a36-233">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="c1a36-234">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="c1a36-234">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="c1a36-235">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="c1a36-235">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="c1a36-236">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="c1a36-236">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="c1a36-237">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c1a36-237">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="c1a36-238">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="c1a36-238">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="c1a36-239">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="c1a36-239">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="c1a36-240">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="c1a36-240">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="c1a36-241">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c1a36-241">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="c1a36-242">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c1a36-242">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="c1a36-243">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="c1a36-243">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="c1a36-244">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="c1a36-244">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
