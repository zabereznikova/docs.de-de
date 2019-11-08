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
ms.openlocfilehash: f0245feb710f33d5fcea2a7125b8753ba6064018
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740430"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="d0c00-102">Serialisieren und Deserialisieren von JSON in .net</span><span class="sxs-lookup"><span data-stu-id="d0c00-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0c00-103">Die JSON-serialisierungsdokumentation befindet sich in der Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="d0c00-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="d0c00-104">In diesem Artikel werden nicht alle Szenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="d0c00-105">Weitere Informationen finden Sie unter " [System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) "-Probleme im dotnet/corefx-Repository auf GitHub, insbesondere die mit der Bezeichnung " [JSON-funktionsdoc](https://github.com/dotnet/corefx/labels/json-functionality-doc)".</span><span class="sxs-lookup"><span data-stu-id="d0c00-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="d0c00-106">In diesem Artikel wird gezeigt, wie Sie den <xref:System.Text.Json>-Namespace zum Serialisieren und Deserialisieren in und aus JavaScript Object Notation (JSON) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="d0c00-107">Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework, wie z. b. [ASP.net Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="d0c00-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="d0c00-108">Namespaces</span><span class="sxs-lookup"><span data-stu-id="d0c00-108">Namespaces</span></span>

<span data-ttu-id="d0c00-109">Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="d0c00-110">Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="d0c00-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="d0c00-111">Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Direktiven für einen oder beide Namespaces:</span><span class="sxs-lookup"><span data-stu-id="d0c00-111">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="d0c00-112">Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden derzeit in `System.Text.Json`nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="d0c00-113">Schreiben von .NET-Objekten in JSON (Serialisieren)</span><span class="sxs-lookup"><span data-stu-id="d0c00-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="d0c00-114">Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, müssen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-114">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d0c00-115">Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-115">The following example creates JSON as a string:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="d0c00-116">Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d0c00-116">The following example uses synchronous code to create a JSON file:</span></span>

```csharp
File.WriteAllText(outputFileName, JsonSerializer.Serialize(weatherForecast));
```

<span data-ttu-id="d0c00-117">Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d0c00-117">The following example uses asynchronous code to create a JSON file:</span></span>

```csharp
using (FileStream fs = File.Create(outputFileName))
{
    await JsonSerializer.SerializeAsync(fs, weatherForecast);
}
```

<span data-ttu-id="d0c00-118">In den vorangehenden Beispielen wird der Typrückschluss für den serialisierten Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0c00-118">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="d0c00-119">Eine Überladung von `Serialize()` nimmt einen generischen Typparameter an:</span><span class="sxs-lookup"><span data-stu-id="d0c00-119">An overload of `Serialize()` takes a generic type parameter:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

### <a name="serialization-example"></a><span data-ttu-id="d0c00-120">Beispiel für die Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d0c00-120">Serialization example</span></span>

<span data-ttu-id="d0c00-121">Hier ist ein Beispieltyp, der Auflistungen und Klassen enthält:</span><span class="sxs-lookup"><span data-stu-id="d0c00-121">Here's an example type that contains collections and nested classes:</span></span>

```csharp
public class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public IList<DateTimeOffset> DatesAvailable { get; set;}
    public Dictionary<string, HighLowTemperatures> TemperatureRanges { get; set; }
    public string [] SummaryWords { get; set; }
}

public class HighLowTemperatures
{
    public Temperature High { get; set; }
    public Temperature Low { get; set; }
}

public class Temperature
{
    public int DegreesCelsius { get; set; }
}
```

<span data-ttu-id="d0c00-122">Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="d0c00-122">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="d0c00-123">Die JSON-Ausgabe wird standardmäßig minimiert:</span><span class="sxs-lookup"><span data-stu-id="d0c00-123">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="d0c00-124">Im folgenden Beispiel wird derselbe JSON-Code dargestellt, der formatiert ist (d. h. mit Leerraum und Einzug):</span><span class="sxs-lookup"><span data-stu-id="d0c00-124">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": {
        "DegreesCelsius": 20
      },
      "Low": {
        "DegreesCelsius": -10
      }
    },
    "Hot": {
      "High": {
        "DegreesCelsius": 60
      },
      "Low": {
        "DegreesCelsius": 20
      }
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="d0c00-125">In UTF-8 serialisieren</span><span class="sxs-lookup"><span data-stu-id="d0c00-125">Serialize to UTF-8</span></span>

<span data-ttu-id="d0c00-126">Um zu UTF-8 zu serialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="d0c00-126">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] jsonUtf8Bytes = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="d0c00-127">Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A> Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> annimmt, ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d0c00-127">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="d0c00-128">Die Serialisierung in UTF-8 ist ungefähr 5-10% schneller als die Verwendung der Zeichen folgen basierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-128">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="d0c00-129">Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichen folgen (UTF-16) konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-129">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="d0c00-130">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="d0c00-130">Serialization behavior</span></span>

