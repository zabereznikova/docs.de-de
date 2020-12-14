---
title: Behandeln von Überlauf-JSON mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET Überlauf-JSON beim Serialisieren in und Deserialisieren aus JSON behandeln können.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 265ce4f77d353720419122d17c36e508a377b68f
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008915"
---
# <a name="how-to-handle-overflow-json-with-no-locsystemtextjson"></a><span data-ttu-id="8eace-103">Behandeln von Überlauf-JSON mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8eace-103">How to handle overflow JSON with System.Text.Json</span></span>

<span data-ttu-id="8eace-104">In diesem Artikel erfahren Sie, wie Überlauf-JSON mit dem `System.Text.Json`-Namespace behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="8eace-104">In this article, you will learn how to handle overflow JSON with the `System.Text.Json` namespace.</span></span>

## <a name="handle-overflow-json"></a><span data-ttu-id="8eace-105">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="8eace-105">Handle overflow JSON</span></span>

<span data-ttu-id="8eace-106">Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, die nicht von Eigenschaften des Zieltyps dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8eace-106">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="8eace-107">Angenommen, Ihr Zieltyp ist folgender:</span><span class="sxs-lookup"><span data-stu-id="8eace-107">For example, suppose your target type is this:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

<span data-ttu-id="8eace-108">Und der zu deserialisierende JSON-Code ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8eace-108">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="8eace-109">Wenn Sie den angezeigten JSON-Code in den gezeigten Typ deserialisieren, gibt es keinen Ort mehr für die Eigenschaften `DatesAvailable` und `SummaryWords`, und sie gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="8eace-109">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="8eace-110">Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das Attribut [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) auf eine Eigenschaft des Typs `Dictionary<string,object>` oder `Dictionary<string,JsonElement>` an:</span><span class="sxs-lookup"><span data-stu-id="8eace-110">To capture extra data such as these properties, apply the [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithExtensionData":::

<span data-ttu-id="8eace-111">Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="8eace-111">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

| <span data-ttu-id="8eace-112">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8eace-112">Property</span></span> | <span data-ttu-id="8eace-113">Wert</span><span class="sxs-lookup"><span data-stu-id="8eace-113">Value</span></span> | <span data-ttu-id="8eace-114">Notizen</span><span class="sxs-lookup"><span data-stu-id="8eace-114">Notes</span></span> |
|--|--|--|
| `Date` | `"8/1/2019 12:00:00 AM -07:00"` |  |
| `TemperatureCelsius` | `0` | <span data-ttu-id="8eace-115">Keine Übereinstimmung unter Berücksichtigung von Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die Eigenschaft nicht festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8eace-115">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| `Summary` | `"Hot"` |  |
| `ExtensionData` | `temperatureCelsius: 25` | <span data-ttu-id="8eace-116">Da die Groß-/Kleinschreibung nicht übereinstimmte, ist diese JSON-Eigenschaft ein zusätzliches Element und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="8eace-116">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span> |
| `DatesAvailable` | `[ "8/1/2019 12:00:00 AM -07:00", "8/2/2019 12:00:00 AM -07:00" ]` | <span data-ttu-id="8eace-117">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="8eace-117">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span> |
| `SummaryWords` | `[ "Cool", "Windy", "Humid" ]` | <span data-ttu-id="8eace-118">Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="8eace-118">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span> |

<span data-ttu-id="8eace-119">Wenn das Zielobjekt serialisiert wird, werden die Schlüssel-Wert-Paare der Erweiterungsdaten zu genau solchen JSON-Eigenschaften, wie sie im eingehenden JSON-Code waren:</span><span class="sxs-lookup"><span data-stu-id="8eace-119">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="8eace-120">Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code vorkommt.</span><span class="sxs-lookup"><span data-stu-id="8eace-120">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="8eace-121">Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert würden.</span><span class="sxs-lookup"><span data-stu-id="8eace-121">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="see-also"></a><span data-ttu-id="8eace-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8eace-122">See also</span></span>

* [<span data-ttu-id="8eace-123">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="8eace-123">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="8eace-124">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="8eace-124">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="8eace-125">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="8eace-125">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="8eace-126">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="8eace-126">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="8eace-127">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="8eace-127">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="8eace-128">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8eace-128">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="8eace-129">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="8eace-129">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="8eace-130">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="8eace-130">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="8eace-131">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="8eace-131">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="8eace-132">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8eace-132">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="8eace-133">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8eace-133">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="8eace-134">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="8eace-134">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="8eace-135">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="8eace-135">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="8eace-136">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8eace-136">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="8eace-137">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8eace-137">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="8eace-138">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="8eace-138">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="8eace-139">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="8eace-139">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
