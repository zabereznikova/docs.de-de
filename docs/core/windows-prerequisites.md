---
title: "Voraussetzungen für .NET Core unter Windows"
description: "Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können."
keywords: ".NET Core, Windows, Voraussetzungen, Abhängigkeiten, Visual Studio"
author: mairaw
ms.author: mairaw
ms.date: 06/26/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0e414af0edbafed5b7f540eda6de2e5078eac789
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="70953-104">Voraussetzungen für .NET Core unter Windows</span><span class="sxs-lookup"><span data-stu-id="70953-104">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="70953-105">In diesem Artikel erfahren Sie, welche Abhängigkeiten Sie benötigen, um .NET Core-Anwendungen auf Windows-Computern bereitzustellen und auszuführen sowie mit Visual Studio zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="70953-105">This article shows you what dependencies you need to deploy and run .NET Core applications on Windows machines and develop using Visual Studio.</span></span>

## <a name="supported-windows-versions"></a><span data-ttu-id="70953-106">Unterstützte Windows-Versionen</span><span class="sxs-lookup"><span data-stu-id="70953-106">Supported Windows versions</span></span>

<span data-ttu-id="70953-107">.NET Core wird von folgenden Windows-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="70953-107">.NET Core is supported on the following versions of Windows:</span></span>

* <span data-ttu-id="70953-108">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="70953-108">Windows 7 SP1</span></span>
* <span data-ttu-id="70953-109">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="70953-109">Windows 8.1</span></span>
* <span data-ttu-id="70953-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="70953-110">Windows 10</span></span>
* <span data-ttu-id="70953-111">Windows Server 2008 R2 SP1 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="70953-111">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="70953-112">Windows Server 2012 SP1 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="70953-112">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="70953-113">Windows Server 2012 R2 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="70953-113">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="70953-114">Windows Server 2016 (vollständiger Server, Serverkern oder Nano-Server)</span><span class="sxs-lookup"><span data-stu-id="70953-114">Windows Server 2016 (Full Server, Server Core or Nano Server)</span></span>

<span data-ttu-id="70953-115">In den [Versionshinweisen zu .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) finden Sie eine umfassende Liste mit unterstützten Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="70953-115">See the [.NET Core Release Notes](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) for the full set of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="70953-116">.NET Core-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="70953-116">.NET Core dependencies</span></span>

<span data-ttu-id="70953-117">.NET Core benötigt Visual C++ Redistributable zur Ausführung unter Windows-Versionen vor Windows 10 und Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="70953-117">.NET Core requires the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="70953-118">Diese Abhängigkeit wird für Sie automatisch installiert, wenn Sie das .NET Core-Installationsprogramm verwenden.</span><span class="sxs-lookup"><span data-stu-id="70953-118">This dependency is automatically installed for you if you use the .NET Core installer.</span></span> <span data-ttu-id="70953-119">Sie müssen [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685) jedoch manuell installieren, wenn Sie .NET Core über das [Installationsskript](./tools/dotnet-install-script.md) installieren oder eine eigenständige .NET Core-Anwendung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="70953-119">However, you need to manually install the [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685) if you are installing .NET Core via the [installer script](./tools/dotnet-install-script.md) or deploying a self-contained .NET Core application.</span></span>

> [!NOTE]
> <span data-ttu-id="70953-120"><em>Nur Für Windows 7- und Windows Server 2008-Computer:</em></span><span class="sxs-lookup"><span data-stu-id="70953-120"><em>For Windows 7 and Windows Server 2008 machines only:</em></span></span><br>
> <span data-ttu-id="70953-121">Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und den über Windows Update installierten Hotfix [KB2533623](https://support.microsoft.com/help/2533623) enthält.</span><span class="sxs-lookup"><span data-stu-id="70953-121">Make sure that your Windows installation is up-to-date and includes hotfix [KB2533623](https://support.microsoft.com/help/2533623) installed through Windows Update.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="70953-122">Voraussetzungen für Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="70953-122">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="70953-123">Sie können einen beliebigen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden.</span><span class="sxs-lookup"><span data-stu-id="70953-123">You can use any editor of your choice to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="70953-124">Wenn Sie jedoch .NET Core-Anwendungen unter Windows in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio 2017](#visual-studio-2017) verwenden.</span><span class="sxs-lookup"><span data-stu-id="70953-124">However, if you want to develop .NET Core applications on Windows in an integrated development environment, you can use [Visual Studio 2017](#visual-studio-2017).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70953-125">Obwohl Visual Studio 2015 mit einer Vorschauversion von .NET Core-Tools verwendet werden kann, werden diese Projekte *project.json*-basiert sein, was nun veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="70953-125">Even though, it's possible to use Visual Studio 2015 with a preview version of the .NET Core tooling, these projects will be *project.json*-based, which is now deprecated.</span></span> <span data-ttu-id="70953-126">Visual Studio 2017 verwendet auf MSBuild basierende Projektdateien.</span><span class="sxs-lookup"><span data-stu-id="70953-126">Visual Studio 2017 uses project files based on MSBuild.</span></span> <span data-ttu-id="70953-127">Weitere Informationen über die Formatänderungen finden Sie unter [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Globale Übersicht der Änderungen).</span><span class="sxs-lookup"><span data-stu-id="70953-127">For more information about the format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

<span data-ttu-id="70953-128">Wenn Sie Visual Studio 2017 zum Entwickeln von .NET Core-Anwendungen verwenden möchten, müssen Sie die neueste Version von Visual Studio mit dem **plattformübergreifenden .NET Core**-Toolset (im Abschnitt **Andere Toolsets**) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="70953-128">To use Visual Studio 2017 to develop .NET Core apps, you'll need to have the latest version of Visual Studio installed with the **.NET Core cross-platform development** toolset (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="70953-129">![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs_workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="70953-129">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs_workloads.jpg)</span></span>

<span data-ttu-id="70953-130">Es gibt verschiedene Editionen von Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="70953-130">There are different editions of Visual Studio 2017.</span></span> <span data-ttu-id="70953-131">Sie können [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) für den Einstieg kostenlos herunterladen.</span><span class="sxs-lookup"><span data-stu-id="70953-131">You can download [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) for free to get started.</span></span>  <span data-ttu-id="70953-132">Weitere Informationen zum Installationsvorgang für Visual Studio finden Sie unter [Installieren von Visual Studio 2017](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="70953-132">To learn more about the Visual Studio installation process, see [Install Visual Studio 2017](/visualstudio/install/install-visual-studio).</span></span>

<span data-ttu-id="70953-133">Um sicherzustellen, dass Sie die neueste Version von Visual Studio 2017 ausführen, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="70953-133">To verify that you're running the latest version of Visual Studio 2017, do the following:</span></span>

 * <span data-ttu-id="70953-134">Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="70953-134">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
 * <span data-ttu-id="70953-135">Im Dialogfeld **Info zu Microsoft Visual Studio** muss als Versionsnummer 15.0.26228.4 oder höher angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="70953-135">In the **About Microsoft Visual Studio** dialog, the version number should be 15.0.26228.4 or higher.</span></span>

<span data-ttu-id="70953-136">Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="70953-136">You can read more about the changes in Visual Studio 2017 in the [release notes](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).</span></span>

