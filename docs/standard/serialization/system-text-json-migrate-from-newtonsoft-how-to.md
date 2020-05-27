---
title: Migrieren von Newtonsoft.Json zu System.Text.Json – .NET
author: ''
ms.author: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: ''
helpviewer_keywords: []
ms.openlocfilehash: fe370b34d311816a815f3b2d419751ac7871f013
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703580"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a><span data-ttu-id="8d577-102">Migration von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8d577-102">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>

<span data-ttu-id="8d577-103">In diesem Artikel wird erläutert, wie Sie von [Newtonsoft.Json](https://www.newtonsoft.com/json) zu <xref:System.Text.Json> migrieren.</span><span class="sxs-lookup"><span data-stu-id="8d577-103">This article shows how to migrate from [Newtonsoft.Json](https://www.newtonsoft.com/json) to <xref:System.Text.Json>.</span></span>

<span data-ttu-id="8d577-104">Der `System.Text.Json`-Namespace bietet Funktionalitäten zum Serialisieren in und Deserialisieren aus JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="8d577-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="8d577-105">Die `System.Text.Json`-Bibliothek ist im ist im freigegebenen [.NET Core 3.0](https://aka.ms/netcore3download)-Framework enthalten.</span><span class="sxs-lookup"><span data-stu-id="8d577-105">The `System.Text.Json` library is included in the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span> <span data-ttu-id="8d577-106">Installieren Sie für andere Zielframeworks das NuGet-Paket [System.Text.Json](https://www.nuget.org/packages/System.Text.Json).</span><span class="sxs-lookup"><span data-stu-id="8d577-106">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="8d577-107">Das Paket unterstützt:</span><span class="sxs-lookup"><span data-stu-id="8d577-107">The package supports:</span></span>

* <span data-ttu-id="8d577-108">.NET Standard 2.0 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="8d577-108">.NET Standard 2.0 and later versions</span></span>
* <span data-ttu-id="8d577-109">.NET Framework 4.7.2 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="8d577-109">.NET Framework 4.7.2 and later versions</span></span>
* <span data-ttu-id="8d577-110">.NET Core 2.0, 2.1 und 2.2</span><span class="sxs-lookup"><span data-stu-id="8d577-110">.NET Core 2.0, 2.1, and 2.2</span></span>

<span data-ttu-id="8d577-111">`System.Text.Json` konzentriert sich hauptsächlich auf Leistung, Sicherheit und Einhaltung von Standards.</span><span class="sxs-lookup"><span data-stu-id="8d577-111">`System.Text.Json` focuses primarily on performance, security, and standards compliance.</span></span> <span data-ttu-id="8d577-112">Es weist einige wesentliche Unterschiede beim Standardverhalten auf und zielt nicht auf Featureparität mit `Newtonsoft.Json` ab.</span><span class="sxs-lookup"><span data-stu-id="8d577-112">It has some key differences in default behavior and doesn't aim to have feature parity with `Newtonsoft.Json`.</span></span> <span data-ttu-id="8d577-113">In einigen Szenarien verfügt `System.Text.Json` über keine integrierte Funktionalität, doch gibt es dafür empfohlene Problemumgehungen.</span><span class="sxs-lookup"><span data-stu-id="8d577-113">For some scenarios, `System.Text.Json` has no built-in functionality, but there are recommended workarounds.</span></span> <span data-ttu-id="8d577-114">In anderen Szenarien sind Problemumgehungen nicht praktikabel.</span><span class="sxs-lookup"><span data-stu-id="8d577-114">For other scenarios, workarounds are impractical.</span></span> <span data-ttu-id="8d577-115">Wenn Ihre Anwendung von einer fehlenden Funktion abhängig ist, sollten Sie erwägen, [ein Issue zu registrieren](https://github.com/dotnet/runtime/issues/new), um herauszufinden, ob Unterstützung für Ihr Szenario hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d577-115">If your application depends on a missing feature, consider [filing an issue](https://github.com/dotnet/runtime/issues/new) to find out if support for your scenario can be added.</span></span>

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

<span data-ttu-id="8d577-116">Der Großteil dieses Artikels behandelt die Verwendungsweise der <xref:System.Text.Json.JsonSerializer>-API, aber er enthält auch Anleitungen zur Verwendung der Typen <xref:System.Text.Json.JsonDocument> (der das Dokumentobjektmodell (DOM) darstellt), <xref:System.Text.Json.Utf8JsonReader> und <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="8d577-116">Most of this article is about how to use the <xref:System.Text.Json.JsonSerializer> API, but it also includes guidance on how to use the <xref:System.Text.Json.JsonDocument> (which represents the Document Object Model or DOM), <xref:System.Text.Json.Utf8JsonReader>, and <xref:System.Text.Json.Utf8JsonWriter> types.</span></span>

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a><span data-ttu-id="8d577-117">Tabelle mit Unterschieden zwischen Newtonsoft.Json und System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8d577-117">Table of differences between Newtonsoft.Json and System.Text.Json</span></span>

<span data-ttu-id="8d577-118">In der folgenden Tabelle sind die `Newtonsoft.Json`-Funktionen mit ihren Entsprechungen in `System.Text.Json` aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8d577-118">The following table lists `Newtonsoft.Json` features and `System.Text.Json` equivalents.</span></span> <span data-ttu-id="8d577-119">Die Entsprechungen lassen sich in die folgenden Kategorien einteilen:</span><span class="sxs-lookup"><span data-stu-id="8d577-119">The equivalents fall into the following categories:</span></span>

* <span data-ttu-id="8d577-120">Unterstützt durch integrierte Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="8d577-120">Supported by built-in functionality.</span></span> <span data-ttu-id="8d577-121">Um ein ähnliches Verhalten von `System.Text.Json` zu erzielen, ist möglicherweise die Verwendung eines Attributs oder einer globalen Option erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8d577-121">Getting similar behavior from `System.Text.Json` may require the use of an attribute or global option.</span></span>
* <span data-ttu-id="8d577-122">Nicht unterstützt, Problemumgehung ist möglich.</span><span class="sxs-lookup"><span data-stu-id="8d577-122">Not supported, workaround is possible.</span></span> <span data-ttu-id="8d577-123">Die Problemumgehungen sind [benutzerdefinierte Konverter](system-text-json-converters-how-to.md), die möglicherweise keine vollständige Parität mit der `Newtonsoft.Json`-Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-123">The workarounds are [custom converters](system-text-json-converters-how-to.md), which may not provide complete parity with `Newtonsoft.Json` functionality.</span></span> <span data-ttu-id="8d577-124">Für einige davon wird Beispielcode als Beispiele bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8d577-124">For some of these, sample code is provided as examples.</span></span> <span data-ttu-id="8d577-125">Wenn Sie von diesen `Newtonsoft.Json`-Funktionen abhängig sind, erfordert die Migration Änderungen an Ihren .NET-Objektmodellen oder andere Codeänderungen.</span><span class="sxs-lookup"><span data-stu-id="8d577-125">If you rely on these `Newtonsoft.Json` features, migration will require modifications to your .NET object models or other code changes.</span></span>
* <span data-ttu-id="8d577-126">Nicht unterstützt, Problemumgehung ist nicht praktikabel oder nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="8d577-126">Not supported, workaround is not practical or possible.</span></span> <span data-ttu-id="8d577-127">Wenn Sie von diesen `Newtonsoft.Json`-Funktionen abhängig sind, ist die Migration nicht ohne wesentliche Änderungen möglich.</span><span class="sxs-lookup"><span data-stu-id="8d577-127">If you rely on these `Newtonsoft.Json` features, migration will not be possible without significant changes.</span></span>

| <span data-ttu-id="8d577-128">Feature in Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="8d577-128">Newtonsoft.Json feature</span></span>                               | <span data-ttu-id="8d577-129">Äquivalent in System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8d577-129">System.Text.Json equivalent</span></span> |
|---
<span data-ttu-id="8d577-130">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-130">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-131">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-131">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-132">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-132">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-133">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-133">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-134">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-134">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-135">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-135">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-136">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-136">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-137">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-137">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-138">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-138">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-139">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-139">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-140">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-140">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-141">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-141">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-142">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-142">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-143">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-143">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-144">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-144">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-145">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-145">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-146">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-146">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-147">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-147">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-148">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-148">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-149">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-149">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-150">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-150">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-151">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-151">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-152">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-152">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-153">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-153">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-154">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-154">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-155">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-155">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-156">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-156">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-157">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-157">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-158">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-158">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-159">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-159">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-160">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-160">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-161">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-161">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-162">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-162">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-163">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-163">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-164">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-164">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-165">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-165">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-166">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-166">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-167">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-167">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-168">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-168">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-169">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-169">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-170">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-170">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-171">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-171">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-172">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-172">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-173">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-173">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-174">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-174">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-175">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-175">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-176">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-176">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-177">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-177">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-178">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-178">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-179">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-179">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-180">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-180">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-181">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-181">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-182">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-182">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-183">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-183">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-184">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-184">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-185">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-185">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-186">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-186">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-187">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-187">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-188">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-188">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-189">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-189">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-190">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-190">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-191">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-191">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-192">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-192">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-193">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-193">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-194">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-194">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-195">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-195">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-196">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-196">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-197">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-197">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-198">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-198">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-199">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-199">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-200">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-200">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-201">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-201">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-202">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-202">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-203">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-203">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-204">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-204">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="8d577-205">----------------------------|--- title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-205">----------------------------|--- title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-206">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-206">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-207">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-207">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-208">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-208">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-209">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-209">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-210">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-210">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-211">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-211">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-212">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-212">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-213">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-213">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-214">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-214">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-215">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-215">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-216">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-216">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-217">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-217">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-218">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-218">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-219">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-219">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-220">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-220">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-221">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-221">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-222">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-222">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-223">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-223">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-224">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-224">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-225">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-225">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-226">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-226">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-227">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-227">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-228">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-228">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-229">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-229">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-230">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-230">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-231">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-231">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-232">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-232">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-233">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-233">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-234">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-234">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-235">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-235">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-236">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-236">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-237">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-237">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="8d577-238">title: 'Migrieren von Newtonsoft.Json zu System.Text.Json – .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="8d577-238">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="8d577-239">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="8d577-239">'System.Text.Json'</span></span>
- <span data-ttu-id="8d577-240">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="8d577-240">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="8d577-241">---------------| | Deserialisierung standardmäßig ohne Beachtung der Groß-/Kleinschreibung           | ✔️ [Globale Einstellung PropertyNameCaseInsensitive](#case-insensitive-deserialization) | | Binnenmajuskel bei Eigenschaftennamen                             | ✔️ [Globale Einstellung PropertyNamingPolicy](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | Minimales Escapen von Zeichen                            | ✔️ [Striktes Escapen von Zeichen, konfigurierbar](#minimal-character-escaping) | | `NullValueHandling.Ignore` globale Einstellung             | ✔️ [Globale Option IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) | | Kommentare zulassen                                        | ✔️ [Globale Einstellung ReadCommentHandling](#comments) | | Nachstehende Kommas zulassen                                 | ✔️ [Globale Einstellung AllowTrailingCommas](#trailing-commas) | | Benutzerdefinierte Registrierung von Konvertern                         | ✔️ [Abweichende Rangfolge](#converter-registration-precedence) | | Standardmäßig keine maximale Tiefe                           | ✔️ [Maximale Standardtiefe von 64, konfigurierbar](#maximum-depth) | | Unterstützung für eine Vielzahl von Typen                    | ⚠️ [Benutzerdefinierte Konverter für einige Typen erforderlich](#types-without-built-in-support) | | Zeichenfolgen als Zahlen deserialisieren                        | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#quoted-numbers) | | `Dictionary` mit Schlüssel deserialisieren, der keine Zeichenfolge ist          | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#dictionary-with-non-string-key) | | Polymorphe Serialisierung                             | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#polymorphic-serialization) | | Polymorphe Deserialisierung                           | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#polymorphic-deserialization) | | Abgeleiteten Typ in `object`-Eigenschaften deserialisieren      | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#deserialization-of-object-properties) | | JSON-Literal `null` in Non-Nullable-Werttypen deserialisieren | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#deserialize-null-to-non-nullable-type) | | In unveränderliche Klassen und Strukturen deserialisieren          | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#deserialize-to-immutable-classes-and-structs) | | `[JsonConstructor]`-Attribut                         | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#specify-constructor-to-use) | | `Required`-Einstellung im `[JsonProperty]`-Attribut        | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#required-properties) | | `NullValueHandling`-Einstellung im `[JsonProperty]`-Attribut | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#conditionally-ignore-a-property)  | | `DefaultValueHandling`-Einstellung im `[JsonProperty]`-Attribut | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#conditionally-ignore-a-property)  | | `DefaultValueHandling` Globale Einstellung                 | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#conditionally-ignore-a-property) | | `DefaultContractResolver` zum Ausschließen von Eigenschaften       | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#conditionally-ignore-a-property) | | Einstellungen `DateTimeZoneHandling` und `DateFormatString`   | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#specify-date-format) | | Rückrufe                                             | ⚠️ [Nicht unterstützt, Umgehung, Beispiel](#callbacks) | | Unterstützung für öffentliche und nicht öffentliche Felder              | ⚠️ [Nicht unterstützt, Umgehung](#public-and-non-public-fields) | | Unterstützung für Getter und Setter für interne und private Eigenschaften | ⚠️ [Nicht unterstützt, Umgehung](#internal-and-private-property-setters-and-getters) | | `JsonConvert.PopulateObject`-Methode                   | ⚠️ [Nicht unterstützt, Umgehung](#populate-existing-objects) | | Globale Einstellung `ObjectCreationHandling`               | ⚠️ [Nicht unterstützt, Umgehung](#reuse-rather-than-replace-properties) | | Ohne Setter zu Sammlungen hinzufügen                    | ⚠️ [Nicht unterstützt, Umgehung](#add-to-collections-without-setters) | | Globale Einstellung `PreserveReferencesHandling`           | ❌ [Nicht unterstützt](#preserve-object-references-and-handle-loops) | | Globale Einstellung `ReferenceLoopHandling`                | ❌ [Nicht unterstützt](#preserve-object-references-and-handle-loops) | | Unterstützung für `System.Runtime.Serialization`-Attribute | ❌ [Nicht unterstützt](#systemruntimeserialization-attributes) | | Globale Einstellung `MissingMemberHandling`                | ❌ [Nicht unterstützt](#missingmemberhandling) | | Eigenschaftennamen ohne Anführungszeichen zulassen                   | ❌ [Nicht unterstützt](#json-strings-property-names-and-string-values) | | Einzelne Anführungszeichen um Zeichenfolgenwerte zulassen              | ❌ [Nicht unterstützt](#json-strings-property-names-and-string-values) | | JSON-Werte, die keine Zeichenfolgen sind, für Zeichenfolgeneigenschaften zulassen    | ❌ [Nicht unterstützt](#non-string-values-for-string-properties) |</span><span class="sxs-lookup"><span data-stu-id="8d577-241">---------------| | Case-insensitive deserialization by default           | ✔️ [PropertyNameCaseInsensitive global setting](#case-insensitive-deserialization) | | Camel-case property names                             | ✔️ [PropertyNamingPolicy global setting](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | Minimal character escaping                            | ✔️ [Strict character escaping, configurable](#minimal-character-escaping) | | `NullValueHandling.Ignore` global setting             | ✔️ [IgnoreNullValues global option](system-text-json-how-to.md#exclude-all-null-value-properties) | | Allow comments                                        | ✔️ [ReadCommentHandling global setting](#comments) | | Allow trailing commas                                 | ✔️ [AllowTrailingCommas global setting](#trailing-commas) | | Custom converter registration                         | ✔️ [Order of precedence differs](#converter-registration-precedence) | | No maximum depth by default                           | ✔️ [Default maximum depth 64, configurable](#maximum-depth) | | Support for a broad range of types                    | ⚠️ [Some types require custom converters](#types-without-built-in-support) | | Deserialize strings as numbers                        | ⚠️ [Not supported, workaround, sample](#quoted-numbers) | | Deserialize `Dictionary` with non-string key          | ⚠️ [Not supported, workaround, sample](#dictionary-with-non-string-key) | | Polymorphic serialization                             | ⚠️ [Not supported, workaround, sample](#polymorphic-serialization) | | Polymorphic deserialization                           | ⚠️ [Not supported, workaround, sample](#polymorphic-deserialization) | | Deserialize inferred type to `object` properties      | ⚠️ [Not supported, workaround, sample](#deserialization-of-object-properties) | | Deserialize JSON `null` literal to non-nullable value types | ⚠️ [Not supported, workaround, sample](#deserialize-null-to-non-nullable-type) | | Deserialize to immutable classes and structs          | ⚠️ [Not supported, workaround, sample](#deserialize-to-immutable-classes-and-structs) | | `[JsonConstructor]` attribute                         | ⚠️ [Not supported, workaround, sample](#specify-constructor-to-use) | | `Required` setting on `[JsonProperty]` attribute        | ⚠️ [Not supported, workaround, sample](#required-properties) | | `NullValueHandling` setting on `[JsonProperty]` attribute | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property)  | | `DefaultValueHandling` setting on `[JsonProperty]` attribute | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property)  | | `DefaultValueHandling` global setting                 | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property) | | `DefaultContractResolver` to exclude properties       | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property) | | `DateTimeZoneHandling`, `DateFormatString` settings   | ⚠️ [Not supported, workaround, sample](#specify-date-format) | | Callbacks                                             | ⚠️ [Not supported, workaround, sample](#callbacks) | | Support for public and non-public fields              | ⚠️ [Not supported, workaround](#public-and-non-public-fields) | | Support for internal and private property setters and getters | ⚠️ [Not supported, workaround](#internal-and-private-property-setters-and-getters) | | `JsonConvert.PopulateObject` method                   | ⚠️ [Not supported, workaround](#populate-existing-objects) | | `ObjectCreationHandling` global setting               | ⚠️ [Not supported, workaround](#reuse-rather-than-replace-properties) | | Add to collections without setters                    | ⚠️ [Not supported, workaround](#add-to-collections-without-setters) | | `PreserveReferencesHandling` global setting           | ❌ [Not supported](#preserve-object-references-and-handle-loops) | | `ReferenceLoopHandling` global setting                | ❌ [Not supported](#preserve-object-references-and-handle-loops) | | Support for `System.Runtime.Serialization` attributes | ❌ [Not supported](#systemruntimeserialization-attributes) | | `MissingMemberHandling` global setting                | ❌ [Not supported](#missingmemberhandling) | | Allow property names without quotes                   | ❌ [Not supported](#json-strings-property-names-and-string-values) | | Allow single quotes around string values              | ❌ [Not supported](#json-strings-property-names-and-string-values) | | Allow non-string JSON values for string properties    | ❌ [Not supported](#non-string-values-for-string-properties) |</span></span>

<span data-ttu-id="8d577-242">Dies ist keine vollständige Liste der `Newtonsoft.Json`-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8d577-242">This is not an exhaustive list of `Newtonsoft.Json` features.</span></span> <span data-ttu-id="8d577-243">Die Liste enthält viele der Szenarien, die in [GitHub-Issues](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) oder [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json)-Beiträgen angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="8d577-243">The list includes many of the scenarios that have been requested in [GitHub issues](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) or [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) posts.</span></span> <span data-ttu-id="8d577-244">Wenn Sie eine Problemumgehung für eins der hier aufgelisteten Szenarien implementieren, für das derzeit kein Beispielcode vorhanden ist, und wenn Sie Ihre Lösung teilen möchten, wählen Sie **Diese Seite** im Abschnitt **Feedback** unten auf dieser Seite aus.</span><span class="sxs-lookup"><span data-stu-id="8d577-244">If you implement a workaround for one of the scenarios listed here that doesn't currently have sample code, and if you want to share your solution, select **This page** in the **Feedback** section at the bottom of this page.</span></span> <span data-ttu-id="8d577-245">Dadurch wird ein Issue im GitHub-Repository dieser Dokumentation erstellt und dieses ebenfalls im Abschnitt **Feedback** auf dieser Seite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8d577-245">That creates an issue in this documentation's GitHub repo and lists it in the **Feedback** section on this page too.</span></span>

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a><span data-ttu-id="8d577-246">Unterschiede beim Standardverhalten von JsonSerializer im Vergleich zu Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="8d577-246">Differences in default JsonSerializer behavior compared to Newtonsoft.Json</span></span>

<span data-ttu-id="8d577-247"><xref:System.Text.Json> ist standardmäßig strikt und vermeidet jegliche Vermutung oder Interpretation im Namen des Aufrufers, womit deterministisches Verhalten betont wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-247"><xref:System.Text.Json> is strict by default and avoids any guessing or interpretation on the caller's behalf, emphasizing deterministic behavior.</span></span> <span data-ttu-id="8d577-248">Die Bibliothek ist absichtlich auf diese Weise für Leistung und Sicherheit konzipiert.</span><span class="sxs-lookup"><span data-stu-id="8d577-248">The library is intentionally designed this way for performance and security.</span></span> <span data-ttu-id="8d577-249">`Newtonsoft.Json` ist standardmäßig flexibel.</span><span class="sxs-lookup"><span data-stu-id="8d577-249">`Newtonsoft.Json` is flexible by default.</span></span> <span data-ttu-id="8d577-250">Dieser grundlegende Unterschied beim Design steht hinter vielen der folgenden spezifischen Unterschiede im Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="8d577-250">This fundamental difference in design is behind many of the following specific differences in default behavior.</span></span>

### <a name="case-insensitive-deserialization"></a><span data-ttu-id="8d577-251">Deserialisierung ohne Berücksichtigung von Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="8d577-251">Case-insensitive deserialization</span></span>

<span data-ttu-id="8d577-252">Während der Deserialisierung führt `Newtonsoft.Json` standardmäßig einen Abgleich der Eigenschaftsnamen ohne Berücksichtigung von Groß-/Kleinschreibung durch.</span><span class="sxs-lookup"><span data-stu-id="8d577-252">During deserialization, `Newtonsoft.Json` does case-insensitive property name matching by default.</span></span> <span data-ttu-id="8d577-253">Das Standardverhalten von <xref:System.Text.Json> berücksichtigt die Groß-/Kleinschreibung, was eine bessere Leistung liefert, weil ein exakter Abgleich erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8d577-253">The <xref:System.Text.Json> default is case-sensitive, which gives better performance since it's doing an exact match.</span></span> <span data-ttu-id="8d577-254">Informationen, wie Sie einen Abgleich ohne Berücksichtigung von Groß-/Kleinschreibung durchführen, finden Sie unter [Eigenschaftenabgleich ohne Berücksichtigung von Groß-/Kleinschreibung](system-text-json-how-to.md#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="8d577-254">For information about how to do case-insensitive matching, see [Case-insensitive property matching](system-text-json-how-to.md#case-insensitive-property-matching).</span></span>

<span data-ttu-id="8d577-255">Wenn Sie `System.Text.Json` indirekt durch Verwendung von ASP.NET Core verwenden, müssen Sie nichts tun, um ein Verhalten wie `Newtonsoft.Json` zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8d577-255">If you're using `System.Text.Json` indirectly by using ASP.NET Core, you don't need to do anything to get behavior like `Newtonsoft.Json`.</span></span> <span data-ttu-id="8d577-256">ASP.NET Core gibt die Einstellungen für die Verwendung von [Eigenschaftsnamen mit Camel-Case-Schreibweise](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) an sowie für den Abgleich ohne Berücksichtigung von Groß-/Kleinschreibung, wenn `System.Text.Json` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-256">ASP.NET Core specifies the settings for [camel-casing property names](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) and case-insensitive matching when it uses `System.Text.Json`.</span></span>

### <a name="minimal-character-escaping"></a><span data-ttu-id="8d577-257">Minimales Escapen von Zeichen</span><span class="sxs-lookup"><span data-stu-id="8d577-257">Minimal character escaping</span></span>

<span data-ttu-id="8d577-258">Während der Serialisierung ist `Newtonsoft.Json` relativ nachsichtig, wenn es um das Durchlassen von Zeichen geht, ohne sie zu escapen.</span><span class="sxs-lookup"><span data-stu-id="8d577-258">During serialization, `Newtonsoft.Json` is relatively permissive about letting characters through without escaping them.</span></span> <span data-ttu-id="8d577-259">Dies bedeutet, dass sie nicht durch `\uxxxx` ersetzt werden, wobei `xxxx` der Codepunkt des Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="8d577-259">That is, it doesn't replace them with `\uxxxx` where `xxxx` is the character's code point.</span></span> <span data-ttu-id="8d577-260">Wenn sie escapet werden, geschieht dies durch Ausgabe eines umgekehrten Schrägstrichs (`\`) vor dem Zeichen (z. B. wird `"` zu `\"`).</span><span class="sxs-lookup"><span data-stu-id="8d577-260">Where it does escape them, it does so by emitting a `\` before the character (for example, `"` becomes `\"`).</span></span> <span data-ttu-id="8d577-261"><xref:System.Text.Json> escapet standardmäßig mehr Zeichen, um eine tief greifenden Abwehr als Schutz vor Cross-Site Scripting (XSS)- oder Information-Disclosure-Angriffen (Veröffentlichung von Informationen) zu bieten, wobei dies durch Verwendung der Abfolge von sechs Zeichen erzielt wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-261"><xref:System.Text.Json> escapes more characters by default to provide defense-in-depth protections against cross-site scripting (XSS) or information-disclosure attacks and does so by using the six-character sequence.</span></span> <span data-ttu-id="8d577-262">`System.Text.Json` escapet standardmäßig alle Nicht-ASCII-Zeichen, sodass Sie nichts machen müssen, wenn Sie `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json` verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d577-262">`System.Text.Json` escapes all non-ASCII characters by default, so you don't need to do anything if you're using `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json`.</span></span> <span data-ttu-id="8d577-263">`System.Text.Json` escapet außerdem standardmäßig HTML-abhängige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8d577-263">`System.Text.Json` also escapes HTML-sensitive characters, by default.</span></span> <span data-ttu-id="8d577-264">Informationen, wie Sie das Standardverhalten von `System.Text.Json` außer Kraft setzen können, finden Sie unter [Anpassen der Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).</span><span class="sxs-lookup"><span data-stu-id="8d577-264">For information about how to override the default `System.Text.Json` behavior, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="comments"></a><span data-ttu-id="8d577-265">Kommentare</span><span class="sxs-lookup"><span data-stu-id="8d577-265">Comments</span></span>

<span data-ttu-id="8d577-266">Während der Deserialisierung ignoriert `Newtonsoft.Json` standardmäßig Kommentare in der JSON-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d577-266">During deserialization, `Newtonsoft.Json` ignores comments in the JSON by default.</span></span> <span data-ttu-id="8d577-267">Das Standardverhalten von <xref:System.Text.Json> besteht im Auslösen von Ausnahmen für Kommentare, weil die Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) diese nicht umfasst.</span><span class="sxs-lookup"><span data-stu-id="8d577-267">The <xref:System.Text.Json> default is to throw exceptions for comments because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't include them.</span></span> <span data-ttu-id="8d577-268">Informationen, wie Sie Kommentare zulassen können, finden Sie unter [Zulassen von Kommentaren und nachfolgenden Kommas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="8d577-268">For information about how to allow comments, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span>

### <a name="trailing-commas"></a><span data-ttu-id="8d577-269">Nachfolgende Kommas</span><span class="sxs-lookup"><span data-stu-id="8d577-269">Trailing commas</span></span>

<span data-ttu-id="8d577-270">Während der Deserialisierung ignoriert `Newtonsoft.Json` standardmäßig nachfolgende Kommas.</span><span class="sxs-lookup"><span data-stu-id="8d577-270">During deserialization, `Newtonsoft.Json` ignores trailing commas by default.</span></span> <span data-ttu-id="8d577-271">Es ignoriert ferner mehrere nachfolgende Kommas (z. B. `[{"Color":"Red"},{"Color":"Green"},,]`).</span><span class="sxs-lookup"><span data-stu-id="8d577-271">It also ignores multiple trailing commas (for example, `[{"Color":"Red"},{"Color":"Green"},,]`).</span></span> <span data-ttu-id="8d577-272">Das Standardverhalten von <xref:System.Text.Json> besteht im Auslösen von Ausnahmen für nachfolgende Kommas, weil die Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) diese nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="8d577-272">The <xref:System.Text.Json> default is to throw exceptions for trailing commas because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span> <span data-ttu-id="8d577-273">Informationen, wie Sie `System.Text.Json` dazu bringen, diese zu akzeptieren, finden Sie unter [Zulassen von Kommentaren und nachfolgenden Kommas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="8d577-273">For information about how to make `System.Text.Json` accept them, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span> <span data-ttu-id="8d577-274">Es gibt keine Möglichkeit, mehrere nachfolgende Kommas zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="8d577-274">There's no way to allow multiple trailing commas.</span></span>

### <a name="converter-registration-precedence"></a><span data-ttu-id="8d577-275">Rangfolge für die Registrierung von Konvertern</span><span class="sxs-lookup"><span data-stu-id="8d577-275">Converter registration precedence</span></span>

<span data-ttu-id="8d577-276">Die Rangfolge der Registrierung von benutzerdefinierten Konvertern in `Newtonsoft.Json` ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8d577-276">The `Newtonsoft.Json` registration precedence for custom converters is as follows:</span></span>

* <span data-ttu-id="8d577-277">Attribut auf Eigenschaftsebene</span><span class="sxs-lookup"><span data-stu-id="8d577-277">Attribute on property</span></span>
* <span data-ttu-id="8d577-278">Attribut auf Typebene</span><span class="sxs-lookup"><span data-stu-id="8d577-278">Attribute on type</span></span>
* <span data-ttu-id="8d577-279">[Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)-Sammlung</span><span class="sxs-lookup"><span data-stu-id="8d577-279">[Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) collection</span></span>

<span data-ttu-id="8d577-280">Diese Reihenfolge bedeutet, dass ein benutzerdefinierter Konverter in der `Converters`-Sammlung von einem Konverter außer Kraft gesetzt wird, der durch Anwenden eines Attributs auf Typebene registriert wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-280">This order means that a custom converter in the `Converters` collection is overridden by a converter that is registered by applying an attribute at the type level.</span></span> <span data-ttu-id="8d577-281">Beide dieser Registrierungen werden von einem Attribut auf Eigenschaftsebene außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="8d577-281">Both of those registrations are overridden by an attribute at the property level.</span></span>

<span data-ttu-id="8d577-282">Die Rangfolge der Registrierung von benutzerdefinierten Konvertern in <xref:System.Text.Json> weicht hiervon ab:</span><span class="sxs-lookup"><span data-stu-id="8d577-282">The <xref:System.Text.Json> registration precedence for custom converters is different:</span></span>

* <span data-ttu-id="8d577-283">Attribut auf Eigenschaftsebene</span><span class="sxs-lookup"><span data-stu-id="8d577-283">Attribute on property</span></span>
* <span data-ttu-id="8d577-284"><xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung</span><span class="sxs-lookup"><span data-stu-id="8d577-284"><xref:System.Text.Json.JsonSerializerOptions.Converters> collection</span></span>
* <span data-ttu-id="8d577-285">Attribut auf Typebene</span><span class="sxs-lookup"><span data-stu-id="8d577-285">Attribute on type</span></span>

<span data-ttu-id="8d577-286">Der Unterschied besteht hierbei darin, dass ein benutzerdefinierter Konverter in der `Converters`-Sammlung ein Attribut auf Typebene außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="8d577-286">The difference here is that a custom converter in the `Converters` collection overrides an attribute at the type level.</span></span> <span data-ttu-id="8d577-287">Die Absicht hinter dieser Rangfolge ist es, dass Änderungen zur Laufzeit eine zur Entwurfszeit getroffene Auswahl außer Kraft setzen sollen.</span><span class="sxs-lookup"><span data-stu-id="8d577-287">The intention behind this order of precedence is to make run-time changes override design-time choices.</span></span> <span data-ttu-id="8d577-288">Diese Rangfolge lässt sich nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="8d577-288">There's no way to change the precedence.</span></span>

<span data-ttu-id="8d577-289">Weitere Informationen zur Registrierung benutzerdefinierter Konverter finden Sie unter [Registrieren eines benutzerdefinierten Konverters](system-text-json-converters-how-to.md#register-a-custom-converter).</span><span class="sxs-lookup"><span data-stu-id="8d577-289">For more information about custom converter registration, see [Register a custom converter](system-text-json-converters-how-to.md#register-a-custom-converter).</span></span>

### <a name="maximum-depth"></a><span data-ttu-id="8d577-290">Maximale Tiefe</span><span class="sxs-lookup"><span data-stu-id="8d577-290">Maximum depth</span></span>

<span data-ttu-id="8d577-291">`Newtonsoft.Json` besitzt kein standardmäßiges Limit für die maximale Tiefe.</span><span class="sxs-lookup"><span data-stu-id="8d577-291">`Newtonsoft.Json` doesn't have a maximum depth limit by default.</span></span> <span data-ttu-id="8d577-292">Für <xref:System.Text.Json> gibt es ein Standardlimit von 64, das sich durch Festlegen von <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType> konfigurieren lässt.</span><span class="sxs-lookup"><span data-stu-id="8d577-292">For <xref:System.Text.Json> there's a default limit  of 64, and it's configurable by setting <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.</span></span>

### <a name="json-strings-property-names-and-string-values"></a><span data-ttu-id="8d577-293">JSON-Zeichenfolgen (Eigenschaftsnamen und Zeichenfolgenwerte)</span><span class="sxs-lookup"><span data-stu-id="8d577-293">JSON strings (property names and string values)</span></span>

<span data-ttu-id="8d577-294">Während der Deserialisierung akzeptiert `Newtonsoft.Json` Eigenschaftsnamen, die in doppelten oder einfachen Anführungszeichen stehen oder gar keine Anführungszeichen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8d577-294">During deserialization, `Newtonsoft.Json` accepts property names surrounded by double quotes, single quotes, or without quotes.</span></span> <span data-ttu-id="8d577-295">Es akzeptiert Zeichenfolgenwerte, die in doppelten oder einfachen Anführungszeichen stehen.</span><span class="sxs-lookup"><span data-stu-id="8d577-295">It accepts string values surrounded by double quotes or single quotes.</span></span> <span data-ttu-id="8d577-296">`Newtonsoft.Json` akzeptiert beispielsweise folgendes JSON:</span><span class="sxs-lookup"><span data-stu-id="8d577-296">For example, `Newtonsoft.Json` accepts the following JSON:</span></span>

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

<span data-ttu-id="8d577-297">`System.Text.Json` akzeptiert nur Eigenschaftsnamen und Zeichenfolgenwerte, die in doppelten Anführungszeichen stehen, weil dieses Format von der Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) gefordert wird und das einzige Format ist, das als gültiges JSON-Format gilt.</span><span class="sxs-lookup"><span data-stu-id="8d577-297">`System.Text.Json` only accepts property names and string values in double quotes because that format is required by the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification and is the only format considered valid JSON.</span></span>

<span data-ttu-id="8d577-298">Ein in einfache Anführungszeichen eingeschlossener Wert führt zu einer [JsonException](xref:System.Text.Json.JsonException) mit folgender Meldung:</span><span class="sxs-lookup"><span data-stu-id="8d577-298">A value enclosed in single quotes results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a><span data-ttu-id="8d577-299">Werte, die keine Zeichenfolgen sind, für Zeichenfolgeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8d577-299">Non-string values for string properties</span></span>

<span data-ttu-id="8d577-300">`Newtonsoft.Json` akzeptiert Werte, die keine Zeichenfolgen sind, z. B. eine Zahl oder die Literale `true` und `false`, für die Deserialisierung von Eigenschaften vom Typ „String“ (Zeichenfolge).</span><span class="sxs-lookup"><span data-stu-id="8d577-300">`Newtonsoft.Json` accepts non-string values, such as a number or the literals `true` and `false`, for deserialization to properties of type string.</span></span> <span data-ttu-id="8d577-301">Im Folgenden finden Sie ein JSON-Beispiel, das `Newtonsoft.Json` erfolgreich in die folgende Klasse deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="8d577-301">Here's an example of JSON that `Newtonsoft.Json` successfully deserializes to the following class:</span></span>

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

<span data-ttu-id="8d577-302">`System.Text.Json` deserialisiert Werte, die keine Zeichenfolgen sind, nicht in Zeichenfolgeneigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8d577-302">`System.Text.Json` doesn't deserialize non-string values into string properties.</span></span> <span data-ttu-id="8d577-303">Ein für ein Zeichenfolgenfeld empfangener Wert, der keine Zeichenfolge ist, führt zu einer [JsonException](xref:System.Text.Json.JsonException) mit folgender Meldung:</span><span class="sxs-lookup"><span data-stu-id="8d577-303">A non-string value received for a string field results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a><span data-ttu-id="8d577-304">Szenarien, die JsonSerializer verwenden und Problemumgehungen erfordern</span><span class="sxs-lookup"><span data-stu-id="8d577-304">Scenarios using JsonSerializer that require workarounds</span></span>

<span data-ttu-id="8d577-305">Die folgenden Szenarien werden von der integrierten Funktionalität nicht unterstützt, aber es sind Problemumgehungen möglich.</span><span class="sxs-lookup"><span data-stu-id="8d577-305">The following scenarios aren't supported by built-in functionality, but workarounds are possible.</span></span> <span data-ttu-id="8d577-306">Die Problemumgehungen sind [benutzerdefinierte Konverter](system-text-json-converters-how-to.md), die möglicherweise keine vollständige Parität mit der `Newtonsoft.Json`-Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-306">The workarounds are [custom converters](system-text-json-converters-how-to.md), which may not provide complete parity with `Newtonsoft.Json` functionality.</span></span> <span data-ttu-id="8d577-307">Für einige davon wird Beispielcode als Beispiele bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8d577-307">For some of these, sample code is provided as examples.</span></span> <span data-ttu-id="8d577-308">Wenn Sie von diesen `Newtonsoft.Json`-Funktionen abhängig sind, erfordert die Migration Änderungen an Ihren .NET-Objektmodellen oder andere Codeänderungen.</span><span class="sxs-lookup"><span data-stu-id="8d577-308">If you rely on these `Newtonsoft.Json` features, migration will require modifications to your .NET object models or other code changes.</span></span>

### <a name="types-without-built-in-support"></a><span data-ttu-id="8d577-309">Typen ohne integrierte Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8d577-309">Types without built-in support</span></span>

<span data-ttu-id="8d577-310"><xref:System.Text.Json> bietet für die folgenden Typen keine integrierte Unterstützung:</span><span class="sxs-lookup"><span data-stu-id="8d577-310"><xref:System.Text.Json> doesn't provide built-in support for the following types:</span></span>

* <span data-ttu-id="8d577-311"><xref:System.Data.DataTable> und verwandte Typen</span><span class="sxs-lookup"><span data-stu-id="8d577-311"><xref:System.Data.DataTable> and related types</span></span>
* <span data-ttu-id="8d577-312">F#-Typen, z. B. [Diskriminierte Unions](../../fsharp/language-reference/discriminated-unions.md), [Datensatztypen](../../fsharp/language-reference/records.md) und [anonyme Datensatztypen](../../fsharp/language-reference/anonymous-records.md).</span><span class="sxs-lookup"><span data-stu-id="8d577-312">F# types, such as [discriminated unions](../../fsharp/language-reference/discriminated-unions.md), [record types](../../fsharp/language-reference/records.md), and [anonymous record types](../../fsharp/language-reference/anonymous-records.md).</span></span>
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <span data-ttu-id="8d577-313"><xref:System.ValueTuple> und seine zugehörigen generischen Typen</span><span class="sxs-lookup"><span data-stu-id="8d577-313"><xref:System.ValueTuple> and its associated generic types</span></span>

<span data-ttu-id="8d577-314">Benutzerdefinierte Konverter können für Typen implementiert werden, für die keine integrierte Unterstützung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8d577-314">Custom converters can be implemented for types that don't have built-in support.</span></span>

### <a name="quoted-numbers"></a><span data-ttu-id="8d577-315">Zahlen in Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="8d577-315">Quoted numbers</span></span>

<span data-ttu-id="8d577-316">`Newtonsoft.Json` kann Zahlen serialisieren oder deserialisieren, die von JSON-Zeichenfolgen (in Anführungszeichen) dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-316">`Newtonsoft.Json` can serialize or deserialize numbers represented by JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="8d577-317">Beispielsweise kann es `{"DegreesCelsius":"23"}` akzeptieren, anstelle von `{"DegreesCelsius":23}`.</span><span class="sxs-lookup"><span data-stu-id="8d577-317">For example, it can accept: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="8d577-318">Um dieses Verhalten in <xref:System.Text.Json> zu aktivieren, implementieren Sie einen benutzerdefinierten Konverter, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8d577-318">To enable that behavior in <xref:System.Text.Json>, implement a custom converter like the following example.</span></span> <span data-ttu-id="8d577-319">Der Konverter verarbeitet als `long` definierte Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8d577-319">The converter handles properties defined as `long`:</span></span>

* <span data-ttu-id="8d577-320">Er serialisiert sie als JSON-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="8d577-320">It serializes them as JSON strings.</span></span>
* <span data-ttu-id="8d577-321">Er akzeptiert während der Deserialisierung JSON-Zahlen und Zahlen in Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="8d577-321">It accepts JSON numbers and numbers within quotes while deserializing.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/LongToStringConverter.cs)]

<span data-ttu-id="8d577-322">Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) für einzelne `long`-Eigenschaften oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="8d577-322">Register this custom converter by [using an attribute](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) on individual `long` properties or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

