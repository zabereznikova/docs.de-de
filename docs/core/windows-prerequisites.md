---
title: "Voraussetzungen für .NET Core unter Windows"
description: "Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können."
author: JRAlexander
ms.author: johalex
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 16a72edde39e4857dbdfb400f195deb9975f993c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="7fbac-103">Voraussetzungen für .NET Core unter Windows</span><span class="sxs-lookup"><span data-stu-id="7fbac-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="7fbac-104">Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Windows.</span><span class="sxs-lookup"><span data-stu-id="7fbac-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="7fbac-105">Die unterstützten Betriebssystemversionen und die daraus folgenden Abhängigkeiten gelten für die drei Möglichkeiten, um .NET Core-Apps unter Windows zu entwickeln:</span><span class="sxs-lookup"><span data-stu-id="7fbac-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="7fbac-106">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="7fbac-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="7fbac-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7fbac-107">Visual Studio 2017</span></span>](https://www.visualstudio.com/downloads/)
* [<span data-ttu-id="7fbac-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7fbac-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="7fbac-109">Von .NET Core unterstützte Windows-Versionen</span><span class="sxs-lookup"><span data-stu-id="7fbac-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="7fbac-110">.NET Core wird von folgenden Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7fbac-110">.NET Core is supported on the following versions of :</span></span>

* <span data-ttu-id="7fbac-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="7fbac-111">Windows 7 SP1</span></span>
* <span data-ttu-id="7fbac-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7fbac-112">Windows 8.1</span></span>
* <span data-ttu-id="7fbac-113">Windows 10, Windows 10 Anniversary Update (Version 1607) oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="7fbac-113">Windows 10, Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="7fbac-114">Windows Server 2008 R2 SP1 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="7fbac-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="7fbac-115">Windows Server 2012 SP1 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="7fbac-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="7fbac-116">Windows Server 2012 R2 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="7fbac-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="7fbac-117">Windows Server 2016 (vollständiger Server, Serverkern oder Nano-Server)</span><span class="sxs-lookup"><span data-stu-id="7fbac-117">Windows Server 2016 (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="7fbac-118">Eine umfassende Liste mit von .NET Core 2.x unterstützten Betriebssystemen finden Sie unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssysteme)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7fbac-118">See [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems.</span></span>

<span data-ttu-id="7fbac-119">Eine umfassende Liste mit von .NET Core 1.x unterstützten Betriebssystemen finden Sie unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssysteme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7fbac-119">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="7fbac-120">.NET Core-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="7fbac-120">.NET Core dependencies</span></span>

<span data-ttu-id="7fbac-121">.NET Core 1.1 und früher erfordert Visual C++ Redistributable, wenn auf Windows-Versionen vor Windows 10 und Windows Server 2016 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7fbac-121">.NET Core 1.1 and earlier requires the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="7fbac-122">Diese Abhängigkeit wird automatisch durch das .NET Core-Installationsprogramm installiert.</span><span class="sxs-lookup"><span data-stu-id="7fbac-122">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="7fbac-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) muss in folgenden Fällen installiert werden:</span><span class="sxs-lookup"><span data-stu-id="7fbac-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

   * <span data-ttu-id="7fbac-124">Beim Installieren von .NET Core mit dem [Installationsprogrammskript](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="7fbac-124">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
   * <span data-ttu-id="7fbac-125">Beim Bereitstellen einer eigenständigen .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7fbac-125">Deploying a self-contained .NET Core application.</span></span>

> [!NOTE]
> <span data-ttu-id="7fbac-126"><em>Nur Für Windows 7- und Windows Server 2008-Computer:</em></span><span class="sxs-lookup"><span data-stu-id="7fbac-126"><em>For Windows 7 and Windows Server 2008 machines only:</em></span></span><br>
> <span data-ttu-id="7fbac-127">Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und den über Windows Update installierten Hotfix [KB2533623](https://support.microsoft.com/help/2533623) enthält.</span><span class="sxs-lookup"><span data-stu-id="7fbac-127">Make sure that your Windows installation is up-to-date and includes hotfix [KB2533623](https://support.microsoft.com/help/2533623) installed through Windows Update.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="7fbac-128">Voraussetzungen für Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7fbac-128">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="7fbac-129">Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden.</span><span class="sxs-lookup"><span data-stu-id="7fbac-129">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span>  <span data-ttu-id="7fbac-130">[Visual Studio 2017](#visual-studio-2017) stellt eine integrierte Entwicklungsumgebung für .NET Core-Apps unter Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="7fbac-130">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="7fbac-131">Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="7fbac-131">You can read more about the changes in Visual Studio 2017 in the [release notes](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).</span></span>
# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7fbac-132">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7fbac-132">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7fbac-133">So entwickeln Sie .NET Core 2.x-Apps in Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="7fbac-133">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="7fbac-134">[Download and install Visual Studio 2017 version 15.3.0 or higher (Laden Sie Visual Studio Version 15.3.0 oder höher herunter und installieren Sie diese)](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **.NET Core cross-platform development (Plattformübergreifende .NET Core-Entwicklung)**, das im Abschnitt **Andere Toolsets** ausgewählt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="7fbac-134">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="7fbac-135">![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-15-3-workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="7fbac-135">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs-15-3-workloads.jpg)</span></span>

<span data-ttu-id="7fbac-136">Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert ist, verwendet Visual Studio 2017 standardmäßig .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="7fbac-136">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="7fbac-137">Installieren Sie die .NET Core 2.x SDK, um .NET Core 2.x in Visual Studio 2017 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7fbac-137">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="7fbac-138">Installieren Sie das [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="7fbac-138">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="7fbac-139">Weisen Sie bestehende oder neue .NET Core 1.x-Projekte neu .NET Core 2.x zu, indem Sie die folgenden Anweisungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="7fbac-139">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="7fbac-140">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7fbac-140">On the **Project** menu, Choose **Properties**.</span></span> 
    * <span data-ttu-id="7fbac-141">Setzen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="7fbac-141">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.0“](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="7fbac-143">Sobald die .NET Core 2.x SDK installiert ist, verwendet Visual Studio 2017 diese standardmäßig und unterstützt die folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="7fbac-143">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

  * <span data-ttu-id="7fbac-144">Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x-Projekte.</span><span class="sxs-lookup"><span data-stu-id="7fbac-144">Open, build, and run existing .NET Core 1.x projects.</span></span>
  * <span data-ttu-id="7fbac-145">Neuzuweisen von .NET Core 1.x-Projekten auf .NET Core 2.x sowie Erstellen und Ausführen derselben.</span><span class="sxs-lookup"><span data-stu-id="7fbac-145">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
  * <span data-ttu-id="7fbac-146">Erstellen neuer .NET Core 2.x-Projekte.</span><span class="sxs-lookup"><span data-stu-id="7fbac-146">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7fbac-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7fbac-147">.NET Core 1.x</span></span>](#tab/netcore1x)
<span data-ttu-id="7fbac-148">[download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher (Laden Sie Visual Studio 2017 RTM (Version 15.0.26228.4 oder höher))](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **.NET Core cross-platform development (Plattformübergreifende .NET Core-Entwicklung)** herunter, das im Abschnitt **Andere Toolsets** ausgewählt sein sollte, um .NET Core 1.x-Apps in Visual Studio zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="7fbac-148">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="7fbac-149">![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs_workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="7fbac-149">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs_workloads.jpg)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="7fbac-150">Es ist möglich, Visual Studio 2015 für die .NET Core 1.x-Entwicklung zu verwenden, es wird jedoch aus den folgenden Gründen nicht empfohlen:</span><span class="sxs-lookup"><span data-stu-id="7fbac-150">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="7fbac-151">Bei den .NET Core-Tools handelt es sich um eine nicht unterstützte Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="7fbac-151">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="7fbac-152">Die Projekte basieren auf dem Format „project.json“, das veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="7fbac-152">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="7fbac-153">Weitere Informationen zu den Änderungen der Projektformate finden Sie unter [High-level overview of changes (Globale Übersicht der Änderungen)](./tools/cli-msbuild-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="7fbac-153">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

>[!TIP]
  > <span data-ttu-id="7fbac-154">So überprüfen Sie Ihre Version von Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="7fbac-154">To verify your Visual Studio 2017 version:</span></span>
>
     > * <span data-ttu-id="7fbac-155">Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="7fbac-155">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
     > * <span data-ttu-id="7fbac-156">Verifizieren Sie die Versionsnummer im Dialogfeld **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="7fbac-156">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>     * <span data-ttu-id="7fbac-157">Für .NET Core 2.x-Apps muss diese Visual Studio 2017 Version 15.3. (26730.01) oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="7fbac-157">For .NET Core 2.x apps, Visual Studio 2017 version 15.3 (26730.01) or higher.</span></span>
>     * <span data-ttu-id="7fbac-158">Für .NET Core 1.x-Apps muss diese Visual Studio 2017 Version 15.0. (26228.04) oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="7fbac-158">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 (26228.04) or higher.</span></span>
