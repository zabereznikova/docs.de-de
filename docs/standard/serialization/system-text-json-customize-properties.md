---
title: Anpassen von Eigenschaftsnamen und -werten mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET Eigenschaftsnamen und -werte bei der Serialisierung mit System.Text.Json anpassen.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 4b88509313e719ea993e00d889bc6145f4976a2d
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008902"
---
# <a name="how-to-customize-property-names-and-values-with-no-locsystemtextjson"></a><span data-ttu-id="8f7f2-103">Anpassen von Eigenschaftsnamen und -werten mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8f7f2-103">How to customize property names and values with System.Text.Json</span></span>

<span data-ttu-id="8f7f2-104">Standardmäßig bleiben Eigenschaftsnamen und Wörterbuchschlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-104">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="8f7f2-105">Enumerationswerte werden als Zahlen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-105">Enum values are represented as numbers.</span></span> <span data-ttu-id="8f7f2-106">In diesem Artikel lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-106">In this article, you'll learn how to:</span></span>

> [!NOTE]
> <span data-ttu-id="8f7f2-107">Der [Webstandard](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) ist die Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-107">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is camel case.</span></span>

* [<span data-ttu-id="8f7f2-108">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="8f7f2-108">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="8f7f2-109">Konvertieren aller Eigenschaftsnamen in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="8f7f2-109">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="8f7f2-110">Implementieren einer benutzerdefinierten Benennungsrichtlinie für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8f7f2-110">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="8f7f2-111">Konvertieren von Wörterbuchschlüsseln in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="8f7f2-111">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="8f7f2-112">Konvertieren von Enumerationen in Zeichenfolgen und Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="8f7f2-112">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="8f7f2-113">Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und -werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="8f7f2-113">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

## <a name="customize-individual-property-names"></a><span data-ttu-id="8f7f2-114">Anpassen einzelner Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="8f7f2-114">Customize individual property names</span></span>

<span data-ttu-id="8f7f2-115">Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das Attribut [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="8f7f2-115">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="8f7f2-116">Hier finden Sie einen zu serialisierenden Beispieltyp und die daraus resultierende JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-116">Here's an example type to serialize and resulting JSON:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8f7f2-117">Der über dieses Attribut festgelegte Eigenschaftsname:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-117">The property name set by this attribute:</span></span>

* <span data-ttu-id="8f7f2-118">Dies gilt in beide Richtungen, für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-118">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="8f7f2-119">Es hat Vorrang vor Benennungsrichtlinien für Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-119">Takes precedence over property naming policies.</span></span>

## <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="8f7f2-120">Verwenden der Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="8f7f2-120">Use camel case for all JSON property names</span></span>

<span data-ttu-id="8f7f2-121">Um die Camel-Case-Schreibweise für alle JSON-Eigenschaftsnamen zu verwenden, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-121">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs" id="Serialize":::

<span data-ttu-id="8f7f2-122">Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-122">Here's an example class to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8f7f2-123">Die Camel-Case-Benennungsrichtlinie für Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-123">The camel case property naming policy:</span></span>

* <span data-ttu-id="8f7f2-124">Gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-124">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8f7f2-125">Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-125">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="8f7f2-126">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Camel-Case-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-126">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

## <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="8f7f2-127">Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8f7f2-127">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="8f7f2-128">Um eine benutzerdefinierte Benennungsrichtlinie für JSON-Eigenschaften zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und setzen Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode außer Kraft, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-128">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs":::

<span data-ttu-id="8f7f2-129">Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihre Benennungsrichtlinienklasse fest:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-129">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs" id="Serialize":::

<span data-ttu-id="8f7f2-130">Hier finden Sie eine zu serialisierenden Beispielklasse und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-130">Here's an example class to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8f7f2-131">Die Benennungsrichtlinie für JSON-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-131">The JSON property naming policy:</span></span>

* <span data-ttu-id="8f7f2-132">Gilt für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-132">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8f7f2-133">Wird von `[JsonPropertyName]`-Attributen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-133">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="8f7f2-134">Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-134">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

## <a name="camel-case-dictionary-keys"></a><span data-ttu-id="8f7f2-135">Wörterbuchschlüssel in Camel-Case-Schreibweise</span><span class="sxs-lookup"><span data-stu-id="8f7f2-135">Camel case dictionary keys</span></span>

<span data-ttu-id="8f7f2-136">Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>` ist, können die Schlüssel vom Typ `string` in Camel-Case-Schreibweise konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-136">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="8f7f2-137">Legen Sie hierzu <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase` fest, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-137">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs" id="Serialize":::

<span data-ttu-id="8f7f2-138">Das Serialisieren eines Objekts mit einem Wörterbuch namens `TemperatureRanges`, das die Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` enthält, würde zu einer JSON-Ausgabe wie im folgenden Beispiel führen:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-138">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="8f7f2-139">Die Camel-Case-Benennungsrichtlinie für Wörterbuchschlüssel gilt nur für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-139">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="8f7f2-140">Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei auch dann, wenn Sie `JsonNamingPolicy.CamelCase` als `DictionaryKeyPolicy` angeben.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-140">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

## <a name="enums-as-strings"></a><span data-ttu-id="8f7f2-141">Enumerationen als Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="8f7f2-141">Enums as strings</span></span>

<span data-ttu-id="8f7f2-142">Standardmäßig werden Enumerationen als Zahlen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-142">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="8f7f2-143">Um Enumerationen als Zeichenfolgen zu serialisieren, verwenden Sie <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-143">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="8f7f2-144">Angenommen, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-144">For example, suppose you need to serialize the following class that has an enum:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnum":::

<span data-ttu-id="8f7f2-145">Wenn die Zusammenfassung `Hot` ist, hat das serialisierte JSON standardmäßig den numerischen Wert 3:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-145">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="8f7f2-146">Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-146">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Serialize":::

<span data-ttu-id="8f7f2-147">Das resultierende JSON sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-147">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="8f7f2-148">Zeichenfolgennamen von Enumerationen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8f7f2-148">Enum string names can be deserialized as well, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Deserialize":::

## <a name="see-also"></a><span data-ttu-id="8f7f2-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f7f2-149">See also</span></span>

* [<span data-ttu-id="8f7f2-150">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="8f7f2-150">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="8f7f2-151">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="8f7f2-151">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="8f7f2-152">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="8f7f2-152">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="8f7f2-153">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="8f7f2-153">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="8f7f2-154">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8f7f2-154">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="8f7f2-155">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="8f7f2-155">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="8f7f2-156">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="8f7f2-156">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="8f7f2-157">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="8f7f2-157">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="8f7f2-158">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="8f7f2-158">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="8f7f2-159">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8f7f2-159">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="8f7f2-160">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8f7f2-160">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="8f7f2-161">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="8f7f2-161">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="8f7f2-162">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="8f7f2-162">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="8f7f2-163">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8f7f2-163">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="8f7f2-164">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8f7f2-164">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="8f7f2-165">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="8f7f2-165">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="8f7f2-166">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="8f7f2-166">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
