---
title: Zulassen einiger Arten von ungültigem JSON-Code mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET Kommentare, nachfolgende Kommas und Zahlen in Anführungszeichen beim Serialisieren in und Deserialisieren aus JSON zulassen.
ms.date: 12/03/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2559b081010fb0a2fa208b121cb095efdeb8da2e
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009807"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a><span data-ttu-id="35177-103">Zulassen einiger Arten von ungültigem JSON-Code mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="35177-103">How to allow some kinds of invalid JSON with System.Text.Json</span></span>

<span data-ttu-id="35177-104">In diesem Artikel erfahren Sie, wie Sie Kommentare, nachfolgende Kommas und Zahlen in Anführungszeichen in JSON zulassen, und wie Sie Zahlen als Zeichenfolgen schreiben.</span><span class="sxs-lookup"><span data-stu-id="35177-104">In this article, you will learn how to allow comments, trailing commas, and quoted numbers in JSON, and how to write numbers as strings.</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="35177-105">Zulassen von Kommentaren und nachfolgenden Kommas</span><span class="sxs-lookup"><span data-stu-id="35177-105">Allow comments and trailing commas</span></span>

<span data-ttu-id="35177-106">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="35177-106">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="35177-107">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest.</span><span class="sxs-lookup"><span data-stu-id="35177-107">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="35177-108">Und um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="35177-108">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="35177-109">Das folgende Beispiel veranschaulicht, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="35177-109">The following example shows how to allow both:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

<span data-ttu-id="35177-110">Im Folgenden finden Sie ein JSON-Beispiel mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="35177-110">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
  // Comments on
  /* separate lines */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="35177-111">Zulassen oder Schreiben von Zahlen in Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="35177-111">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="35177-112">Einige Serialisierungsmodule codieren Zahlen als (in Anführungszeichen eingeschlossene) JSON-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="35177-112">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span>

<span data-ttu-id="35177-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35177-113">For example:</span></span>

```json
{
    "DegreesCelsius": "23"
}
```

<span data-ttu-id="35177-114">Verwenden Sie anstelle von</span><span class="sxs-lookup"><span data-stu-id="35177-114">Instead of:</span></span>

```json
{
    "DegreesCelsius": 23
}
```

<span data-ttu-id="35177-115">Um Zahlen in Anführungszeichen zu serialisieren oder Zahlen in Anführungszeichen im gesamten Graphen des Eingabeobjekts zu akzeptieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> wie im folgenden Beispiel gezeigt fest:</span><span class="sxs-lookup"><span data-stu-id="35177-115">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

<span data-ttu-id="35177-116">Wenn Sie `System.Text.Json` indirekt über ASP.NET Core verwenden, sind beim Deserialisieren Zahlen in Anführungszeichen erlaubt, da ASP.NET Core [Webstandardoptionen](xref:System.Text.Json.JsonSerializerDefaults.Web) angibt.</span><span class="sxs-lookup"><span data-stu-id="35177-116">When you use `System.Text.Json` indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref:System.Text.Json.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="35177-117">Um Zahlen in Anführungszeichen für bestimmte Eigenschaften, Felder oder Typen zuzulassen oder zu schreiben, verwenden Sie das Attribut [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).</span><span class="sxs-lookup"><span data-stu-id="35177-117">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="35177-118">`System.Text.Json` in .NET Core 3.1 unterstützt keine Serialisierung oder Deserialisierung von Zahlen in Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="35177-118">`System.Text.Json` in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="35177-119">Weitere Informationen finden Sie unter [Zulassen oder Schreiben von Zahlen in Anführungszeichen](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span><span class="sxs-lookup"><span data-stu-id="35177-119">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="35177-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35177-120">See also</span></span>

* [<span data-ttu-id="35177-121">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="35177-121">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="35177-122">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="35177-122">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="35177-123">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="35177-123">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="35177-124">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="35177-124">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="35177-125">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="35177-125">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="35177-126">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="35177-126">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="35177-127">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="35177-127">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="35177-128">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="35177-128">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="35177-129">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="35177-129">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="35177-130">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="35177-130">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="35177-131">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="35177-131">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="35177-132">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="35177-132">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="35177-133">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="35177-133">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="35177-134">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="35177-134">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="35177-135">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="35177-135">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="35177-136">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="35177-136">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="35177-137">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="35177-137">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
