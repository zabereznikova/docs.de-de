---
title: Tools für Azure .NET-Entwickler
description: Informationen zum Abrufen der Tools für das Verwenden der Azure .NET-Bibliotheken in einer Windows-, Linux- oder Mac-Umgebung
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174834"
---
# <a name="azure-tools-for-developing-with-net"></a><span data-ttu-id="486e4-103">Azure-Tools für die Entwicklung mit .NET</span><span class="sxs-lookup"><span data-stu-id="486e4-103">Azure tools for developing with .NET</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="486e4-104">SDK-Downloads</span><span class="sxs-lookup"><span data-stu-id="486e4-104">SDK downloads</span></span>

<span data-ttu-id="486e4-105">Azure-Bibliotheken für .NET werden als [NuGet-Pakete](https://www.nuget.org/packages?q=windowsazureofficial) implementiert.</span><span class="sxs-lookup"><span data-stu-id="486e4-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="486e4-106">In der [API-Referenz](/dotnet/api/overview/azure/?view=azure-dotnet) finden Sie die Referenzdokumentation, aufgeschlüsselt nach Azure-Diensten.</span><span class="sxs-lookup"><span data-stu-id="486e4-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for reference documentation organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="486e4-107">Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="486e4-107">Development tools</span></span>

<span data-ttu-id="486e4-108">In Visual Studio sind Tools für viele Azure-Dienste integriert.</span><span class="sxs-lookup"><span data-stu-id="486e4-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="486e4-109">Für bestimmte Azure-Dienste sind zusätzliche Tools oder Emulatoren verfügbar, z. B. für den [Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="486e4-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="486e4-110">Wenn Sie weitere Tools für Ihren Azure-Dienst suchen, ziehen Sie die Dokumentation zurate.</span><span class="sxs-lookup"><span data-stu-id="486e4-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="486e4-111">Wählen Sie unten Ihre bevorzugte Entwicklungsumgebung aus.</span><span class="sxs-lookup"><span data-stu-id="486e4-111">Select your preferred development environment below.</span></span>

## <a name="visual-studio-on-windows"></a>[<span data-ttu-id="486e4-112">Visual Studio unter Windows</span><span class="sxs-lookup"><span data-stu-id="486e4-112">Visual Studio on Windows</span></span>](#tab/vs)

<span data-ttu-id="486e4-113">Visual Studio 2017 und höher bietet integrierte Unterstützung für die Azure-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="486e4-113">Visual Studio version 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="486e4-114">Die folgenden Schritten beschreiben, wie Sie die Unterstützung für die Azure-Entwicklung in Visual Studio einrichten.</span><span class="sxs-lookup"><span data-stu-id="486e4-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="486e4-115">Für Visual Studio 2015 und früher befolgen Sie <a href="vs2015-install.md">diese Anleitung</a>.</span><span class="sxs-lookup"><span data-stu-id="486e4-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="486e4-116">Schritt 1: Herunterladen von Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="486e4-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="486e4-117">Sie können diesen Schritt überspringen, wenn Sie bereits Visual Studio 2019 installiert haben.</span><span class="sxs-lookup"><span data-stu-id="486e4-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="486e4-118">Herunterladen von Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="486e4-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="486e4-119">Schritt 2: Installieren der beiden Azure-Workloads</span><span class="sxs-lookup"><span data-stu-id="486e4-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="486e4-120">Installieren Sie im Visual Studio-Installer das Programm „Visual Studio“ (oder ändern Sie die vorhandene Installation).</span><span class="sxs-lookup"><span data-stu-id="486e4-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="486e4-121">Stellen Sie sicher, dass die Arbeitsauslastungen *Azure-Entwicklung* und *ASP.NET und Webentwicklung* ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="486e4-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="486e4-122">Schritt 3: Entwickeln mit .NET in Azure</span><span class="sxs-lookup"><span data-stu-id="486e4-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="486e4-123">Beginnen Sie der [Bereitstellung Ihrer ersten ASP.NET Core-Web-App in Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="486e4-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="visual-studio-code-cross-platform"></a>[<span data-ttu-id="486e4-124">Visual Studio Code (plattformübergreifend)</span><span class="sxs-lookup"><span data-stu-id="486e4-124">Visual Studio Code (cross-platform)</span></span>](#tab/vscode)

<span data-ttu-id="486e4-125">Visual Studio Code ist alles, was Sie für plattformübergreifende Azure-Entwicklung benötigen.</span><span class="sxs-lookup"><span data-stu-id="486e4-125">Visual Studio Code has everything you need for cross-platform Azure development.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="486e4-126">Schritt 1: Herunterladen des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="486e4-126">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="486e4-127">Das SDK und Befehlszeilentools für .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="486e4-127">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="486e4-128">.NET Core SDK herunterladen</span><span class="sxs-lookup"><span data-stu-id="486e4-128">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="486e4-129">Schritt 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="486e4-129">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="486e4-130">Bearbeiten und Debuggen von .NET Core-Apps unter jedem Betriebssystem: Windows, Mac und Linux.</span><span class="sxs-lookup"><span data-stu-id="486e4-130">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="486e4-131">Visual Studio Code herunterladen</span><span class="sxs-lookup"><span data-stu-id="486e4-131">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a><span data-ttu-id="486e4-132">Schritt 3: Azure Tools-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="486e4-132">Step 3: Azure Tools extension</span></span>

<span data-ttu-id="486e4-133">Installieren Sie die Azure Tools-Erweiterung in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="486e4-133">Install the Azure Tools extension in Visual Studio Code.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="486e4-134">Azure Tools-Erweiterung installieren</span><span class="sxs-lookup"><span data-stu-id="486e4-134">Install Azure Tools extension</span></span>](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a><span data-ttu-id="486e4-135">Schritt 4: Entwickeln mit .NET in Azure</span><span class="sxs-lookup"><span data-stu-id="486e4-135">Step 4: Develop with .NET on Azure</span></span>

<span data-ttu-id="486e4-136">Beginnen Sie der [Bereitstellung Ihrer ersten ASP.NET Core-Web-App in Azure App Serviceunter Linux](/azure/app-service/containers/quickstart-dotnetcore).</span><span class="sxs-lookup"><span data-stu-id="486e4-136">Get started by [deploying your first ASP.NET Core web app on Azure App Service on Linux](/azure/app-service/containers/quickstart-dotnetcore).</span></span>

---
