---
ms.openlocfilehash: ec6724ab378dd614c55a024ede18d997d27be3a3
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032685"
---
### <a name="target-framework-net-framework-support-dropped"></a><span data-ttu-id="5ddd7-101">Zielframework: .NET Framework-Unterstützung aufgehoben</span><span class="sxs-lookup"><span data-stu-id="5ddd7-101">Target framework: .NET Framework support dropped</span></span>

<span data-ttu-id="5ddd7-102">Ab ASP.NET Core 3.0 ist .NET Framework kein unterstütztes Zielframework mehr.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-102">Starting with ASP.NET Core 3.0, .NET Framework is an unsupported target framework.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5ddd7-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5ddd7-103">Change description</span></span>

<span data-ttu-id="5ddd7-104">.NET Framework 4.8 ist die letzte Hauptversion von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-104">.NET Framework 4.8 is the last major version of .NET Framework.</span></span> <span data-ttu-id="5ddd7-105">Neue ASP.NET Core-Apps sollten mit .NET Core erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-105">New ASP.NET Core apps should be built on .NET Core.</span></span> <span data-ttu-id="5ddd7-106">Ab dem Release .NET Core 3.0 können Sie sich ASP.NET Core 3.0 als Teil von .NET Core vorstellen.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-106">Starting with the .NET Core 3.0 release, you can think of ASP.NET Core 3.0 as being part of .NET Core.</span></span>

<span data-ttu-id="5ddd7-107">Kunden, die ASP.NET Core mit .NET Framework verwenden, erhalten mit dem [LTS-Release 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1) weiterhin vollständige Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-107">Customers using ASP.NET Core with .NET Framework can continue in a fully supported fashion using the [2.1 LTS release](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="5ddd7-108">Support und Wartung für 2.1 werden mindestens bis zum 21. August 2021 fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-108">Support and servicing for 2.1 continues until at least August 21, 2021.</span></span> <span data-ttu-id="5ddd7-109">Dieses Datum liegt gemäß der [.NET-Supportrichtlinie](https://dotnet.microsoft.com/platform/support-policy) drei Jahre nach der Bekanntgabe des LTS-Release.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-109">This date is three years after declaration of the LTS release per the [.NET Support Policy](https://dotnet.microsoft.com/platform/support-policy).</span></span> <span data-ttu-id="5ddd7-110">Die Unterstützung für ASP.NET Core 2.1-Pakete **auf Grundlage von .NET Framework** wird unbegrenzt verlängert (ähnlich der [Dienstrichtlinie für andere paketbasierte ASP.NET-Frameworks](https://dotnet.microsoft.com/platform/support/policy/aspnet)).</span><span class="sxs-lookup"><span data-stu-id="5ddd7-110">Support for ASP.NET Core 2.1 packages **on .NET Framework** will extend indefinitely, similar to the [servicing policy for other package-based ASP.NET frameworks](https://dotnet.microsoft.com/platform/support/policy/aspnet).</span></span>

<span data-ttu-id="5ddd7-111">Weitere Informationen zum Portieren von .NET Framework zu .NET Core finden Sie unter [Portieren zu .NET Core](~/docs/core/porting/index.md).</span><span class="sxs-lookup"><span data-stu-id="5ddd7-111">For more information about porting from .NET Framework to .NET Core, see [Porting to .NET Core](~/docs/core/porting/index.md).</span></span>

<span data-ttu-id="5ddd7-112">`Microsoft.Extensions`-Pakete (z. B. Protokollierung, Abhängigkeitsinjektion und Konfiguration) und Entity Framework Core sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-112">`Microsoft.Extensions` packages (such as logging, dependency injection, and configuration) and Entity Framework Core aren't affected.</span></span> <span data-ttu-id="5ddd7-113">Sie unterstützen .NET Standard auch weiterhin.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-113">They'll continue to support .NET Standard.</span></span>

<span data-ttu-id="5ddd7-114">Weitere Informationen zu den Gründen für diese Änderung finden Sie im [ursprünglichen Blogbeitrag](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="5ddd7-114">For more information on the motivation for this change, see [the original blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5ddd7-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5ddd7-115">Version introduced</span></span>

<span data-ttu-id="5ddd7-116">3.0</span><span class="sxs-lookup"><span data-stu-id="5ddd7-116">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5ddd7-117">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="5ddd7-117">Old behavior</span></span>

<span data-ttu-id="5ddd7-118">ASP.NET Core-Apps konnten unter .NET Core oder .NET Framework ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-118">ASP.NET Core apps could run on either .NET Core or .NET Framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5ddd7-119">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="5ddd7-119">New behavior</span></span>

<span data-ttu-id="5ddd7-120">ASP.NET Core-Apps können nur unter .NET Core ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-120">ASP.NET Core apps can only be run on .NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5ddd7-121">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5ddd7-121">Recommended action</span></span>

<span data-ttu-id="5ddd7-122">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5ddd7-122">Take one of the following actions:</span></span>

- <span data-ttu-id="5ddd7-123">Verwenden Sie für Ihre App auch weiterhin ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-123">Keep your app on ASP.NET Core 2.1.</span></span>
- <span data-ttu-id="5ddd7-124">Migrieren Sie Ihre App und die Abhängigkeiten zu .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5ddd7-124">Migrate your app and dependencies to .NET Core.</span></span>

#### <a name="category"></a><span data-ttu-id="5ddd7-125">Kategorie</span><span class="sxs-lookup"><span data-stu-id="5ddd7-125">Category</span></span>

<span data-ttu-id="5ddd7-126">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5ddd7-126">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5ddd7-127">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5ddd7-127">Affected APIs</span></span>

<span data-ttu-id="5ddd7-128">Keiner</span><span class="sxs-lookup"><span data-stu-id="5ddd7-128">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
