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
ms.openlocfilehash: 3c988a0151f57b67db19f41aeb88c6fb9b808cb3
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179200"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="eee1d-102">Serialisieren und Deserialisieren von JSON in .net</span><span class="sxs-lookup"><span data-stu-id="eee1d-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eee1d-103">Die JSON-serialisierungsdokumentation befindet sich in der Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="eee1d-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="eee1d-104">In diesem Artikel werden nicht alle Szenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="eee1d-105">Weitere Informationen finden Sie unter " [System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) "-Probleme im dotnet/corefx-Repository auf GitHub, insbesondere die mit der Bezeichnung " [JSON-funktionsdoc](https://github.com/dotnet/corefx/labels/json-functionality-doc)".</span><span class="sxs-lookup"><span data-stu-id="eee1d-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="eee1d-106">In diesem Artikel wird gezeigt, wie Sie den <xref:System.Text.Json>-Namespace zum Serialisieren und Deserialisieren in und aus JavaScript Object Notation (JSON) verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee1d-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="eee1d-107">Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework, wie z. b. [ASP.net Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="eee1d-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="eee1d-108">Namespaces</span><span class="sxs-lookup"><span data-stu-id="eee1d-108">Namespaces</span></span>

<span data-ttu-id="eee1d-109">Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="eee1d-110">Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="eee1d-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="eee1d-111">Die in diesem Artikel gezeigten Codebeispiele erfordern daher mindestens eine der folgenden `using`-Direktiven:</span><span class="sxs-lookup"><span data-stu-id="eee1d-111">Therefore, the code examples shown in this article require one or both of the following `using` directives:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="eee1d-112">Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden derzeit in `System.Text.Json` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="eee1d-113">Schreiben von .NET-Objekten in JSON (Serialisieren)</span><span class="sxs-lookup"><span data-stu-id="eee1d-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="eee1d-114">Um JSON in eine Zeichenfolge zu schreiben, nennen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="eee1d-114">To write JSON to a string, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="eee1d-115">Im folgenden Beispiel wird eine-Überladung mit einem generischen Typparameter verwendet:</span><span class="sxs-lookup"><span data-stu-id="eee1d-115">The following example uses an overload with a generic type parameter:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="eee1d-116">Sie können den generischen Typparameter weglassen und stattdessen einen generischen Typrückschluss verwenden:</span><span class="sxs-lookup"><span data-stu-id="eee1d-116">You can omit the generic type parameter and use generic type inference instead:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="eee1d-117">Hier ist ein Beispieltyp, der serialisiert werden kann, der Auflistungen und Klassen enthält:</span><span class="sxs-lookup"><span data-stu-id="eee1d-117">Here's an example type to be serialized, which contains collections and nested classes:</span></span>

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

<span data-ttu-id="eee1d-118">Die JSON-Ausgabe wird standardmäßig minimiert:</span><span class="sxs-lookup"><span data-stu-id="eee1d-118">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="eee1d-119">Im folgenden Beispiel wird derselbe JSON-Code dargestellt, der formatiert ist (d. h. mit Leerraum und Einzug):</span><span class="sxs-lookup"><span data-stu-id="eee1d-119">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

<span data-ttu-id="eee1d-120">Über Ladungen von <xref:System.Text.Json.JsonSerializer.Serialize%2A> können Sie zu einer <xref:System.IO.Stream> serialisieren.</span><span class="sxs-lookup"><span data-stu-id="eee1d-120">Overloads of <xref:System.Text.Json.JsonSerializer.Serialize%2A> let you serialize to a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="eee1d-121">Async-Versionen der `Stream`-über Ladungen sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eee1d-121">Async versions of the `Stream` overloads are available.</span></span>

### <a name="serialize-to-utf-8"></a><span data-ttu-id="eee1d-122">In UTF-8 serialisieren</span><span class="sxs-lookup"><span data-stu-id="eee1d-122">Serialize to UTF-8</span></span>

