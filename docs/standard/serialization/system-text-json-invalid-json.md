---
title: Zulassen einiger Arten von ungültigem JSON-Code mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET Kommentare, nachfolgende Kommas und Zahlen in Anführungszeichen beim Serialisieren in und Deserialisieren aus JSON zulassen.
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
ms.openlocfilehash: 60cbb98bb65ee5c1ffdd3043e42a04004530a115
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439766"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a><span data-ttu-id="2fbab-103">Zulassen einiger Arten von ungültigem JSON-Code mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="2fbab-103">How to allow some kinds of invalid JSON with System.Text.Json</span></span>

<span data-ttu-id="2fbab-104">In diesem Artikel erfahren Sie, wie Sie Kommentare, nachfolgende Kommas und Zahlen in Anführungszeichen in JSON zulassen, und wie Sie Zahlen als Zeichenfolgen schreiben.</span><span class="sxs-lookup"><span data-stu-id="2fbab-104">In this article, you will learn how to allow comments, trailing commas, and quoted numbers in JSON, and how to write numbers as strings.</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="2fbab-105">Zulassen von Kommentaren und nachfolgenden Kommas</span><span class="sxs-lookup"><span data-stu-id="2fbab-105">Allow comments and trailing commas</span></span>

<span data-ttu-id="2fbab-106">Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="2fbab-106">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="2fbab-107">Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip` fest.</span><span class="sxs-lookup"><span data-stu-id="2fbab-107">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="2fbab-108">Und um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="2fbab-108">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="2fbab-109">Das folgende Beispiel veranschaulicht, wie Sie beides zulassen:</span><span class="sxs-lookup"><span data-stu-id="2fbab-109">The following example shows how to allow both:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

<span data-ttu-id="2fbab-110">Im Folgenden finden Sie ein JSON-Beispiel mit Kommentaren und einem nachfolgenden Komma:</span><span class="sxs-lookup"><span data-stu-id="2fbab-110">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="2fbab-111">Zulassen oder Schreiben von Zahlen in Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="2fbab-111">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="2fbab-112">Einige Serialisierungsmodule codieren Zahlen als (in Anführungszeichen eingeschlossene) JSON-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2fbab-112">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span>

<span data-ttu-id="2fbab-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2fbab-113">For example:</span></span>

```json
{
    "DegreesCelsius": "23"
}
```

<span data-ttu-id="2fbab-114">Verwenden Sie anstelle von</span><span class="sxs-lookup"><span data-stu-id="2fbab-114">Instead of:</span></span>

```json
{
    "DegreesCelsius": 23
}
```

<span data-ttu-id="2fbab-115">Um Zahlen in Anführungszeichen zu serialisieren oder Zahlen in Anführungszeichen im gesamten Graphen des Eingabeobjekts zu akzeptieren, legen Sie <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> wie im folgenden Beispiel gezeigt fest:</span><span class="sxs-lookup"><span data-stu-id="2fbab-115">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

<span data-ttu-id="2fbab-116">Wenn Sie `System.Text.Json` indirekt über ASP.NET Core verwenden, sind beim Deserialisieren Zahlen in Anführungszeichen erlaubt, da ASP.NET Core [Webstandardoptionen](xref:System.Text.Json.JsonSerializerDefaults.Web) angibt.</span><span class="sxs-lookup"><span data-stu-id="2fbab-116">When you use `System.Text.Json` indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref:System.Text.Json.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="2fbab-117">Um Zahlen in Anführungszeichen für bestimmte Eigenschaften, Felder oder Typen zuzulassen oder zu schreiben, verwenden Sie das Attribut [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).</span><span class="sxs-lookup"><span data-stu-id="2fbab-117">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="2fbab-118">`System.Text.Json` in .NET Core 3.1 unterstützt keine Serialisierung oder Deserialisierung von Zahlen in Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="2fbab-118">`System.Text.Json` in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="2fbab-119">Weitere Informationen finden Sie unter [Zulassen oder Schreiben von Zahlen in Anführungszeichen](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span><span class="sxs-lookup"><span data-stu-id="2fbab-119">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="2fbab-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fbab-120">See also</span></span>

* [<span data-ttu-id="2fbab-121">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="2fbab-121">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="2fbab-122">Instanziieren von JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="2fbab-122">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="2fbab-123">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="2fbab-123">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="2fbab-124">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="2fbab-124">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="2fbab-125">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2fbab-125">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="2fbab-126">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="2fbab-126">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="2fbab-127">Beibehalten zirkulärer Verweise</span><span class="sxs-lookup"><span data-stu-id="2fbab-127">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="2fbab-128">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="2fbab-128">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="2fbab-129">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="2fbab-129">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="2fbab-130">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="2fbab-130">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
