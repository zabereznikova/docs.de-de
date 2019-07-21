---
title: Voraussetzungen für .NET Core unter Windows
description: Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können.
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 1921ef565c2d04624009f7684e439ddba1cdf57e
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331073"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="51fe3-103">Voraussetzungen für .NET Core unter Windows</span><span class="sxs-lookup"><span data-stu-id="51fe3-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="51fe3-104">Dieser Artikel beschreibt die zur Ausführung von .NET Core-Anwendungen auf Windows unterstützten Betriebssystemversionen.</span><span class="sxs-lookup"><span data-stu-id="51fe3-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="51fe3-105">Die unterstützten Betriebssystemversionen und die daraus folgenden Abhängigkeiten gelten für die drei Möglichkeiten, um .NET Core-Apps unter Windows zu entwickeln:</span><span class="sxs-lookup"><span data-stu-id="51fe3-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="51fe3-106">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="51fe3-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="51fe3-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51fe3-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [<span data-ttu-id="51fe3-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="51fe3-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="51fe3-109">Wenn Sie auf Windows mit Visual Studio 2017 entwickeln, nutzen Sie die ausführlicheren Informationen über die für die .NET Core-Entwicklung unterstützten Mindestversionen im Abschnitt [Voraussetzungen für Visual Studio 2017](#prerequisites-with-visual-studio-2017).</span><span class="sxs-lookup"><span data-stu-id="51fe3-109">Also, if you're developing on Windows using Visual Studio 2017, the [Prerequisites with Visual Studio 2017](#prerequisites-with-visual-studio-2017) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="51fe3-110">Von .NET Core unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="51fe3-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="51fe3-111">Die folgenden Artikel enthalten eine vollständige Liste der von .NET Core unterstützten Betriebssysteme je nach Version:</span><span class="sxs-lookup"><span data-stu-id="51fe3-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="51fe3-112">.NET Core 3.0 (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="51fe3-112">.NET Core 3.0 (Preview)</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="51fe3-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="51fe3-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="51fe3-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="51fe3-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="51fe3-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="51fe3-115">.NET Core 1.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

<span data-ttu-id="51fe3-116">Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Downloads](https://dotnet.microsoft.com/download) für die neueste Version bzw. [.NET Download Archives](https://dotnet.microsoft.com/download/archives#dotnet-core) für ältere Versionen.</span><span class="sxs-lookup"><span data-stu-id="51fe3-116">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="51fe3-117">.NET Core-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="51fe3-117">.NET Core dependencies</span></span>

<span data-ttu-id="51fe3-118">.NET Core 1.1 und frühere Versionen benötigen Visual C++ Redistributable zur Ausführung unter Windows-Versionen vor Windows 10 und Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="51fe3-118">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="51fe3-119">Diese Abhängigkeit wird automatisch durch das .NET Core-Installationsprogramm installiert.</span><span class="sxs-lookup"><span data-stu-id="51fe3-119">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="51fe3-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) muss in folgenden Fällen installiert werden:</span><span class="sxs-lookup"><span data-stu-id="51fe3-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="51fe3-121">Beim Installieren von .NET Core mit dem [Installationsprogrammskript](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="51fe3-121">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="51fe3-122">Beim Bereitstellen einer eigenständigen .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="51fe3-122">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="51fe3-123">Beim Erstellen des Produkt aus der Quelle.</span><span class="sxs-lookup"><span data-stu-id="51fe3-123">Building the product from source.</span></span>
* <span data-ttu-id="51fe3-124">Beim Installieren von .NET Core über eine *ZIP*-Datei.</span><span class="sxs-lookup"><span data-stu-id="51fe3-124">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="51fe3-125">Dazu können Build-/CI-/CD-Server gehören.</span><span class="sxs-lookup"><span data-stu-id="51fe3-125">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="51fe3-126">**Für Windows 8.1 und frühere Versionen oder Windows Server 2012 R2 und frühere Versionen:**</span><span class="sxs-lookup"><span data-stu-id="51fe3-126">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="51fe3-127">Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) enthält, das über Windows Update installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="51fe3-127">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="51fe3-128">Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung wie die folgende angezeigt: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="51fe3-128">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="51fe3-129">**Für Windows 7 oder Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="51fe3-129">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="51fe3-130">Stellen Sie sicher, dass Sie neben KB2999226 auch [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="51fe3-130">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="51fe3-131">Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung ähnlich der folgenden angezeigt: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="51fe3-131">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-for-net-core-30-preview-3"></a><span data-ttu-id="51fe3-132">Voraussetzungen für .NET Core 3.0 Vorschauversion 3</span><span class="sxs-lookup"><span data-stu-id="51fe3-132">Prerequisites for .NET Core 3.0 Preview 3</span></span>

<span data-ttu-id="51fe3-133">.NET Core 3.0 Vorschauversion 3 hat die gleichen Voraussetzungen wie andere Versionen von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51fe3-133">.NET Core 3.0 Preview 3 has the same prerequisites as other versions of .NET Core.</span></span> <span data-ttu-id="51fe3-134">Wenn jedoch .NET Core 3.0-Projekte mit Visual Studio erstellt werden sollen, müssen Sie [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) verwenden.</span><span class="sxs-lookup"><span data-stu-id="51fe3-134">However, if you want to use Visual Studio to create .NET Core 3.0 projects, you must use the [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="51fe3-135">Visual Studio 2019 kann parallel mit anderen Versionen von Visual Studio installiert werden, ohne dass dadurch Konflikte entstehen.</span><span class="sxs-lookup"><span data-stu-id="51fe3-135">Visual Studio 2019 can be installed side-by-side with other versions of Visual Studio without conflict.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="51fe3-136">Voraussetzungen für Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="51fe3-136">Prerequisites with Visual Studio 2017</span></span>
    
<span data-ttu-id="51fe3-137">Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden.</span><span class="sxs-lookup"><span data-stu-id="51fe3-137">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="51fe3-138">Visual Studio 2017 stellt eine integrierte Entwicklungsumgebung für .NET Core-Apps unter Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="51fe3-138">Visual Studio 2017 provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="51fe3-139">Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](/visualstudio/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="51fe3-139">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="51fe3-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="51fe3-140">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="51fe3-141">So entwickeln Sie .NET Core-Apps in Visual Studio 2017 mithilfe des .NET Core 2.2 SDK:</span><span class="sxs-lookup"><span data-stu-id="51fe3-141">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="51fe3-142">[Laden Sie Visual Studio 2017 Version 15.9.0 oder höher herunter, und installieren Sie diese](/visualstudio/install/install-visual-studio) zusammen mit der Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Andere Toolsets** ausgewählt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="51fe3-142">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="51fe3-144">Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert ist, verwendet Visual Studio in der Regel eine frühere Version von .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="51fe3-144">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="51fe3-145">Visual Studio 2017 15.9 verwendet z. B. .NET Core 2.1 SDK standardmäßig nach der Installation der Workload.</span><span class="sxs-lookup"><span data-stu-id="51fe3-145">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="51fe3-146">So aktualisieren Sie Visual Studio, um .NET Core 2.2 SDK zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="51fe3-146">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="51fe3-147">Installieren Sie das [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="51fe3-147">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="51fe3-148">Wenn Ihr Projekt die neueste .NET Core-Runtime verwenden soll, weisen Sie vorhandene oder neue .NET Core-Projekte .NET Core 2.2 mithilfe der folgenden Anweisungen neu zu:</span><span class="sxs-lookup"><span data-stu-id="51fe3-148">If you want your project to use the latest .NET Core runtime, retarget existing or new .NET Core projects to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="51fe3-149">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="51fe3-149">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="51fe3-150">Legen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.2** fest.</span><span class="sxs-lookup"><span data-stu-id="51fe3-150">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.2“](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="51fe3-152">Nach der Konfiguration von Visual Studio mit dem .NET Core 2.2 SDK können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="51fe3-152">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="51fe3-153">Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x- und .NET Core 2.x-Projekte.</span><span class="sxs-lookup"><span data-stu-id="51fe3-153">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="51fe3-154">Neuzuweisen von .NET Core 1.x- und 2.x-Projekten zu .NET Core 2.2 sowie Erstellen und Ausführen derselben.</span><span class="sxs-lookup"><span data-stu-id="51fe3-154">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="51fe3-155">Erstellen Sie neue .NET Core 2.2-Projekte.</span><span class="sxs-lookup"><span data-stu-id="51fe3-155">Create new .NET Core 2.2 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="51fe3-156">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="51fe3-156">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="51fe3-157">[Laden Sie Visual Studio 2017 RTM herunter, und installieren es](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Andere Toolsets** ausgewählt sein sollte, um .NET Core 1.x-Apps in Visual Studio zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="51fe3-157">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="51fe3-159">Es ist möglich, Visual Studio 2015 für die .NET Core 1.x-Entwicklung zu verwenden, es wird jedoch aus den folgenden Gründen nicht empfohlen:</span><span class="sxs-lookup"><span data-stu-id="51fe3-159">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="51fe3-160">Bei den .NET Core-Tools handelt es sich um eine nicht unterstützte Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="51fe3-160">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="51fe3-161">Die Projekte basieren auf dem Format „project.json“, das veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="51fe3-161">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="51fe3-162">Weitere Informationen zu den Änderungen der Projektformate finden Sie unter [High-level overview of changes (Globale Übersicht der Änderungen)](./tools/cli-msbuild-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="51fe3-162">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="51fe3-163">So überprüfen Sie Ihre Version von Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="51fe3-163">To verify your Visual Studio version:</span></span>
>
> * <span data-ttu-id="51fe3-164">Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="51fe3-164">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="51fe3-165">Verifizieren Sie die Versionsnummer im Dialogfeld **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="51fe3-165">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="51fe3-166">Für .NET Core 3.0 Vorschauversion 3-Apps muss dies Visual Studio 2019 Version 16.0 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="51fe3-166">For .NET Core 3.0 Preview 3 apps, Visual Studio 2019 version 16.0 or higher.</span></span>
>   * <span data-ttu-id="51fe3-167">Für .NET Core 2.2-Apps muss dies Visual Studio 2017 Version 15.9 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="51fe3-167">For .NET Core 2.2 apps, Visual Studio 2017 version 15.9 or higher.</span></span>
>   * <span data-ttu-id="51fe3-168">Für .NET Core 2.1-Apps muss dies Visual Studio 2017 Version 15.7 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="51fe3-168">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="51fe3-169">Für .NET Core 1.x-Apps muss dies Visual Studio 2017 Version 15.0 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="51fe3-169">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