<span data-ttu-id="eee1d-123">Um zu UTF-8 zu serialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="eee1d-123">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="eee1d-124">Als Alternative steht eine <xref:System.Text.Json.JsonSerializer.Serialize%2A>-Überladung, die eine <xref:System.Text.Json.Utf8JsonWriter> annimmt, zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eee1d-124">As an alternative, a <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is available.</span></span>

<span data-ttu-id="eee1d-125">Die Serialisierung in UTF-8 ist ungefähr 5-10% schneller als die Verwendung der Zeichen folgen basierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="eee1d-125">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="eee1d-126">Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichen folgen (UTF-16) konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-126">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="eee1d-127">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="eee1d-127">Serialization behavior</span></span>

* <span data-ttu-id="eee1d-128">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="eee1d-128">By default, all public properties are serialized.</span></span> <span data-ttu-id="eee1d-129">Sie können [Eigenschaften angeben, die ausgeschlossen werden sollen](#exclude-properties).</span><span class="sxs-lookup"><span data-stu-id="eee1d-129">You can [specify properties to exclude](#exclude-properties).</span></span>
* <span data-ttu-id="eee1d-130">Der [standardcodierer](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) schützt nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die entsprechend [der JSON-Spezifikation](https://tools.ietf.org/html/rfc8259#section-7)mit Escapezeichen versehen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-130">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="eee1d-131">Standardmäßig wird JSON minimiert.</span><span class="sxs-lookup"><span data-stu-id="eee1d-131">By default, JSON is minified.</span></span> <span data-ttu-id="eee1d-132">Sie können [den JSON-Code ziemlich ausdrucken](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="eee1d-132">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="eee1d-133">Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen den .net-Namen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-133">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="eee1d-134">Sie können die [JSON-namens](#customize-json-names)Schreibweise anpassen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-134">You can [customize JSON name casing](#customize-json-names).</span></span>
* <span data-ttu-id="eee1d-135">Zirkuläre Verweise werden erkannt, und Ausnahmen werden ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="eee1d-135">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="eee1d-136">Weitere Informationen finden Sie unter dem [Problem für zirkuläre Verweise](https://github.com/dotnet/corefx/issues/38579) im dotnet/corefx-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="eee1d-136">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="eee1d-137">Derzeit werden Felder ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-137">Currently, fields are excluded.</span></span>

<span data-ttu-id="eee1d-138">Folgende Typen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-138">Supported types include:</span></span>

* <span data-ttu-id="eee1d-139">.Net-primitive, die JavaScript-primitiven zugeordnet sind, z. b. numerische Typen, Zeichen folgen und boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="eee1d-139">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="eee1d-140">Benutzerdefinierte [Plain Old CLR Objects (POCOS)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="eee1d-140">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="eee1d-141">Eindimensionales und verzweigte Arrays (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="eee1d-141">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="eee1d-142">`Dictionary<string,TValue>`, wobei `TValue` `object`, `JsonElement` oder ein poco ist.</span><span class="sxs-lookup"><span data-stu-id="eee1d-142">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="eee1d-143">Sammlungen aus den folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="eee1d-143">Collections from the following namespaces.</span></span> <span data-ttu-id="eee1d-144">Weitere Informationen finden Sie im [Thema zur Unterstützung von Sammlungen](https://github.com/dotnet/corefx/issues/36643) im dotnet/corefx-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="eee1d-144">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="eee1d-145">Lesen von JSON in .NET-Objekte (Deserialisieren)</span><span class="sxs-lookup"><span data-stu-id="eee1d-145">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="eee1d-146">Um eine Zeichenfolge zu deserialisieren, nennen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-146">To deserialize from a string, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method, as shown in the following example:</span></span>

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="eee1d-147">Ein Beispiel finden Sie im Abschnitt zum [serialisieren](#how-to-write-net-objects-to-json-serialize) .</span><span class="sxs-lookup"><span data-stu-id="eee1d-147">For an example, see the [serialize](#how-to-write-net-objects-to-json-serialize) section.</span></span> <span data-ttu-id="eee1d-148">Das JSON-und .NET-Objekt sind identisch, aber die Richtung ist umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-148">The JSON and .NET object are the same, but the direction is reversed.</span></span>

<span data-ttu-id="eee1d-149">Über Ladungen von <xref:System.Text.Json.JsonSerializer.Deserialize*> können von einem `Stream` deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="eee1d-149">Overloads of <xref:System.Text.Json.JsonSerializer.Deserialize*> let you deserialize from a `Stream`.</span></span>  <span data-ttu-id="eee1d-150">Async-Versionen der `Stream`-über Ladungen sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eee1d-150">Async versions of the `Stream` overloads are available.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="eee1d-151">Aus UTF-8 Deserialisieren</span><span class="sxs-lookup"><span data-stu-id="eee1d-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="eee1d-152">Um von UTF-8 zu deserialisieren, müssen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Überladung aufrufen, die eine `Utf8JsonReader` oder eine `ReadOnlySpan<byte>` annimmt, wie in den folgenden Beispielen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples:</span></span>

```csharp
byte[] utf8Json;
//...
var readOnlySpan = new ReadOnlySpan<byte>(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
byte[] utf8Json;
//...
var utf8Reader = new Utf8JsonReader(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="eee1d-153">Deserialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="eee1d-153">Deserialization behavior</span></span>

* <span data-ttu-id="eee1d-154">Standardmäßig wird die Groß-/Kleinschreibung bei der Übereinstimmung von Eigenschaften Namen</span><span class="sxs-lookup"><span data-stu-id="eee1d-154">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="eee1d-155">Sie können die [Groß-/Kleinschreibung](#case-insensitive-property-matching)nicht beachten.</span><span class="sxs-lookup"><span data-stu-id="eee1d-155">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="eee1d-156">Wenn der JSON-Wert einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="eee1d-156">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="eee1d-157">Die Deserialisierung für Verweis Typen ohne Parameter losen Konstruktor wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-157">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="eee1d-158">Die Deserialisierung zu unveränderlichen Objekten oder schreibgeschützten Eigenschaften wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-158">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="eee1d-159">Weitere Informationen finden Sie im GitHub- [Problem bei der Unterstützung für unveränderliche Objekte](https://github.com/dotnet/corefx/issues/38569) und im Repository "dotnet/corefx" auf GitHub Unterstützung für schreibgeschützte [Eigenschaften](https://github.com/dotnet/corefx/issues/38163) .</span><span class="sxs-lookup"><span data-stu-id="eee1d-159">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="eee1d-160">Standardmäßig werden Enumerationen als Zahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-160">By default, enums are supported as numbers.</span></span>
* <span data-ttu-id="eee1d-161">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-161">Fields aren't supported.</span></span>
* <span data-ttu-id="eee1d-162">Standardmäßig lösen Kommentare oder nachfolgende Kommas in der JSON-Datei Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="eee1d-162">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="eee1d-163">Sie können bei Bedarf [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas) .</span><span class="sxs-lookup"><span data-stu-id="eee1d-163">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas) if needed.</span></span>
* <span data-ttu-id="eee1d-164">Der Standardwert für die [Maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) ist 64.</span><span class="sxs-lookup"><span data-stu-id="eee1d-164">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="eee1d-165">Serialisieren in formatierten JSON-Code</span><span class="sxs-lookup"><span data-stu-id="eee1d-165">Serialize to formatted JSON</span></span>

<span data-ttu-id="eee1d-166">Um die JSON-Ausgabe zu Recht drucken, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="eee1d-166">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="eee1d-167">Hier ist ein Beispieltyp, der serialisiert werden soll, und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="eee1d-167">Here's an example type to be serialized and JSON output:</span></span>

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

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="eee1d-168">Kommentare und nachfolgende Kommas zulassen</span><span class="sxs-lookup"><span data-stu-id="eee1d-168">Allow comments and trailing commas</span></span>

<span data-ttu-id="eee1d-169">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="eee1d-169">By default comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="eee1d-170">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest.</span><span class="sxs-lookup"><span data-stu-id="eee1d-170">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="eee1d-171">Um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="eee1d-171">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="eee1d-172">Im folgenden Beispiel wird gezeigt, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="eee1d-172">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="eee1d-173">Im folgenden finden Sie ein Beispiel für JSON mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="eee1d-173">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a><span data-ttu-id="eee1d-174">Anpassen von JSON-Namen</span><span class="sxs-lookup"><span data-stu-id="eee1d-174">Customize JSON names</span></span>

<span data-ttu-id="eee1d-175">Standardmäßig sind Eigenschaftsnamen und Wörterbuch Schlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="eee1d-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="eee1d-176">In diesem Abschnitt wird Folgendes erläutert:</span><span class="sxs-lookup"><span data-stu-id="eee1d-176">This section explains how to:</span></span>

* <span data-ttu-id="eee1d-177">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="eee1d-177">Customize individual property names</span></span>
* <span data-ttu-id="eee1d-178">Alle Eigenschaftsnamen in Camel-Case konvertieren</span><span class="sxs-lookup"><span data-stu-id="eee1d-178">Convert all property names to camel case</span></span>
* <span data-ttu-id="eee1d-179">Implementieren einer benutzerdefinierten Benennungs Richtlinie für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eee1d-179">Implement a custom property naming policy</span></span>
* <span data-ttu-id="eee1d-180">Wörterbuch Schlüssel in Kamel-Schreibweise konvertieren</span><span class="sxs-lookup"><span data-stu-id="eee1d-180">Convert dictionary keys to camel case</span></span>

<span data-ttu-id="eee1d-181">Derzeit gibt es keine Unterstützung für das automatische Umrechnen von aufruten in Kamel Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="eee1d-181">Currently, there's no support for automatically converting enums to camel case.</span></span> <span data-ttu-id="eee1d-182">Weitere Informationen finden Sie im Repository "dotnet/corefx" auf GitHub [unter "Problem bei der Unterstützung von Unterstützung](https://github.com/dotnet/corefx/issues/37725) in der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="eee1d-182">For more information, see the [issue on enum camel case support](https://github.com/dotnet/corefx/issues/37725) in the dotnet/corefx repository on GitHub.</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="eee1d-183">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="eee1d-183">Customize individual property names</span></span>

<span data-ttu-id="eee1d-184">Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das [[jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) -Attribut.</span><span class="sxs-lookup"><span data-stu-id="eee1d-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="eee1d-185">Hier ist ein Beispiel für die Serialisierung und die daraus resultierende JSON-Datei:</span><span class="sxs-lookup"><span data-stu-id="eee1d-185">Here's an example type to serialize and resulting JSON:</span></span>

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

<span data-ttu-id="eee1d-186">Der durch dieses Attribut festgelegte Eigenschaftsname:</span><span class="sxs-lookup"><span data-stu-id="eee1d-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="eee1d-187">Gilt für die Serialisierung und Deserialisierung in beide Richtungen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="eee1d-188">Hat Vorrang vor Eigenschafts Benennungs Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="eee1d-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="eee1d-189">Bei allen JSON-Eigenschaftsnamen die Kamel-Schreibweise verwenden</span><span class="sxs-lookup"><span data-stu-id="eee1d-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="eee1d-190">Wenn Sie die Kamel-Schreibweise für alle JSON-Eigenschaftsnamen verwenden möchten, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="eee1d-191">Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="eee1d-191">Here's an example class to serialize and JSON output:</span></span>

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
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="eee1d-192">Die Benennungs Richtlinie für die Camel-Case-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="eee1d-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="eee1d-193">Gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="eee1d-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="eee1d-194">Wird von `[JsonPropertyName]`-Attributen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="eee1d-194">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="eee1d-195">Verwenden einer benutzerdefinierten JSON-Eigenschafts Benennungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="eee1d-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="eee1d-196">Um eine benutzerdefinierte JSON-Eigenschafts Benennungs Richtlinie zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und überschreiben Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="eee1d-197">Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihrer Benennungs Richtlinien Klasse fest:</span><span class="sxs-lookup"><span data-stu-id="eee1d-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="eee1d-198">Im folgenden finden Sie eine Beispiel Klasse zum Serialisieren der JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="eee1d-198">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="eee1d-199">Die Benennungs Richtlinie für die JSON-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="eee1d-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="eee1d-200">Gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="eee1d-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="eee1d-201">Wird von `[JsonPropertyName]`-Attributen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="eee1d-201">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="eee1d-202">Camel-Case-Wörterbuch Schlüssel</span><span class="sxs-lookup"><span data-stu-id="eee1d-202">Camel case dictionary keys</span></span>

<span data-ttu-id="eee1d-203">Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die `string`-Schlüssel in die Kamel-Schreibweise konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="eee1d-203">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="eee1d-204">Legen Sie zu diesem Zweck <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-204">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="eee1d-205">Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="eee1d-205">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="eee1d-206">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eee1d-206">Property</span></span> |<span data-ttu-id="eee1d-207">Wert</span><span class="sxs-lookup"><span data-stu-id="eee1d-207">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="eee1d-208">date</span><span class="sxs-lookup"><span data-stu-id="eee1d-208">Date</span></span>    | <span data-ttu-id="eee1d-209">8/1/2019 12:00:00 UHR-07:00</span><span class="sxs-lookup"><span data-stu-id="eee1d-209">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="eee1d-210">Temperatur</span><span class="sxs-lookup"><span data-stu-id="eee1d-210">TemperatureC</span></span>| <span data-ttu-id="eee1d-211">25</span><span class="sxs-lookup"><span data-stu-id="eee1d-211">25</span></span> |
| <span data-ttu-id="eee1d-212">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="eee1d-212">Summary</span></span>| <span data-ttu-id="eee1d-213">Luft</span><span class="sxs-lookup"><span data-stu-id="eee1d-213">Hot</span></span>|
| <span data-ttu-id="eee1d-214">Temperatureranges</span><span class="sxs-lookup"><span data-stu-id="eee1d-214">TemperatureRanges</span></span> | <span data-ttu-id="eee1d-215">Kalt, 20</span><span class="sxs-lookup"><span data-stu-id="eee1d-215">Cold, 20</span></span><br><span data-ttu-id="eee1d-216">Heiß, 40</span><span class="sxs-lookup"><span data-stu-id="eee1d-216">Hot, 40</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "cold": 20,
    "hot": 40
  }
}
```

<span data-ttu-id="eee1d-217">Die Camel Case Naming-Richtlinie gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="eee1d-217">The camel case naming policy applies to serialization only.</span></span>

## <a name="exclude-properties"></a><span data-ttu-id="eee1d-218">Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="eee1d-218">Exclude properties</span></span>

<span data-ttu-id="eee1d-219">Standardmäßig werden alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="eee1d-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="eee1d-220">Wenn Sie nicht möchten, dass einige von Ihnen in der JSON-Ausgabe angezeigt werden, haben Sie mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="eee1d-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="eee1d-221">In diesem Abschnitt wird erläutert, wie Folgendes ausgeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="eee1d-221">This section explains how to exclude:</span></span>

* <span data-ttu-id="eee1d-222">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eee1d-222">Individual properties</span></span>
* <span data-ttu-id="eee1d-223">Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eee1d-223">All read-only properties</span></span>
* <span data-ttu-id="eee1d-224">Alle NULL-Wert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eee1d-224">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="eee1d-225">Einzelne Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="eee1d-225">Exclude individual properties</span></span>

<span data-ttu-id="eee1d-226">Verwenden Sie das Attribut [[jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) , um einzelne Eigenschaften zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="eee1d-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="eee1d-227">Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="eee1d-227">Here's an example type to serialize and JSON output:</span></span>

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

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="eee1d-228">Alle schreibgeschützten Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="eee1d-228">Exclude all read-only properties</span></span>

<span data-ttu-id="eee1d-229">Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="eee1d-230">Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="eee1d-230">Here's an example type to serialize and JSON output:</span></span>

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

<span data-ttu-id="eee1d-231">Diese Option gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="eee1d-231">This option applies only to serialization.</span></span> <span data-ttu-id="eee1d-232">Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="eee1d-232">During deserialization, read-only properties are ignored by default.</span></span> <span data-ttu-id="eee1d-233">Eine Eigenschaft ist schreibgeschützt, wenn Sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.</span><span class="sxs-lookup"><span data-stu-id="eee1d-233">A property is read-only if it contains a public getter but not a public setter.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="eee1d-234">Alle NULL-Wert Eigenschaften ausschließen</span><span class="sxs-lookup"><span data-stu-id="eee1d-234">Exclude all null value properties</span></span>

<span data-ttu-id="eee1d-235">Um alle NULL-Wert Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="eee1d-236">Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="eee1d-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="eee1d-237">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eee1d-237">Property</span></span> |<span data-ttu-id="eee1d-238">Wert</span><span class="sxs-lookup"><span data-stu-id="eee1d-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="eee1d-239">date</span><span class="sxs-lookup"><span data-stu-id="eee1d-239">Date</span></span>    | <span data-ttu-id="eee1d-240">8/1/2019 12:00:00 UHR-07:00</span><span class="sxs-lookup"><span data-stu-id="eee1d-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="eee1d-241">Temperatur</span><span class="sxs-lookup"><span data-stu-id="eee1d-241">TemperatureC</span></span>| <span data-ttu-id="eee1d-242">25</span><span class="sxs-lookup"><span data-stu-id="eee1d-242">25</span></span> |
| <span data-ttu-id="eee1d-243">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="eee1d-243">Summary</span></span>| <span data-ttu-id="eee1d-244">NULL</span><span class="sxs-lookup"><span data-stu-id="eee1d-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="eee1d-245">Diese Einstellung gilt für die Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="eee1d-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="eee1d-246">Während der Deserialisierung werden NULL-Werte in JSON nur ignoriert, wenn Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="eee1d-246">During deserialization, null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="eee1d-247">NULL-Werte für Werttypen, die keine NULL-Werte zulassen, verursachen Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-247">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="eee1d-248">Weitere Informationen finden Sie im Repository dotnet/corefx auf GitHub unter dem [Problem für Werttypen, die keine NULL-Werte](https://github.com/dotnet/corefx/issues/40922) zulassen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-248">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="eee1d-249">Nichtbeachtung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="eee1d-249">Case-insensitive property matching</span></span>

<span data-ttu-id="eee1d-250">Standardmäßig wird bei der Deserialisierung nach Groß-/Kleinschreibung unterschieden, dass Eigenschaften Namen Übereinstimmungen zwischen JSON und den Zielobjekt Eigenschaften aufweisen.</span><span class="sxs-lookup"><span data-stu-id="eee1d-250">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="eee1d-251">Um dieses Verhalten zu ändern, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="eee1d-251">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="eee1d-252">Im folgenden finden Sie eine Beispiel-JSON-Datei mit den Namen der Kamel</span><span class="sxs-lookup"><span data-stu-id="eee1d-252">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="eee1d-253">Sie kann in den folgenden Typ deserialisiert werden, der über die Namen der Pascal-Großbuchstaben verfügt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-253">It can be deserialized into the following type that has Pascal case property names.</span></span>

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

## <a name="include-properties-of-derived-classes"></a><span data-ttu-id="eee1d-254">Einschließen von Eigenschaften abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="eee1d-254">Include properties of derived classes</span></span>

<span data-ttu-id="eee1d-255">Die polymorphe Serialisierung wird nicht unterstützt, wenn Sie zum Zeitpunkt der Kompilierung angeben, welcher Typ serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="eee1d-255">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="eee1d-256">Nehmen Sie beispielsweise an, Sie verfügen über eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastWithWind`:</span><span class="sxs-lookup"><span data-stu-id="eee1d-256">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

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

<span data-ttu-id="eee1d-257">Und nehmen wir an, dass der Typ, der zur Kompilierzeit an die `Serialize`-Methode geleitet oder von diesem abgeleitet wurde, `WeatherForecast` ist:</span><span class="sxs-lookup"><span data-stu-id="eee1d-257">And suppose the type passed to, or inferred by, the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="eee1d-258">In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastWithWind`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="eee1d-258">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="eee1d-259">Es werden nur die Basisklassen Eigenschaften serialisiert:</span><span class="sxs-lookup"><span data-stu-id="eee1d-259">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="eee1d-260">Dieses Verhalten soll das versehentliche verfügbar machen von Daten in einem abgeleiteten, von der Laufzeit erstellten Typ verhindern.</span><span class="sxs-lookup"><span data-stu-id="eee1d-260">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="eee1d-261">Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs zu serialisieren:</span><span class="sxs-lookup"><span data-stu-id="eee1d-261">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="eee1d-262">Aufrufen einer Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A>, mit der Sie den Typ zur Laufzeit angeben können:</span><span class="sxs-lookup"><span data-stu-id="eee1d-262">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="eee1d-263">Deklarieren Sie das zu serialisierende Objekt als `object`.</span><span class="sxs-lookup"><span data-stu-id="eee1d-263">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="eee1d-264">Im vorangehenden Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in der JSON-Ausgabe enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="eee1d-264">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="eee1d-265">Handle für Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="eee1d-265">Handle overflow JSON</span></span>

<span data-ttu-id="eee1d-266">Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, der nicht durch Eigenschaften des Zieltyps dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="eee1d-266">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="eee1d-267">Angenommen, Ihr Zieltyp lautet:</span><span class="sxs-lookup"><span data-stu-id="eee1d-267">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="eee1d-268">Der JSON-Code, der deserialisiert werden soll, lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="eee1d-268">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="eee1d-269">Wenn Sie den JSON-Code deserialisieren, der in den angezeigten Typ angezeigt wird, sind die Eigenschaften "`DatesAvailable`" und "`SummaryWords`" nicht mehr vorhanden und gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="eee1d-269">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="eee1d-270">Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) -Attribut auf eine Eigenschaft vom Typ `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:</span><span class="sxs-lookup"><span data-stu-id="eee1d-270">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

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

<span data-ttu-id="eee1d-271">Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="eee1d-271">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="eee1d-272">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eee1d-272">Property</span></span> |<span data-ttu-id="eee1d-273">Wert</span><span class="sxs-lookup"><span data-stu-id="eee1d-273">Value</span></span>  |<span data-ttu-id="eee1d-274">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eee1d-274">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="eee1d-275">date</span><span class="sxs-lookup"><span data-stu-id="eee1d-275">Date</span></span>    | <span data-ttu-id="eee1d-276">8/1/2019 12:00:00 UHR-07:00</span><span class="sxs-lookup"><span data-stu-id="eee1d-276">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="eee1d-277">Temperatur</span><span class="sxs-lookup"><span data-stu-id="eee1d-277">TemperatureC</span></span>| <span data-ttu-id="eee1d-278">0</span><span class="sxs-lookup"><span data-stu-id="eee1d-278">0</span></span> | <span data-ttu-id="eee1d-279">Unterscheidung nach Groß-/Kleinschreibung (`temperatureC` im JSON-Code), sodass die-Eigenschaft nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eee1d-279">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="eee1d-280">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="eee1d-280">Summary</span></span> | <span data-ttu-id="eee1d-281">Luft</span><span class="sxs-lookup"><span data-stu-id="eee1d-281">Hot</span></span> ||
| <span data-ttu-id="eee1d-282">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="eee1d-282">ExtensionData</span></span> | <span data-ttu-id="eee1d-283">Temperatur: 25</span><span class="sxs-lookup"><span data-stu-id="eee1d-283">temperatureC: 25</span></span> |<span data-ttu-id="eee1d-284">Da die Groß-/Kleinschreibung nicht entsprach, ist diese JSON-Eigenschaft ein zusätzliches und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="eee1d-284">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="eee1d-285">Datesavailable:</span><span class="sxs-lookup"><span data-stu-id="eee1d-285">DatesAvailable:</span></span><br>  <span data-ttu-id="eee1d-286">8/1/2019 12:00:00 UHR-07:00</span><span class="sxs-lookup"><span data-stu-id="eee1d-286">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="eee1d-287">8/2/2019 12:00:00 UHR-07:00</span><span class="sxs-lookup"><span data-stu-id="eee1d-287">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="eee1d-288">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="eee1d-288">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="eee1d-289">Summarywords:</span><span class="sxs-lookup"><span data-stu-id="eee1d-289">SummaryWords:</span></span><br><span data-ttu-id="eee1d-290">Toll</span><span class="sxs-lookup"><span data-stu-id="eee1d-290">Cool</span></span><br><span data-ttu-id="eee1d-291">Digen</span><span class="sxs-lookup"><span data-stu-id="eee1d-291">Windy</span></span><br><span data-ttu-id="eee1d-292">Feu</span><span class="sxs-lookup"><span data-stu-id="eee1d-292">Humid</span></span> |<span data-ttu-id="eee1d-293">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="eee1d-293">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="eee1d-294">Wenn das Zielobjekt serialisiert wird, werden die Erweiterungs-Datenschlüssel Wert-Paare zu JSON-Eigenschaften, genauso wie Sie im eingehenden JSON-Code waren:</span><span class="sxs-lookup"><span data-stu-id="eee1d-294">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="eee1d-295">Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eee1d-295">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="eee1d-296">Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="eee1d-296">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="use-utf8jsonwriter-directly"></a><span data-ttu-id="eee1d-297">Verwenden Sie Utf8JsonWriter direkt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-297">Use Utf8JsonWriter directly</span></span>

<span data-ttu-id="eee1d-298">Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.Utf8JsonWriter>-Klasse direkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee1d-298">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class directly.</span></span>

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

## <a name="use-utf8jsonreader-directly"></a><span data-ttu-id="eee1d-299">Verwenden Sie Utf8JsonReader direkt.</span><span class="sxs-lookup"><span data-stu-id="eee1d-299">Use Utf8JsonReader directly</span></span>

<span data-ttu-id="eee1d-300">Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.Utf8JsonReader>-Klasse direkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee1d-300">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class directly.</span></span> <span data-ttu-id="eee1d-301">Der Code geht davon aus, dass die `jsonUtf8`-Variable ein Bytearray ist, das gültige JSON-codierte JSON-Codierung enthält.</span><span class="sxs-lookup"><span data-stu-id="eee1d-301">The code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="eee1d-302">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="eee1d-302">Additional resources</span></span>

* [<span data-ttu-id="eee1d-303">Übersicht über System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="eee1d-303">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="eee1d-304">System. Text. JSON-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="eee1d-304">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="eee1d-305">DateTime-und DateTimeOffset-Unterstützung in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="eee1d-305">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
