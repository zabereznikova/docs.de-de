---
title: Voraussetzungen für .NET Core unter Windows
description: Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können.
author: mairaw
ms.author: mairaw
ms.date: 08/31/2018
ms.openlocfilehash: bbf54c8d215783656830f0fa035708be82a7c39c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482609"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="87405-103">Voraussetzungen für .NET Core unter Windows</span><span class="sxs-lookup"><span data-stu-id="87405-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="87405-104">Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Windows.</span><span class="sxs-lookup"><span data-stu-id="87405-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="87405-105">Die unterstützten Betriebssystemversionen und die daraus folgenden Abhängigkeiten gelten für die drei Möglichkeiten, um .NET Core-Apps unter Windows zu entwickeln:</span><span class="sxs-lookup"><span data-stu-id="87405-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="87405-106">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="87405-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="87405-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="87405-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="87405-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="87405-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="87405-109">Von .NET Core unterstützte Windows-Versionen</span><span class="sxs-lookup"><span data-stu-id="87405-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="87405-110">.NET Core wird von folgenden Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="87405-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="87405-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="87405-111">Windows 7 SP1</span></span>
* <span data-ttu-id="87405-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="87405-112">Windows 8.1</span></span>
* <span data-ttu-id="87405-113">Windows 10 Anniversary Update (Version 1607) oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="87405-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="87405-114">Windows Server 2008 R2 SP1 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="87405-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="87405-115">Windows Server 2012 SP1 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="87405-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="87405-116">Windows Server 2012 R2 (vollständiger Server oder Serverkern)</span><span class="sxs-lookup"><span data-stu-id="87405-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="87405-117">Windows Server 2016 oder höhere Versionen (vollständiger Server, Serverkern oder Nano-Server)</span><span class="sxs-lookup"><span data-stu-id="87405-117">Windows Server 2016 or later versions (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="87405-118">Die folgenden Artikel enthalten eine vollständige Liste der von .NET Core unterstützten Betriebssysteme je nach Version:</span><span class="sxs-lookup"><span data-stu-id="87405-118">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="87405-119">.NET Core 2.1 – Supported OS Versions (Von .NET Core 2.1 unterstützte Betriebssysteme)</span><span class="sxs-lookup"><span data-stu-id="87405-119">.NET Core 2.1 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="87405-120">.NET Core 2.0 – Supported OS Versions (Von .NET Core 2.0 unterstützte Betriebssysteme)</span><span class="sxs-lookup"><span data-stu-id="87405-120">.NET Core 2.0 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)
* [<span data-ttu-id="87405-121">.NET Core 1.x – Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssysteme)</span><span class="sxs-lookup"><span data-stu-id="87405-121">.NET Core 1.x - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

## <a name="net-core-dependencies"></a><span data-ttu-id="87405-122">.NET Core-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="87405-122">.NET Core dependencies</span></span>