* <span data-ttu-id="d0c00-131">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="d0c00-131">By default, all public properties are serialized.</span></span> <span data-ttu-id="d0c00-132">Sie können [Eigenschaften angeben, die ausgeschlossen werden sollen](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="d0c00-132">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="d0c00-133">Der [standardcodierer](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) schützt nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die entsprechend [der JSON-Spezifikation](https://tools.ietf.org/html/rfc8259#section-7)mit Escapezeichen versehen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-133">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="d0c00-134">Standardmäßig wird JSON minimiert.</span><span class="sxs-lookup"><span data-stu-id="d0c00-134">By default, JSON is minified.</span></span> <span data-ttu-id="d0c00-135">Sie können [den JSON-Code ziemlich ausdrucken](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="d0c00-135">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="d0c00-136">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen den .net-Namen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-136">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="d0c00-137">Sie können die [JSON-namens](#customize-json-names-and-values)Schreibweise anpassen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-137">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="d0c00-138">Zirkuläre Verweise werden erkannt, und Ausnahmen werden ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d0c00-138">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="d0c00-139">Weitere Informationen finden Sie unter dem [Problem für zirkuläre Verweise](https://github.com/dotnet/corefx/issues/38579) im dotnet/corefx-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="d0c00-139">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="d0c00-140">Derzeit werden Felder ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="d0c00-141">Folgende Typen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-141">Supported types include:</span></span>

* <span data-ttu-id="d0c00-142">.Net-primitive, die JavaScript-primitiven zugeordnet sind, z. b. numerische Typen, Zeichen folgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="d0c00-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="d0c00-143">Benutzerdefinierte [Plain Old CLR Objects (POCOS)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="d0c00-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="d0c00-144">Eindimensionales und verzweigte Arrays (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="d0c00-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="d0c00-145">`Dictionary<string,TValue>`, wo `TValue` `object`, `JsonElement`oder poco ist.</span><span class="sxs-lookup"><span data-stu-id="d0c00-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="d0c00-146">Sammlungen aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="d0c00-146">Collections from the following namespaces.</span></span> <span data-ttu-id="d0c00-147">Weitere Informationen finden Sie im [Thema zur Unterstützung von Sammlungen](https://github.com/dotnet/corefx/issues/36643) im dotnet/corefx-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="d0c00-147">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="d0c00-148">Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md) , um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="d0c00-149">Lesen von JSON in .NET-Objekte (Deserialisieren)</span><span class="sxs-lookup"><span data-stu-id="d0c00-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="d0c00-150">Um eine Zeichenfolge oder eine Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d0c00-151">Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen:</span><span class="sxs-lookup"><span data-stu-id="d0c00-151">The following example reads JSON from a string:</span></span>

```csharp
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="d0c00-152">Wenn Sie aus einer Datei mithilfe von synchronem Code deserialisieren möchten, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="d0c00-153">Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode abrufen:</span><span class="sxs-lookup"><span data-stu-id="d0c00-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

```csharp
using (FileStream fs = File.OpenRead(inputFileName))
{
    weatherForecast = await JsonSerializer.DeserializeAsync<WeatherForecast>(fs);
}
```

<span data-ttu-id="d0c00-154">Einen Beispieltyp und entsprechende JSON finden Sie im Abschnitt [Serialization example](#serialization-example) .</span><span class="sxs-lookup"><span data-stu-id="d0c00-154">For an example type and corresponding JSON, see the [Serialization example](#serialization-example) section.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="d0c00-155">Aus UTF-8 Deserialisieren</span><span class="sxs-lookup"><span data-stu-id="d0c00-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="d0c00-156">Um von UTF-8 zu deserialisieren, müssen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> Überladung aufrufen, die eine `Utf8JsonReader` oder eine `ReadOnlySpan<byte>`annimmt, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="d0c00-157">In den Beispielen wird davon ausgegangen, dass sich die JSON in einem Bytearray namens jsonUtf8Bytes</span><span class="sxs-lookup"><span data-stu-id="d0c00-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

```csharp
var readOnlySpan = new ReadOnlySpan<byte>(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
var utf8Reader = new Utf8JsonReader(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="d0c00-158">Deserialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="d0c00-158">Deserialization behavior</span></span>

* <span data-ttu-id="d0c00-159">Standardmäßig wird die Groß-/Kleinschreibung bei der Übereinstimmung von Eigenschaften Namen</span><span class="sxs-lookup"><span data-stu-id="d0c00-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="d0c00-160">Sie können die [Groß-/Kleinschreibung](#case-insensitive-property-matching)nicht beachten.</span><span class="sxs-lookup"><span data-stu-id="d0c00-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="d0c00-161">Wenn der JSON-Wert einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d0c00-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="d0c00-162">Die Deserialisierung für Verweis Typen ohne Parameter losen Konstruktor wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="d0c00-163">Die Deserialisierung zu unveränderlichen Objekten oder schreibgeschützten Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="d0c00-164">Weitere Informationen finden Sie im GitHub- [Problem bei der Unterstützung für unveränderliche Objekte](https://github.com/dotnet/corefx/issues/38569) und im Repository "dotnet/corefx" auf GitHub Unterstützung für schreibgeschützte [Eigenschaften](https://github.com/dotnet/corefx/issues/38163) .</span><span class="sxs-lookup"><span data-stu-id="d0c00-164">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="d0c00-165">Standardmäßig werden Enumerationen als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-165">By default, enums are supported as numbers.</span></span> <span data-ttu-id="d0c00-166">Enumerationsnamen können als Zeichen folgen [serialisiert](#enums-as-strings)werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-166">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="d0c00-167">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-167">Fields aren't supported.</span></span>
* <span data-ttu-id="d0c00-168">Standardmäßig lösen Kommentare oder nachfolgende Kommas in der JSON-Datei Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="d0c00-168">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="d0c00-169">Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="d0c00-169">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="d0c00-170">Der Standardwert für die [Maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) ist 64.</span><span class="sxs-lookup"><span data-stu-id="d0c00-170">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="d0c00-171">Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md) , um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-171">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="d0c00-172">Serialisieren in formatierten JSON-Code</span><span class="sxs-lookup"><span data-stu-id="d0c00-172">Serialize to formatted JSON</span></span>

<span data-ttu-id="d0c00-173">Um die JSON-Ausgabe zu Recht drucken, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true`fest:</span><span class="sxs-lookup"><span data-stu-id="d0c00-173">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="d0c00-174">Hier ist ein Beispieltyp, der serialisiert und eine ziemlich gedruckte JSON-Ausgabe ist:</span><span class="sxs-lookup"><span data-stu-id="d0c00-174">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="d0c00-175">Anpassen von JSON-Namen und-Werten</span><span class="sxs-lookup"><span data-stu-id="d0c00-175">Customize JSON names and values</span></span>

<span data-ttu-id="d0c00-176">Standardmäßig sind Eigenschaftsnamen und Wörterbuch Schlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="d0c00-176">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="d0c00-177">Enumerationswerte werden als Zahlen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-177">Enum values are represented as numbers.</span></span> <span data-ttu-id="d0c00-178">In diesem Abschnitt wird Folgendes erläutert:</span><span class="sxs-lookup"><span data-stu-id="d0c00-178">This section explains how to:</span></span>

* <span data-ttu-id="d0c00-179">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="d0c00-179">Customize individual property names</span></span>
* <span data-ttu-id="d0c00-180">Alle Eigenschaftsnamen in Camel-Case konvertieren</span><span class="sxs-lookup"><span data-stu-id="d0c00-180">Convert all property names to camel case</span></span>
* <span data-ttu-id="d0c00-181">Implementieren einer benutzerdefinierten Benennungs Richtlinie für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0c00-181">Implement a custom property naming policy</span></span>
* <span data-ttu-id="d0c00-182">Wörterbuch Schlüssel in Kamel-Schreibweise konvertieren</span><span class="sxs-lookup"><span data-stu-id="d0c00-182">Convert dictionary keys to camel case</span></span>
* <span data-ttu-id="d0c00-183">Enumerationszeichen in Zeichen folgen und Camel-Case konvertieren</span><span class="sxs-lookup"><span data-stu-id="d0c00-183">Convert enums to strings and camel case</span></span> 

<span data-ttu-id="d0c00-184">Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und-Werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="d0c00-184">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="d0c00-185">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="d0c00-185">Customize individual property names</span></span>

<span data-ttu-id="d0c00-186">Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das [[jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) -Attribut.</span><span class="sxs-lookup"><span data-stu-id="d0c00-186">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="d0c00-187">Hier ist ein Beispiel für die Serialisierung und die daraus resultierende JSON-Datei:</span><span class="sxs-lookup"><span data-stu-id="d0c00-187">Here's an example type to serialize and resulting JSON:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="d0c00-188">Der durch dieses Attribut festgelegte Eigenschaftsname:</span><span class="sxs-lookup"><span data-stu-id="d0c00-188">The property name set by this attribute:</span></span>

* <span data-ttu-id="d0c00-189">Gilt für die Serialisierung und Deserialisierung in beide Richtungen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-189">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="d0c00-190">Hat Vorrang vor Eigenschafts Benennungs Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="d0c00-190">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="d0c00-191">Bei allen JSON-Eigenschaftsnamen die Kamel-Schreibweise verwenden</span><span class="sxs-lookup"><span data-stu-id="d0c00-191">Use camel case for all JSON property names</span></span>

<span data-ttu-id="d0c00-192">Wenn Sie die Kamel-Schreibweise für alle JSON-Eigenschaftsnamen verwenden möchten, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-192">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="d0c00-193">Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d0c00-193">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureCelsius { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="d0c00-194">Die Benennungs Richtlinie für die Camel-Case-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="d0c00-194">The camel case property naming policy:</span></span>

* <span data-ttu-id="d0c00-195">Gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="d0c00-195">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="d0c00-196">Wird von `[JsonPropertyName]` Attributen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="d0c00-196">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="d0c00-197">Aus diesem Grund ist der Name der JSON-Eigenschaft `Wind` im Beispiel nicht Camel Case.</span><span class="sxs-lookup"><span data-stu-id="d0c00-197">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="d0c00-198">Verwenden einer benutzerdefinierten JSON-Eigenschafts Benennungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d0c00-198">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="d0c00-199">Um eine benutzerdefinierte JSON-Benennungs Richtlinie zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und überschreiben Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-199">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="d0c00-200">Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihrer Benennungs Richtlinien Klasse fest:</span><span class="sxs-lookup"><span data-stu-id="d0c00-200">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="d0c00-201">Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d0c00-201">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATUREC": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="d0c00-202">Die Benennungs Richtlinie für die JSON-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="d0c00-202">The JSON property naming policy:</span></span>

* <span data-ttu-id="d0c00-203">Gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="d0c00-203">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="d0c00-204">Wird von `[JsonPropertyName]` Attributen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="d0c00-204">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="d0c00-205">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="d0c00-205">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="d0c00-206">Camel-Case-Wörterbuch Schlüssel</span><span class="sxs-lookup"><span data-stu-id="d0c00-206">Camel case dictionary keys</span></span>

<span data-ttu-id="d0c00-207">Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>`ist, können die `string` Schlüssel in die Kamel-Schreibweise konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-207">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="d0c00-208">Legen Sie zu diesem Zweck <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-208">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="d0c00-209">Das Serialisieren eines Objekts mit einem Wörterbuch mit dem Namen `TemperatureRanges`, das Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` hat, führt zu einer JSON-Ausgabe wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d0c00-209">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="d0c00-210">Die Camel-Case-Benennungs Richtlinie für Wörterbuch Schlüssel gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="d0c00-210">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="d0c00-211">Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei, auch wenn Sie `JsonNamingPolicy.CamelCase` für die `DictionaryKeyPolicy`angeben.</span><span class="sxs-lookup"><span data-stu-id="d0c00-211">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="d0c00-212">Enumerationszeichen als Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="d0c00-212">Enums as strings</span></span>

<span data-ttu-id="d0c00-213">Standardmäßig werden Enumerationen als Zahlen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="d0c00-213">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="d0c00-214">Verwenden Sie die <xref:System.Text.Json.Serialization.JsonStringEnumConverter>, um Enumerationsnamen als Zeichen folgen zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="d0c00-214">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="d0c00-215">Nehmen Sie beispielsweise an, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-215">For example, suppose you need to serialize the following class that has an enum:</span></span>

```csharp
class WeatherForecastWithEnum
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public Summary Summary { get; set; }
}

public enum Summary
{
    Cold, Cool, Warm, Hot
}
```

<span data-ttu-id="d0c00-216">Wenn die Zusammenfassung `Hot`ist, hat die serialisierte JSON standardmäßig den numerischen Wert 3:</span><span class="sxs-lookup"><span data-stu-id="d0c00-216">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": 3
}
```

<span data-ttu-id="d0c00-217">Der folgende Beispielcode serialisiert stattdessen die Enumeration-Namen und konvertiert sie in die Groß-/Kleinschreibung:</span><span class="sxs-lookup"><span data-stu-id="d0c00-217">The following sample code serializes the enum names instead, and converts them to camel case:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
jsonWithEnumsAsStrings = JsonSerializer.Serialize(weatherForecastWithEnum, options);
```

<span data-ttu-id="d0c00-218">Der resultierende JSON-Code sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="d0c00-218">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="d0c00-219">Die Unterstützung von enumerationszeichen als Zeichen folgen gilt auch für die Deserialisierung, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-219">The support for enums as strings applies to deserialization also, as shown in the following example:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
weatherForecastWithEnum = JsonSerializer.Deserialize<WeatherForecastWithEnum>(jsonWithEnumsAsStrings, options);
```

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="d0c00-220">Ausschließen von Eigenschaften von der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d0c00-220">Exclude properties from serialization</span></span>

<span data-ttu-id="d0c00-221">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="d0c00-221">By default, all public properties are serialized.</span></span> <span data-ttu-id="d0c00-222">Wenn Sie nicht möchten, dass einige von Ihnen in der JSON-Ausgabe angezeigt werden, haben Sie mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="d0c00-222">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="d0c00-223">In diesem Abschnitt wird erläutert, wie Folgendes ausgeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="d0c00-223">This section explains how to exclude:</span></span>

* <span data-ttu-id="d0c00-224">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0c00-224">Individual properties</span></span>
* <span data-ttu-id="d0c00-225">Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0c00-225">All read-only properties</span></span>
* <span data-ttu-id="d0c00-226">Alle NULL-Wert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0c00-226">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="d0c00-227">Einzelne Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="d0c00-227">Exclude individual properties</span></span>

<span data-ttu-id="d0c00-228">Verwenden Sie das Attribut [[jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) , um einzelne Eigenschaften zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="d0c00-228">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="d0c00-229">Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d0c00-229">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonIgnore]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="d0c00-230">Alle schreibgeschützten Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="d0c00-230">Exclude all read-only properties</span></span>

<span data-ttu-id="d0c00-231">Eine Eigenschaft ist schreibgeschützt, wenn Sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.</span><span class="sxs-lookup"><span data-stu-id="d0c00-231">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="d0c00-232">Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-232">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="d0c00-233">Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d0c00-233">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public int WindSpeed { get; private set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="d0c00-234">Diese Option gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="d0c00-234">This option applies only to serialization.</span></span> <span data-ttu-id="d0c00-235">Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d0c00-235">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="d0c00-236">Alle NULL-Wert Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="d0c00-236">Exclude all null value properties</span></span>

<span data-ttu-id="d0c00-237">Um alle NULL-Wert Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-237">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="d0c00-238">Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d0c00-238">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="d0c00-239">property</span><span class="sxs-lookup"><span data-stu-id="d0c00-239">Property</span></span> |<span data-ttu-id="d0c00-240">Wert</span><span class="sxs-lookup"><span data-stu-id="d0c00-240">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="d0c00-241">Datum</span><span class="sxs-lookup"><span data-stu-id="d0c00-241">Date</span></span>    | <span data-ttu-id="d0c00-242">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="d0c00-242">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="d0c00-243">Temperatur</span><span class="sxs-lookup"><span data-stu-id="d0c00-243">TemperatureC</span></span>| <span data-ttu-id="d0c00-244">25</span><span class="sxs-lookup"><span data-stu-id="d0c00-244">25</span></span> |
| <span data-ttu-id="d0c00-245">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d0c00-245">Summary</span></span>| <span data-ttu-id="d0c00-246">NULL</span><span class="sxs-lookup"><span data-stu-id="d0c00-246">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="d0c00-247">Diese Einstellung gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="d0c00-247">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="d0c00-248">Informationen zu den Auswirkungen auf die Deserialisierung finden Sie unter [Ignorieren von NULL beim Deserialisieren](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="d0c00-248">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="d0c00-249">Zeichencodierung anpassen</span><span class="sxs-lookup"><span data-stu-id="d0c00-249">Customize character encoding</span></span>

<span data-ttu-id="d0c00-250">Standardmäßig schützt das Serialisierungsprogramm alle nicht-ASCII-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-250">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="d0c00-251">Das heißt, Sie ersetzt Sie durch `\uxxxx`, wobei `xxxxx` der Unicode-Code des Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="d0c00-251">That is, it replaces them with `\uxxxx` where `xxxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="d0c00-252">Wenn die `Summary`-Eigenschaft z. b. auf Cyrillic-"-Eigenschaft" festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="d0c00-252">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="d0c00-253">Serialisieren von sprach Zeichensätzen</span><span class="sxs-lookup"><span data-stu-id="d0c00-253">Serialize language character sets</span></span>

<span data-ttu-id="d0c00-254">Zum Serialisieren der Zeichensätze von mindestens einer Sprache geben Sie [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) beim Erstellen einer Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>an, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-254">To serialize the character set(s) of one or more languages, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(UnicodeRanges.Cyrillic, UnicodeRanges.GreekExtended)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="d0c00-255">Dieser Code serialisiert kyrillische und griechische Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-255">This code serializes Cyrillic and Greek characters.</span></span> <span data-ttu-id="d0c00-256">Kyrillische Zeichen werden im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-256">Cyrillic characters are shown in the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жарко",
}
```

<span data-ttu-id="d0c00-257">Um alle Sprachen anzugeben, verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d0c00-257">To specify all languages, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="d0c00-258">Serialisieren bestimmter Zeichen</span><span class="sxs-lookup"><span data-stu-id="d0c00-258">Serialize specific characters</span></span>

<span data-ttu-id="d0c00-259">Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne mit Escapezeichen versehen zu werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-259">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="d0c00-260">Im folgenden Beispiel werden nur die ersten zwei Zeichen von "..." serialisiert:</span><span class="sxs-lookup"><span data-stu-id="d0c00-260">The following example serializes only the first two characters of жарко:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var encoderSettings = new TextEncoderSettings();
encoderSettings.AllowCharacters('\u0436', '\u0430');
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(encoderSettings)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="d0c00-261">Im folgenden finden Sie ein Beispiel für JSON, das durch den vorangehenden Code generiert wird:</span><span class="sxs-lookup"><span data-stu-id="d0c00-261">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="d0c00-262">Alle Zeichen serialisieren</span><span class="sxs-lookup"><span data-stu-id="d0c00-262">Serialize all characters</span></span>

<span data-ttu-id="d0c00-263">Um das Escapezeichen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-263">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
```

```csharp
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.UnsafeRelaxedJsonEscaping
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

> [!CAUTION]
> <span data-ttu-id="d0c00-264">Im Gegensatz zum Standard-Encoder ist der `UnsafeRelaxedJsonEscaping` Encoder:</span><span class="sxs-lookup"><span data-stu-id="d0c00-264">Unlike the default encoder, the `UnsafeRelaxedJsonEscaping` encoder:</span></span>
>
> * <span data-ttu-id="d0c00-265">Führt keine Escapezeichen für HTML-sensible Zeichen wie `<`, `>`, `&`und `'`aus.</span><span class="sxs-lookup"><span data-stu-id="d0c00-265">Doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="d0c00-266">Bietet keinen zusätzlichen Schutz im umfassenden Schutz gegen XSS-oder Informations Offenlegungs Angriffe, wie z. b. solche, die sich aus dem Client und dem Server ergeben könnten, die auf dem *CharSet*nicht einverstanden sind.</span><span class="sxs-lookup"><span data-stu-id="d0c00-266">Doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
> * <span data-ttu-id="d0c00-267">Ist besser als der Standard Encoder, für den Zeichen ohne Escapezeichen übergeben werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-267">Is more permissive than the default encoder on which characters are allowed to pass through unescaped.</span></span>
>
> <span data-ttu-id="d0c00-268">Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d0c00-268">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="d0c00-269">Sie können Sie beispielsweise verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8`sendet.</span><span class="sxs-lookup"><span data-stu-id="d0c00-269">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="d0c00-270">Gestatten Sie niemals, dass die Roh`UnsafeRelaxedJsonEscaping` Ausgabe in eine HTML-Seite oder ein `<script>` Element ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d0c00-270">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="d0c00-271">Serialisieren von Eigenschaften abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="d0c00-271">Serialize properties of derived classes</span></span>

<span data-ttu-id="d0c00-272">Die polymorphe Serialisierung wird nicht unterstützt, wenn Sie zum Zeitpunkt der Kompilierung angeben, welcher Typ serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0c00-272">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="d0c00-273">Nehmen Sie beispielsweise an, Sie verfügen über eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastWithWind`:</span><span class="sxs-lookup"><span data-stu-id="d0c00-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
class WeatherForecastWithWind : WeatherForecast
{
    public int WindSpeed { get; set; }
}
```

<span data-ttu-id="d0c00-274">Angenommen, das Typargument der `Serialize` Methode zum Zeitpunkt der Kompilierung ist `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="d0c00-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="d0c00-275">In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastWithWind`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="d0c00-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="d0c00-276">Es werden nur die Basisklassen Eigenschaften serialisiert:</span><span class="sxs-lookup"><span data-stu-id="d0c00-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="d0c00-277">Dieses Verhalten soll das versehentliche verfügbar machen von Daten in einem abgeleiteten, von der Laufzeit erstellten Typ verhindern.</span><span class="sxs-lookup"><span data-stu-id="d0c00-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="d0c00-278">Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs zu serialisieren:</span><span class="sxs-lookup"><span data-stu-id="d0c00-278">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="d0c00-279">Aufrufen einer Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A>, mit der Sie den Typ zur Laufzeit angeben können:</span><span class="sxs-lookup"><span data-stu-id="d0c00-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="d0c00-280">Deklarieren Sie das Objekt, das als `object`serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0c00-280">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="d0c00-281">Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in der JSON-Ausgabe enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="d0c00-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="d0c00-282">Weitere Informationen zur polymorphen Deserialisierung finden Sie [unter Unterstützung der polymorphen Deserialisierung](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="d0c00-282">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="d0c00-283">Kommentare und nachfolgende Kommas zulassen</span><span class="sxs-lookup"><span data-stu-id="d0c00-283">Allow comments and trailing commas</span></span>

<span data-ttu-id="d0c00-284">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="d0c00-284">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="d0c00-285">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip`fest.</span><span class="sxs-lookup"><span data-stu-id="d0c00-285">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="d0c00-286">Um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="d0c00-286">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="d0c00-287">Im folgenden Beispiel wird gezeigt, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="d0c00-287">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="d0c00-288">Im folgenden finden Sie ein Beispiel für JSON mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="d0c00-288">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="d0c00-289">Nichtbeachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="d0c00-289">Case-insensitive property matching</span></span>

<span data-ttu-id="d0c00-290">Standardmäßig wird bei der Deserialisierung nach Groß-/Kleinschreibung unterschieden, dass Eigenschaften Namen Übereinstimmungen zwischen JSON und den Zielobjekt Eigenschaften aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-290">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="d0c00-291">Um dieses Verhalten zu ändern, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true`fest:</span><span class="sxs-lookup"><span data-stu-id="d0c00-291">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="d0c00-292">Im folgenden finden Sie eine Beispiel-JSON-Datei mit den Namen der Kamel</span><span class="sxs-lookup"><span data-stu-id="d0c00-292">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="d0c00-293">Sie kann in den folgenden Typ deserialisiert werden, der über die Namen der Pascal-Großbuchstaben verfügt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-293">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
}
```

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="d0c00-294">Handle für Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="d0c00-294">Handle overflow JSON</span></span>

<span data-ttu-id="d0c00-295">Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, der nicht durch Eigenschaften des Zieltyps dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d0c00-295">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="d0c00-296">Angenommen, Ihr Zieltyp lautet:</span><span class="sxs-lookup"><span data-stu-id="d0c00-296">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="d0c00-297">Der JSON-Code, der deserialisiert werden soll, lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-297">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
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

<span data-ttu-id="d0c00-298">Wenn Sie den JSON-Code deserialisieren, der in den angezeigten Typ angezeigt wird, sind die Eigenschaften `DatesAvailable` und `SummaryWords` nicht mehr vorhanden und gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="d0c00-298">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="d0c00-299">Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) -Attribut auf eine Eigenschaft vom Typ `Dictionary<string,object>` oder `Dictionary<string,JsonElement>`an:</span><span class="sxs-lookup"><span data-stu-id="d0c00-299">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonExtensionData]
    public Dictionary<string, object> ExtensionData { get; set; }
}
```

<span data-ttu-id="d0c00-300">Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="d0c00-300">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="d0c00-301">property</span><span class="sxs-lookup"><span data-stu-id="d0c00-301">Property</span></span> |<span data-ttu-id="d0c00-302">Wert</span><span class="sxs-lookup"><span data-stu-id="d0c00-302">Value</span></span>  |<span data-ttu-id="d0c00-303">Notizen</span><span class="sxs-lookup"><span data-stu-id="d0c00-303">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="d0c00-304">Datum</span><span class="sxs-lookup"><span data-stu-id="d0c00-304">Date</span></span>    | <span data-ttu-id="d0c00-305">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="d0c00-305">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="d0c00-306">Temperatur</span><span class="sxs-lookup"><span data-stu-id="d0c00-306">TemperatureC</span></span>| <span data-ttu-id="d0c00-307">0</span><span class="sxs-lookup"><span data-stu-id="d0c00-307">0</span></span> | <span data-ttu-id="d0c00-308">Unterscheidung nach Groß-/Kleinschreibung (`temperatureC` im JSON-Code), sodass die-Eigenschaft nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d0c00-308">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="d0c00-309">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d0c00-309">Summary</span></span> | <span data-ttu-id="d0c00-310">Luft</span><span class="sxs-lookup"><span data-stu-id="d0c00-310">Hot</span></span> ||
| <span data-ttu-id="d0c00-311">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="d0c00-311">ExtensionData</span></span> | <span data-ttu-id="d0c00-312">Temperatur: 25</span><span class="sxs-lookup"><span data-stu-id="d0c00-312">temperatureC: 25</span></span> |<span data-ttu-id="d0c00-313">Da die Groß-/Kleinschreibung nicht entsprach, ist diese JSON-Eigenschaft ein zusätzliches und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="d0c00-313">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="d0c00-314">Datesavailable:</span><span class="sxs-lookup"><span data-stu-id="d0c00-314">DatesAvailable:</span></span><br>  <span data-ttu-id="d0c00-315">8/1/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="d0c00-315">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="d0c00-316">8/2/2019 12:00:00 Uhr-07:00</span><span class="sxs-lookup"><span data-stu-id="d0c00-316">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="d0c00-317">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="d0c00-317">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="d0c00-318">Summarywords:</span><span class="sxs-lookup"><span data-stu-id="d0c00-318">SummaryWords:</span></span><br><span data-ttu-id="d0c00-319">Toll</span><span class="sxs-lookup"><span data-stu-id="d0c00-319">Cool</span></span><br><span data-ttu-id="d0c00-320">Digen</span><span class="sxs-lookup"><span data-stu-id="d0c00-320">Windy</span></span><br><span data-ttu-id="d0c00-321">Feu</span><span class="sxs-lookup"><span data-stu-id="d0c00-321">Humid</span></span> |<span data-ttu-id="d0c00-322">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="d0c00-322">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="d0c00-323">Wenn das Zielobjekt serialisiert wird, werden die Erweiterungs-Datenschlüssel Wert-Paare zu JSON-Eigenschaften, genauso wie Sie im eingehenden JSON-Code waren:</span><span class="sxs-lookup"><span data-stu-id="d0c00-323">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 0,
  "Summary": "Hot",
  "temperatureC": 25,
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

<span data-ttu-id="d0c00-324">Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d0c00-324">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="d0c00-325">Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-325">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="d0c00-326">NULL beim Deserialisieren ignorieren</span><span class="sxs-lookup"><span data-stu-id="d0c00-326">Ignore null when deserializing</span></span>

<span data-ttu-id="d0c00-327">Wenn eine Eigenschaft in JSON NULL ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-327">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="d0c00-328">In einigen Szenarios hat die Ziel Eigenschaft möglicherweise einen Standardwert, und Sie möchten nicht, dass ein NULL-Wert den Standardwert überschreibt.</span><span class="sxs-lookup"><span data-stu-id="d0c00-328">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="d0c00-329">Nehmen Sie beispielsweise an, der folgende Code stellt das Zielobjekt dar:</span><span class="sxs-lookup"><span data-stu-id="d0c00-329">For example, suppose the following code represents your target object:</span></span>

```csharp
class WeatherForecastWithDefault
{
    public WeatherForecastWithDefault()
    {
        Summary = "No summary";
    }
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="d0c00-330">Angenommen, der folgende JSON-Code wird deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="d0c00-330">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": null,
}
```

<span data-ttu-id="d0c00-331">Nach der Deserialisierung ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts NULL.</span><span class="sxs-lookup"><span data-stu-id="d0c00-331">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="d0c00-332">Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0c00-332">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithDefault>(json, options);
```

<span data-ttu-id="d0c00-333">Bei dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault` Objekts der Standardwert "keine Zusammenfassung" nach der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="d0c00-333">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="d0c00-334">NULL-Werte in JSON werden nur ignoriert, wenn Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="d0c00-334">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="d0c00-335">NULL-Werte für Werttypen, die keine NULL-Werte zulassen, verursachen Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-335">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="d0c00-336">Weitere Informationen finden Sie im Repository dotnet/corefx auf GitHub unter dem [Problem für Werttypen, die keine NULL-Werte](https://github.com/dotnet/corefx/issues/40922) zulassen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-336">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="d0c00-337">Utf8JsonReader, Utf8JsonWriter und jsondocument</span><span class="sxs-lookup"><span data-stu-id="d0c00-337">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="d0c00-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, reiner Vorwärtsleser mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="d0c00-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="d0c00-339">Der `Utf8JsonReader` ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Parser und deserialisierern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d0c00-339">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="d0c00-340">Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` unter dem Cover.</span><span class="sxs-lookup"><span data-stu-id="d0c00-340">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="d0c00-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ist eine hochleistungsfähige Methode zum Schreiben von UTF-8-codiertem JSON-Text aus gängigen .NET-Typen wie `String`, `Int32`und `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="d0c00-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="d0c00-342">Der Writer ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Serialisierern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d0c00-342">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="d0c00-343">Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` unter dem Cover.</span><span class="sxs-lookup"><span data-stu-id="d0c00-343">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="d0c00-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mit `Utf8JsonReader`ein Schreib geschütztes Dokumentobjektmodell (DOM) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="d0c00-345">Das Dom bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="d0c00-345">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="d0c00-346">Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den <xref:System.Text.Json.JsonElement> Typ zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-346">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="d0c00-347">Der `JsonElement` stellt Array-und Objekt Enumeratoren zusammen mit APIs bereit, um JSON-Text in allgemeine .NET-Typen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d0c00-347">The `JsonElement` provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="d0c00-348">`JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d0c00-348">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="d0c00-349">In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-349">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="d0c00-350">Verwenden von jsondocument für den Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="d0c00-350">Use JsonDocument for access to data</span></span>

<span data-ttu-id="d0c00-351">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="d0c00-351">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data:</span></span>

```csharp
double sum = 0;
int count = 0;

using (JsonDocument document = JsonDocument.Parse(jsonString))
{
    JsonElement root = document.RootElement;
    JsonElement studentsElement = root.GetProperty("Students");
    foreach (JsonElement student in studentsElement.EnumerateArray())
    {
        if (student.TryGetProperty("Grade", out JsonElement gradeElement))
        {
            sum += gradeElement.GetDouble();
        }
        else
        {
            sum += 70;
        }
        count++;
    }
}

double average = sum / count;
Console.WriteLine($"Average grade: {average}");
```

<span data-ttu-id="d0c00-352">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="d0c00-352">The preceding code:</span></span>

* <span data-ttu-id="d0c00-353">Geht davon aus, dass der zu analysierende JSON-Code eine Zeichenfolge namens `jsonString`</span><span class="sxs-lookup"><span data-stu-id="d0c00-353">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="d0c00-354">Berechnet eine durchschnittliche Qualität für Objekte in einem `Students` Array mit einer `Grade`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d0c00-354">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="d0c00-355">Weist einen Standardwert von 70 für Studenten zu, die nicht über eine Qualität verfügen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-355">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="d0c00-356">Zählt Schüler und Studenten durch Inkrementieren einer `count` Variablen bei jeder Iterationen.</span><span class="sxs-lookup"><span data-stu-id="d0c00-356">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="d0c00-357">Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A>aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="d0c00-357">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span></span>

  ```csharp
  count = studentsElement.GetArrayLength();
  ```

<span data-ttu-id="d0c00-358">Im folgenden finden Sie ein Beispiel für die JSON, die von diesem Code verarbeitet wird:</span><span class="sxs-lookup"><span data-stu-id="d0c00-358">Here's an example of the JSON that this code processes:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher's Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="d0c00-359">Verwenden von jsondocument zum Schreiben von JSON</span><span class="sxs-lookup"><span data-stu-id="d0c00-359">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="d0c00-360">Im folgenden Beispiel wird gezeigt, wie JSON aus einem <xref:System.Text.Json.JsonDocument>geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="d0c00-360">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);

var writerOptions = new JsonWriterOptions { Indented = true };
var documentOptions = new JsonDocumentOptions { CommentHandling = JsonCommentHandling.Skip };

using (FileStream fs = File.Create(outputFileName))
using (var writer = new Utf8JsonWriter(fs, options: writerOptions))
using (JsonDocument document = JsonDocument.Parse(jsonString, documentOptions))
{
    JsonElement root = document.RootElement;

    if (root.ValueKind == JsonValueKind.Object)
    {
        writer.WriteStartObject();
    }
    else
    {
        return;
    }

    foreach (JsonProperty property in root.EnumerateObject())
    {
        property.WriteTo(writer);
    }

    writer.WriteEndObject();

    writer.Flush();
}
```

<span data-ttu-id="d0c00-361">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="d0c00-361">The preceding code:</span></span>

* <span data-ttu-id="d0c00-362">Liest eine JSON-Datei, lädt die Daten in eine `JsonDocument`und schreibt formatierte (hübsch gedruckte) JSON-Daten in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="d0c00-362">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="d0c00-363">Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-363">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="d0c00-364">Wenn Sie fertig sind, ruft <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf.</span><span class="sxs-lookup"><span data-stu-id="d0c00-364">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="d0c00-365">Eine Alternative besteht darin, den Writer automatisch zu leeren, wenn er verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="d0c00-365">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="d0c00-366">Im folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die durch den Beispielcode verarbeitet werden soll:</span><span class="sxs-lookup"><span data-stu-id="d0c00-366">Here's an example of JSON input to be processed by the example code:</span></span>

```json
{"Class Name": "Science","Teacher's Name": "Jane","Semester": "2019-01-01","Students": [{"Name": "John","Grade": 94.3},{"Name": "James","Grade": 81.0},{"Name": "Julia","Grade": 91.9},{"Name": "Jessica","Grade": 72.4},{"Name": "Johnathan"}],"Final": true}
```

<span data-ttu-id="d0c00-367">Das Ergebnis ist die folgende ziemlich gedruckte JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d0c00-367">The result is the following pretty-printed JSON output:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher\u0027s Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="d0c00-368">Utf8JsonWriter verwenden</span><span class="sxs-lookup"><span data-stu-id="d0c00-368">Use Utf8JsonWriter</span></span>

<span data-ttu-id="d0c00-369">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonWriter>-Klasse verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="d0c00-369">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

```csharp
var options = new JsonWriterOptions
{
    Indented = true
};

using (var stream = new MemoryStream())
{
    using (var writer = new Utf8JsonWriter(stream, options))
    {
        writer.WriteStartObject();
        writer.WriteString("date", DateTimeOffset.UtcNow);
        writer.WriteNumber("temp", 42);
        writer.WriteEndObject();
    }

    string json = Encoding.UTF8.GetString(stream.ToArray());
    Console.WriteLine(json);
}
```

## <a name="use-utf8jsonreader"></a><span data-ttu-id="d0c00-370">Utf8JsonReader verwenden</span><span class="sxs-lookup"><span data-stu-id="d0c00-370">Use Utf8JsonReader</span></span>

<span data-ttu-id="d0c00-371">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonReader>-Klasse verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="d0c00-371">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

```csharp
var options = new JsonReaderOptions
{
    AllowTrailingCommas = true,
    CommentHandling = JsonCommentHandling.Skip
};
Utf8JsonReader reader = new Utf8JsonReader(jsonUtf8, options);

while (reader.Read())
{
    Console.Write(reader.TokenType);

    switch (reader.TokenType)
    {
        case JsonTokenType.PropertyName:
        case JsonTokenType.String:
            {
                string text = reader.GetString();
                Console.Write(" ");
                Console.Write(text);
                break;
            }

        case JsonTokenType.Number:
            {
                int value = reader.GetInt32();
                Console.Write(" ");
                Console.Write(value);
                break;
            }

            // Other token types elided for brevity
    }

    Console.WriteLine();
}
```

<span data-ttu-id="d0c00-372">Der vorangehende Code geht davon aus, dass es sich bei der `jsonUtf8` Variable um ein Bytearray handelt, das gültige JSON-Codierung als UTF-8 enthält</span><span class="sxs-lookup"><span data-stu-id="d0c00-372">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="d0c00-373">Filtern von Daten mithilfe von Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="d0c00-373">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="d0c00-374">Im folgenden Beispiel wird gezeigt, wie eine Datei synchron gelesen und nach einem Wert gesucht wird:</span><span class="sxs-lookup"><span data-stu-id="d0c00-374">The following example shows how to read a file synchronously and search for a value:</span></span>

```csharp
class Program
{
    private static readonly byte[] s_nameUtf8 = Encoding.UTF8.GetBytes("name");
    private static readonly byte[] s_universityUtf8 = Encoding.UTF8.GetBytes("University");

    private static void ReaderFromFileSync(string fileName)
    {
         string jsonString = File.ReadAllText(fileName);
         ReadOnlySpan<byte> jsonReadOnlySpan = Encoding.UTF8.GetBytes(jsonString);

        int count = 0;
        int total = 0;

        var json = new Utf8JsonReader(jsonReadOnlySpan, isFinalBlock: true, state: default);

        while (json.Read())
        {
            JsonTokenType tokenType = json.TokenType;

            switch (tokenType)
            {
                case JsonTokenType.StartObject:
                    total++;
                    break;
                case JsonTokenType.PropertyName:
                    if (json.ValueSpan.SequenceEqual(s_nameUtf8))
                    {
                        bool result = json.Read();

                        Debug.Assert(result);  // Assume valid JSON
                        Debug.Assert(json.TokenType == JsonTokenType.String);   // Assume known, valid JSON schema

                        if (json.ValueSpan.EndsWith(s_universityUtf8))
                        {
                            count++;
                        }
                    }
                    break;
            }
        }
        Console.WriteLine($"{count} out of {total} have names that end with 'University'");
    }
}
```

<span data-ttu-id="d0c00-375">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="d0c00-375">The preceding code:</span></span>

* <span data-ttu-id="d0c00-376">Geht davon aus, dass die Datei als UTF-16 codiert ist, und transcodiert Sie in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d0c00-376">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="d0c00-377">Eine Datei, die als UTF-8 codiert ist, kann mithilfe des folgenden Codes direkt in eine `ReadOnlySpan<byte>`gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="d0c00-377">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="d0c00-378">Geht davon aus, dass der JSON-Code ein Array von Objekten enthält und jedes Objekt eine "Name"-Eigenschaft vom Typ "String" enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="d0c00-378">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="d0c00-379">Zählt Objekte und `name` Eigenschaftswerte, die mit "University" enden.</span><span class="sxs-lookup"><span data-stu-id="d0c00-379">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="d0c00-380">Im folgenden finden Sie ein JSON-Beispiel, das der vorherige Code lesen kann.</span><span class="sxs-lookup"><span data-stu-id="d0c00-380">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="d0c00-381">Die resultierende Zusammenfassungs Meldung lautet: "2 von 4 haben Namen, die mit" University "enden:</span><span class="sxs-lookup"><span data-stu-id="d0c00-381">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

```json
[
  {
    "web_pages": [ "https://contoso.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contoso.edu" ],
    "name": "Contoso Community College"
  },
  {
    "web_pages": [ "http://fabrikam.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikam.edu" ],
    "name": "Fabrikam Community College"
  },
  {
    "web_pages": [ "http://www.contosouniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contosouniversity.edu" ],
    "name": "Contoso University"
  },
  {
    "web_pages": [ "http://www.fabrikamuniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikamuniversity.edu" ],
    "name": "Fabrikam University"
  }
]
```

## <a name="additional-resources"></a><span data-ttu-id="d0c00-382">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d0c00-382">Additional resources</span></span>

* [<span data-ttu-id="d0c00-383">Übersicht über System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="d0c00-383">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="d0c00-384">System. Text. JSON-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="d0c00-384">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="d0c00-385">Schreiben von benutzerdefinierten Konvertern für "System. Text. JSON"</span><span class="sxs-lookup"><span data-stu-id="d0c00-385">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="d0c00-386">DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="d0c00-386">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