### <a name="dictionary-with-non-string-key"></a><span data-ttu-id="8d577-323">Wörterbuch mit Schlüssel, der keine Zeichenfolgen ist</span><span class="sxs-lookup"><span data-stu-id="8d577-323">Dictionary with non-string key</span></span>

<span data-ttu-id="8d577-324">`Newtonsoft.Json` unterstützt Sammlungen vom Typ `Dictionary<TKey, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="8d577-324">`Newtonsoft.Json` supports collections of type `Dictionary<TKey, TValue>`.</span></span> <span data-ttu-id="8d577-325">Die integrierte Unterstützung für Wörterbuchsammlungen in <xref:System.Text.Json> ist auf `Dictionary<string, TValue>` beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8d577-325">The built-in support for dictionary collections in <xref:System.Text.Json> is limited to `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="8d577-326">Das heißt, der Schlüssel muss eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="8d577-326">That is, the key must be a string.</span></span>

<span data-ttu-id="8d577-327">Um ein Wörterbuch mit einem Schlüssel vom Typ „integer“ (Ganzzahl) oder einem anderen Typ zu unterstützen, erstellen Sie einen Konverter wie das Beispiel in [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="8d577-327">To support a dictionary with an integer or some other type as the key, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).</span></span>

### <a name="polymorphic-serialization"></a><span data-ttu-id="8d577-328">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8d577-328">Polymorphic serialization</span></span>

