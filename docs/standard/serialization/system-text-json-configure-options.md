---
title: Instanziieren von JsonSerializerOptions mit System.Text.Json
description: Erfahren Sie, wie Sie JsonSerializerOptions-Instanzen durch Kopieren vorhandener Instanzen oder mit Webstandards instanziieren können.
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
ms.openlocfilehash: 0febfe15f36856f10699fd327fb17c146277eb9b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439810"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a><span data-ttu-id="85fbc-103">Instanziieren von JsonSerializerOptions-Instanzen mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="85fbc-103">How to instantiate JsonSerializerOptions instances with System.Text.Json</span></span>

<span data-ttu-id="85fbc-104">In diesem Artikel erfahren Sie, wie Sie <xref:System.Text.Json.JsonSerializerOptions>-Instanzen durch Kopieren vorhandener Instanzen oder mit Webstandards instanziieren können.</span><span class="sxs-lookup"><span data-stu-id="85fbc-104">In this article, you'll learn how to instantiate <xref:System.Text.Json.JsonSerializerOptions> instances by copying existing instances or with web defaults.</span></span>

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="85fbc-105">Kopieren von JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="85fbc-105">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="85fbc-106">Es gibt einen [JsonSerializerOptions-Konstruktor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)), mit dem Sie eine neue Instanz mit den Optionen einer vorhandenen Instanz erstellen können, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="85fbc-106">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="85fbc-107">Ein Konstruktor des Typs `JsonSerializerOptions`, der eine vorhandene Instanz verwendet, steht in .NET Core 3.1 nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="85fbc-107">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="85fbc-108">Webstandardwerte für JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="85fbc-108">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="85fbc-109">Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:</span><span class="sxs-lookup"><span data-stu-id="85fbc-109">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="85fbc-110">Es gibt einen [JsonSerializerOptions-Konstruktor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true), mit dem Sie eine neue Instanz mit den Standardoptionen erstellen können, die ASP.NET Core für Web-Apps verwendet (siehe folgendes Beispiel):</span><span class="sxs-lookup"><span data-stu-id="85fbc-110">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="85fbc-111">Nachstehend finden Sie die Optionen, die für Web-Apps unterschiedliche Standardeinstellungen haben:</span><span class="sxs-lookup"><span data-stu-id="85fbc-111">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="85fbc-112">Ein Konstruktor des Typs `JsonSerializerOptions`, der eine Gruppe von Standardwerten angibt, steht in .NET Core 3.1 nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="85fbc-112">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="85fbc-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85fbc-113">See also</span></span>

* [<span data-ttu-id="85fbc-114">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="85fbc-114">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="85fbc-115">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="85fbc-115">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="85fbc-116">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="85fbc-116">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="85fbc-117">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="85fbc-117">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="85fbc-118">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="85fbc-118">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="85fbc-119">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="85fbc-119">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="85fbc-120">Beibehalten zirkulärer Verweise</span><span class="sxs-lookup"><span data-stu-id="85fbc-120">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="85fbc-121">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="85fbc-121">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="85fbc-122">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="85fbc-122">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="85fbc-123">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="85fbc-123">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
