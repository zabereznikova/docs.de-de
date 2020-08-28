---
title: Neuerungen in .NET Core 3.1
description: Erfahren Sie mehr zu den neuen Features in .NET Core 3.1.
dev_langs:
- csharp
author: adegeo
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 42d4f7e8800bf2d13d584084f8a41bad2ada534f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608126"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="cfde3-103">Neuerungen in .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="cfde3-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="cfde3-104">In diesem Artikel werden Neuerungen in .NET Core 3.1 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cfde3-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="cfde3-105">Diese Version enthält kleinere Verbesserungen an .NET Core 3.0, wobei der Schwerpunkt auf kleinen, aber wichtigen Korrekturen liegt.</span><span class="sxs-lookup"><span data-stu-id="cfde3-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="cfde3-106">Das wichtigste Merkmal von .NET Core 3.1 ist, dass es sich um eine Version mit [langfristigem Support (Long-Term Support, LTS)](#long-term-support) handelt.</span><span class="sxs-lookup"><span data-stu-id="cfde3-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="cfde3-107">Wenn Sie Visual Studio 2019 verwenden, müssen Sie ein Update auf [Visual Studio 2019, Version 16.4 oder höher](https://visualstudio.microsoft.com/downloads/) durchführen, um mit .NET Core 3.1-Projekten arbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="cfde3-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4 or later](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="cfde3-108">Weitere Informationen zu Neuerungen in Visual Studio 16.4 finden Sie unter [Neuerungen in Visual Studio 2019 Version 16.4](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164).</span><span class="sxs-lookup"><span data-stu-id="cfde3-108">For information on what's new in Visual Studio version 16.4, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="cfde3-109">Visual Studio für Mac unterstützt und umfasst auch .NET Core 3.1, und zwar in Visual Studio für Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="cfde3-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="cfde3-110">Weitere Informationen zu dieser Version finden Sie unter [Ankündigung von .NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span><span class="sxs-lookup"><span data-stu-id="cfde3-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="cfde3-111">[Laden Sie .NET Core 3.1 herunter](https://dotnet.microsoft.com/download/dotnet-core/3.1), um unter Windows, macOS oder Linux loszulegen.</span><span class="sxs-lookup"><span data-stu-id="cfde3-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="cfde3-112">Langfristiger Support</span><span class="sxs-lookup"><span data-stu-id="cfde3-112">Long-term support</span></span>

<span data-ttu-id="cfde3-113">NET Core 3.1 ist eine LTS-Version mit Support von Microsoft für die nächsten drei Jahre.</span><span class="sxs-lookup"><span data-stu-id="cfde3-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="cfde3-114">Es wird dringend empfohlen, Ihre Anwendungen auf .NET Core 3.1 umzustellen.</span><span class="sxs-lookup"><span data-stu-id="cfde3-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="cfde3-115">Der aktuelle Lebenszyklus anderer Hauptversionen ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cfde3-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="cfde3-116">Freigabe</span><span class="sxs-lookup"><span data-stu-id="cfde3-116">Release</span></span> | <span data-ttu-id="cfde3-117">Hinweis</span><span class="sxs-lookup"><span data-stu-id="cfde3-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="cfde3-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cfde3-118">.NET Core 3.0</span></span> | <span data-ttu-id="cfde3-119">Ende des Lebenszyklus: 03. März 2020</span><span class="sxs-lookup"><span data-stu-id="cfde3-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="cfde3-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cfde3-120">.NET Core 2.2</span></span> | <span data-ttu-id="cfde3-121">Ende des Lebenszyklus: 23. Dezember 2019</span><span class="sxs-lookup"><span data-stu-id="cfde3-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="cfde3-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cfde3-122">.NET Core 2.1</span></span> | <span data-ttu-id="cfde3-123">Ende des Lebenszyklus: 21. August 2021</span><span class="sxs-lookup"><span data-stu-id="cfde3-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="cfde3-124">Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="cfde3-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="macos-apphost-and-notarization"></a><span data-ttu-id="cfde3-125">macOS-appHost und -Notarisierung</span><span class="sxs-lookup"><span data-stu-id="cfde3-125">macOS appHost and notarization</span></span>

<span data-ttu-id="cfde3-126">*nur unter macOS*</span><span class="sxs-lookup"><span data-stu-id="cfde3-126">*macOS only*</span></span>

<span data-ttu-id="cfde3-127">Ab dem notarisierten .NET Core SDK 3.1 für macOS, ist die appHost-Einstellung standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cfde3-127">Starting with the notarized .NET Core SDK 3.1 for macOS, the appHost setting is disabled by default.</span></span> <span data-ttu-id="cfde3-128">Weitere Informationen finden Sie unter [macOS Catalina-Notarisierung und die Auswirkungen auf .NET Core-Downloads und -Projekte](../install/macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cfde3-128">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="cfde3-129">Wenn die appHost-Einstellung aktiviert ist, erzeugt .NET Core eine native ausführbare Mach-O-Datei, wenn Sie einen Build- oder Veröffentlichungsprozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="cfde3-129">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="cfde3-130">Ihre App wird im Kontext von appHost ausgeführt, wenn sie mit dem Befehl `dotnet run` über den Quellcode oder durch direktes Starten der ausführbaren Mach-O-Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cfde3-130">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="cfde3-131">Ohne die appHost-Datei können Benutzer eine [frameworkabhängige](../deploying/index.md#publish-framework-dependent) App nur mit dem Befehl `dotnet <filename.dll>` starten.</span><span class="sxs-lookup"><span data-stu-id="cfde3-131">Without the appHost, the only way a user can start a [framework-dependent](../deploying/index.md#publish-framework-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="cfde3-132">Es wird immer eine appHost-Datei erstellt, wenn Sie Ihre App [eigenständig](../deploying/index.md#publish-self-contained) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="cfde3-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="cfde3-133">Sie können die appHost-Datei entweder auf Projektebene konfigurieren oder für einen spezifischen `dotnet`-Befehl mit dem `-p:UseAppHost`-Parameter aktivieren:</span><span class="sxs-lookup"><span data-stu-id="cfde3-133">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="cfde3-134">Projektdatei</span><span class="sxs-lookup"><span data-stu-id="cfde3-134">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="cfde3-135">Befehlszeilenparameter</span><span class="sxs-lookup"><span data-stu-id="cfde3-135">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="cfde3-136">Weitere Informationen über die `UseAppHost`-Einstellung finden Sie unter [MSBuild-Eigenschaften für Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span><span class="sxs-lookup"><span data-stu-id="cfde3-136">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="cfde3-137">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfde3-137">Windows Forms</span></span>

<span data-ttu-id="cfde3-138">*Nur Windows*</span><span class="sxs-lookup"><span data-stu-id="cfde3-138">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="cfde3-139">Bei Windows Forms gibt es Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="cfde3-139">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="cfde3-140">Windows Forms wurden ältere Steuerelemente hinzugefügt, die in der Visual Studio Designer-Toolbox seit einiger Zeit nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cfde3-140">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="cfde3-141">Diese wurden bereits in .NET Framework 2.0 durch neue Steuerelemente ersetzt.</span><span class="sxs-lookup"><span data-stu-id="cfde3-141">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="cfde3-142">Sie wurden aus dem Desktop SDK für .NET Core 3.1 entfernt.</span><span class="sxs-lookup"><span data-stu-id="cfde3-142">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="cfde3-143">Entferntes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cfde3-143">Removed control</span></span> | <span data-ttu-id="cfde3-144">Empfohlener Ersatz</span><span class="sxs-lookup"><span data-stu-id="cfde3-144">Recommended replacement</span></span> | <span data-ttu-id="cfde3-145">Zugehörige entfernte APIs</span><span class="sxs-lookup"><span data-stu-id="cfde3-145">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="cfde3-146">DataGrid</span><span class="sxs-lookup"><span data-stu-id="cfde3-146">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="cfde3-147">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="cfde3-147">DataGridCell</span></span><br/><span data-ttu-id="cfde3-148">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="cfde3-148">DataGridRow</span></span><br/><span data-ttu-id="cfde3-149">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="cfde3-149">DataGridTableCollection</span></span><br/><span data-ttu-id="cfde3-150">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="cfde3-150">DataGridColumnCollection</span></span><br/><span data-ttu-id="cfde3-151">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="cfde3-151">DataGridTableStyle</span></span><br/><span data-ttu-id="cfde3-152">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="cfde3-152">DataGridColumnStyle</span></span><br/><span data-ttu-id="cfde3-153">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="cfde3-153">DataGridLineStyle</span></span><br/><span data-ttu-id="cfde3-154">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="cfde3-154">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="cfde3-155">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="cfde3-155">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="cfde3-156">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="cfde3-156">DataGridBoolColumn</span></span><br/><span data-ttu-id="cfde3-157">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="cfde3-157">DataGridTextBox</span></span><br/><span data-ttu-id="cfde3-158">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="cfde3-158">GridColumnStylesCollection</span></span><br/><span data-ttu-id="cfde3-159">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="cfde3-159">GridTableStylesCollection</span></span><br/><span data-ttu-id="cfde3-160">HitTestType</span><span class="sxs-lookup"><span data-stu-id="cfde3-160">HitTestType</span></span> |
| <span data-ttu-id="cfde3-161">ToolBar</span><span class="sxs-lookup"><span data-stu-id="cfde3-161">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="cfde3-162">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="cfde3-162">ToolBarAppearance</span></span> |
| <span data-ttu-id="cfde3-163">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="cfde3-163">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="cfde3-164">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="cfde3-164">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="cfde3-165">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="cfde3-165">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="cfde3-166">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="cfde3-166">ToolBarButtonStyle</span></span><br/><span data-ttu-id="cfde3-167">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="cfde3-167">ToolBarTextAlign</span></span> |
| <span data-ttu-id="cfde3-168">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="cfde3-168">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="cfde3-169">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="cfde3-169">MenuItemCollection</span></span> |
| <span data-ttu-id="cfde3-170">MainMenu</span><span class="sxs-lookup"><span data-stu-id="cfde3-170">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="cfde3-171">MenuItem</span><span class="sxs-lookup"><span data-stu-id="cfde3-171">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="cfde3-172">Es wird empfohlen, Ihre Anwendungen auf .NET Core 3.1 zu aktualisieren und auf die Ersatzsteuerelemente umzusteigen.</span><span class="sxs-lookup"><span data-stu-id="cfde3-172">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="cfde3-173">Das Ersetzen der Steuerelemente ist ein unkomplizierter Prozess, der im Wesentlichen das Suchen und Ersetzen des jeweiligen Typs vorsieht.</span><span class="sxs-lookup"><span data-stu-id="cfde3-173">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="cfde3-174">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="cfde3-174">C++/CLI</span></span>

<span data-ttu-id="cfde3-175">*Nur Windows*</span><span class="sxs-lookup"><span data-stu-id="cfde3-175">*Windows only*</span></span>

<span data-ttu-id="cfde3-176">Es wurde Unterstützung für die Erstellung von C++/CLI-Projekten (auch „verwaltete C++-Projekte“ genannt) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cfde3-176">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="cfde3-177">Die im Rahmen dieser Projekte erstellten Binärdateien sind mit .NET Core 3.0 und höheren Versionen kompatibel.</span><span class="sxs-lookup"><span data-stu-id="cfde3-177">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="cfde3-178">Installieren Sie die [Workload „Desktopentwicklung mit C++“](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads), um Unterstützung für C++/CLI in Visual Studio 2019 Version 16.4 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cfde3-178">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="cfde3-179">Diese Workload fügt Visual Studio zwei Vorlagen hinzu:</span><span class="sxs-lookup"><span data-stu-id="cfde3-179">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="cfde3-180">CLR-Klassenbibliothek (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="cfde3-180">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="cfde3-181">Leeres CLR-Projekt (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="cfde3-181">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="cfde3-182">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cfde3-182">Next steps</span></span>

- [<span data-ttu-id="cfde3-183">Breaking Changes bei der Migration von Version 3.0 zu Version 3.1</span><span class="sxs-lookup"><span data-stu-id="cfde3-183">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="cfde3-184">Überprüfen von Breaking Changes in .NET Core 3.1 für Windows Forms-Apps</span><span class="sxs-lookup"><span data-stu-id="cfde3-184">Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
