---
title: '.NET Core: Einführung und Übersicht'
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET, mit der Sie Windows-, Linux- und macOS-Apps erstellen können. Erfahren Sie mehr über .NET Core, und legen Sie los.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: b28ad965e54680e2e1134c389266741ade28084f
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226581"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="f8d1d-104">Einführung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="f8d1d-104">Introduction to .NET Core</span></span>

<span data-ttu-id="f8d1d-105">[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)-Entwicklungsplattform.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform.</span></span> <span data-ttu-id="f8d1d-106">Sie können .NET Core-Apps für Windows, macOS und Linux für x64-, x86-, ARM32- und ARM64-Prozessoren erstellen und dabei verschiedene Programmiersprachen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-106">You can create .NET Core apps for Windows, macOS, and Linux for x64, x86, ARM32, and ARM64 processors using multiple programming languages.</span></span> <span data-ttu-id="f8d1d-107">Es werden Frameworks und APIs für die [Cloud](/aspnet/core/), für [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), für [Clientbenutzeroberflächen](../desktop-wpf/overview/index.md) und für [Machine Learning](/dotnet/machine-learning/) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-107">Frameworks and APIs are provided for [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [client UI](../desktop-wpf/overview/index.md), and [machine learning](/dotnet/machine-learning/).</span></span>

<span data-ttu-id="f8d1d-108">[Laden Sie das .NET Core SDK herunter](https://dotnet.microsoft.com/download), um .NET Core auf Ihrem Computer zu testen.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-108">[Download the .NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your machine.</span></span> <span data-ttu-id="f8d1d-109">[.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/) ist die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-109">The latest version is [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

## <a name="download-net-core"></a><span data-ttu-id="f8d1d-110">Herunterladen von .NET Core</span><span class="sxs-lookup"><span data-stu-id="f8d1d-110">Download .NET Core</span></span>

<span data-ttu-id="f8d1d-111">Zum Abrufen von .NET Core stehen die folgenden Möglichkeiten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f8d1d-111">You can get .NET Core in the following ways:</span></span>

* [<span data-ttu-id="f8d1d-112">Installationsprogramme für Windows und macOS</span><span class="sxs-lookup"><span data-stu-id="f8d1d-112">Installers for Windows and macOS</span></span>](https://dotnet.microsoft.com/download)
* [<span data-ttu-id="f8d1d-113">Linux-Pakete</span><span class="sxs-lookup"><span data-stu-id="f8d1d-113">Linux packages</span></span>](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [<span data-ttu-id="f8d1d-114">Docker-Container</span><span class="sxs-lookup"><span data-stu-id="f8d1d-114">Docker containers</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
* [<span data-ttu-id="f8d1d-115">ZIP-Dateien und Tarballs</span><span class="sxs-lookup"><span data-stu-id="f8d1d-115">Zips and tarballs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [<span data-ttu-id="f8d1d-116">Installationsskripts</span><span class="sxs-lookup"><span data-stu-id="f8d1d-116">Install scripts</span></span>](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [<span data-ttu-id="f8d1d-117">Versionshinweise</span><span class="sxs-lookup"><span data-stu-id="f8d1d-117">Release notes</span></span>](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a><span data-ttu-id="f8d1d-118">Erstellen Ihrer ersten Anwendung</span><span class="sxs-lookup"><span data-stu-id="f8d1d-118">Create your first application</span></span>

<span data-ttu-id="f8d1d-119">Öffnen Sie nach der Installation von .NET Core SDK eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="f8d1d-120">Verwenden Sie die folgenden Befehle, um eine Anwendung zu erstellen und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f8d1d-120">Use the following commands to create and run an application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="f8d1d-121">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f8d1d-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="contribute"></a><span data-ttu-id="f8d1d-122">Mitwirken</span><span class="sxs-lookup"><span data-stu-id="f8d1d-122">Contribute</span></span>

<span data-ttu-id="f8d1d-123">.NET Core ist eine offene Plattform.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-123">.NET Core is an open platform.</span></span> <span data-ttu-id="f8d1d-124">Alle Benutzer dürfen gerne daran mitwirken.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-124">Everyone is welcome to participate.</span></span>

* <span data-ttu-id="f8d1d-125">Bei Produktproblemen und -fragen hilft die [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/61/index.html).</span><span class="sxs-lookup"><span data-stu-id="f8d1d-125">File product issues and questions at [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span></span>
* <span data-ttu-id="f8d1d-126">Beiträge müssen über eins der Projektrepositorys eingereicht werden, z. B. [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn) oder [aspnetcore](https://github.com/dotnet/aspnetcore).</span><span class="sxs-lookup"><span data-stu-id="f8d1d-126">Product contributions should be made on one of the project repositories, such as [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn), or [aspnetcore](https://github.com/dotnet/aspnetcore).</span></span> <span data-ttu-id="f8d1d-127">Weitere Informationen finden Sie unter [.NET Core-Repositorys](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span><span class="sxs-lookup"><span data-stu-id="f8d1d-127">For more information, see [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span></span>

## <a name="support"></a><span data-ttu-id="f8d1d-128">Support</span><span class="sxs-lookup"><span data-stu-id="f8d1d-128">Support</span></span>

<span data-ttu-id="f8d1d-129">.NET Core wird von Microsoft unter Windows, macOS und Linux sowie von Red Hat unter Red Hat Enterprise Linux unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8d1d-129">.NET Core is supported by Microsoft on Windows, macOS, and Linux and by Red Hat on Red Hat Enterprise Linux.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8d1d-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f8d1d-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f8d1d-131">.NET Core-Tutorials</span><span class="sxs-lookup"><span data-stu-id="f8d1d-131">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="f8d1d-132">.NET Core im Browser testen</span><span class="sxs-lookup"><span data-stu-id="f8d1d-132">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
