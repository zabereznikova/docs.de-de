---
title: Leitfaden für .NET Core
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET zur Erstellung von Windows-, Linux- und Mac-Apps. Erfahren Sie mehr über .NET Core, und legen Sie los.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: b302b6fc7e097a811c718d2244f603246cb5c259
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49121037"
---
# <a name="net-core-guide"></a><span data-ttu-id="0b757-104">Leitfaden für .NET Core</span><span class="sxs-lookup"><span data-stu-id="0b757-104">.NET Core Guide</span></span>

<span data-ttu-id="0b757-105">[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)-Entwicklungsplattform, die von Microsoft und der .NET-Community auf [GitHub](https://github.com/dotnet/core) gepflegt wird.</span><span class="sxs-lookup"><span data-stu-id="0b757-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="0b757-106">Sie ist plattformübergreifend, d.h., sie unterstützt Windows, macOS und Linux und kann lokal, in der Cloud und in IoT-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b757-106">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and IoT applications.</span></span>

<span data-ttu-id="0b757-107">In den [weiteren Informationen zu .NET Core](about.md) erfahren Sie mehr über .NET Core, einschließlich den Eigenschaften, den unterstützten Sprachen und Frameworks sowie Schlüssel-APIs.</span><span class="sxs-lookup"><span data-stu-id="0b757-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="0b757-108">Sehen Sie sich die [.NET Core-Tutorials](tutorials/index.md) an. Dort erfahren Sie, wie Sie eine einfache .NET Core-Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b757-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="0b757-109">Es dauert nur wenige Minuten, bis Ihre erste App einsatzbereit ist.</span><span class="sxs-lookup"><span data-stu-id="0b757-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="0b757-110">Wenn Sie .NET Core in Ihrem Browser ausprobieren möchten, sehen Sie sich den Schnellstart [„Hello World“ in C#](https://docs.microsoft.com/dotnet/csharp/quick-starts/numbers-in-csharp) an.</span><span class="sxs-lookup"><span data-stu-id="0b757-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](https://docs.microsoft.com/dotnet/csharp/quick-starts/numbers-in-csharp) quickstart.</span></span>

## <a name="download-net-core-21"></a><span data-ttu-id="0b757-111">.NET Core 2.1 herunterladen</span><span class="sxs-lookup"><span data-stu-id="0b757-111">Download .NET Core 2.1</span></span>

<span data-ttu-id="0b757-112">Laden Sie das [.NET Core 2.1-SDK](https://www.microsoft.com/net/download) herunter, um .NET Core auf Ihrem Windows-, macOS- oder Linux-Computer zu testen.</span><span class="sxs-lookup"><span data-stu-id="0b757-112">Download the [.NET Core  2.1 SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="0b757-113">Besuchen Sie [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/), wenn Sie lieber Docker-Container verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0b757-113">Visit [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) if you prefer to use Docker containers.</span></span>

<span data-ttu-id="0b757-114">Alle .NET Core-Versionen sind unter den [.NET Core-Downloads](https://www.microsoft.com/net/download/archives) verfügbar, wenn Sie nach einer anderen .NET Core-Version suchen.</span><span class="sxs-lookup"><span data-stu-id="0b757-114">All .NET Core versions are available at [.NET Core Downloads](https://www.microsoft.com/net/download/archives) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-21"></a><span data-ttu-id="0b757-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0b757-115">.NET Core 2.1</span></span>

<span data-ttu-id="0b757-116">[.NET Core 2.1](whats-new/dotnet-core-2-1.md) ist die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="0b757-116">The latest version is [.NET Core 2.1](whats-new/dotnet-core-2-1.md).</span></span> <span data-ttu-id="0b757-117">Neue Features sind unter anderem: globale Tools, Hochleistungs-APIs (z.B. <xref:System.Span%601?displayProperty=nameWithType>), mehrstufige JIT-Kompilierung, Leistungsverbesserungen für [Build](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) und [Runtime](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/) sowie Unterstützung für Alpine und ARM32.</span><span class="sxs-lookup"><span data-stu-id="0b757-117">New features include: global tools, high-performance APIs (such as <xref:System.Span%601?displayProperty=nameWithType>), tiered JIT compilation, [build](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and [runtime performance improvements](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/), and support for Alpine and ARM32.</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="0b757-118">Erstellen Ihrer ersten Anwendung</span><span class="sxs-lookup"><span data-stu-id="0b757-118">Create your first application</span></span>

<span data-ttu-id="0b757-119">Öffnen Sie nach der Installation von .NET Core SDK eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="0b757-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="0b757-120">Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="0b757-120">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="0b757-121">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0b757-121">You should see the following output:</span></span>

```console
Hello World!
```

## <a name="support"></a><span data-ttu-id="0b757-122">Unterstützung</span><span class="sxs-lookup"><span data-stu-id="0b757-122">Support</span></span>

<span data-ttu-id="0b757-123">.NET Core wird von [Microsoft auf Windows, Mac OS und Linux unterstützt](https://www.microsoft.com/net/support/policy).</span><span class="sxs-lookup"><span data-stu-id="0b757-123">.NET Core is [supported by Microsoft](https://www.microsoft.com/net/support/policy), on Windows, macOS and Linux.</span></span> <span data-ttu-id="0b757-124">Die Plattform wird aus Sicherheits- und Qualitätsgründen mehrmals im Jahr (normalerweise monatlich) aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0b757-124">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="0b757-125">Binäre .NET Core-Verteilungen werden unter Azure auf von Microsoft verwalteten Servern erstellt und getestet und genauso wie jedes andere Produkt von Microsoft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0b757-125">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="0b757-126">[Red Hat unterstützt .NET Core](http://redhatloves.net/) auf Red Hat Enterprise Linux 7 (RHEL).</span><span class="sxs-lookup"><span data-stu-id="0b757-126">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="0b757-127">Red Hat erstellt .NET Core aus einer Quelle und stellt es in den [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0b757-127">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="0b757-128">Red Hat und Microsoft arbeiten eng zusammen, um sicherzustellen, dass .NET Core ebenso auf RHEL funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0b757-128">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
