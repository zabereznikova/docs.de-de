---
title: Tools für Azure .NET- und .NET Core-Entwickler
description: Informationen zum Abrufen der Tools für das Verwenden der Azure .NET-Bibliotheken in einer Windows-, Linux- oder Mac-Umgebung
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433163"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="f5c96-103">Tools für .NET- und .NET Core-Azure-Entwickler</span><span class="sxs-lookup"><span data-stu-id="f5c96-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="f5c96-104">SDK-Downloads</span><span class="sxs-lookup"><span data-stu-id="f5c96-104">SDK downloads</span></span>

<span data-ttu-id="f5c96-105">Azure-Bibliotheken für .NET werden als [NuGet-Pakete](https://www.nuget.org/packages?q=windowsazureofficial)implementiert.</span><span class="sxs-lookup"><span data-stu-id="f5c96-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="f5c96-106">Installationsanweisungen, die vom Azure-Dienst organisiert werden, finden Sie in der [API-Referenz.](/dotnet/api/overview/azure/?view=azure-dotnet)</span><span class="sxs-lookup"><span data-stu-id="f5c96-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="f5c96-107">Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="f5c96-107">Development tools</span></span>

<span data-ttu-id="f5c96-108">Visual Studio verfügt über Tools für viele Azure-Dienste, die integriert sind.</span><span class="sxs-lookup"><span data-stu-id="f5c96-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="f5c96-109">Für einige Azure-Dienste sind zusätzliche Tools oder Emulatoren verfügbar, z. [B. Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="f5c96-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="f5c96-110">Weitere Tools finden Sie ggf. in der Dokumentation für Ihren Azure-Dienst.</span><span class="sxs-lookup"><span data-stu-id="f5c96-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="f5c96-111">Mit diesen Anweisungen wird die empfohlene Startentwicklungsumgebung für Ihr Betriebssystem installiert.</span><span class="sxs-lookup"><span data-stu-id="f5c96-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="f5c96-112">Windows</span><span class="sxs-lookup"><span data-stu-id="f5c96-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="f5c96-113">Visual Studio-Versionen 2017 und höher bieten integrierte Unterstützung für die Azure-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="f5c96-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="f5c96-114">In den folgenden Schritten wird beschrieben, wie Sie die Azure-Entwicklungsunterstützung in Visual Studio aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5c96-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="f5c96-115"><a href="vs2015-install.md">Befolgen Sie für</a>Visual Studio 2015 und früher diese Anweisungen .</span><span class="sxs-lookup"><span data-stu-id="f5c96-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="f5c96-116">Schritt 1: Herunterladen von Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f5c96-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="f5c96-117">Sie können diesen Schritt überspringen, wenn Sie Visual Studio 2019 bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="f5c96-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5c96-118">Visual Studio 2019 herunterladen</span><span class="sxs-lookup"><span data-stu-id="f5c96-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="f5c96-119">Schritt 2: Installieren der beiden Azure-Workloads</span><span class="sxs-lookup"><span data-stu-id="f5c96-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="f5c96-120">Installieren Sie Visual Studio im Visual Studio-Installationsprogramm (oder ändern Sie eine vorhandene Installation).</span><span class="sxs-lookup"><span data-stu-id="f5c96-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="f5c96-121">Stellen Sie sicher, dass die *Azure-Entwicklungs-* und *ASP.NET- und Webentwicklungsworkloads* ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="f5c96-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="f5c96-122">Schritt 3: Entwickeln mit .NET in Azure</span><span class="sxs-lookup"><span data-stu-id="f5c96-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="f5c96-123">Beginnen Sie der [Bereitstellung Ihrer ersten ASP.NET Core-Web-App in Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f5c96-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="f5c96-124">macOS</span><span class="sxs-lookup"><span data-stu-id="f5c96-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="f5c96-125">Visual Studio für Mac ist alles, was Sie für die Azure-Entwicklung brauchen.</span><span class="sxs-lookup"><span data-stu-id="f5c96-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="f5c96-126">Schritt 1: Herunterladen von Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="f5c96-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5c96-127">Visual Studio für Mac herunterladen</span><span class="sxs-lookup"><span data-stu-id="f5c96-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="f5c96-128">Während der Installation werden Azure-Tools standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f5c96-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="f5c96-129">Linux</span><span class="sxs-lookup"><span data-stu-id="f5c96-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="f5c96-130">Visual Studio Code ist alles, was Sie für die Azure-Entwicklung unter Linux brauchen.</span><span class="sxs-lookup"><span data-stu-id="f5c96-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="f5c96-131">Schritt 1. .NET Core SDK herunterladen</span><span class="sxs-lookup"><span data-stu-id="f5c96-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="f5c96-132">Das SDK und Befehlszeilentools für .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="f5c96-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5c96-133">.NET Core SDK herunterladen</span><span class="sxs-lookup"><span data-stu-id="f5c96-133">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="f5c96-134">Schritt 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f5c96-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="f5c96-135">Bearbeiten und Debuggen von .NET Core-Apps unter jedem Betriebssystem: Windows, Mac und Linux.</span><span class="sxs-lookup"><span data-stu-id="f5c96-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5c96-136">Visual Studio Code herunterladen</span><span class="sxs-lookup"><span data-stu-id="f5c96-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