<span data-ttu-id="8d577-329">`Newtonsoft.Json` führt automatisch eine polymorphe Serialisierung durch.</span><span class="sxs-lookup"><span data-stu-id="8d577-329">`Newtonsoft.Json` automatically does polymorphic serialization.</span></span> <span data-ttu-id="8d577-330">Informationen zu den eingeschränkten polymorphen Serialisierungsfunktionen von <xref:System.Text.Json> finden Sie unter [Serialisieren von Eigenschaften abgeleiteter Klassen](system-text-json-how-to.md#serialize-properties-of-derived-classes).</span><span class="sxs-lookup"><span data-stu-id="8d577-330">For information about the limited polymorphic serialization capabilities of <xref:System.Text.Json>, see [Serialize properties of derived classes](system-text-json-how-to.md#serialize-properties-of-derived-classes).</span></span>

<span data-ttu-id="8d577-331">Die dort beschriebene Problemumgehung besteht darin, Eigenschaften zu definieren, die abgeleitete Klassen als `object`-Typ enthalten können.</span><span class="sxs-lookup"><span data-stu-id="8d577-331">The workaround described there is to define properties that may contain derived classes as type `object`.</span></span> <span data-ttu-id="8d577-332">Wenn dies nicht möglich ist, besteht eine weitere Möglichkeit darin, einen Konverter mit einer `Write`-Methode für die gesamte Vererbungstyphierarchie zu erstellen, wie im Beispiel in [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-polymorphic-deserialization) gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8d577-332">If that isn't possible, another option is to create a converter with a `Write` method for the whole inheritance type hierarchy like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="polymorphic-deserialization"></a><span data-ttu-id="8d577-333">Polymorphe Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="8d577-333">Polymorphic deserialization</span></span>

<span data-ttu-id="8d577-334">`Newtonsoft.Json` verfügt über eine `TypeNameHandling`-Einstellung, mit der dem JSON-Code beim Serialisieren Typnamen-Metadaten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-334">`Newtonsoft.Json` has a `TypeNameHandling` setting that adds type name metadata to the JSON while serializing.</span></span> <span data-ttu-id="8d577-335">Sie verwendet die Metadaten während der Deserialisierung, um die polymorphe Deserialisierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="8d577-335">It uses the metadata while deserializing to do polymorphic deserialization.</span></span> <span data-ttu-id="8d577-336"><xref:System.Text.Json> kann in einem begrenzten Bereich [polymorphe Serialisierung](system-text-json-how-to.md#serialize-properties-of-derived-classes) durchführen, aber keine polymorphe Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="8d577-336"><xref:System.Text.Json> can do a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but not polymorphic deserialization.</span></span>

<span data-ttu-id="8d577-337">Um polymorphe Deserialisierung zu unterstützen, erstellen Sie einen Konverter wie das Beispiel in [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="8d577-337">To support polymorphic deserialization, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="deserialization-of-object-properties"></a><span data-ttu-id="8d577-338">Deserialisierung von Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="8d577-338">Deserialization of object properties</span></span>

<span data-ttu-id="8d577-339">Wenn `Newtonsoft.Json` in <xref:System.Object> deserialisieren, wird Folgendes ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="8d577-339">When `Newtonsoft.Json` deserializes to <xref:System.Object>, it:</span></span>

* <span data-ttu-id="8d577-340">Es leitet den Typ primitiver Werte in der JSON-Nutzlast (außer `null`) ab und gibt die gespeicherten Typen `string`, `long`, `double`, `boolean` oder `DateTime` als geschachteltes Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="8d577-340">Infers the type of primitive values in the JSON payload (other than `null`) and returns the stored `string`, `long`, `double`, `boolean`, or `DateTime` as a boxed object.</span></span> <span data-ttu-id="8d577-341">*Primitive Werte* sind einzelne JSON-Werte, wie eine JSON-Zahl, -Zeichenfolge, `true`, `false` oder `null`.</span><span class="sxs-lookup"><span data-stu-id="8d577-341">*Primitive values* are single JSON values such as a JSON number, string, `true`, `false`, or `null`.</span></span>
* <span data-ttu-id="8d577-342">Gibt ein `JObject` oder `JArray` für komplexe Werte in der JSON-Nutzlast zurück.</span><span class="sxs-lookup"><span data-stu-id="8d577-342">Returns a `JObject` or `JArray` for complex values in the JSON payload.</span></span> <span data-ttu-id="8d577-343">*Komplexe Werte* sind Sammlungen von JSON-Schlüssel-Wert-Paaren in geschweiften Klammern (`{}`) oder Listen mit Werten in eckigen Klammern (`[]`).</span><span class="sxs-lookup"><span data-stu-id="8d577-343">*Complex values* are collections of JSON key-value pairs within braces (`{}`) or lists of values within brackets (`[]`).</span></span> <span data-ttu-id="8d577-344">Die Eigenschaften und Werte in geschweiften oder eckigen Klammern können zusätzliche Eigenschaften oder Werte besitzen.</span><span class="sxs-lookup"><span data-stu-id="8d577-344">The properties and values within the braces or brackets can have additional properties or values.</span></span>
* <span data-ttu-id="8d577-345">Gibt einen Nullverweis zurück, wenn die Nutzlast das JSON-Literal `null` enthält.</span><span class="sxs-lookup"><span data-stu-id="8d577-345">Returns a null reference when the payload has the `null` JSON literal.</span></span>

<span data-ttu-id="8d577-346"><xref:System.Text.Json> speichert bei der Deserialisierung in <xref:System.Object> ein geschachteltes `JsonElement` sowohl für primitive als auch für komplexe Werte, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8d577-346"><xref:System.Text.Json> stores a boxed `JsonElement` for both primitive and complex values whenever deserializing to <xref:System.Object>, for example:</span></span>

* <span data-ttu-id="8d577-347">Eine `object`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8d577-347">An `object` property.</span></span>
* <span data-ttu-id="8d577-348">Ein `object`-Wörterbuchwert.</span><span class="sxs-lookup"><span data-stu-id="8d577-348">An `object` dictionary value.</span></span>
* <span data-ttu-id="8d577-349">Ein `object`-Arraywert.</span><span class="sxs-lookup"><span data-stu-id="8d577-349">An `object` array value.</span></span>
* <span data-ttu-id="8d577-350">Ein Stamm-`object`.</span><span class="sxs-lookup"><span data-stu-id="8d577-350">A root `object`.</span></span>

<span data-ttu-id="8d577-351">`System.Text.Json` behandelt `null` jedoch genau wie `Newtonsoft.Json` und gibt einen Nullverweis zurück, wenn die Nutzlast das JSON-Literal `null` enthält.</span><span class="sxs-lookup"><span data-stu-id="8d577-351">However, `System.Text.Json` treats `null` the same as `Newtonsoft.Json` and returns a null reference when the payload has the `null` JSON literal in it.</span></span>

<span data-ttu-id="8d577-352">Um Typrückschlüsse für `object`-Eigenschaften zu implementieren, erstellen Sie einen Konverter wie in [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="8d577-352">To implement type inference for `object` properties, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).</span></span>

### <a name="deserialize-null-to-non-nullable-type"></a><span data-ttu-id="8d577-353">Deserialisieren eines Null-Typs in einen Non-Nullable-Typ</span><span class="sxs-lookup"><span data-stu-id="8d577-353">Deserialize null to non-nullable type</span></span>

<span data-ttu-id="8d577-354">`Newtonsoft.Json` löst im folgenden Szenario keine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="8d577-354">`Newtonsoft.Json` doesn't throw an exception in the following scenario:</span></span>

* <span data-ttu-id="8d577-355">`NullValueHandling` ist auf `Ignore` festgelegt, und</span><span class="sxs-lookup"><span data-stu-id="8d577-355">`NullValueHandling` is set to `Ignore`, and</span></span>
* <span data-ttu-id="8d577-356">Während der Deserialisierung enthält JSON einen Nullwert für einen Non-Nullable-Werttyp.</span><span class="sxs-lookup"><span data-stu-id="8d577-356">During deserialization, the JSON contains a null value for a non-nullable value type.</span></span>

<span data-ttu-id="8d577-357">Im selben Szenario löst <xref:System.Text.Json> eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="8d577-357">In the same scenario, <xref:System.Text.Json> does throw an exception.</span></span> <span data-ttu-id="8d577-358">(Die entsprechende Einstellung für die Behandlung von Null ist <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="8d577-358">(The corresponding null handling setting is <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)</span></span>

<span data-ttu-id="8d577-359">Wenn Sie den Zieltyp besitzen, besteht die beste Problemumgehung darin, die betreffende Eigenschaft „nullable“ zu machen (z. B. `int` in `int?` ändern).</span><span class="sxs-lookup"><span data-stu-id="8d577-359">If you own the target type, the best workaround is to make the property in question nullable (for example, change `int` to `int?`).</span></span>

<span data-ttu-id="8d577-360">Eine weitere Problemumgehung besteht darin, einen Konverter für den Typ zu erstellen, wie im folgenden Beispiel, das Nullwerte für `DateTimeOffset`-Typen behandelt:</span><span class="sxs-lookup"><span data-stu-id="8d577-360">Another workaround is to make a converter for the type, such as the following example that handles null values for `DateTimeOffset` types:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs)]

<span data-ttu-id="8d577-361">Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die Eigenschaft](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="8d577-361">Register this custom converter by [using an attribute on the property](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="8d577-362">**Hinweis**: Der vorherige Konverter **behandelt Nullwerte anders**, als dies `Newtonsoft.Json` für POCOS tut, die Standardwerte angeben.</span><span class="sxs-lookup"><span data-stu-id="8d577-362">**Note:** The preceding converter **handles null values differently** than `Newtonsoft.Json` does for POCOs that specify default values.</span></span> <span data-ttu-id="8d577-363">Angenommen, der folgende Code stellt Ihr Zielobjekt dar:</span><span class="sxs-lookup"><span data-stu-id="8d577-363">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="8d577-364">Und nehmen wir weiterhin an, der folgende JSON-Code wird mithilfe des vorherigen Konverters deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="8d577-364">And suppose the following JSON is deserialized by using the preceding converter:</span></span>

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="8d577-365">Nach der Deserialisierung hat die `Date`-Eigenschaft den Wert „1/1/0001“ (`default(DateTimeOffset)`), d. h., der im Konstruktor festgelegte Wert wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="8d577-365">After deserialization, the `Date` property has 1/1/0001 (`default(DateTimeOffset)`), that is, the value set in the constructor is overwritten.</span></span> <span data-ttu-id="8d577-366">Beim selben POCO und JSON-Code würde die Deserialisierung mit `Newtonsoft.Json` den Wert „1/1/2001“ in der `Date`-Eigenschaft belassen.</span><span class="sxs-lookup"><span data-stu-id="8d577-366">Given the same POCO and JSON, `Newtonsoft.Json` deserialization would leave 1/1/2001 in the `Date` property.</span></span>

### <a name="deserialize-to-immutable-classes-and-structs"></a><span data-ttu-id="8d577-367">Deserialisieren in unveränderliche Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="8d577-367">Deserialize to immutable classes and structs</span></span>

<span data-ttu-id="8d577-368">`Newtonsoft.Json` kann in unveränderliche Klassen und Strukturen deserialisieren, weil es Konstruktoren verwenden kann, die Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="8d577-368">`Newtonsoft.Json` can deserialize to immutable classes and structs because it can use constructors that have parameters.</span></span> <span data-ttu-id="8d577-369"><xref:System.Text.Json> unterstützt nur öffentliche parameterlose Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="8d577-369"><xref:System.Text.Json> supports only public parameterless constructors.</span></span> <span data-ttu-id="8d577-370">Als Problemumgehung können Sie einen Konstruktor mit Parametern in einem benutzerdefinierten Konverter aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8d577-370">As a workaround, you can call a constructor with parameters in a custom converter.</span></span>

<span data-ttu-id="8d577-371">Im Folgenden finden Sie eine unveränderliche Struktur mit mehreren Konstruktorparametern:</span><span class="sxs-lookup"><span data-stu-id="8d577-371">Here's an immutable struct with multiple constructor parameters:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePoint.cs#ImmutablePoint)]

<span data-ttu-id="8d577-372">Und hier sehen Sie einen Konverter, der diese Struktur serialisiert und deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="8d577-372">And here's a converter that serializes and deserializes this struct:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs)]

<span data-ttu-id="8d577-373">Registrieren Sie diesen benutzerdefinierten Konverter durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="8d577-373">Register this custom converter by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="8d577-374">Ein Beispiel für einen ähnlichen Konverter, der offene generische Eigenschaften behandelt, finden Sie unter der [Integrierter Konverter für Schlüssel-Wert-Paare](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).</span><span class="sxs-lookup"><span data-stu-id="8d577-374">For an example of a similar converter that handles open generic properties, see the [built-in converter for key-value pairs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).</span></span>

### <a name="specify-constructor-to-use"></a><span data-ttu-id="8d577-375">Angeben des zu verwendenden Konstruktors</span><span class="sxs-lookup"><span data-stu-id="8d577-375">Specify constructor to use</span></span>

<span data-ttu-id="8d577-376">Mit dem `[JsonConstructor]`-Attribut von `Newtonsoft.Json` können Sie angeben, welcher Konstruktor beim Deserialisieren in ein POCO aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="8d577-376">The `Newtonsoft.Json` `[JsonConstructor]` attribute lets you specify which constructor to call when deserializing to a POCO.</span></span> <span data-ttu-id="8d577-377"><xref:System.Text.Json> unterstützt nur parameterlose Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="8d577-377"><xref:System.Text.Json> supports only parameterless constructors.</span></span> <span data-ttu-id="8d577-378">Als Problemumgehung können Sie einen beliebigen aufrufen, den Sie in einem benutzerdefinierten Konverter benötigen.</span><span class="sxs-lookup"><span data-stu-id="8d577-378">As a workaround, you can call whichever constructor you need in a custom converter.</span></span> <span data-ttu-id="8d577-379">Siehe das Beispiel für das [Deserialisieren in unveränderliche Klassen und Strukturen](#deserialize-to-immutable-classes-and-structs).</span><span class="sxs-lookup"><span data-stu-id="8d577-379">See the example for [Deserialize to immutable classes and structs](#deserialize-to-immutable-classes-and-structs).</span></span>

### <a name="required-properties"></a><span data-ttu-id="8d577-380">Erforderliche Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8d577-380">Required properties</span></span>

<span data-ttu-id="8d577-381">In `Newtonsoft.Json` geben Sie an, dass eine Eigenschaft erforderlich ist, indem Sie `Required` für das `[JsonProperty]`-Attribut festlegen.</span><span class="sxs-lookup"><span data-stu-id="8d577-381">In `Newtonsoft.Json`, you specify that a property is required by setting `Required` on the `[JsonProperty]` attribute.</span></span> <span data-ttu-id="8d577-382">`Newtonsoft.Json` löst eine Ausnahme aus, wenn im JSON für eine als erforderlich markierte Eigenschaft kein Wert empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-382">`Newtonsoft.Json` throws an exception if no value is received in the JSON for a property marked as required.</span></span>

<span data-ttu-id="8d577-383"><xref:System.Text.Json> löst keine Ausnahme aus, wenn kein Wert für eine der Eigenschaften des Zieltyps empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-383"><xref:System.Text.Json> doesn't throw an exception if no value is received for one of the properties of the target type.</span></span> <span data-ttu-id="8d577-384">Wenn Sie z. B. eine `WeatherForecast`-Klasse haben:</span><span class="sxs-lookup"><span data-stu-id="8d577-384">For example, if you have a `WeatherForecast` class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="8d577-385">Der folgende JSON-Code wird ohne Fehler deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="8d577-385">The following JSON is deserialized without error:</span></span>

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

<span data-ttu-id="8d577-386">Damit die Deserialisierung fehlschlägt, wenn der JSON-Code keine `Date`-Eigenschaft enthält, implementieren Sie einen benutzerdefinierten Konverter.</span><span class="sxs-lookup"><span data-stu-id="8d577-386">To make deserialization fail if no `Date` property is in the JSON, implement a custom converter.</span></span> <span data-ttu-id="8d577-387">Der folgende Beispielcode für einen Konverter löst nach Abschluss der Deserialisierung eine Ausnahme aus, wenn die `Date`-Eigenschaft nicht festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="8d577-387">The following sample converter code throws an exception if the `Date` property isn't set after deserialization is complete:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs)]

<span data-ttu-id="8d577-388">Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die POCO-Klasse](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="8d577-388">Register this custom converter by [using an attribute on the POCO class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="8d577-389">Wenn Sie sich an dieses Muster halten, übergeben Sie das options-Objekt nicht, wenn Sie <xref:System.Text.Json.JsonSerializer.Serialize%2A> oder <xref:System.Text.Json.JsonSerializer.Deserialize%2A> rekursiv aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8d577-389">If you follow this pattern, don't pass in the options object when recursively calling <xref:System.Text.Json.JsonSerializer.Serialize%2A> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A>.</span></span> <span data-ttu-id="8d577-390">Das options-Objekt enthält die <xref:System.Text.Json.JsonSerializerOptions.Converters%2A>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="8d577-390">The options object contains the <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> collection.</span></span> <span data-ttu-id="8d577-391">Wenn Sie es an `Serialize` oder `Deserialize` übergeben, ruft sich der benutzerdefinierte Konverter selbst auf, wodurch eine Endlosschleife entsteht, die zu einer Stapelüberlaufausnahme führt.</span><span class="sxs-lookup"><span data-stu-id="8d577-391">If you pass it in to `Serialize` or `Deserialize`, the custom converter calls into itself, making an infinite loop that results in a stack overflow exception.</span></span> <span data-ttu-id="8d577-392">Wenn die Standardoptionen nicht praktikabel sind, erstellen Sie eine neue Instanz der Optionen mit den Einstellungen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="8d577-392">If the default options are not feasible, create a new instance of the options with the settings that you need.</span></span> <span data-ttu-id="8d577-393">Diese Vorgehensweise ist langsam, da jede neue Instanz unabhängig zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-393">This approach will be slow since each new instance caches independently.</span></span>

<span data-ttu-id="8d577-394">Der vorherige Konvertercode ist ein vereinfachtes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="8d577-394">The preceding converter code is a simplified example.</span></span> <span data-ttu-id="8d577-395">Zusätzliche Logik wäre erforderlich, wenn Sie Attribute (z. B. [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)) oder andere Optionen (z. B. benutzerdefinierte Encoder) behandeln müssen.</span><span class="sxs-lookup"><span data-stu-id="8d577-395">Additional logic would be required if you need to handle attributes (such as [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) or different options (such as custom encoders).</span></span> <span data-ttu-id="8d577-396">Der Beispielcode verarbeitet außerdem keine Eigenschaften, für die im Konstruktor ein Standardwert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8d577-396">Also, the example code doesn't handle properties for which a default value is set in the constructor.</span></span> <span data-ttu-id="8d577-397">Und dieser Ansatz unterscheidet nicht zwischen den folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="8d577-397">And this approach doesn't differentiate between the following scenarios:</span></span>

* <span data-ttu-id="8d577-398">Im JSON fehlt eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8d577-398">A property is missing from the JSON.</span></span>
* <span data-ttu-id="8d577-399">Im JSON ist eine Eigenschaft für einen Non-Nullable-Typ vorhanden, aber der Wert ist der Standardwert für den Typ, z. B. Null für einen `int`.</span><span class="sxs-lookup"><span data-stu-id="8d577-399">A property for a non-nullable type is present in the JSON, but the value is the default for the type, such as zero for an `int`.</span></span>
* <span data-ttu-id="8d577-400">Im JSON ist eine Eigenschaft für einen Nullable-Werttyp vorhanden, aber der Wert ist Null.</span><span class="sxs-lookup"><span data-stu-id="8d577-400">A property for a nullable value type is present in the JSON, but the value is null.</span></span>

### <a name="conditionally-ignore-a-property"></a><span data-ttu-id="8d577-401">Bedingtes Ignorieren einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8d577-401">Conditionally ignore a property</span></span>

<span data-ttu-id="8d577-402">`Newtonsoft.Json` bietet mehrere Möglichkeiten, um eine Eigenschaft bei der Serialisierung oder Deserialisierung bedingt zu ignorieren:</span><span class="sxs-lookup"><span data-stu-id="8d577-402">`Newtonsoft.Json` has several ways to conditionally ignore a property on serialization or deserialization:</span></span>

* <span data-ttu-id="8d577-403">`DefaultContractResolver` ermöglicht das Auswählen von Eigenschaften, die eingeschlossen oder ausgeschlossen werden sollen, basierend auf beliebigen Kriterien.</span><span class="sxs-lookup"><span data-stu-id="8d577-403">`DefaultContractResolver` lets you select properties to include or exclude, based on arbitrary criteria.</span></span>
* <span data-ttu-id="8d577-404">Mit den Einstellungen `NullValueHandling` und `DefaultValueHandling` von `JsonSerializerSettings` können Sie angeben, dass alle Eigenschaften mit Nullwert oder Standardwert ignoriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8d577-404">The `NullValueHandling` and `DefaultValueHandling` settings on `JsonSerializerSettings` let you specify that all null-value or default-value properties should be ignored.</span></span>
* <span data-ttu-id="8d577-405">Mit den Einstellungen `NullValueHandling` und `DefaultValueHandling` des `[JsonProperty]`-Attributs können Sie einzelne Eigenschaften angeben, die ignoriert werden sollen, wenn Sie auf Null oder den Standardwert festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="8d577-405">The `NullValueHandling` and `DefaultValueHandling` settings on the `[JsonProperty]` attribute let you specify individual properties that should be ignored when set to null or the default value.</span></span>

<span data-ttu-id="8d577-406"><xref:System.Text.Json> bietet die folgenden Möglichkeiten, um während der Serialisierung Eigenschaften auszulassen:</span><span class="sxs-lookup"><span data-stu-id="8d577-406"><xref:System.Text.Json> provides the following ways to omit properties while serializing:</span></span>

* <span data-ttu-id="8d577-407">Das [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties)-Attribut einer Eigenschaft bewirkt, dass die Eigenschaft während der Serialisierung im JSON-Code ausgelassen wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-407">The [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) attribute on a property causes the property to be omitted from the JSON during serialization.</span></span>
* <span data-ttu-id="8d577-408">Mit der globalen Option [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) können Sie alle Eigenschaften mit Nullwert ausschließen.</span><span class="sxs-lookup"><span data-stu-id="8d577-408">The [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) global option lets you exclude all null-value properties.</span></span>
* <span data-ttu-id="8d577-409">Mit der globalen Option [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) können Sie alle schreibgeschützten Eigenschaften ausschließen.</span><span class="sxs-lookup"><span data-stu-id="8d577-409">The [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) global option lets you exclude all read-only properties.</span></span>

<span data-ttu-id="8d577-410">Diese Optionen gestatten Ihnen Folgendes **nicht**:</span><span class="sxs-lookup"><span data-stu-id="8d577-410">These options **don't** let you:</span></span>

* <span data-ttu-id="8d577-411">Ignorieren aller Eigenschaften, die den Standardwert für den Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8d577-411">Ignore all properties that have the default value for the type.</span></span>
* <span data-ttu-id="8d577-412">Ignorieren ausgewählter Eigenschaften, die den Standardwert für den Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8d577-412">Ignore selected properties that have the default value for the type.</span></span>
* <span data-ttu-id="8d577-413">Ignorieren ausgewählter Eigenschaften, wenn deren Wert Null ist.</span><span class="sxs-lookup"><span data-stu-id="8d577-413">Ignore selected properties if their value is null.</span></span>
* <span data-ttu-id="8d577-414">Ignorieren ausgewählter Eigenschaften auf Grundlage beliebiger Kriterien, die zur Laufzeit ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-414">Ignore selected properties based on arbitrary criteria evaluated at run time.</span></span>

<span data-ttu-id="8d577-415">Für diese Funktionalität können Sie einen benutzerdefinierten Konverter schreiben.</span><span class="sxs-lookup"><span data-stu-id="8d577-415">For that functionality, you can write a custom converter.</span></span> <span data-ttu-id="8d577-416">Im Folgenden finden Sie ein Beispiel-POCO und einen benutzerdefinierten Konverter dafür, um diesen Ansatz zu veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="8d577-416">Here's a sample POCO and a custom converter for it that illustrates this approach:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

<span data-ttu-id="8d577-417">Der Konverter bewirkt, dass die `Summary`-Eigenschaft bei der Serialisierung ausgelassen wird, wenn ihr Wert Null, eine leere Zeichenfolge oder „N/V“ ist.</span><span class="sxs-lookup"><span data-stu-id="8d577-417">The converter causes the `Summary` property to be omitted from serialization if its value is null, an empty string, or "N/A".</span></span>

<span data-ttu-id="8d577-418">Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die Klasse](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="8d577-418">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="8d577-419">Für diesen Ansatz ist zusätzliche Logik erforderlich, wenn:</span><span class="sxs-lookup"><span data-stu-id="8d577-419">This approach requires additional logic if:</span></span>

* <span data-ttu-id="8d577-420">Das POCO komplexe Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="8d577-420">The POCO includes complex properties.</span></span>
* <span data-ttu-id="8d577-421">Sie Attribute wie `[JsonIgnore]` oder Optionen wie benutzerdefinierte Encoder verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="8d577-421">You need to handle attributes such as `[JsonIgnore]` or options such as custom encoders.</span></span>

### <a name="specify-date-format"></a><span data-ttu-id="8d577-422">Angeben des Datumsformats</span><span class="sxs-lookup"><span data-stu-id="8d577-422">Specify date format</span></span>

<span data-ttu-id="8d577-423">`Newtonsoft.Json` bietet verschiedene Möglichkeiten, um zu kontrollieren, wie Eigenschaften des Typs `DateTime` und `DateTimeOffset` serialisiert und deserialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="8d577-423">`Newtonsoft.Json` provides several ways to control how properties of `DateTime` and `DateTimeOffset` types are serialized and deserialized:</span></span>

* <span data-ttu-id="8d577-424">Die `DateTimeZoneHandling`-Einstellung kann verwendet werden, um alle `DateTime`-Werte als UTC-Datumsangaben zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="8d577-424">The `DateTimeZoneHandling` setting can be used to serialize all `DateTime` values as UTC dates.</span></span>
* <span data-ttu-id="8d577-425">Die `DateFormatString`-Einstellung und `DateTime`-Konverter können verwendet werden, um das Format von Datumszeichenfolgen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="8d577-425">The `DateFormatString` setting and `DateTime` converters can be used to customize the format of date strings.</span></span>

<span data-ttu-id="8d577-426">In <xref:System.Text.Json> ist das einzige Format, das über integrierte Unterstützung verfügt, ISO 8601-1:2019, da es weit verbreitet und eindeutig ist und Roundtrips exakt gestaltet.</span><span class="sxs-lookup"><span data-stu-id="8d577-426">In <xref:System.Text.Json>, the only format that has built-in support is ISO 8601-1:2019 since it's widely adopted, unambiguous, and makes round trips precisely.</span></span> <span data-ttu-id="8d577-427">Um ein beliebiges anderes Format zu verwenden, erstellen Sie einen benutzerdefinierten Konverter.</span><span class="sxs-lookup"><span data-stu-id="8d577-427">To use any other format, create a custom converter.</span></span> <span data-ttu-id="8d577-428">Weitere Informationen finden Sie unter [Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md).</span><span class="sxs-lookup"><span data-stu-id="8d577-428">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>

### <a name="callbacks"></a><span data-ttu-id="8d577-429">Rückrufe</span><span class="sxs-lookup"><span data-stu-id="8d577-429">Callbacks</span></span>

<span data-ttu-id="8d577-430">`Newtonsoft.Json` ermöglicht das Ausführen von benutzerdefiniertem Code an mehreren Stellen im Serialisierungs- oder Deserialisierungsprozess:</span><span class="sxs-lookup"><span data-stu-id="8d577-430">`Newtonsoft.Json` lets you execute custom code at several points in the serialization or deserialization process:</span></span>

* <span data-ttu-id="8d577-431">OnDeserializing (bei Beginn der Deserialisierung eines Objekts)</span><span class="sxs-lookup"><span data-stu-id="8d577-431">OnDeserializing (when beginning to deserialize an object)</span></span>
* <span data-ttu-id="8d577-432">OnDeserialized (nach Abschluss der Deserialisierung eines Objekts)</span><span class="sxs-lookup"><span data-stu-id="8d577-432">OnDeserialized (when finished deserializing an object)</span></span>
* <span data-ttu-id="8d577-433">OnSerializing (bei Beginn der Serialisierung eines Objekts)</span><span class="sxs-lookup"><span data-stu-id="8d577-433">OnSerializing (when beginning to serialize an object)</span></span>
* <span data-ttu-id="8d577-434">OnSerialized (nach Abschluss der Serialisierung eines Objekts)</span><span class="sxs-lookup"><span data-stu-id="8d577-434">OnSerialized (when finished serializing an object)</span></span>

<span data-ttu-id="8d577-435">In <xref:System.Text.Json> können Sie Rückrufe simulieren, indem Sie einen benutzerdefinierten Konverter schreiben.</span><span class="sxs-lookup"><span data-stu-id="8d577-435">In <xref:System.Text.Json>, you can simulate callbacks by writing a custom converter.</span></span> <span data-ttu-id="8d577-436">Im folgenden Beispiel wird ein benutzerdefinierter Konverter für ein POCO gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8d577-436">The following example shows a custom converter for a POCO.</span></span> <span data-ttu-id="8d577-437">Der Konverter enthält Code, der an jeder Stelle eine Meldung anzeigt, die einem `Newtonsoft.Json`-Rückruf entspricht.</span><span class="sxs-lookup"><span data-stu-id="8d577-437">The converter includes code that displays a message at each point that corresponds to a `Newtonsoft.Json` callback.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs)]

<span data-ttu-id="8d577-438">Registrieren Sie diesen benutzerdefinierten Konverter [mithilfe eines Attributs für die Klasse](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oder durch [Hinzufügen des Konverters](system-text-json-converters-how-to.md#registration-sample---converters-collection) zur <xref:System.Text.Json.JsonSerializerOptions.Converters>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="8d577-438">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="8d577-439">Wenn Sie einen benutzerdefinierten Konverter verwenden, der sich am vorangehenden Beispiel orientiert:</span><span class="sxs-lookup"><span data-stu-id="8d577-439">If you use a custom converter that follows the preceding sample:</span></span>

* <span data-ttu-id="8d577-440">Der `OnDeserializing`-Code hat keinen Zugriff auf die neue POCO-Instanz.</span><span class="sxs-lookup"><span data-stu-id="8d577-440">The `OnDeserializing` code doesn't have access to the new POCO instance.</span></span> <span data-ttu-id="8d577-441">Um die neue POCO-Instanz zu Beginn der Deserialisierung zu bearbeiten, fügen Sie diesen Code in den POCO-Konstruktor ein.</span><span class="sxs-lookup"><span data-stu-id="8d577-441">To manipulate the new POCO instance at the start of deserialization, put that code in the POCO constructor.</span></span>
* <span data-ttu-id="8d577-442">Übergeben Sie das options-Objekt nicht, wenn Sie `Serialize` oder `Deserialize` rekursiv aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8d577-442">Don't pass in the options object when recursively calling `Serialize` or `Deserialize`.</span></span> <span data-ttu-id="8d577-443">Das options-Objekt enthält die `Converters`-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="8d577-443">The options object contains the `Converters` collection.</span></span> <span data-ttu-id="8d577-444">Wenn Sie es an `Serialize` oder `Deserialize` übergeben, wird der Konverter verwendet, wodurch eine Endlosschleife entsteht, die zu einer Stapelüberlaufausnahme führt.</span><span class="sxs-lookup"><span data-stu-id="8d577-444">If you pass it in to `Serialize` or `Deserialize`, the converter will be used, making an infinite loop that results in a stack overflow exception.</span></span>

### <a name="public-and-non-public-fields"></a><span data-ttu-id="8d577-445">Öffentliche und nicht öffentliche Felder</span><span class="sxs-lookup"><span data-stu-id="8d577-445">Public and non-public fields</span></span>

<span data-ttu-id="8d577-446">`Newtonsoft.Json` kann Felder ebenso wie Eigenschaften serialisieren und deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="8d577-446">`Newtonsoft.Json` can serialize and deserialize fields as well as properties.</span></span> <span data-ttu-id="8d577-447"><xref:System.Text.Json> funktioniert nur mit öffentlichen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8d577-447"><xref:System.Text.Json> only works with public properties.</span></span> <span data-ttu-id="8d577-448">Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-448">Custom converters can provide this functionality.</span></span>

### <a name="internal-and-private-property-setters-and-getters"></a><span data-ttu-id="8d577-449">Interne und private Eigenschaften-Setter und -Getter</span><span class="sxs-lookup"><span data-stu-id="8d577-449">Internal and private property setters and getters</span></span>

<span data-ttu-id="8d577-450">`Newtonsoft.Json` kann private und interne Eigenschaften-Setter und -Getter über das `JsonProperty`-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d577-450">`Newtonsoft.Json` can use private and internal property setters and getters via the `JsonProperty` attribute.</span></span> <span data-ttu-id="8d577-451"><xref:System.Text.Json> unterstützt nur öffentliche Setter.</span><span class="sxs-lookup"><span data-stu-id="8d577-451"><xref:System.Text.Json> supports only public setters.</span></span> <span data-ttu-id="8d577-452">Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-452">Custom converters can provide this functionality.</span></span>

### <a name="populate-existing-objects"></a><span data-ttu-id="8d577-453">Auffüllen vorhandener Objekte</span><span class="sxs-lookup"><span data-stu-id="8d577-453">Populate existing objects</span></span>

<span data-ttu-id="8d577-454">Die `JsonConvert.PopulateObject`-Methode in `Newtonsoft.Json` deserialisiert ein JSON-Dokument in eine vorhandene Instanz einer Klasse, anstatt eine neue Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-454">The `JsonConvert.PopulateObject` method in `Newtonsoft.Json` deserializes a JSON document to an existing instance of a class, instead of creating a new instance.</span></span> <span data-ttu-id="8d577-455"><xref:System.Text.Json> erstellt immer eine neue Instanz des Zieltyps unter Verwendung des standardmäßigen öffentlichen parameterlosen Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="8d577-455"><xref:System.Text.Json> always creates a new instance of the target type by using the default public parameterless constructor.</span></span> <span data-ttu-id="8d577-456">Benutzerdefinierte Konverter können in eine vorhandene Instanz deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="8d577-456">Custom converters can deserialize to an existing instance.</span></span>

### <a name="reuse-rather-than-replace-properties"></a><span data-ttu-id="8d577-457">Wiederverwenden statt Ersetzen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8d577-457">Reuse rather than replace properties</span></span>

<span data-ttu-id="8d577-458">Mit der Einstellung `Newtonsoft.Json` `ObjectCreationHandling` können Sie angeben, dass Objekte in Eigenschaften wiederverwendet werden sollen, anstatt während der Deserialisierung ersetzt zu werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-458">The `Newtonsoft.Json` `ObjectCreationHandling` setting lets you specify that objects in properties should be reused rather than replaced during deserialization.</span></span> <span data-ttu-id="8d577-459"><xref:System.Text.Json> ersetzt Objekte in Eigenschaften immer.</span><span class="sxs-lookup"><span data-stu-id="8d577-459"><xref:System.Text.Json> always replaces objects in properties.</span></span>  <span data-ttu-id="8d577-460">Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-460">Custom converters can provide this functionality.</span></span>

### <a name="add-to-collections-without-setters"></a><span data-ttu-id="8d577-461">Hinzufügen zu Sammlungen ohne Setter</span><span class="sxs-lookup"><span data-stu-id="8d577-461">Add to collections without setters</span></span>

<span data-ttu-id="8d577-462">Während der Deserialisierung fügt `Newtonsoft.Json` einer Sammlung Objekte hinzu, auch wenn die Eigenschaft über keinen Setter verfügt.</span><span class="sxs-lookup"><span data-stu-id="8d577-462">During deserialization, `Newtonsoft.Json` adds objects to a collection even if the property has no setter.</span></span> <span data-ttu-id="8d577-463"><xref:System.Text.Json> ignoriert Eigenschaften, die keinen Setter besitzen.</span><span class="sxs-lookup"><span data-stu-id="8d577-463"><xref:System.Text.Json> ignores properties that don't have setters.</span></span> <span data-ttu-id="8d577-464">Benutzerdefinierte Konverter können diese Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-464">Custom converters can provide this functionality.</span></span>

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a><span data-ttu-id="8d577-465">Zurzeit von JsonSerializer nicht unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="8d577-465">Scenarios that JsonSerializer currently doesn't support</span></span>

<span data-ttu-id="8d577-466">Für die folgenden Szenarien sind Problemumgehungen nicht praktikabel oder möglich.</span><span class="sxs-lookup"><span data-stu-id="8d577-466">For the following scenarios, workarounds are not practical or possible.</span></span> <span data-ttu-id="8d577-467">Wenn Sie von diesen `Newtonsoft.Json`-Funktionen abhängig sind, ist die Migration nicht ohne wesentliche Änderungen möglich.</span><span class="sxs-lookup"><span data-stu-id="8d577-467">If you rely on these `Newtonsoft.Json` features, migration will not be possible without significant changes.</span></span>

### <a name="preserve-object-references-and-handle-loops"></a><span data-ttu-id="8d577-468">Erhalten von Objektverweise und Behandeln von Schleifen</span><span class="sxs-lookup"><span data-stu-id="8d577-468">Preserve object references and handle loops</span></span>

<span data-ttu-id="8d577-469">Standardmäßig serialisiert `Newtonsoft.Json` als Wert.</span><span class="sxs-lookup"><span data-stu-id="8d577-469">By default, `Newtonsoft.Json` serializes by value.</span></span> <span data-ttu-id="8d577-470">Wenn ein Objekt beispielsweise zwei Eigenschaften enthält, die einen Verweis auf dasselbe `Person`-Objekt enthalten, werden die Werte der Eigenschaften dieses `Person`-Objekts in JSON dupliziert.</span><span class="sxs-lookup"><span data-stu-id="8d577-470">For example, if an object contains two properties that contain a reference to the same `Person` object, the values of that `Person` object's properties are duplicated in the JSON.</span></span>

<span data-ttu-id="8d577-471">`Newtonsoft.Json` verfügt über eine `PreserveReferencesHandling`-Einstellung für `JsonSerializerSettings`, mit der Sie als Verweis serialisieren können:</span><span class="sxs-lookup"><span data-stu-id="8d577-471">`Newtonsoft.Json` has a `PreserveReferencesHandling` setting on `JsonSerializerSettings` that lets you serialize by reference:</span></span>

* <span data-ttu-id="8d577-472">Dem für das erste `Person`-Objekt erstellten JSON-Code werden Bezeichnermetadaten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8d577-472">An identifier metadata is added to the JSON created for the first `Person` object.</span></span>
* <span data-ttu-id="8d577-473">Der für das zweite `Person`-Objekt erstellte JSON-Code enthält einen Verweis auf diesen Bezeichner anstelle der Eigenschaftswerte.</span><span class="sxs-lookup"><span data-stu-id="8d577-473">The JSON that is created for the second `Person` object contains a reference to that identifier instead of property values.</span></span>

<span data-ttu-id="8d577-474">`Newtonsoft.Json` verfügt außerdem über eine `ReferenceLoopHandling`-Einstellung, mit der Sie Zirkelbezüge ignorieren können, anstatt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="8d577-474">`Newtonsoft.Json` also has a `ReferenceLoopHandling` setting that lets you ignore circular references rather than throw an exception.</span></span>

<span data-ttu-id="8d577-475"><xref:System.Text.Json> unterstützt nur die Serialisierung nach Wert und löst für Zirkelbezüge eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="8d577-475"><xref:System.Text.Json> only supports serialization by value and throws an exception for circular references.</span></span>

### <a name="systemruntimeserialization-attributes"></a><span data-ttu-id="8d577-476">System.Runtime.Serialization-Attribute</span><span class="sxs-lookup"><span data-stu-id="8d577-476">System.Runtime.Serialization attributes</span></span>

<span data-ttu-id="8d577-477"><xref:System.Text.Json> unterstützt keine Attribute aus dem `System.Runtime.Serialization`-Namespace, z. B. `DataMemberAttribute` und `IgnoreDataMemberAttribute`.</span><span class="sxs-lookup"><span data-stu-id="8d577-477"><xref:System.Text.Json> doesn't support attributes from the `System.Runtime.Serialization` namespace, such as `DataMemberAttribute` and `IgnoreDataMemberAttribute`.</span></span>

### <a name="octal-numbers"></a><span data-ttu-id="8d577-478">Oktalzahlen</span><span class="sxs-lookup"><span data-stu-id="8d577-478">Octal numbers</span></span>

<span data-ttu-id="8d577-479">`Newtonsoft.Json` behandelt Zahlen mit einer führenden Null als Oktalzahlen.</span><span class="sxs-lookup"><span data-stu-id="8d577-479">`Newtonsoft.Json` treats numbers with a leading zero as octal numbers.</span></span> <span data-ttu-id="8d577-480"><xref:System.Text.Json> lässt keine führenden Nullen zu, da sie von der Spezifikation [RFC 8259](https://tools.ietf.org/html/rfc8259) nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-480"><xref:System.Text.Json> doesn't allow leading zeroes because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span>

### <a name="missingmemberhandling"></a><span data-ttu-id="8d577-481">MissingMemberHandling</span><span class="sxs-lookup"><span data-stu-id="8d577-481">MissingMemberHandling</span></span>

<span data-ttu-id="8d577-482">`Newtonsoft.Json` kann so konfiguriert werden, dass während der Deserialisierung Ausnahmen ausgelöst werden, wenn JSON Eigenschaften enthält, die im Zieltyp fehlen.</span><span class="sxs-lookup"><span data-stu-id="8d577-482">`Newtonsoft.Json` can be configured to throw exceptions during deserialization if the JSON includes properties that are missing in the target type.</span></span> <span data-ttu-id="8d577-483"><xref:System.Text.Json> ignoriert zusätzliche Eigenschaften im JSON-Code, außer wenn Sie das Attribut [[JsonExtensionData]](system-text-json-how-to.md#handle-overflow-json) verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d577-483"><xref:System.Text.Json> ignores extra properties in the JSON, except when you use the [[JsonExtensionData] attribute](system-text-json-how-to.md#handle-overflow-json).</span></span> <span data-ttu-id="8d577-484">Für die fehlende Member-Funktion gibt es keine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="8d577-484">There's no workaround for the missing member feature.</span></span>

### <a name="tracewriter"></a><span data-ttu-id="8d577-485">TraceWriter</span><span class="sxs-lookup"><span data-stu-id="8d577-485">TraceWriter</span></span>

<span data-ttu-id="8d577-486">Mit `Newtonsoft.Json` können Sie Debuggen, indem Sie einen `TraceWriter` verwenden, um Protokolle anzuzeigen, die von der Serialisierung oder Deserialisierung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-486">`Newtonsoft.Json` lets you debug by using a `TraceWriter` to view logs that are generated by serialization or deserialization.</span></span> <span data-ttu-id="8d577-487"><xref:System.Text.Json> führt keine Protokollierung aus.</span><span class="sxs-lookup"><span data-stu-id="8d577-487"><xref:System.Text.Json> doesn't do logging.</span></span>

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a><span data-ttu-id="8d577-488">„JsonDocument“ und „JsonElement“ im Vergleich zu „JToken“ (wie „JObject“, „JArray“)</span><span class="sxs-lookup"><span data-stu-id="8d577-488">JsonDocument and JsonElement compared to JToken (like JObject, JArray)</span></span>

<span data-ttu-id="8d577-489"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, ein **schreibgeschütztes** Dokumentobjektmodell (DOM) aus vorhandenen JSON-Nutzlasten zu analysieren und zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-489"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to parse and build a **read-only** Document Object Model (DOM) from existing JSON payloads.</span></span> <span data-ttu-id="8d577-490">Das DOM bietet zufälligen Zugriff auf Daten in einer JSON-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="8d577-490">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="8d577-491">Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den Typ <xref:System.Text.Json.JsonElement> zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-491">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="8d577-492">Der `JsonElement`-Typ stellt APIs zum Konvertieren von JSON-Text in allgemeine .NET-Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="8d577-492">The `JsonElement` type provides APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="8d577-493">`JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8d577-493">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

### <a name="jsondocument-is-idisposable"></a><span data-ttu-id="8d577-494">„JsonDocument“ ist „IDisposable“</span><span class="sxs-lookup"><span data-stu-id="8d577-494">JsonDocument is IDisposable</span></span>

<span data-ttu-id="8d577-495">`JsonDocument` erstellt eine In-Memory-Ansicht der Daten in einem gepoolten Puffer.</span><span class="sxs-lookup"><span data-stu-id="8d577-495">`JsonDocument` builds an in-memory view of the data into a pooled buffer.</span></span> <span data-ttu-id="8d577-496">Daher implementiert der `JsonDocument`-Typ `IDisposable`, im Gegensatz zu `JObject` oder `JArray` von `Newtonsoft.Json`,  und muss innerhalb eines using-Blocks verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-496">Therefore, unlike `JObject` or `JArray` from `Newtonsoft.Json`, the `JsonDocument` type implements `IDisposable` and needs to be used inside a using block.</span></span>

<span data-ttu-id="8d577-497">Gibt nur ein `JsonDocument` von ihrer API zurück, wenn Sie den Besitz der Lebensdauer und die Verantwortung für die Entsorgung an den Aufrufer übertragen möchten.</span><span class="sxs-lookup"><span data-stu-id="8d577-497">Only return a `JsonDocument` from your API if you want to transfer lifetime ownership and dispose responsibility to the caller.</span></span> <span data-ttu-id="8d577-498">In den meisten Szenarien ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8d577-498">In most scenarios, that isn't necessary.</span></span> <span data-ttu-id="8d577-499">Wenn der Aufrufer mit dem gesamten JSON-Dokument arbeiten muss, geben Sie den <xref:System.Text.Json.JsonElement.Clone%2A> des <xref:System.Text.Json.JsonDocument.RootElement%2A> zurück, bei dem es sich um ein <xref:System.Text.Json.JsonElement> handelt.</span><span class="sxs-lookup"><span data-stu-id="8d577-499">If the caller needs to work with the entire JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of the <xref:System.Text.Json.JsonDocument.RootElement%2A>, which is a <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="8d577-500">Wenn der Aufrufer mit einem bestimmten Element innerhalb des JSON-Dokuments arbeiten muss, geben Sie den <xref:System.Text.Json.JsonElement.Clone%2A> dieses <xref:System.Text.Json.JsonElement> zurück.</span><span class="sxs-lookup"><span data-stu-id="8d577-500">If the caller needs to work with a particular element within the JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of that <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="8d577-501">Wenn Sie das `RootElement` oder ein Unterelement direkt zurückgeben, ohne einen `Clone` zu erstellen, kann der Aufrufer nicht auf das zurückgegebene `JsonElement` zugreifen, nachdem das `JsonDocument`, das dessen Besitzer ist, entsorgt wurde.</span><span class="sxs-lookup"><span data-stu-id="8d577-501">If you return the `RootElement` or a sub-element directly without making a `Clone`, the caller won't be able to access the returned `JsonElement` after the `JsonDocument` that owns it is disposed.</span></span>

<span data-ttu-id="8d577-502">Hier sehen Sie ein Beispiel, in dem Sie einen `Clone` erstellen müssen:</span><span class="sxs-lookup"><span data-stu-id="8d577-502">Here's an example that requires you to make a `Clone`:</span></span>

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

<span data-ttu-id="8d577-503">Der vorangehende Code erwartet ein `JsonElement`, das eine `fileName`-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="8d577-503">The preceding code expects a `JsonElement` that contains a `fileName` property.</span></span> <span data-ttu-id="8d577-504">Er öffnet die JSON-Datei und erstellt ein `JsonDocument`.</span><span class="sxs-lookup"><span data-stu-id="8d577-504">It opens the JSON file and creates a `JsonDocument`.</span></span> <span data-ttu-id="8d577-505">Die Methode setzt voraus, dass der Aufrufer mit dem gesamten Dokument arbeiten möchte, weshalb sie den `Clone` des `RootElement` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8d577-505">The method assumes that the caller wants to work with the entire document, so it returns the `Clone` of the `RootElement`.</span></span>

<span data-ttu-id="8d577-506">Wenn Sie ein `JsonElement` erhalten und ein Unterelement zurückgeben, ist es nicht notwendig, einen `Clone` des Unterelements zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8d577-506">If you receive a `JsonElement` and are returning a sub-element, it's not necessary to return a `Clone` of the sub-element.</span></span> <span data-ttu-id="8d577-507">Der Aufrufer ist dafür verantwortlich, das `JsonDocument` zu erhalten, zu dem das übergebene `JsonElement` gehört.</span><span class="sxs-lookup"><span data-stu-id="8d577-507">The caller is responsible for keeping alive the `JsonDocument` that the passed-in `JsonElement` belongs to.</span></span> <span data-ttu-id="8d577-508">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8d577-508">For example:</span></span>

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a><span data-ttu-id="8d577-509">Das „JsonDocument“ ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="8d577-509">JsonDocument is read-only</span></span>

<span data-ttu-id="8d577-510">Das <xref:System.Text.Json>-DOM kann keine JSON-Elemente hinzufügen, entfernen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="8d577-510">The <xref:System.Text.Json> DOM can't add, remove, or modify JSON elements.</span></span> <span data-ttu-id="8d577-511">Es ist auf diese Weise konzipiert, um Leistung zu gewährleisten und Zuordnungen für die Analyse gängiger JSON-Nutzlastgrößen (d. h. <1 MB) zu verringern.</span><span class="sxs-lookup"><span data-stu-id="8d577-511">It's designed this way for performance and to reduce allocations for parsing common JSON payload sizes (that is, < 1 MB).</span></span> <span data-ttu-id="8d577-512">Wenn Ihr Szenario derzeit ein änderbares DOM verwendet, könnte eine der folgenden Problemumgehungen praktikabel sein:</span><span class="sxs-lookup"><span data-stu-id="8d577-512">If your scenario currently uses a modifiable DOM, one of the following workarounds might be feasible:</span></span>

* <span data-ttu-id="8d577-513">Um ein `JsonDocument` von Grund auf neu zu erstellen (d. h. ohne eine vorhandene JSON-Nutzlast an die `Parse`-Methode zu übergeben), schreiben Sie den JSON-Text unter Verwendung von `Utf8JsonWriter`, und analysieren Sie dessen Ausgabe, um ein neues `JsonDocument` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-513">To build a `JsonDocument` from scratch (that is, without passing in an existing JSON payload to the `Parse` method), write the JSON text by using the `Utf8JsonWriter` and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="8d577-514">Um ein vorhandenes `JsonDocument` zu ändern, verwenden Sie es, um JSON-Text zu schreiben, wobei Sie währenddessen Änderungen daran vornehmen, und analysieren seine Ausgabe, um daraus ein neues `JsonDocument` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d577-514">To modify an existing `JsonDocument`, use it to write JSON text, making changes while you write, and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="8d577-515">Informationen zum Zusammenführen vorhandener JSON-Dokumente, entsprechend den APIs `JObject.Merge` oder `JContainer.Merge` aus `Newtonsoft.Json`, finden Sie unter [diesem GitHub-Issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).</span><span class="sxs-lookup"><span data-stu-id="8d577-515">To merge existing JSON documents, equivalent to the `JObject.Merge` or `JContainer.Merge` APIs from `Newtonsoft.Json`, see [this GitHub issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).</span></span>

### <a name="jsonelement-is-a-union-struct"></a><span data-ttu-id="8d577-516">„JsonElement“ ist eine union-Struktur</span><span class="sxs-lookup"><span data-stu-id="8d577-516">JsonElement is a union struct</span></span>

<span data-ttu-id="8d577-517">`JsonDocument` macht das `RootElement` als Eigenschaft des Typs <xref:System.Text.Json.JsonElement> verfügbar, wobei es sich um einen union-Strukturtyp handelt, der jedes JSON-Element umfasst.</span><span class="sxs-lookup"><span data-stu-id="8d577-517">`JsonDocument` exposes the `RootElement` as a property of type <xref:System.Text.Json.JsonElement>, which is a union, struct type that encompasses any JSON element.</span></span> <span data-ttu-id="8d577-518">`Newtonsoft.Json` verwendet dedizierte hierarchische Typen wie `JObject`, `JArray`, `JToken` usw.</span><span class="sxs-lookup"><span data-stu-id="8d577-518">`Newtonsoft.Json` uses dedicated hierarchical types like `JObject`,`JArray`, `JToken`, and so forth.</span></span> <span data-ttu-id="8d577-519">`JsonElement` ist das, was Sie durchsuchen und worüber Sie aufzählen können, und Sie können `JsonElement` verwenden, um JSON-Elemente in .NET-Typen zu materialisieren.</span><span class="sxs-lookup"><span data-stu-id="8d577-519">`JsonElement` is what you can search and enumerate over, and you can use `JsonElement` to materialize JSON elements into .NET types.</span></span>

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a><span data-ttu-id="8d577-520">Durchsuchen eines „JSonDocument“ und „JsonElement“ nach Unterelementen</span><span class="sxs-lookup"><span data-stu-id="8d577-520">How to search a JsonDocument and JsonElement for sub-elements</span></span>

<span data-ttu-id="8d577-521">Suchen nach JSON-Token mithilfe von `JObject` oder `JArray` von `Newtonsoft.Json` sind in der Regel relativ schnell, da es sich dabei um Nachschlagevorgänge in einem Wörterbuch handelt.</span><span class="sxs-lookup"><span data-stu-id="8d577-521">Searches for JSON tokens using `JObject` or `JArray` from `Newtonsoft.Json` tend to be relatively fast because they're lookups in some dictionary.</span></span> <span data-ttu-id="8d577-522">Im Vergleich dazu erfordern Suchen im `JsonElement` eine sequenzielle Suche der Eigenschaften, sodass sie deswegen relativ langsam sind (z. B. bei Verwendung von `TryGetProperty`).</span><span class="sxs-lookup"><span data-stu-id="8d577-522">By comparison, searches on `JsonElement` require a sequential search of the properties and hence is relatively slow (for example when using `TryGetProperty`).</span></span> <span data-ttu-id="8d577-523"><xref:System.Text.Json> ist darauf ausgelegt, die anfängliche Analysezeit zu minimieren anstatt die Nachschlagezeit.</span><span class="sxs-lookup"><span data-stu-id="8d577-523"><xref:System.Text.Json> is designed to minimize initial parse time rather than lookup time.</span></span> <span data-ttu-id="8d577-524">Verwenden Sie deshalb die folgenden Ansätze, um die Leistung beim Durchsuchen eines `JsonDocument`-Objekts zu optimieren:</span><span class="sxs-lookup"><span data-stu-id="8d577-524">Therefore, use the following approaches to optimize performance when searching through a `JsonDocument` object:</span></span>

* <span data-ttu-id="8d577-525">Verwenden Sie die integrierten Enumeratoren (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> und <xref:System.Text.Json.JsonElement.EnumerateObject%2A>), anstatt ihre eigene Indizierung oder eigene Schleifen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d577-525">Use the built-in enumerators (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> and <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) rather than doing your own indexing or loops.</span></span>
* <span data-ttu-id="8d577-526">Führen Sie keine sequenzielle Suche im gesamten `JsonDocument` durch alle Eigenschaften durch, indem Sie `RootElement` verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d577-526">Don't do a sequential search on the whole `JsonDocument` through every property by using `RootElement`.</span></span> <span data-ttu-id="8d577-527">Suchen Sie stattdessen in geschachtelten JSON-Objekten, basierend auf der bekannten Struktur der JSON-Daten.</span><span class="sxs-lookup"><span data-stu-id="8d577-527">Instead, search on nested JSON objects based on the known structure of the JSON data.</span></span> <span data-ttu-id="8d577-528">Wenn Sie z. B. nach einer `Grade`-Eigenschaft in `Student`-Objekten suchen, durchlaufen Sie die `Student`-Objekte per Schleife, und rufen Sie den Wert von `Grade` für jedes ab, anstatt auf der Suche nach `Grade`-Eigenschaften alle `JsonElement`-Objekte zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="8d577-528">For example, if you're looking for a `Grade` property in `Student` objects, loop through the `Student` objects and get the value of `Grade` for each, rather than searching through all `JsonElement` objects looking for `Grade` properties.</span></span> <span data-ttu-id="8d577-529">Die letztgenannte Vorgehensweise führt zu unnötigen Durchläufen sämtlicher Daten.</span><span class="sxs-lookup"><span data-stu-id="8d577-529">Doing the latter will result in unnecessary passes over the same data.</span></span>

<span data-ttu-id="8d577-530">Ein Codebeispiel finden Sie unter [Verwenden von „JsonDocument“ für den Zugriff auf Daten](system-text-json-how-to.md#use-jsondocument-for-access-to-data).</span><span class="sxs-lookup"><span data-stu-id="8d577-530">For a code example, see [Use JsonDocument for access to data](system-text-json-how-to.md#use-jsondocument-for-access-to-data).</span></span>

## <a name="utf8jsonreader-compared-to-jsontextreader"></a><span data-ttu-id="8d577-531">„Utf8JsonReader“ im Vergleich zu „JsonTextReader“</span><span class="sxs-lookup"><span data-stu-id="8d577-531">Utf8JsonReader compared to JsonTextReader</span></span>

<span data-ttu-id="8d577-532"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist ein leistungsstarker, rein vorwärtsgerichteter Reader mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der aus einem [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) oder [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-532"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601).</span></span> <span data-ttu-id="8d577-533">Der `Utf8JsonReader` ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierungsprogrammen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d577-533">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span>

<span data-ttu-id="8d577-534">In den folgenden Abschnitten werden empfohlene Programmiermuster für die Verwendung von `Utf8JsonReader` erläutert.</span><span class="sxs-lookup"><span data-stu-id="8d577-534">The following sections explain recommended programming patterns for using `Utf8JsonReader`.</span></span>

### <a name="utf8jsonreader-is-a-ref-struct"></a><span data-ttu-id="8d577-535">„Utf8JsonReader“ ist eine ref-Struktur.</span><span class="sxs-lookup"><span data-stu-id="8d577-535">Utf8JsonReader is a ref struct</span></span>

<span data-ttu-id="8d577-536">Da der `Utf8JsonReader`-Typ eine *ref-Struktur* ist, unterliegt er [bestimmten Einschränkungen](../../csharp/language-reference/builtin-types/struct.md#ref-struct).</span><span class="sxs-lookup"><span data-stu-id="8d577-536">Because the `Utf8JsonReader` type is a *ref struct*, it has [certain limitations](../../csharp/language-reference/builtin-types/struct.md#ref-struct).</span></span> <span data-ttu-id="8d577-537">Beispielsweise kann er nicht als Feld in einer anderen Klasse oder Struktur als einer ref-Struktur gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-537">For example, it can't be stored as a field on a class or struct other than a ref struct.</span></span> <span data-ttu-id="8d577-538">Um eine hohe Leistung zu erzielen, muss dieser Typ eine `ref struct` sein, da er die Eingabe [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), die wiederum eine ref-Struktur ist, zwischenspeichern muss.</span><span class="sxs-lookup"><span data-stu-id="8d577-538">To achieve high performance, this type must be a `ref struct` since it needs to cache the input [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), which itself is a ref struct.</span></span> <span data-ttu-id="8d577-539">Darüber hinaus ist dieser Typ änderbar, da er den Zustand enthält.</span><span class="sxs-lookup"><span data-stu-id="8d577-539">In addition, this type is mutable since it holds state.</span></span> <span data-ttu-id="8d577-540">Daher **übergeben Sie ihn als Verweis** anstatt als Wert.</span><span class="sxs-lookup"><span data-stu-id="8d577-540">Therefore, **pass it by ref** rather than by value.</span></span> <span data-ttu-id="8d577-541">Die Übergabe als Wert würde zu einer Strukturkopie führen, und die Zustandsänderungen wären für den Aufrufer nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8d577-541">Passing it by value would result in a struct copy and the state changes would not be visible to the caller.</span></span> <span data-ttu-id="8d577-542">Dies unterscheidet sich von `Newtonsoft.Json`, da der `Newtonsoft.Json` `JsonTextReader` eine Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="8d577-542">This differs from `Newtonsoft.Json` since the `Newtonsoft.Json` `JsonTextReader` is a class.</span></span> <span data-ttu-id="8d577-543">Weitere Informationen zum Verwenden von ref-Strukturen finden Sie unter [Schreiben von sicherem und effizientem C#-Code](../../csharp/write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="8d577-543">For more information about how to use ref structs, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>

### <a name="read-utf-8-text"></a><span data-ttu-id="8d577-544">Lesen von UTF-8-Text</span><span class="sxs-lookup"><span data-stu-id="8d577-544">Read UTF-8 text</span></span>

<span data-ttu-id="8d577-545">Um die bestmögliche Leistung bei Verwendung des `Utf8JsonReader` zu erzielen, lesen Sie JSON-Nutzlasten bereits als UTF-8-codierten Text und nicht als UTF-16-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="8d577-545">To achieve the best possible performance while using the `Utf8JsonReader`, read JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="8d577-546">Ein Codebeispiel finden Sie unter [Filtern von Daten mithilfe von Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).</span><span class="sxs-lookup"><span data-stu-id="8d577-546">For a code example, see [Filter data using Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).</span></span>

### <a name="read-with-a-stream-or-pipereader"></a><span data-ttu-id="8d577-547">Lesen mit einem Stream oder PipeReader</span><span class="sxs-lookup"><span data-stu-id="8d577-547">Read with a Stream or PipeReader</span></span>

<span data-ttu-id="8d577-548">Der `Utf8JsonReader` unterstützt das Lesen aus einem UTF-8-codierten [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) oder [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (wobei es sich um das Ergebnis des Lesens aus einem <xref:System.IO.Pipelines.PipeReader> handelt).</span><span class="sxs-lookup"><span data-stu-id="8d577-548">The `Utf8JsonReader` supports reading from a UTF-8 encoded [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>).</span></span>

<span data-ttu-id="8d577-549">Beim synchronen Lesen können Sie die JSON-Nutzlast bis zum Ende des Streams in ein Bytearray einlesen und dieses dann an den Reader übergeben.</span><span class="sxs-lookup"><span data-stu-id="8d577-549">For synchronous reading, you could read the JSON payload until the end of the stream into a byte array and pass that into the reader.</span></span> <span data-ttu-id="8d577-550">Zum Lesen aus einer Zeichenfolge (die UTF-16-codiert ist), rufen Sie <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A> auf,</span><span class="sxs-lookup"><span data-stu-id="8d577-550">For reading from a string (which is encoded as UTF-16), call <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A></span></span> <span data-ttu-id="8d577-551">um die Zeichenfolge zuerst in ein UTF-8-codiertes Bytearray zu transcodieren.</span><span class="sxs-lookup"><span data-stu-id="8d577-551">to first transcode the string to a UTF-8 encoded byte array.</span></span> <span data-ttu-id="8d577-552">Übergeben Sie diese dann an den `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="8d577-552">Then pass that to the `Utf8JsonReader`.</span></span>

<span data-ttu-id="8d577-553">Da der `Utf8JsonReader` die Eingabe als JSON-Text betrachtet, wird eine UTF-8-Bytereihenfolgen-Marke (BOM) als ungültiges JSON-Format angesehen.</span><span class="sxs-lookup"><span data-stu-id="8d577-553">Since the `Utf8JsonReader` considers the input to be JSON text, a UTF-8 byte order mark (BOM) is considered invalid JSON.</span></span> <span data-ttu-id="8d577-554">Der Aufrufer muss dies ausfiltern, bevor die Daten an den Reader übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-554">The caller needs to filter that out before passing the data to the reader.</span></span>

<span data-ttu-id="8d577-555">Codebeispiele finden Sie unter [Verwenden von Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).</span><span class="sxs-lookup"><span data-stu-id="8d577-555">For code examples, see [Use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).</span></span>

### <a name="read-with-multi-segment-readonlysequence"></a><span data-ttu-id="8d577-556">Lesen mit „ReadOnlySequence“ mit mehreren Segmenten</span><span class="sxs-lookup"><span data-stu-id="8d577-556">Read with multi-segment ReadOnlySequence</span></span>

<span data-ttu-id="8d577-557">Wenn es sich bei Ihrer JSON-Eingabe um ein [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) handelt, kann auf jedes JSON-Element über die `ValueSpan`-Eigenschaft des Readers zugegriffen werden, während Sie die Leseschleife durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="8d577-557">If your JSON input is a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), each JSON element can be accessed from the `ValueSpan` property on the reader as you go through the read loop.</span></span> <span data-ttu-id="8d577-558">Wenn Ihre Eingabe jedoch ein [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) ist (was das Ergebnis des Lesens aus einem <xref:System.IO.Pipelines.PipeReader> ist), können einige JSON-Elemente mehrere Segmente des `ReadOnlySequence<byte>`-Objekts umspannen.</span><span class="sxs-lookup"><span data-stu-id="8d577-558">However, if your input is a [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>), some JSON elements might straddle multiple segments of the `ReadOnlySequence<byte>` object.</span></span> <span data-ttu-id="8d577-559">Auf diese Elemente könnte nicht über <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in einem zusammenhängenden Speicherblock zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-559">These elements would not be accessible from <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in a contiguous memory block.</span></span> <span data-ttu-id="8d577-560">Rufen Sie stattdessen, immer wenn Sie ein aus mehreren Segmenten bestehendes `ReadOnlySequence<byte>` als Eingabe haben, die <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A>-Eigenschaft des Readers ab, um zu ermitteln, wie der Zugriff auf das aktuelle JSON-Element erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="8d577-560">Instead, whenever you have a multi-segment `ReadOnlySequence<byte>` as input, poll the <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> property on the reader to figure out how to access the current JSON element.</span></span> <span data-ttu-id="8d577-561">Ein empfohlenes Muster finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="8d577-561">Here's a recommended pattern:</span></span>

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a><span data-ttu-id="8d577-562">Verwenden von „ValueTextEquals“ für das Nachschlagen von Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="8d577-562">Use ValueTextEquals for property name lookups</span></span>

<span data-ttu-id="8d577-563">Verwenden Sie nicht <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>, um byteweise Vergleiche durchzuführen, indem Sie <xref:System.MemoryExtensions.SequenceEqual%2A> für das Nachschlagen von Eigenschaftennamen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8d577-563">Don't use <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> to do byte-by-byte comparisons by calling <xref:System.MemoryExtensions.SequenceEqual%2A> for property name lookups.</span></span> <span data-ttu-id="8d577-564">Rufen Sie stattdessen <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> auf, da diese Methode die Escapezeichen von allen in JSON escapeten Zeichen entfernt.</span><span class="sxs-lookup"><span data-stu-id="8d577-564">Call <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> instead, because that method unescapes any characters that are escaped in the JSON.</span></span> <span data-ttu-id="8d577-565">Hier finden Sie ein Beispiel, das zeigt, wie Sie nach einer Eigenschaft suchen, die „name“ heißt:</span><span class="sxs-lookup"><span data-stu-id="8d577-565">Here's an example that shows how to search for a property that is named "name":</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a><span data-ttu-id="8d577-566">Lesen von Nullwerten in Nullable-Werttypen</span><span class="sxs-lookup"><span data-stu-id="8d577-566">Read null values into nullable value types</span></span>

<span data-ttu-id="8d577-567">`Newtonsoft.Json` bietet APIs, die <xref:System.Nullable%601> zurückgeben, z. B. `ReadAsBoolean`, das einen `Null` `TokenType` für Sie verarbeitet, indem es einen `bool?` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8d577-567">`Newtonsoft.Json` provides APIs that return <xref:System.Nullable%601>, such as `ReadAsBoolean`, which handles a `Null` `TokenType` for you by returning a `bool?`.</span></span> <span data-ttu-id="8d577-568">Die integrierten `System.Text.Json`-APIs geben nur Non-Nullable-Werttypen zurück.</span><span class="sxs-lookup"><span data-stu-id="8d577-568">The built-in `System.Text.Json` APIs return only non-nullable value types.</span></span> <span data-ttu-id="8d577-569"><xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> gibt beispielsweise einen `bool` zurück.</span><span class="sxs-lookup"><span data-stu-id="8d577-569">For example, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> returns a `bool`.</span></span> <span data-ttu-id="8d577-570">Wenn es `Null` in JSON findet, löst es eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="8d577-570">It throws an exception if it finds `Null` in the JSON.</span></span> <span data-ttu-id="8d577-571">In den folgenden Beispielen werden zwei Möglichkeiten zum Behandeln von Nullwerten veranschaulicht, eine, bei der ein Nullable-Werttyp zurückgegeben wird, und eine andere, bei der der Standardwert zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="8d577-571">The following examples show two ways to handle nulls, one by returning a nullable value type and one by returning the default value:</span></span>

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a><span data-ttu-id="8d577-572">Festlegung von Zielversionen</span><span class="sxs-lookup"><span data-stu-id="8d577-572">Multi-targeting</span></span>

<span data-ttu-id="8d577-573">Wenn Sie weiterhin `Newtonsoft.Json` für bestimmte Zielframeworks verwenden müssen, können Sie mehrere Zielversionen verwenden und zwei Implementierungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d577-573">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="8d577-574">Dies ist jedoch nicht trivial und erfordert einige `#ifdefs` sowie Quellduplizierung.</span><span class="sxs-lookup"><span data-stu-id="8d577-574">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="8d577-575">Eine Möglichkeit, so viel Code wie möglich gemeinsam zu verwenden, besteht darin, `Utf8JsonReader` und `Newtonsoft.Json` `JsonTextReader` in einen `ref struct`-Wrapper einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8d577-575">One way to share as much code as possible is to create a `ref struct` wrapper around `Utf8JsonReader` and `Newtonsoft.Json` `JsonTextReader`.</span></span> <span data-ttu-id="8d577-576">Mit diesem Wrapper wird der öffentliche Oberflächenbereich vereinheitlicht, während die Verhaltensunterschiede isoliert werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-576">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="8d577-577">Auf diese Weise können Sie die Änderungen hauptsächlich auf die Konstruktion des Typs beschränken und den neuen Typ gleichzeitig als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="8d577-577">This lets you isolate the changes mainly to the construction of the type, along with passing the new type around by reference.</span></span> <span data-ttu-id="8d577-578">Dies ist das Muster, an dem sich die [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)-Bibliothek orientiert:</span><span class="sxs-lookup"><span data-stu-id="8d577-578">This is the pattern that the [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="8d577-579">UnifiedJsonReader.JsonTextReader.cs</span><span class="sxs-lookup"><span data-stu-id="8d577-579">UnifiedJsonReader.JsonTextReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [<span data-ttu-id="8d577-580">UnifiedJsonReader.Utf8JsonReader.cs</span><span class="sxs-lookup"><span data-stu-id="8d577-580">UnifiedJsonReader.Utf8JsonReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a><span data-ttu-id="8d577-581">„Utf8JsonWriter“ im Vergleich zu „JsonTextWriter“</span><span class="sxs-lookup"><span data-stu-id="8d577-581">Utf8JsonWriter compared to JsonTextWriter</span></span>

<span data-ttu-id="8d577-582">Mit <xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell mit hohem Durchsatz schreiben.</span><span class="sxs-lookup"><span data-stu-id="8d577-582"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="8d577-583">Der Writer ist ein Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d577-583">The writer is a low-level type that can be used to build custom serializers.</span></span>

<span data-ttu-id="8d577-584">In den folgenden Abschnitten werden empfohlene Programmiermuster für die Verwendung von `Utf8JsonWriter` erläutert.</span><span class="sxs-lookup"><span data-stu-id="8d577-584">The following sections explain recommended programming patterns for using `Utf8JsonWriter`.</span></span>

### <a name="write-with-utf-8-text"></a><span data-ttu-id="8d577-585">Schreiben mit UTF-8-Text</span><span class="sxs-lookup"><span data-stu-id="8d577-585">Write with UTF-8 text</span></span>

<span data-ttu-id="8d577-586">Um die bestmögliche Leistung bei Verwendung des `Utf8JsonWriter` zu erzielen, schreiben Sie JSON-Nutzlasten bereits als UTF-8-codierten Text und nicht als UTF-16-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="8d577-586">To achieve the best possible performance while using the `Utf8JsonWriter`, write JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="8d577-587">Verwenden Sie <xref:System.Text.Json.JsonEncodedText>, um bekannte Zeichenfolgen-Eigenschaftsnamen sowie -werte als statische Elemente zwischenzuspeichern und vorzucodieren, und übergeben Sie diese dann an den Writer, anstatt UTF-16-Zeichenfolgenliterale zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d577-587">Use <xref:System.Text.Json.JsonEncodedText> to cache and pre-encode known string property names and values as statics, and pass those to the writer, rather than using UTF-16 string literals.</span></span> <span data-ttu-id="8d577-588">Dies ist schneller als das Zwischenspeichern und Verwenden von UTF-8-Bytearrays.</span><span class="sxs-lookup"><span data-stu-id="8d577-588">This is faster than caching and using UTF-8 byte arrays.</span></span>

<span data-ttu-id="8d577-589">Diese Vorgehensweise funktioniert auch, wenn Sie benutzerdefiniert escapen müssen.</span><span class="sxs-lookup"><span data-stu-id="8d577-589">This approach also works if you need to do custom escaping.</span></span> <span data-ttu-id="8d577-590">`System.Text.Json` gestattet Ihnen nicht, während des Schreibens einer Zeichenfolge das Escapen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8d577-590">`System.Text.Json` doesn't let you disable escaping while writing a string.</span></span> <span data-ttu-id="8d577-591">Sie können jedoch Ihren eigenen benutzerdefinierten <xref:System.Text.Encodings.Web.JavaScriptEncoder> als Option an den Writer übergeben oder Ihren eigenen `JsonEncodedText` erstellen, der Ihren `JavascriptEncoder` für das Escapen verwendet, und dann den `JsonEncodedText` anstelle der Zeichenfolge schreiben.</span><span class="sxs-lookup"><span data-stu-id="8d577-591">However, you could pass in your own custom <xref:System.Text.Encodings.Web.JavaScriptEncoder> as an option to the writer, or create your own `JsonEncodedText` that uses your `JavascriptEncoder` to do the escaping, and then write the `JsonEncodedText` instead of the string.</span></span> <span data-ttu-id="8d577-592">Weitere Informationen finden Sie unter [Anpassen der Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).</span><span class="sxs-lookup"><span data-stu-id="8d577-592">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="write-raw-values"></a><span data-ttu-id="8d577-593">Schreiben von Rohwerten</span><span class="sxs-lookup"><span data-stu-id="8d577-593">Write raw values</span></span>

<span data-ttu-id="8d577-594">Die `Newtonsoft.Json` `WriteRawValue`-Methode schreibt JSON-Rohcode, wenn ein Wert erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="8d577-594">The `Newtonsoft.Json` `WriteRawValue` method writes raw JSON where a value is expected.</span></span> <span data-ttu-id="8d577-595"><xref:System.Text.Json> besitzt keine direkte Entsprechung, aber hier finden Sie eine Problemumgehung, die sicherstellt, dass nur gültiger JSON-Code geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="8d577-595"><xref:System.Text.Json> has no direct equivalent, but here's a workaround that ensures only valid JSON is written:</span></span>

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a><span data-ttu-id="8d577-596">Anpassen des Escapens von Zeichen</span><span class="sxs-lookup"><span data-stu-id="8d577-596">Customize character escaping</span></span>

<span data-ttu-id="8d577-597">Die [StringEscapeHandling-](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)-Einstellung von `JsonTextWriter` bietet Optionen, um alle Nicht-ASCII-Zeichen **oder** HTML-Zeichen zu escapen.</span><span class="sxs-lookup"><span data-stu-id="8d577-597">The [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) setting of `JsonTextWriter` offers options to escape all non-ASCII characters **or** HTML characters.</span></span> <span data-ttu-id="8d577-598">Standardmäßig escapet `Utf8JsonWriter` alle Nicht-ASCII- **und** HTML-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8d577-598">By default, `Utf8JsonWriter` escapes all non-ASCII **and** HTML characters.</span></span> <span data-ttu-id="8d577-599">Dieses Escapen erfolgt als tief greifende Abwehr aus Gründen des Schutzes.</span><span class="sxs-lookup"><span data-stu-id="8d577-599">This escaping is done for defense-in-depth security reasons.</span></span> <span data-ttu-id="8d577-600">Um eine andere Escaperichtlinie anzugeben, erstellen Sie einen <xref:System.Text.Encodings.Web.JavaScriptEncoder>, und legen Sie <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType> fest.</span><span class="sxs-lookup"><span data-stu-id="8d577-600">To specify a different escaping policy, create a <xref:System.Text.Encodings.Web.JavaScriptEncoder> and set <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8d577-601">Weitere Informationen finden Sie unter [Anpassen der Zeichencodierung](system-text-json-how-to.md#customize-character-encoding).</span><span class="sxs-lookup"><span data-stu-id="8d577-601">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="customize-json-format"></a><span data-ttu-id="8d577-602">Anpassen des JSON-Formats</span><span class="sxs-lookup"><span data-stu-id="8d577-602">Customize JSON format</span></span>

<span data-ttu-id="8d577-603">`JsonTextWriter` umfasst die folgenden Einstellungen, für die es bei `Utf8JsonWriter` keine Entsprechung gibt:</span><span class="sxs-lookup"><span data-stu-id="8d577-603">`JsonTextWriter` includes the following settings, for which `Utf8JsonWriter` has no equivalent:</span></span>

* <span data-ttu-id="8d577-604">[Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm): Gibt an, um wie viele Zeichen ein Einzug erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="8d577-604">[Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - Specifies how many characters to indent.</span></span> <span data-ttu-id="8d577-605">`Utf8JsonWriter` führt Einzüge immer um 2 Zeichen aus.</span><span class="sxs-lookup"><span data-stu-id="8d577-605">`Utf8JsonWriter` always does 2-character indentation.</span></span>
* <span data-ttu-id="8d577-606">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm): Gibt das für Einzüge zu verwendende Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="8d577-606">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - Specifies the character to use for indentation.</span></span>  <span data-ttu-id="8d577-607">`Utf8JsonWriter` verwendet immer Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="8d577-607">`Utf8JsonWriter` always uses whitespace.</span></span>
* <span data-ttu-id="8d577-608">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm): Gibt das Zeichen an, das zum Umschließen von Zeichenfolgenwerten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8d577-608">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - Specifies the character to use to surround string values.</span></span>  <span data-ttu-id="8d577-609">`Utf8JsonWriter` verwendet immer doppelte Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="8d577-609">`Utf8JsonWriter` always uses double quotes.</span></span>
* <span data-ttu-id="8d577-610">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm): Gibt an, ob Eigenschaftsnamen in Anführungszeichen gesetzt werden sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="8d577-610">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - Specifies whether or not to surround property names with quotes.</span></span>  <span data-ttu-id="8d577-611">`Utf8JsonWriter` umschließt sie immer mit Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="8d577-611">`Utf8JsonWriter` always surrounds them with quotes.</span></span>

<span data-ttu-id="8d577-612">Es gibt keine Problemumgehungen, mit denen Sie den von `Utf8JsonWriter` auf diese Weisen erzeugten JSON-Code anpassen können.</span><span class="sxs-lookup"><span data-stu-id="8d577-612">There are no workarounds that would let you customize the JSON produced by `Utf8JsonWriter` in these ways.</span></span>

### <a name="write-null-values"></a><span data-ttu-id="8d577-613">Schreiben von Nullwerten</span><span class="sxs-lookup"><span data-stu-id="8d577-613">Write null values</span></span>

<span data-ttu-id="8d577-614">Um Nullwerte mithilfe von `Utf8JsonWriter` zu schreiben, rufen Sie Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="8d577-614">To write null values by using `Utf8JsonWriter`, call:</span></span>

* <span data-ttu-id="8d577-615"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>, um ein Schlüssel-Wert-Paar mit Null als Wert zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8d577-615"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> to write a key-value pair with null as the value.</span></span>
* <span data-ttu-id="8d577-616"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>, um Null als Element eines JSON-Arrays zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8d577-616"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> to write null as an element of a JSON array.</span></span>

<span data-ttu-id="8d577-617">Wenn eine Zeichenfolge Null ist, entsprechen bei einer Zeichenfolgeneigenschaft <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> und <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> den Elementen `WriteNull` und `WriteNullValue`.</span><span class="sxs-lookup"><span data-stu-id="8d577-617">For a string property, if the string is null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> and <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> are equivalent to `WriteNull` and `WriteNullValue`.</span></span>

### <a name="write-timespan-uri-or-char-values"></a><span data-ttu-id="8d577-618">Schreiben von TimeSpan-, Uri- oder char-Werten</span><span class="sxs-lookup"><span data-stu-id="8d577-618">Write Timespan, Uri, or char values</span></span>

<span data-ttu-id="8d577-619">`JsonTextWriter` stellt `WriteValue`-Methoden für [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm)-, [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)- und [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm)-Werte bereit.</span><span class="sxs-lookup"><span data-stu-id="8d577-619">`JsonTextWriter` provides `WriteValue` methods for [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm), and [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) values.</span></span> <span data-ttu-id="8d577-620">`Utf8JsonWriter` verfügt über keine entsprechenden Methoden.</span><span class="sxs-lookup"><span data-stu-id="8d577-620">`Utf8JsonWriter` doesn't have equivalent methods.</span></span> <span data-ttu-id="8d577-621">Formatieren Sie diese Werte stattdessen als Zeichenfolgen (z. B. durch Aufrufen von `ToString()`), und rufen Sie <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="8d577-621">Instead, format these values as strings (by calling `ToString()`, for example) and call <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.</span></span>

### <a name="multi-targeting"></a><span data-ttu-id="8d577-622">Festlegung von Zielversionen</span><span class="sxs-lookup"><span data-stu-id="8d577-622">Multi-targeting</span></span>

<span data-ttu-id="8d577-623">Wenn Sie weiterhin `Newtonsoft.Json` für bestimmte Zielframeworks verwenden müssen, können Sie mehrere Zielversionen verwenden und zwei Implementierungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d577-623">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="8d577-624">Dies ist jedoch nicht trivial und erfordert einige `#ifdefs` sowie Quellduplizierung.</span><span class="sxs-lookup"><span data-stu-id="8d577-624">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="8d577-625">Eine Möglichkeit, so viel Code wie möglich gemeinsam zu verwenden, besteht darin, `Utf8JsonWriter` und `Newtonsoft` `JsonTextWriter` in einen Wrapper einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8d577-625">One way to share as much code as possible is to create a wrapper around `Utf8JsonWriter` and `Newtonsoft` `JsonTextWriter`.</span></span> <span data-ttu-id="8d577-626">Mit diesem Wrapper wird der öffentliche Oberflächenbereich vereinheitlicht, während die Verhaltensunterschiede isoliert werden.</span><span class="sxs-lookup"><span data-stu-id="8d577-626">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="8d577-627">Auf diese Weise können Sie die Änderungen hauptsächlich auf die Konstruktion des Typs beschränken.</span><span class="sxs-lookup"><span data-stu-id="8d577-627">This lets you isolate the changes mainly to the construction of the type.</span></span> <span data-ttu-id="8d577-628">Die [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)-Bibliothek orientiert sich an:</span><span class="sxs-lookup"><span data-stu-id="8d577-628">[Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="8d577-629">UnifiedJsonWriter.JsonTextWriter.cs</span><span class="sxs-lookup"><span data-stu-id="8d577-629">UnifiedJsonWriter.JsonTextWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [<span data-ttu-id="8d577-630">UnifiedJsonWriter.Utf8JsonWriter.cs</span><span class="sxs-lookup"><span data-stu-id="8d577-630">UnifiedJsonWriter.Utf8JsonWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a><span data-ttu-id="8d577-631">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8d577-631">Additional resources</span></span>

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* <span data-ttu-id="8d577-632">[System.Text.Json – Übersicht](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8d577-632">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="8d577-633">[Verwenden von System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="8d577-633">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* [<span data-ttu-id="8d577-634">Schreiben von benutzerdefinierten Konvertern</span><span class="sxs-lookup"><span data-stu-id="8d577-634">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="8d577-635">[Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="8d577-635">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="8d577-636">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="8d577-636">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="8d577-637">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="8d577-637">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
