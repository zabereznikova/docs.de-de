---
title: Voraussetzungen für .NET Core unter Windows
description: Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: b1557e6910cb6d0b6d7e2b3ce2aec97d3715fec7
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591668"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="b0354-103">Voraussetzungen für .NET Core unter Windows</span><span class="sxs-lookup"><span data-stu-id="b0354-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="b0354-104">Dieser Artikel beschreibt die zur Ausführung von .NET Core-Anwendungen auf Windows unterstützten Betriebssystemversionen.</span><span class="sxs-lookup"><span data-stu-id="b0354-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="b0354-105">Die unterstützten Betriebssystemversionen und die daraus folgenden Abhängigkeiten gelten für die drei Möglichkeiten, um .NET Core-Apps unter Windows zu entwickeln:</span><span class="sxs-lookup"><span data-stu-id="b0354-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="b0354-106">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="b0354-106">Command line</span></span>](./tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="b0354-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0354-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [<span data-ttu-id="b0354-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b0354-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="b0354-109">Nutzen Sie für die Entwicklung unter Windows mit Visual Studio die ausführlicheren Informationen über die für die .NET Core-Entwicklung unterstützten Mindestversionen im Abschnitt [Voraussetzungen für die Entwicklung von .NET Core-Anwendungen mit Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b0354-109">Also, if you're developing on Windows using Visual Studio, the [Prerequisites to develop .NET Core apps with Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="b0354-110">Von .NET Core unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="b0354-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="b0354-111">Die folgenden Artikel enthalten eine vollständige Liste der von .NET Core unterstützten Betriebssysteme je nach Version:</span><span class="sxs-lookup"><span data-stu-id="b0354-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="b0354-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b0354-112">.NET Core 3.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="b0354-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="b0354-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="b0354-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b0354-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

<span data-ttu-id="b0354-115">Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Downloads](https://dotnet.microsoft.com/download) für die neueste Version bzw. [.NET Download Archives](https://dotnet.microsoft.com/download/archives#dotnet-core) für ältere Versionen.</span><span class="sxs-lookup"><span data-stu-id="b0354-115">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="b0354-116">.NET Core-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="b0354-116">.NET Core dependencies</span></span>

<span data-ttu-id="b0354-117">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) muss in folgenden Fällen installiert werden:</span><span class="sxs-lookup"><span data-stu-id="b0354-117">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="b0354-118">Beim Installieren von .NET Core mit dem [Installationsprogrammskript](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="b0354-118">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="b0354-119">Beim Bereitstellen einer eigenständigen .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b0354-119">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="b0354-120">Beim Erstellen des Produkt aus der Quelle.</span><span class="sxs-lookup"><span data-stu-id="b0354-120">Building the product from source.</span></span>
* <span data-ttu-id="b0354-121">Beim Installieren von .NET Core über eine *ZIP*-Datei.</span><span class="sxs-lookup"><span data-stu-id="b0354-121">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="b0354-122">Dazu können Build-/CI-/CD-Server gehören.</span><span class="sxs-lookup"><span data-stu-id="b0354-122">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="b0354-123">**Für Windows 8.1 und frühere Versionen oder Windows Server 2012 R2 und frühere Versionen:**</span><span class="sxs-lookup"><span data-stu-id="b0354-123">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="b0354-124">Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) enthält, das über Windows Update installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b0354-124">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="b0354-125">Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung wie die folgende angezeigt: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="b0354-125">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="b0354-126">**Für Windows 7 oder Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="b0354-126">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="b0354-127">Stellen Sie sicher, dass Sie neben KB2999226 auch [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="b0354-127">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="b0354-128">Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung ähnlich der folgenden angezeigt: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="b0354-128">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a><span data-ttu-id="b0354-129">Voraussetzungen für die Entwicklung von .NET Core-Anwendungen mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0354-129">Prerequisites to develop .NET Core apps with Visual Studio</span></span>
    
<span data-ttu-id="b0354-130">Für die Entwicklung von .NET Core-Anwendungen können Sie zwar einen beliebigen Editor verwenden. Das .NET Core SDK sowie Visual Studio 2017 und höhere Versionen stellen jedoch eine integrierte Entwicklungsumgebung für .NET Core-Anwendungen unter Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="b0354-130">Even though you can use any editor to develop .NET Core applications using the .NET Core SDK, Visual Studio 2017 and later versions provide an integrated development environment for .NET Core apps on Windows.</span></span>

<a name="vs-mapping"></a>

<span data-ttu-id="b0354-131">Für jede .NET Core-Version ist eine Mindestversion von Visual Studio erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b0354-131">Each .NET Core version has a minimum version of Visual Studio required.</span></span> <span data-ttu-id="b0354-132">So überprüfen Sie Ihre Version von Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b0354-132">To verify your Visual Studio version:</span></span>

* <span data-ttu-id="b0354-133">Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b0354-133">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
* <span data-ttu-id="b0354-134">Verifizieren Sie die Versionsnummer im Dialogfeld **Info zu Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b0354-134">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>

<span data-ttu-id="b0354-135">In der folgenden Tabelle sind die Mindestversionen für die einzelnen SDKs aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="b0354-135">The following table lists the minimum version for each SDK:</span></span>

| <span data-ttu-id="b0354-136">.NET Core SDK-Version</span><span class="sxs-lookup"><span data-stu-id="b0354-136">.NET Core SDK version</span></span> | <span data-ttu-id="b0354-137">Visual Studio-Version</span><span class="sxs-lookup"><span data-stu-id="b0354-137">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="b0354-138">3.0</span><span class="sxs-lookup"><span data-stu-id="b0354-138">3.0</span></span>                   | <span data-ttu-id="b0354-139">Visual Studio 2019 Version 16.3 oder höher</span><span class="sxs-lookup"><span data-stu-id="b0354-139">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="b0354-140">2.2</span><span class="sxs-lookup"><span data-stu-id="b0354-140">2.2</span></span>                   | <span data-ttu-id="b0354-141">Visual Studio 2017 Version 15.9 oder höher</span><span class="sxs-lookup"><span data-stu-id="b0354-141">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="b0354-142">2.1</span><span class="sxs-lookup"><span data-stu-id="b0354-142">2.1</span></span>                   | <span data-ttu-id="b0354-143">Visual Studio 2017 Version 15.7 oder höher</span><span class="sxs-lookup"><span data-stu-id="b0354-143">Visual Studio 2017 version 15.7 or higher.</span></span> |
| <span data-ttu-id="b0354-144">1.x</span><span class="sxs-lookup"><span data-stu-id="b0354-144">1.x</span></span>                   | <span data-ttu-id="b0354-145">Visual Studio 2017 Version 15.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="b0354-145">Visual Studio 2017 version 15.0 or higher.</span></span> |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="b0354-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b0354-146">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="b0354-147">So entwickeln Sie .NET Core-Apps in Visual Studio 2019 mithilfe des .NET Core 3.0 SDK:</span><span class="sxs-lookup"><span data-stu-id="b0354-147">To develop .NET Core apps in Visual Studio 2019 using the .NET Core 3.0 SDK:</span></span>

* <span data-ttu-id="b0354-148">[Laden Sie Visual Studio 2019 Version 16.3 oder höher herunter, und installieren Sie diese Version.](/visualstudio/install/install-visual-studio) Wählen Sie je nach der Art der Anwendung, die Sie entwickeln, eine der folgenden Workloads, die das .NET Core SDK enthält:</span><span class="sxs-lookup"><span data-stu-id="b0354-148">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) and select one of the following workloads that includes the .NET Core SDK, depending on the kind of application you're building:</span></span>

  * <span data-ttu-id="b0354-149">Die Workload **Plattformübergreifende .NET Core-Entwicklung** im Abschnitt **Weitere Toolsets**</span><span class="sxs-lookup"><span data-stu-id="b0354-149">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
  * <span data-ttu-id="b0354-150">Die Workload **ASP.NET und Webentwicklung** im Abschnitt **Web und Cloud**</span><span class="sxs-lookup"><span data-stu-id="b0354-150">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
  * <span data-ttu-id="b0354-151">Die Workload **NET-Desktopentwicklung** im Abschnitt **Windows**</span><span class="sxs-lookup"><span data-stu-id="b0354-151">The **NET desktop development** workload in the **Windows** section.</span></span>

