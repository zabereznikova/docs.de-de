---
title: '.NET Core: Einführung und Übersicht'
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET, mit der Sie Windows-, Linux- und macOS-Apps erstellen können. Erfahren Sie mehr über .NET Core, und legen Sie los.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: f99b446bbd38b2b814c13afa13ab34cd5c9aa086
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645521"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="3dcf3-104">Einführung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="3dcf3-104">Introduction to .NET Core</span></span>

<span data-ttu-id="3dcf3-105">[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)-Entwicklungsplattform.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform.</span></span> <span data-ttu-id="3dcf3-106">Sie können .NET Core-Apps für Windows, macOS und Linux für x64-, x86-, ARM32- und ARM64-Prozessoren erstellen und dabei verschiedene Programmiersprachen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-106">You can create .NET Core apps for Windows, macOS, and Linux for x64, x86, ARM32, and ARM64 processors using multiple programming languages.</span></span> <span data-ttu-id="3dcf3-107">Es werden Frameworks und APIs für die [Cloud](/aspnet/core/), für [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), für [Clientbenutzeroberflächen](../desktop-wpf/overview/index.md) und für [Machine Learning](/dotnet/machine-learning/) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-107">Frameworks and APIs are provided for [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [client UI](../desktop-wpf/overview/index.md), and [machine learning](/dotnet/machine-learning/).</span></span>

<span data-ttu-id="3dcf3-108">[Laden Sie das .NET Core SDK herunter](https://dotnet.microsoft.com/download), um .NET Core auf Ihrem Computer zu testen.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-108">[Download the .NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your machine.</span></span> <span data-ttu-id="3dcf3-109">[.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/) ist die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-109">The latest version is [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

## <a name="download-net-core"></a><span data-ttu-id="3dcf3-110">Herunterladen von .NET Core</span><span class="sxs-lookup"><span data-stu-id="3dcf3-110">Download .NET Core</span></span>

<span data-ttu-id="3dcf3-111">Zum Abrufen von .NET Core stehen die folgenden Möglichkeiten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="3dcf3-111">You can get .NET Core in the following ways:</span></span>

* [<span data-ttu-id="3dcf3-112">Installationsprogramme für Windows und macOS</span><span class="sxs-lookup"><span data-stu-id="3dcf3-112">Installers for Windows and macOS</span></span>](https://dotnet.microsoft.com/download)
* [<span data-ttu-id="3dcf3-113">Linux-Pakete</span><span class="sxs-lookup"><span data-stu-id="3dcf3-113">Linux packages</span></span>](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [<span data-ttu-id="3dcf3-114">Docker-Container</span><span class="sxs-lookup"><span data-stu-id="3dcf3-114">Docker containers</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
* [<span data-ttu-id="3dcf3-115">ZIP-Dateien und Tarballs</span><span class="sxs-lookup"><span data-stu-id="3dcf3-115">Zips and tar balls</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [<span data-ttu-id="3dcf3-116">Installationsskripts</span><span class="sxs-lookup"><span data-stu-id="3dcf3-116">Install scripts</span></span>](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [<span data-ttu-id="3dcf3-117">Versionshinweise</span><span class="sxs-lookup"><span data-stu-id="3dcf3-117">Release notes</span></span>](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a><span data-ttu-id="3dcf3-118">Erstellen Ihrer ersten Anwendung</span><span class="sxs-lookup"><span data-stu-id="3dcf3-118">Create your first application</span></span>

<span data-ttu-id="3dcf3-119">Öffnen Sie nach der Installation von .NET Core SDK eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="3dcf3-120">Verwenden Sie die folgenden Befehle, um eine Anwendung zu erstellen und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3dcf3-120">Use the following commands to create and run an application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="3dcf3-121">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3dcf3-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="contribute"></a><span data-ttu-id="3dcf3-122">Mitwirken</span><span class="sxs-lookup"><span data-stu-id="3dcf3-122">Contribute</span></span>

<span data-ttu-id="3dcf3-123">.NET Core ist eine offene Plattform.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-123">.NET Core is an open platform.</span></span> <span data-ttu-id="3dcf3-124">Alle Benutzer dürfen gerne daran mitwirken.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-124">Everyone is welcome to participate.</span></span>

* <span data-ttu-id="3dcf3-125">Bei Produktproblemen und -fragen hilft die [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/61/index.html).</span><span class="sxs-lookup"><span data-stu-id="3dcf3-125">File product issues and questions at [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span></span>
* <span data-ttu-id="3dcf3-126">Beiträge müssen über eins der Projektrepositorys eingereicht werden, z. B. [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn) oder [aspnetcore](https://github.com/dotnet/aspnetcore).</span><span class="sxs-lookup"><span data-stu-id="3dcf3-126">Product contributions should be made on one of the project repositories, such as [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn), or [aspnetcore](https://github.com/dotnet/aspnetcore).</span></span> <span data-ttu-id="3dcf3-127">Weitere Informationen finden Sie unter [.NET Core-Repositorys](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span><span class="sxs-lookup"><span data-stu-id="3dcf3-127">For more information, see [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span></span>

## <a name="support"></a><span data-ttu-id="3dcf3-128">Support</span><span class="sxs-lookup"><span data-stu-id="3dcf3-128">Support</span></span>

<span data-ttu-id="3dcf3-129">.NET Core wird von Microsoft unter Windows, macOS und Linux sowie von Red Hat unter Red Hat Enterprise Linux unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-129">.NET Core is supported by Microsoft on Windows, macOS, and Linux and by Red Hat on Red Hat Enterprise Linux.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3dcf3-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3dcf3-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3dcf3-131">.NET Core-Tutorials</span><span class="sxs-lookup"><span data-stu-id="3dcf3-131">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="3dcf3-132">.NET Core im Browser testen</span><span class="sxs-lookup"><span data-stu-id="3dcf3-132">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
