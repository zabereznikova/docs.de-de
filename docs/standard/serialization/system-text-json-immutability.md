---
title: Verwenden unveränderlicher Typen und nicht öffentlicher Accessoren mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET unveränderliche Typen und nicht öffentliche Accessoren beim Serialisieren in und Deserialisieren aus JSON verwenden können.
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
ms.openlocfilehash: ff8ecec0d70c877b7cbbd0297b85f0d9578ab828
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008824"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a><span data-ttu-id="56367-103">Verwenden unveränderlicher Typen und nicht öffentlicher Accessoren mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="56367-103">How to use immutable types and non-public accessors with System.Text.Json</span></span>

<span data-ttu-id="56367-104">In diesem Artikel erfahren Sie, wie Sie unveränderliche Typen, z. B. Datensätze, mit dem `System.Text.Json`-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="56367-104">In this article, you will learn how to use immutable types, such as Records, with the `System.Text.Json` namespace.</span></span>

## <a name="immutable-types-and-records"></a><span data-ttu-id="56367-105">Unveränderliche Typen und Datensätze</span><span class="sxs-lookup"><span data-stu-id="56367-105">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="56367-106">`System.Text.Json` kann einen parametrisierten Konstruktor verwenden, der es ermöglicht, eine unveränderliche Klasse oder Struktur zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="56367-106">`System.Text.Json` can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="56367-107">Wenn für eine Klasse der einzige Konstruktor ein parametrisierter ist, wird dieser Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="56367-107">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="56367-108">Geben Sie für eine Struktur oder Klasse mit mehreren Konstruktoren den zu verwendenden Konstruktor an, indem Sie das Attribut [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) anwenden.</span><span class="sxs-lookup"><span data-stu-id="56367-108">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="56367-109">Wenn das Attribut nicht verwendet wird, wird, sofern vorhanden, stets ein öffentlicher parameterloser Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="56367-109">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="56367-110">Das Attribut kann nur mit öffentlichen Konstruktoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56367-110">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="56367-111">Im folgenden Beispiel wird das Attribut `[JsonConstructor]` hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="56367-111">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="56367-112">Datensätze in C# 9 werden, wie im folgenden Beispiel gezeigt, ebenfalls unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56367-112">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="56367-113">Informationen zu Typen, die unveränderlich sind, weil alle ihre Eigenschaftssetter nicht öffentlich sind, finden Sie im folgenden Abschnitt über [nicht öffentliche Eigenschaftenaccessoren](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="56367-113">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="56367-114">`JsonConstructorAttribute` und C# 9-Datensätze werden in .NET Core 3.1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="56367-114">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="56367-115">Nicht öffentliche Eigenschaftenaccessoren</span><span class="sxs-lookup"><span data-stu-id="56367-115">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="56367-116">Um die Verwendung eines nicht öffentlichen Eigenschaftenaccessors zu aktivieren, verwenden Sie das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="56367-116">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="56367-117">Nicht öffentliche Eigenschaftenaccessoren werden in .NET Core 3.1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="56367-117">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="56367-118">Weitere Informationen finden Sie im Artikel [Migration von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="56367-118">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="56367-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56367-119">See also</span></span>

* [<span data-ttu-id="56367-120">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="56367-120">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="56367-121">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="56367-121">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="56367-122">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="56367-122">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="56367-123">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="56367-123">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="56367-124">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="56367-124">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="56367-125">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="56367-125">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="56367-126">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="56367-126">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="56367-127">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="56367-127">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="56367-128">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="56367-128">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="56367-129">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="56367-129">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="56367-130">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="56367-130">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="56367-131">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="56367-131">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="56367-132">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="56367-132">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="56367-133">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="56367-133">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="56367-134">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="56367-134">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="56367-135">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="56367-135">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="56367-136">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="56367-136">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
