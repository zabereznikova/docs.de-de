---
title: Instanziieren von JsonSerializerOptions mit System.Text.Json
description: Hier erfahren Sie, wie Sie Leistungsprobleme vermeiden und vorhandene Konstruktoren für JsonSerializerOptions-Instanzen verwenden.
ms.date: 12/02/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 5f32e1369e58dd9550f28abc822f187dee46c022
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009832"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a><span data-ttu-id="1351a-103">Instanziieren von JsonSerializerOptions-Instanzen mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="1351a-103">How to instantiate JsonSerializerOptions instances with System.Text.Json</span></span>

<span data-ttu-id="1351a-104">In diesem Artikel wird erläutert, wie Sie Leistungsprobleme vermeiden, die bei der Verwendung von <xref:System.Text.Json.JsonSerializerOptions> auftreten können.</span><span class="sxs-lookup"><span data-stu-id="1351a-104">This article explains how to avoid performance problems when you use <xref:System.Text.Json.JsonSerializerOptions>.</span></span> <span data-ttu-id="1351a-105">Zudem wird die Verwendung der vorhandenen parametrisierten Konstruktoren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1351a-105">It also shows how to use the parameterized constructors that are available.</span></span>

## <a name="reuse-jsonserializeroptions-instances"></a><span data-ttu-id="1351a-106">Wiederverwenden von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="1351a-106">Reuse JsonSerializerOptions instances</span></span>

<span data-ttu-id="1351a-107">Wenn Sie `JsonSerializerOptions` wiederholt mit den gleichen Optionen verwenden, sollten Sie nicht bei jeder Verwendung eine neue `JsonSerializerOptions`-Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="1351a-107">If you use `JsonSerializerOptions` repeatedly with the same options, don't create a new `JsonSerializerOptions` instance each time you use it.</span></span> <span data-ttu-id="1351a-108">Verwenden Sie für jeden Aufruf dieselbe Instanz.</span><span class="sxs-lookup"><span data-stu-id="1351a-108">Reuse the same instance for every call.</span></span> <span data-ttu-id="1351a-109">Dieser Leitfaden gilt für Code, den Sie für benutzerdefinierte Konverter und Aufrufe von <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> oder <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> schreiben.</span><span class="sxs-lookup"><span data-stu-id="1351a-109">This guidance applies to code you write for custom converters and when you call <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1351a-110">Der folgende Code veranschaulicht die Leistungseinbußen bei der Verwendung neuer JsonSerializerOptions-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="1351a-110">The following code demonstrates the performance penalty for using new options instances.</span></span>

:::code language="csharp" source="snippets/system-text-json-configure-options/csharp/ReuseOptionsInstances.cs":::

<span data-ttu-id="1351a-111">Der vorangehende Code serialisiert ein kleines Objekt 100.000-mal mit derselben JsonSerializerOptions-Instanz.</span><span class="sxs-lookup"><span data-stu-id="1351a-111">The preceding code serializes a small object 100,000 times using the same options instance.</span></span> <span data-ttu-id="1351a-112">Anschließend wird dasselbe Objekt noch einmal genauso oft serialisiert, doch jedes Mal wird eine neue JsonSerializerOptions-Instanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="1351a-112">Then it serializes the same object the same number of times and creates a new options instance each time.</span></span> <span data-ttu-id="1351a-113">Der Laufzeitunterschied liegt bei 190 Millisekunden im Vergleich zu 40.140 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="1351a-113">A typical run time difference is 190 compared to 40,140 milliseconds.</span></span> <span data-ttu-id="1351a-114">Wenn Sie mehr Iterationen durchführen, wird der Unterschied sogar noch größer.</span><span class="sxs-lookup"><span data-stu-id="1351a-114">The difference is even greater if you increase the number of iterations.</span></span>

