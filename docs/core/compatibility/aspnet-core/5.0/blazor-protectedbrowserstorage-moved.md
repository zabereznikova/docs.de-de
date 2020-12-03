---
title: 'Breaking Change: Blazor: Das Feature ProtectedBrowserStorage wurde in das freigegebene Framework verschoben'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Das Feature ProtectedBrowserStorage wurde in das freigegebene Framework verschoben'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759426"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="699fc-103">Blazor: Das Feature ProtectedBrowserStorage wurde in das freigegebene Framework verschoben</span><span class="sxs-lookup"><span data-stu-id="699fc-103">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="699fc-104">Im Rahmen des Release von ASP.NET Core 5.0 RC2 wurde das Feature `ProtectedBrowserStorage` in das freigegebene Framework von ASP.NET Core verschoben.</span><span class="sxs-lookup"><span data-stu-id="699fc-104">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="699fc-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="699fc-105">Version introduced</span></span>

<span data-ttu-id="699fc-106">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="699fc-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="699fc-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="699fc-107">Old behavior</span></span>

<span data-ttu-id="699fc-108">In ASP.NET Core 5.0, Preview 8 ist das Feature als Teil des Pakets [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) verfügbar, kann aber nur in Blazor WebAssembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="699fc-108">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="699fc-109">In ASP.NET Core 5.0 RC1 ist das Feature als Teil des Pakets [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) verfügbar, das auf das gemeinsame Framework `Microsoft.AspNetCore.App` verweist.</span><span class="sxs-lookup"><span data-stu-id="699fc-109">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="699fc-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="699fc-110">New behavior</span></span>

<span data-ttu-id="699fc-111">In ASP.NET Core 5.0 RC2 wird kein Verweis auf ein NuGet-Paket mehr benötigt, um auf das Feature zu verweisen und dieses zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="699fc-111">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="699fc-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="699fc-112">Reason for change</span></span>

<span data-ttu-id="699fc-113">Die Umstellung auf das freigegebene Framework sorgt für mehr Benutzerfreundlichkeit.</span><span class="sxs-lookup"><span data-stu-id="699fc-113">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="699fc-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="699fc-114">Recommended action</span></span>

<span data-ttu-id="699fc-115">Wenn Sie ein Upgrade von ASP.NET Core 5.0 RC1 ausführen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="699fc-115">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="699fc-116">Entfernen Sie den Verweis auf das Paket `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` aus dem Projekt.</span><span class="sxs-lookup"><span data-stu-id="699fc-116">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="699fc-117">Ersetzen Sie `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` durch `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="699fc-117">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="699fc-118">Entfernen Sie den Aufruf von `AddProtectedBrowserStorage` aus ihrer `Startup`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="699fc-118">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="699fc-119">Wenn Sie ein Upgrade von ASP.NET Core 5.0, Preview 8 ausführen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="699fc-119">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="699fc-120">Entfernen Sie den Verweis auf das Paket `Microsoft.AspNetCore.Components.Web.Extensions` aus dem Projekt.</span><span class="sxs-lookup"><span data-stu-id="699fc-120">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="699fc-121">Ersetzen Sie `using Microsoft.AspNetCore.Components.Web.Extensions;` durch `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="699fc-121">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="699fc-122">Entfernen Sie den Aufruf von `AddProtectedBrowserStorage` aus ihrer `Startup`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="699fc-122">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="699fc-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="699fc-123">Affected APIs</span></span>

<span data-ttu-id="699fc-124">Keine</span><span class="sxs-lookup"><span data-stu-id="699fc-124">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
