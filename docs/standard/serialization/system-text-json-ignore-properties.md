---
title: Ignorieren von Eigenschaften mit System.Text.Json
description: Erfahren Sie, wie Eigenschaften bei der Serialisierung mit System.Text.Json in .NET ignoriert werden.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: ed7ef8509d6660bbbbaf194a87aa9d4815143507
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439767"
---
# <a name="how-to-ignore-properties-with-no-locsystemtextjson"></a><span data-ttu-id="59c51-103">Ignorieren von Eigenschaften mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="59c51-103">How to ignore properties with System.Text.Json</span></span>

<span data-ttu-id="59c51-104">Beim Serialisieren von C#-Objekten in JavaScript Object Notation (JSON) werden standardmäßig alle öffentlichen Eigenschaften serialisiert.</span><span class="sxs-lookup"><span data-stu-id="59c51-104">When serializing C# objects to JavaScript Object Notation (JSON), by default, all public properties are serialized.</span></span> <span data-ttu-id="59c51-105">Wenn Sie möchten, dass einige von ihnen nicht in der resultierenden JSON-Ausgabe vorkommen, haben Sie mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="59c51-105">If you don't want some of them to appear in the resulting JSON, you have several options.</span></span> <span data-ttu-id="59c51-106">In diesem Artikel erfahren Sie, wie Eigenschaften auf der Grundlage verschiedener Kriterien ignoriert werden:</span><span class="sxs-lookup"><span data-stu-id="59c51-106">In this article you learn how to ignore properties based on various criteria:</span></span>

::: zone pivot="dotnet-5-0"

