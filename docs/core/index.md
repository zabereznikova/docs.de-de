---
title: Leitfaden für .NET Core
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET zur Erstellung von Windows-, Linux- und Mac-Apps. Erfahren Sie mehr über .NET Core, und legen Sie los.
author: richlander
ms.date: 09/23/2019
ms.custom: updateeachrelease
ms.openlocfilehash: 95f18ca09852ce139a4b99ed7aef4802d4883e13
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216216"
---
# <a name="net-core-guide"></a><span data-ttu-id="8a2d3-104">Leitfaden für .NET Core</span><span class="sxs-lookup"><span data-stu-id="8a2d3-104">.NET Core Guide</span></span>

<span data-ttu-id="8a2d3-105">[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)-Entwicklungsplattform, die von Microsoft und der .NET-Community auf [GitHub](https://github.com/dotnet/core) gepflegt wird.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="8a2d3-106">Sie ist plattformübergreifend (d.h., sie unterstützt Windows, macOS und Linux) und kann lokal verwendet werden, um Geräte-, Cloud- und IoT-Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="8a2d3-107">In den [weiteren Informationen zu .NET Core](about.md) erfahren Sie mehr über .NET Core, einschließlich den Eigenschaften, den unterstützten Sprachen und Frameworks sowie Schlüssel-APIs.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="8a2d3-108">Sehen Sie sich die [.NET Core-Tutorials](tutorials/index.md) an. Dort erfahren Sie, wie Sie eine einfache .NET Core-Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="8a2d3-109">Es dauert nur wenige Minuten, bis Ihre erste App einsatzbereit ist.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="8a2d3-110">Wenn Sie .NET Core in Ihrem Browser ausprobieren möchten, sehen Sie sich das Onlinetutorial [Zahlen in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) an.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="8a2d3-111">Herunterladen von .NET Core</span><span class="sxs-lookup"><span data-stu-id="8a2d3-111">Download .NET Core</span></span>

<span data-ttu-id="8a2d3-112">Laden Sie das [.NET Core SDK](https://www.microsoft.com/net/download) herunter, um .NET Core auf Ihrem Windows-, macOS- oder Linux-Computer zu testen.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="8a2d3-113">Wenn Sie lieber Docker-Container verwenden möchten, besuchen Sie [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="8a2d3-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="8a2d3-114">Alle .NET Core-Versionen sind unter den [.NET Core-Downloads](https://dotnet.microsoft.com/download/dotnet-core) verfügbar, wenn Sie nach einer anderen .NET Core-Version suchen.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-30"></a><span data-ttu-id="8a2d3-115">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="8a2d3-115">.NET Core 3.0</span></span>

<span data-ttu-id="8a2d3-116">.NET Core 3.0 ist die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-116">The latest version is .NET Core 3.0.</span></span> <span data-ttu-id="8a2d3-117">Neue Features sind unter anderem die Windows Desktop-Unterstützung mit Windows Presentation Foundation (WPF) und Windows Forms, die Webentwicklung Full Stack C# mit Blazor, neue Verbesserungen für SignalR und Azure SignalR Service sowie neue C#-Sprachfunktionen mit C# 8 und noch viel mehr.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-117">New features include Windows Desktop support with Windows Presentation Foundation (WPF) and Windows Forms, full stack C# web development with Blazor, new enhancements to SignalR and Azure SignalR Service, new C# language features with C# 8, and much more.</span></span> <span data-ttu-id="8a2d3-118">Eine Gesamtübersicht über die neuen Features in .NET Core 3.0 finden Sie unter [Neues in .NET Core 3.0](./whats-new/dotnet-core-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="8a2d3-118">For a full listing of the new features in .NET Core 3.0, see [What's new in .NET Core 3.0](./whats-new/dotnet-core-3-0.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="8a2d3-119">Erstellen Ihrer ersten Anwendung</span><span class="sxs-lookup"><span data-stu-id="8a2d3-119">Create your first application</span></span>

<span data-ttu-id="8a2d3-120">Öffnen Sie nach der Installation von .NET Core SDK eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-120">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="8a2d3-121">Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="8a2d3-121">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="8a2d3-122">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8a2d3-122">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="8a2d3-123">Support</span><span class="sxs-lookup"><span data-stu-id="8a2d3-123">Support</span></span>

<span data-ttu-id="8a2d3-124">.NET Core wird von [Microsoft auf Windows, macOS und Linux unterstützt](https://dotnet.microsoft.com/platform/support/policy).</span><span class="sxs-lookup"><span data-stu-id="8a2d3-124">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="8a2d3-125">Die Plattform wird aus Sicherheits- und Qualitätsgründen mehrmals im Jahr (normalerweise monatlich) aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-125">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="8a2d3-126">Binäre .NET Core-Verteilungen werden unter Azure auf von Microsoft verwalteten Servern erstellt und getestet und genauso wie jedes andere Produkt von Microsoft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-126">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="8a2d3-127">[Red Hat unterstützt .NET Core](http://redhatloves.net/) auf Red Hat Enterprise Linux 7 (RHEL).</span><span class="sxs-lookup"><span data-stu-id="8a2d3-127">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="8a2d3-128">Red Hat erstellt .NET Core aus einer Quelle und stellt es in den [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-128">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="8a2d3-129">Red Hat und Microsoft arbeiten eng zusammen, um sicherzustellen, dass .NET Core ebenso auf RHEL funktioniert.</span><span class="sxs-lookup"><span data-stu-id="8a2d3-129">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