<span data-ttu-id="87405-123">.NET Core 1.1 und frühere Versionen benötigen Visual C++ Redistributable zur Ausführung unter Windows-Versionen vor Windows 10 und Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="87405-123">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="87405-124">Diese Abhängigkeit wird automatisch durch das .NET Core-Installationsprogramm installiert.</span><span class="sxs-lookup"><span data-stu-id="87405-124">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="87405-125">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) muss in folgenden Fällen installiert werden:</span><span class="sxs-lookup"><span data-stu-id="87405-125">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="87405-126">Beim Installieren von .NET Core mit dem [Installationsprogrammskript](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="87405-126">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="87405-127">Beim Bereitstellen einer eigenständigen .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="87405-127">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="87405-128">Beim Erstellen des Produkt aus der Quelle.</span><span class="sxs-lookup"><span data-stu-id="87405-128">Building the product from source.</span></span>
* <span data-ttu-id="87405-129">Beim Installieren von .NET Core über eine *ZIP*-Datei.</span><span class="sxs-lookup"><span data-stu-id="87405-129">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="87405-130">Dazu können Build-/CI-/CD-Server gehören.</span><span class="sxs-lookup"><span data-stu-id="87405-130">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="87405-131">**Für Windows 8.1 und frühere Versionen oder Windows Server 2012 R2 und frühere Versionen:**</span><span class="sxs-lookup"><span data-stu-id="87405-131">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="87405-132">Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows) enthält, das über Windows Update installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="87405-132">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="87405-133">Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung wie die folgende angezeigt: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="87405-133">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="87405-134">**Für Windows 7 oder Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="87405-134">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="87405-135">Stellen Sie sicher, dass Sie neben KB2999226 auch [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="87405-135">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="87405-136">Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung ähnlich der folgenden angezeigt: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="87405-136">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="87405-137">Voraussetzungen für Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="87405-137">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="87405-138">Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden.</span><span class="sxs-lookup"><span data-stu-id="87405-138">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="87405-139">[Visual Studio 2017](#visual-studio-2017) stellt eine integrierte Entwicklungsumgebung für .NET Core-Apps unter Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="87405-139">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="87405-140">Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](/visualstudio/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="87405-140">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="87405-141">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="87405-141">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="87405-142">So entwickeln Sie .NET Core 2.1-Apps in Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="87405-142">To develop .NET Core 2.1 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="87405-143">[Download and install Visual Studio 2017 version 15.7.0 or higher (Laden Sie Visual Studio Version 15.7.0 oder höher herunter, und installieren Sie diese)](/visualstudio/install/install-visual-studio) zusammen mit der Workload **Plattformübergreifende .NET Core-Entwicklung** , die im Abschnitt **Andere Toolsets** ausgewählt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="87405-143">[Download and install Visual Studio 2017 version 15.7.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-15-8-workloads.jpg)

<span data-ttu-id="87405-145">Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert wurde, verwendet Visual Studio 2017 15.7 standardmäßig das .NET Core 2.0. SDK und Visual Studio 2017 15.8 das .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="87405-145">After the **.NET Core cross-platform development** toolset is installed, by default, Visual Studio 2017 15.7 uses .NET Core 2.0 SDK and Visual Studio 2017 15.8 uses 2.1 SDK.</span></span>

 2. <span data-ttu-id="87405-146">Wenn Sie Visual Studio 2017 15.7 verwenden, müssen Sie das [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) verwenden oder ein Upgrade auf Visual Studio 2017 15.8 durchführen.</span><span class="sxs-lookup"><span data-stu-id="87405-146">If you're using Visual Studio 2017 15.7, install the [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) or upgrade to Visual Studio 2017 15.8.</span></span>

 3. <span data-ttu-id="87405-147">Weisen Sie .NET Core 2.1 bestehende oder neue .NET Core 2.1-Projekte neu zu, indem Sie die folgenden Anweisungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="87405-147">Retarget existing or new .NET Core projects to .NET Core 2.1 using the following instructions:</span></span>
    * <span data-ttu-id="87405-148">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="87405-148">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="87405-149">Legen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.1** fest.</span><span class="sxs-lookup"><span data-stu-id="87405-149">In the **Target framework** selection menu, set the value to **.NET Core 2.1**.</span></span>

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.0“](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="87405-151">Nach der Konfiguration von Visual Studio mit dem .NET Core 2.1 SDK können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="87405-151">Once you have Visual Studio configured with .NET Core 2.1 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="87405-152">Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x- und .NET Core 2.x-Projekte.</span><span class="sxs-lookup"><span data-stu-id="87405-152">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="87405-153">Neuzuweisen von .NET Core 1.x-Projekten und .NET Core 2.0-Projekten zu .NET Core 2.1 sowie Erstellen und Ausführen derselben.</span><span class="sxs-lookup"><span data-stu-id="87405-153">Retarget .NET Core 1.x and 2.0 projects to .NET Core 2.1, build, and run.</span></span>
* <span data-ttu-id="87405-154">Erstellen neuer .NET Core 2.1-Projekte.</span><span class="sxs-lookup"><span data-stu-id="87405-154">Create new .NET Core 2.1 projects.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="87405-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="87405-155">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="87405-156">So entwickeln Sie .NET Core 2.0-Apps in Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="87405-156">To develop .NET Core 2.0 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="87405-157">[Download and install Visual Studio 2017 version 15.3.0 or higher (Laden Sie Visual Studio Version 15.3.0 oder höher herunter und installieren Sie diese)](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **.NET Core cross-platform development (Plattformübergreifende .NET Core-Entwicklung)**, das im Abschnitt **Andere Toolsets** ausgewählt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="87405-157">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="87405-159">Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert ist, verwendet Visual Studio 2017 standardmäßig .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="87405-159">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="87405-160">Installieren Sie das .NET Core 2.0 SDK, um .NET Core 2.0 in Visual Studio 2017 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="87405-160">Install the .NET Core 2.0 SDK to get .NET Core 2.0 support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="87405-161">Installieren Sie das [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).</span><span class="sxs-lookup"><span data-stu-id="87405-161">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).</span></span>
 3. <span data-ttu-id="87405-162">Weisen Sie .NET Core 2.0 bestehende oder neue .NET Core 1.x-Projekte neu zu, indem Sie die folgenden Anweisungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="87405-162">Retarget existing or new .NET Core 1.x projects to .NET Core 2.0 using the following instructions:</span></span>
    * <span data-ttu-id="87405-163">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="87405-163">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="87405-164">Setzen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="87405-164">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.0“](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="87405-166">Nach der Installation des .NET Core 2.0. SDK verwendet Visual Studio 2017 dieses standardmäßig. Es unterstützt die folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="87405-166">Once the .NET Core 2.0 SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.0 by default, and supports the following actions:</span></span>

* <span data-ttu-id="87405-167">Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x-Projekte.</span><span class="sxs-lookup"><span data-stu-id="87405-167">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="87405-168">Neuzuweisen von .NET Core 1.x-Projekten zu .NET Core 2.0 sowie Erstellen und Ausführen derselben.</span><span class="sxs-lookup"><span data-stu-id="87405-168">Retarget .NET Core 1.x projects to .NET Core 2.0, build, and run.</span></span>
* <span data-ttu-id="87405-169">Erstellen neuer .NET Core 2.0-Projekte.</span><span class="sxs-lookup"><span data-stu-id="87405-169">Create new .NET Core 2.0 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="87405-170">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="87405-170">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="87405-171">[Laden Sie Visual Studio 2017 RTM herunter, und installieren es](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Andere Toolsets** ausgewählt sein sollte, um .NET Core 1.x-Apps in Visual Studio zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="87405-171">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="87405-173">Es ist möglich, Visual Studio 2015 für die .NET Core 1.x-Entwicklung zu verwenden, es wird jedoch aus den folgenden Gründen nicht empfohlen:</span><span class="sxs-lookup"><span data-stu-id="87405-173">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="87405-174">Bei den .NET Core-Tools handelt es sich um eine nicht unterstützte Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="87405-174">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="87405-175">Die Projekte basieren auf dem Format „project.json“, das veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="87405-175">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="87405-176">Weitere Informationen zu den Änderungen der Projektformate finden Sie unter [High-level overview of changes (Globale Übersicht der Änderungen)](./tools/cli-msbuild-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="87405-176">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="87405-177">So überprüfen Sie Ihre Version von Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="87405-177">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="87405-178">Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="87405-178">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="87405-179">Verifizieren Sie die Versionsnummer im Dialogfeld **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="87405-179">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="87405-180">Für Vorschauversion 1 der .NET Core 2.2-Apps muss dies Visual Studio 2017 Version 15.9 (aktuell als Vorschau) oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="87405-180">For .NET Core 2.2 Preview 1 apps, Visual Studio 2017 version 15.9 (currently in Preview) or higher.</span></span>
>   * <span data-ttu-id="87405-181">Für .NET Core 2.1-Apps muss dies Visual Studio 2017 Version 15.7 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="87405-181">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="87405-182">Für .NET Core 2.0-Apps muss dies Visual Studio 2017 Version 15.3 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="87405-182">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="87405-183">Für .NET Core 1.x-Apps muss dies Visual Studio 2017 Version 15.0 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="87405-183">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