<span data-ttu-id="1351a-115">Das Serialisierungsmodul durchläuft während der ersten Serialisierung jedes Typs im Objektgraph eine Aufwärmphase, wenn eine neue JsonSerializerOptions-Instanz übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="1351a-115">The serializer undergoes a warm-up phase during the first serialization of each type in the object graph when a new options instance is passed to it.</span></span> <span data-ttu-id="1351a-116">Diese Aufwärmphase beinhaltet eine Zwischenspeicherung der Metadaten, die für die Serialisierung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="1351a-116">This warm-up includes creating a cache of metadata that is needed for serialization.</span></span> <span data-ttu-id="1351a-117">Diese Metadaten enthalten beispielsweise Delegaten für Eigenschaftengetter und -setter, Konstruktorargumente oder angegebene Attribute.</span><span class="sxs-lookup"><span data-stu-id="1351a-117">The metadata includes delegates to property getters, setters, constructor arguments, specified attributes, and so forth.</span></span> <span data-ttu-id="1351a-118">Dieser Metadatencache wird in der JsonSerializerOptions-Instanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1351a-118">This metadata cache is stored in the options instance.</span></span> <span data-ttu-id="1351a-119">Die Aufwärmphase und die Cacheerstellung erfolgen auch bei der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="1351a-119">The same warm-up process and cache applies to deserialization.</span></span>

<span data-ttu-id="1351a-120">Die Größe des Metadatencaches in einer `JsonSerializerOptions`-Instanz hängt von der Anzahl der zu serialisierenden Typen ab.</span><span class="sxs-lookup"><span data-stu-id="1351a-120">The size of the metadata cache in a `JsonSerializerOptions` instance depends on the number of types to be serialized.</span></span> <span data-ttu-id="1351a-121">Wenn Sie viele verschiedene Typen (z. B. dynamisch generierte Typen) an das Serialisierungsmodul übergeben, nimmt die Cachegröße weiter zu, und eine `OutOfMemoryException`-Ausnahme kann auftreten.</span><span class="sxs-lookup"><span data-stu-id="1351a-121">If you pass numerous types—for example, dynamically generated types—to the serializer, the cache size will continue to grow and can end up causing an `OutOfMemoryException`.</span></span>

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="1351a-122">Kopieren von JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="1351a-122">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1351a-123">Es gibt einen [JsonSerializerOptions-Konstruktor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)), mit dem Sie eine neue Instanz mit den Optionen einer vorhandenen Instanz erstellen können, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1351a-123">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1351a-124">Ein Konstruktor des Typs `JsonSerializerOptions`, der eine vorhandene Instanz verwendet, steht in .NET Core 3.1 nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1351a-124">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="1351a-125">Webstandardwerte für JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="1351a-125">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1351a-126">Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:</span><span class="sxs-lookup"><span data-stu-id="1351a-126">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="1351a-127">Es gibt einen [JsonSerializerOptions-Konstruktor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true), mit dem Sie eine neue Instanz mit den Standardoptionen erstellen können, die ASP.NET Core für Web-Apps verwendet (siehe folgendes Beispiel):</span><span class="sxs-lookup"><span data-stu-id="1351a-127">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1351a-128">Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:</span><span class="sxs-lookup"><span data-stu-id="1351a-128">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="1351a-129">Ein Konstruktor des Typs `JsonSerializerOptions`, der eine Gruppe von Standardwerten angibt, steht in .NET Core 3.1 nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1351a-129">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="1351a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1351a-130">See also</span></span>

* [<span data-ttu-id="1351a-131">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="1351a-131">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1351a-132">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="1351a-132">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="1351a-133">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="1351a-133">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="1351a-134">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="1351a-134">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="1351a-135">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1351a-135">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="1351a-136">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="1351a-136">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="1351a-137">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="1351a-137">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="1351a-138">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="1351a-138">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="1351a-139">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="1351a-139">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="1351a-140">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1351a-140">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="1351a-141">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="1351a-141">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="1351a-142">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="1351a-142">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="1351a-143">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="1351a-143">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="1351a-144">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1351a-144">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="1351a-145">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1351a-145">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="1351a-146">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1351a-146">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="1351a-147">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="1351a-147">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
