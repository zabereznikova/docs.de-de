---
title: Leitfaden für .NET Core
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET zur Erstellung von Windows-, Linux- und Mac-Apps. Erfahren Sie mehr über .NET Core, und legen Sie los.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: b2622dba53d64c9dcf58e852d57de117fe79eb2e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837011"
---
# <a name="net-core-guide"></a><span data-ttu-id="cb084-104">Leitfaden für .NET Core</span><span class="sxs-lookup"><span data-stu-id="cb084-104">.NET Core Guide</span></span>

<span data-ttu-id="cb084-105">[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)-Entwicklungsplattform, die von Microsoft und der .NET-Community auf [GitHub](https://github.com/dotnet/core) gepflegt wird.</span><span class="sxs-lookup"><span data-stu-id="cb084-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="cb084-106">Sie ist plattformübergreifend (d.h., sie unterstützt Windows, macOS und Linux) und kann lokal verwendet werden, um Geräte-, Cloud- und IoT-Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb084-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="cb084-107">In den [weiteren Informationen zu .NET Core](about.md) erfahren Sie mehr über .NET Core, einschließlich den Eigenschaften, den unterstützten Sprachen und Frameworks sowie Schlüssel-APIs.</span><span class="sxs-lookup"><span data-stu-id="cb084-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="cb084-108">Sehen Sie sich die [.NET Core-Tutorials](tutorials/index.md) an. Dort erfahren Sie, wie Sie eine einfache .NET Core-Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb084-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="cb084-109">Es dauert nur wenige Minuten, bis Ihre erste App einsatzbereit ist.</span><span class="sxs-lookup"><span data-stu-id="cb084-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="cb084-110">Wenn Sie .NET Core in Ihrem Browser ausprobieren möchten, sehen Sie sich das Onlinetutorial [Zahlen in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) an.</span><span class="sxs-lookup"><span data-stu-id="cb084-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="cb084-111">Herunterladen von .NET Core</span><span class="sxs-lookup"><span data-stu-id="cb084-111">Download .NET Core</span></span>

<span data-ttu-id="cb084-112">Laden Sie das [.NET Core SDK](https://www.microsoft.com/net/download) herunter, um .NET Core auf Ihrem Windows-, macOS- oder Linux-Computer zu testen.</span><span class="sxs-lookup"><span data-stu-id="cb084-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="cb084-113">Wenn Sie lieber Docker-Container verwenden möchten, besuchen Sie [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="cb084-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="cb084-114">Alle .NET Core-Versionen sind unter den [.NET Core-Downloads](https://dotnet.microsoft.com/download/dotnet-core) verfügbar, wenn Sie nach einer anderen .NET Core-Version suchen.</span><span class="sxs-lookup"><span data-stu-id="cb084-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-31"></a><span data-ttu-id="cb084-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="cb084-115">.NET Core 3.1</span></span>

<span data-ttu-id="cb084-116">.NET Core 3.1 ist die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="cb084-116">The latest version is .NET Core 3.1.</span></span> <span data-ttu-id="cb084-117">Darin enthalten sind geringfügige Verbesserungen im Vergleich zu .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="cb084-117">Which includes minor improvements over .NET Core 3.0.</span></span> <span data-ttu-id="cb084-118">Allerdings ist .NET Core 3.1 ein langfristig unterstütztes Release.</span><span class="sxs-lookup"><span data-stu-id="cb084-118">However, .NET Core 3.1 is a long-term supported release.</span></span> <span data-ttu-id="cb084-119">Weitere Informationen zum .NET Core 3.1-Release finden Sie unter [Neuerungen in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span><span class="sxs-lookup"><span data-stu-id="cb084-119">For more information about the .NET Core 3.1 release, see [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="cb084-120">Erstellen Ihrer ersten Anwendung</span><span class="sxs-lookup"><span data-stu-id="cb084-120">Create your first application</span></span>

<span data-ttu-id="cb084-121">Öffnen Sie nach der Installation von .NET Core SDK eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="cb084-121">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="cb084-122">Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="cb084-122">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="cb084-123">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cb084-123">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="cb084-124">Support</span><span class="sxs-lookup"><span data-stu-id="cb084-124">Support</span></span>

<span data-ttu-id="cb084-125">.NET Core wird von [Microsoft auf Windows, macOS und Linux unterstützt](https://dotnet.microsoft.com/platform/support/policy).</span><span class="sxs-lookup"><span data-stu-id="cb084-125">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="cb084-126">Die Plattform wird aus Sicherheits- und Qualitätsgründen mehrmals im Jahr (normalerweise monatlich) aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="cb084-126">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="cb084-127">Binäre .NET Core-Verteilungen werden unter Azure auf von Microsoft verwalteten Servern erstellt und getestet und genauso wie jedes andere Produkt von Microsoft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb084-127">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="cb084-128">[Red Hat unterstützt .NET Core](http://redhatloves.net/) auf Red Hat Enterprise Linux 7 (RHEL).</span><span class="sxs-lookup"><span data-stu-id="cb084-128">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="cb084-129">Red Hat erstellt .NET Core aus einer Quelle und stellt es in den [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cb084-129">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="cb084-130">Red Hat und Microsoft arbeiten eng zusammen, um sicherzustellen, dass .NET Core ebenso auf RHEL funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cb084-130">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
