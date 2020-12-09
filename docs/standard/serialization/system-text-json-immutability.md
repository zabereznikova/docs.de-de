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
ms.openlocfilehash: d3e61d44ce22b7f50838b6d3ba9cf64004bd3725
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439770"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a><span data-ttu-id="64c17-103">Verwenden unveränderlicher Typen und nicht öffentlicher Accessoren mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="64c17-103">How to use immutable types and non-public accessors with System.Text.Json</span></span>

<span data-ttu-id="64c17-104">In diesem Artikel erfahren Sie, wie Sie unveränderliche Typen, z. B. Datensätze, mit dem `System.Text.Json`-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="64c17-104">In this article, you will learn how to use immutable types, such as Records, with the `System.Text.Json` namespace.</span></span>

## <a name="immutable-types-and-records"></a><span data-ttu-id="64c17-105">Unveränderliche Typen und Datensätze</span><span class="sxs-lookup"><span data-stu-id="64c17-105">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="64c17-106">`System.Text.Json` kann einen parametrisierten Konstruktor verwenden, der es ermöglicht, eine unveränderliche Klasse oder Struktur zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="64c17-106">`System.Text.Json` can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="64c17-107">Wenn für eine Klasse der einzige Konstruktor ein parametrisierter ist, wird dieser Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="64c17-107">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="64c17-108">Geben Sie für eine Struktur oder Klasse mit mehreren Konstruktoren den zu verwendenden Konstruktor an, indem Sie das Attribut [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) anwenden.</span><span class="sxs-lookup"><span data-stu-id="64c17-108">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="64c17-109">Wenn das Attribut nicht verwendet wird, wird, sofern vorhanden, stets ein öffentlicher parameterloser Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="64c17-109">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="64c17-110">Das Attribut kann nur mit öffentlichen Konstruktoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64c17-110">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="64c17-111">Im folgenden Beispiel wird das Attribut `[JsonConstructor]` hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="64c17-111">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="64c17-112">Datensätze in C# 9 werden, wie im folgenden Beispiel gezeigt, ebenfalls unterstützt:</span><span class="sxs-lookup"><span data-stu-id="64c17-112">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="64c17-113">Informationen zu Typen, die unveränderlich sind, weil alle ihre Eigenschaftssetter nicht öffentlich sind, finden Sie im folgenden Abschnitt über [nicht öffentliche Eigenschaftenaccessoren](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="64c17-113">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="64c17-114">`JsonConstructorAttribute` und C# 9-Datensätze werden in .NET Core 3.1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="64c17-114">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="64c17-115">Nicht öffentliche Eigenschaftenaccessoren</span><span class="sxs-lookup"><span data-stu-id="64c17-115">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="64c17-116">Um die Verwendung eines nicht öffentlichen Eigenschaftenaccessors zu aktivieren, verwenden Sie das Attribut [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="64c17-116">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="64c17-117">Nicht öffentliche Eigenschaftenaccessoren werden in .NET Core 3.1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="64c17-117">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="64c17-118">Weitere Informationen finden Sie im Artikel [Migration von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="64c17-118">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="64c17-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64c17-119">See also</span></span>

* [<span data-ttu-id="64c17-120">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="64c17-120">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="64c17-121">Instanziieren von JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="64c17-121">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="64c17-122">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="64c17-122">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="64c17-123">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="64c17-123">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="64c17-124">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="64c17-124">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="64c17-125">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="64c17-125">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="64c17-126">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="64c17-126">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="64c17-127">Beibehalten zirkulärer Verweise</span><span class="sxs-lookup"><span data-stu-id="64c17-127">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="64c17-128">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="64c17-128">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="64c17-129">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="64c17-129">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
