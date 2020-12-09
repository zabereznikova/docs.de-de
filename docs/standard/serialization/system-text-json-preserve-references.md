---
title: Beibehalten von Verweisen mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET beim Serialisieren in und Deserialisieren aus JSON Verweise beibehalten und Zirkelbezüge behandeln.
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
ms.openlocfilehash: 9254ca261c7d748c04c311fa56359014f752ff31
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439789"
---
# <a name="how-to-handle-circular-references-with-no-locsystemtextjson"></a><span data-ttu-id="24bb2-103">Behandeln von Zirkelbezügen mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="24bb2-103">How to handle circular references with System.Text.Json</span></span>

<span data-ttu-id="24bb2-104">In diesem Artikel erfahren Sie, wie Zirkelbezüge mit dem `System.Text.Json`-Namespace behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="24bb2-104">In this article, you will learn how to handle circular references with the `System.Text.Json` namespace.</span></span>

## <a name="preserve-references-and-handle-circular-references"></a><span data-ttu-id="24bb2-105">Beibehalten von Verweisen und Behandeln von Zirkelbezügen</span><span class="sxs-lookup"><span data-stu-id="24bb2-105">Preserve references and handle circular references</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="24bb2-106">Um Verweise beizubehalten und Zirkelbezüge zu behandeln, legen Sie <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> auf <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="24bb2-106">To preserve references and handle circular references, set <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> to <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="24bb2-107">Diese Einstellung bewirkt folgendes Verhalten:</span><span class="sxs-lookup"><span data-stu-id="24bb2-107">This setting causes the following behavior:</span></span>

* <span data-ttu-id="24bb2-108">Beim Serialisieren:</span><span class="sxs-lookup"><span data-stu-id="24bb2-108">On serialize:</span></span>

  <span data-ttu-id="24bb2-109">Beim Schreiben komplexer Typen schreibt das Serialisierungsmodul auch Metadateneigenschaften (`$id`, `$values` und `$ref`).</span><span class="sxs-lookup"><span data-stu-id="24bb2-109">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="24bb2-110">Beim Deserialisieren:</span><span class="sxs-lookup"><span data-stu-id="24bb2-110">On deserialize:</span></span>

  <span data-ttu-id="24bb2-111">Metadaten werden erwartet (obwohl nicht zwingend erforderlich), und der Deserialisierer versucht, sie zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="24bb2-111">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="24bb2-112">Der folgende Code veranschaulicht die Verwendung der Einstellung `Preserve`.</span><span class="sxs-lookup"><span data-stu-id="24bb2-112">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="24bb2-113">Dieses Feature kann nicht verwendet werden, um Wert- oder unveränderliche Typen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="24bb2-113">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="24bb2-114">Bei der Deserialisierung wird die Instanz eines unveränderlichen Typs erstellt, nachdem die gesamten Nutzdaten gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="24bb2-114">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="24bb2-115">Daher wäre es unmöglich, dieselbe Instanz zu deserialisieren, wenn ein Verweis darauf in den JSON-Nutzdaten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="24bb2-115">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="24bb2-116">Für Werttypen, unveränderliche Typen und Arrays werden keine Verweismetadaten serialisiert.</span><span class="sxs-lookup"><span data-stu-id="24bb2-116">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="24bb2-117">Bei der Deserialisierung wird eine Ausnahme ausgelöst, wenn `$ref` oder `$id` gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="24bb2-117">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="24bb2-118">Werttypen ignorieren jedoch `$id` (und `$values` im Falle von Sammlungen), um die Deserialisierung von Nutzdaten zu ermöglichen, die mit Newtonsoft.Json serialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="24bb2-118">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using Newtonsoft.Json.</span></span>  <span data-ttu-id="24bb2-119">Newtonsoft.Json serialisiert die Metadaten für solche Typen.</span><span class="sxs-lookup"><span data-stu-id="24bb2-119">Newtonsoft.Json does serialize metadata for such types.</span></span>

<span data-ttu-id="24bb2-120">Um festzustellen, ob Objekte gleich sind, wird <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType> von System.Text.Json verwendet. Dabei wird beim Vergleich zweier Objektinstanzen die Verweisgleichheit (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) anstelle der Wertgleichheit (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>) verwendet.</span><span class="sxs-lookup"><span data-stu-id="24bb2-120">To determine if objects are equal, System.Text.Json uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="24bb2-121">Weitere Informationen zur Serialisierung und Deserialisierung von Verweisen finden Sie unter <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="24bb2-121">For more information about how references are serialized and deserialized, see <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="24bb2-122">Die <xref:System.Text.Json.Serialization.ReferenceResolver>-Klasse definiert das Verhalten bei Beibehaltung von Verweisen für Serialisierung und Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="24bb2-122">The <xref:System.Text.Json.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="24bb2-123">Erstellen Sie eine abgeleitete Klasse, um benutzerdefiniertes Verhalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="24bb2-123">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="24bb2-124">Ein Beispiel finden Sie unter [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span><span class="sxs-lookup"><span data-stu-id="24bb2-124">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="24bb2-125">System.Text.Json in .NET Core 3.1 unterstützt nur die Serialisierung nach Wert und löst bei Zirkelbezügen eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="24bb2-125">System.Text.Json in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="24bb2-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24bb2-126">See also</span></span>

* [<span data-ttu-id="24bb2-127">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="24bb2-127">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="24bb2-128">Instanziieren von JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="24bb2-128">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="24bb2-129">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="24bb2-129">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="24bb2-130">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="24bb2-130">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="24bb2-131">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="24bb2-131">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="24bb2-132">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="24bb2-132">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="24bb2-133">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="24bb2-133">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="24bb2-134">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="24bb2-134">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="24bb2-135">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="24bb2-135">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="24bb2-136">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="24bb2-136">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