<span data-ttu-id="b0354-152">In der folgenden Abbildung ist die in der Benutzeroberfläche von Visual Studio ausgewählte Workload **Plattformübergreifende .NET Core-Entwicklung** dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b0354-152">The following image shows the **.NET Core cross-platform development** workload selected in the Visual Studio UI:</span></span>

![Screenshot der Visual Studio 2019-Installation mit ausgewählter Workload „Plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-2019-workloads.jpg)

<span data-ttu-id="b0354-154">Nach der Installation dieser Workloads wird von Visual Studio 2019 Version 16.3 standardmäßig das .NET Core 3.0 SDK verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0354-154">Visual Studio 2019 16.3 uses .NET Core 3.0 SDK by default after any of these workloads are installed.</span></span>

<span data-ttu-id="b0354-155">Wenn Ihre vorhandenen Projekte die neueste .NET Core-Runtime verwenden soll, weisen Sie die vorhandenen .NET Core-Projekte mithilfe der folgenden Anweisungen .NET Core 3.0 neu zu:</span><span class="sxs-lookup"><span data-stu-id="b0354-155">If you want your existing projects to use the latest .NET Core runtime, retarget each existing .NET Core project to .NET Core 3.0 using the following instructions:</span></span>

* <span data-ttu-id="b0354-156">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b0354-156">On the **Project** menu, choose **Properties**.</span></span>
* <span data-ttu-id="b0354-157">Legen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 3.0** fest.</span><span class="sxs-lookup"><span data-stu-id="b0354-157">In the **Target framework** selection menu, set the value to **.NET Core 3.0**.</span></span>

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2019 mit dem als Zielframework ausgewählten Menüelement „.NET Core 3.0“](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

<span data-ttu-id="b0354-159">Nach der Konfiguration von Visual Studio mit dem .NET Core 3.0 SDK können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="b0354-159">Once you have Visual Studio configured with .NET Core 3.0 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="b0354-160">Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x- und .NET Core 2.x-Projekte.</span><span class="sxs-lookup"><span data-stu-id="b0354-160">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="b0354-161">Neuzuweisen von .NET Core 1.x- und 2.x-Projekten zu .NET Core 3.0 sowie Erstellen und Ausführen derselben.</span><span class="sxs-lookup"><span data-stu-id="b0354-161">Retarget .NET Core 1.x and 2.x projects to .NET Core 3.0, build, and run.</span></span>
* <span data-ttu-id="b0354-162">Erstellen Sie neue .NET Core 3.0-Projekte.</span><span class="sxs-lookup"><span data-stu-id="b0354-162">Create new .NET Core 3.0 projects.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b0354-163">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b0354-163">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="b0354-164">So entwickeln Sie .NET Core-Apps in Visual Studio 2017 mithilfe des .NET Core 2.2 SDK:</span><span class="sxs-lookup"><span data-stu-id="b0354-164">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

* <span data-ttu-id="b0354-165">[Laden Sie Visual Studio 2019 Version 16.3 oder höher herunter, und installieren Sie diese](/visualstudio/install/install-visual-studio) zusammen mit der Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Weitere Toolsets** ausgewählt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="b0354-165">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
* <span data-ttu-id="b0354-166">[Laden Sie Visual Studio 2017 Version 15.9.0 oder höher herunter, und installieren Sie diese](/visualstudio/install/install-visual-studio) zusammen mit der Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Andere Toolsets** ausgewählt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="b0354-166">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="b0354-168">Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert ist, verwendet Visual Studio in der Regel eine frühere Version von .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="b0354-168">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="b0354-169">Visual Studio 2017 15.9 verwendet z. B. .NET Core 2.1 SDK standardmäßig nach der Installation der Workload.</span><span class="sxs-lookup"><span data-stu-id="b0354-169">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="b0354-170">So aktualisieren Sie Visual Studio, um .NET Core 2.2 SDK zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="b0354-170">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="b0354-171">Installieren Sie das [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="b0354-171">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="b0354-172">Wenn Ihr Projekt die neueste .NET Core-Runtime verwenden soll, weisen Sie vorhandene oder neue .NET Core-Projekte mithilfe der folgenden Anweisungen .NET Core 2.2 neu zu:</span><span class="sxs-lookup"><span data-stu-id="b0354-172">If you want your project to use the latest .NET Core runtime, retarget each existing or new .NET Core project to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="b0354-173">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b0354-173">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="b0354-174">Legen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.2** fest.</span><span class="sxs-lookup"><span data-stu-id="b0354-174">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.2“](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="b0354-176">Nach der Konfiguration von Visual Studio mit dem .NET Core 2.2 SDK können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="b0354-176">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="b0354-177">Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x- und .NET Core 2.x-Projekte.</span><span class="sxs-lookup"><span data-stu-id="b0354-177">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="b0354-178">Neuzuweisen von .NET Core 1.x- und 2.x-Projekten zu .NET Core 2.2 sowie Erstellen und Ausführen derselben.</span><span class="sxs-lookup"><span data-stu-id="b0354-178">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="b0354-179">Erstellen Sie neue .NET Core 2.2-Projekte.</span><span class="sxs-lookup"><span data-stu-id="b0354-179">Create new .NET Core 2.2 projects.</span></span>

---