* [<span data-ttu-id="59c51-107">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59c51-107">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="59c51-108"> Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59c51-108">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="59c51-109">Alle Nullwert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59c51-109">All null-value properties</span></span>](#ignore-all-null-value-properties)
* [<span data-ttu-id="59c51-110">Alle Eigenschaften mit Standardwert</span><span class="sxs-lookup"><span data-stu-id="59c51-110">All default-value properties</span></span>](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [<span data-ttu-id="59c51-111">Einzelne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59c51-111">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="59c51-112"> Alle schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59c51-112">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="59c51-113">Alle Nullwert-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59c51-113">All null-value properties</span></span>](#ignore-all-null-value-properties)
::: zone-end

## <a name="ignore-individual-properties"></a><span data-ttu-id="59c51-114">Ignorieren einzelner Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59c51-114">Ignore individual properties</span></span>

<span data-ttu-id="59c51-115">Um einzelne Eigenschaften zu ignorieren, verwenden Sie das Attribut [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="59c51-115">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="59c51-116">Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="59c51-116">Here's an example type to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithIgnoreAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="59c51-117">Sie können einen bedingten Ausschluss angeben, indem Sie die Eigenschaft `Condition` des Attributs [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) festlegen.</span><span class="sxs-lookup"><span data-stu-id="59c51-117">You can specify conditional exclusion by setting the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="59c51-118">Die Enumeration <xref:System.Text.Json.Serialization.JsonIgnoreCondition> bietet die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="59c51-118">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="59c51-119">`Always`: Die Eigenschaft wird stets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="59c51-119">`Always` - The property is always ignored.</span></span> <span data-ttu-id="59c51-120">Wenn `Condition` nicht angegeben ist, wird diese Option angenommen.</span><span class="sxs-lookup"><span data-stu-id="59c51-120">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="59c51-121">`Never`: Die Eigenschaft wird stets serialisiert und deserialisiert, und zwar unabhängig von den globalen Einstellungen `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` und `IgnoreReadOnlyFields`.</span><span class="sxs-lookup"><span data-stu-id="59c51-121">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="59c51-122">`WhenWritingDefault`: Die Eigenschaft wird bei der Serialisierung ignoriert, wenn es sich um einen Verweistyp `null`, einen Nullwerte zulassenden Typ `null` oder einen Werttyp `default` handelt.</span><span class="sxs-lookup"><span data-stu-id="59c51-122">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null`, a nullable value type `null`, or a value type `default`.</span></span>
* <span data-ttu-id="59c51-123">`WhenWritingNull`: Die Eigenschaft wird bei der Serialisierung ignoriert, wenn es sich um einen Verweistyp `null` oder einen Nullwerte zulassenden Typ `null` handelt.</span><span class="sxs-lookup"><span data-stu-id="59c51-123">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`, or a nullable value type `null`.</span></span>

<span data-ttu-id="59c51-124">Das folgende Beispiel veranschaulicht die Verwendung der Eigenschaft `Condition` des Attributs [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute):</span><span class="sxs-lookup"><span data-stu-id="59c51-124">The following example illustrates use of the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

## <a name="ignore-all-read-only-properties"></a><span data-ttu-id="59c51-125">Ignorieren aller schreibgeschützten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59c51-125">Ignore all read-only properties</span></span>

<span data-ttu-id="59c51-126">Eine Eigenschaft ist schreibgeschützt, wenn sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält.</span><span class="sxs-lookup"><span data-stu-id="59c51-126">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="59c51-127">Um alle schreibgeschützten Eigenschaften bei der Serialisierung zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="59c51-127">To ignore all read-only properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs" id="Serialize":::

<span data-ttu-id="59c51-128">Hier finden Sie einen zu serialisierenden Beispieltyp und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="59c51-128">Here's an example type to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithROProperty":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="59c51-129">Diese Option gilt nur für Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="59c51-129">This option applies only to serialization.</span></span> <span data-ttu-id="59c51-130">Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="59c51-130">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="59c51-131">Diese Option gilt nur für Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="59c51-131">This option applies only to properties.</span></span> <span data-ttu-id="59c51-132">Um schreibgeschützte Felder beim [Serialisieren von Feldern](system-text-json-how-to.md#include-fields) zu ignorieren, verwenden Sie die globale Einstellung <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="59c51-132">To ignore read-only fields when [serializing fields](system-text-json-how-to.md#include-fields), use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

## <a name="ignore-all-null-value-properties"></a><span data-ttu-id="59c51-133">Ignorieren aller Eigenschaften mit dem Wert NULL</span><span class="sxs-lookup"><span data-stu-id="59c51-133">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="59c51-134">Um alle Eigenschaften mit dem Wert NULL zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> auf <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull> fest:</span><span class="sxs-lookup"><span data-stu-id="59c51-134">To ignore all null-value properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="59c51-135">Um bei der Serialisierung alle Eigenschaften mit dem Wert NULL zu ignorieren, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> auf `true` fest:</span><span class="sxs-lookup"><span data-stu-id="59c51-135">To ignore all null-value properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs" id="Serialize":::

<span data-ttu-id="59c51-136">Hier finden Sie ein zu serialisierendes Beispielobjekt und die JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="59c51-136">Here's an example object to serialize and JSON output:</span></span>

| <span data-ttu-id="59c51-137">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="59c51-137">Property</span></span>             | <span data-ttu-id="59c51-138">Wert</span><span class="sxs-lookup"><span data-stu-id="59c51-138">Value</span></span>                         |
|----------------------|-------------------------------|
| `Date`               | `8/1/2019 12:00:00 AM -07:00` |
| `TemperatureCelsius` | `25`                          |
| `Summary`            | `null`                        |

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

## <a name="ignore-all-default-value-properties"></a><span data-ttu-id="59c51-139">Ignorieren aller Eigenschaften mit Standardwert</span><span class="sxs-lookup"><span data-stu-id="59c51-139">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="59c51-140">Um die Serialisierung von Standardwerten in Werttypeigenschaften zu verhindern, legen Sie, wie im folgenden Beispiel gezeigt, die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> auf <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> fest:</span><span class="sxs-lookup"><span data-stu-id="59c51-140">To prevent serialization of default values in value type properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="59c51-141">Die Einstellung <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> verhindert auch die Serialisierung von Verweistypeigenschaften mit dem Wert NULL und Nullwerte zulassenden Typeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="59c51-141">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> setting also prevents serialization of null-value reference type and nullable value type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="59c51-142">Es gibt keine in . NET Core 3.1 integrierte Möglichkeit, die Serialisierung von Eigenschaften mit Standardwerttypen in `System.Text.Json` zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="59c51-142">There is no built-in way to prevent serialization of properties with value type defaults in `System.Text.Json` in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="59c51-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59c51-143">See also</span></span>

* [<span data-ttu-id="59c51-144">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="59c51-144">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="59c51-145">Instanziieren von JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="59c51-145">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="59c51-146">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="59c51-146">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="59c51-147">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="59c51-147">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="59c51-148">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="59c51-148">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="59c51-149">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="59c51-149">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="59c51-150">Beibehalten zirkulärer Verweise</span><span class="sxs-lookup"><span data-stu-id="59c51-150">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="59c51-151">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="59c51-151">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="59c51-152">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="59c51-152">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="59c51-153">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="59c51-153">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
