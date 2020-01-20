---
title: 'Installieren des .NET Core SDK unter Windows, Linux und macOS: .NET Core'
description: Hier erfahren Sie, wie Sie .NET Core unter Windows, Linux und macOS installieren. Informieren Sie sich über die erforderlichen Abhängigkeiten, die für die Entwicklung von .NET Core-Apps benötigt werden.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4a6c8b27812e9f60e52132169dda0464c24abcc2
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740569"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="5d6f2-104">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="5d6f2-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="5d6f2-105">In diesem Artikel wird erläutert, wie Sie das .NET Core SDK installieren.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="5d6f2-106">Das .NET Core SDK wird zum Erstellen von .NET Core-Apps und -Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="5d6f2-107">Die .NET Core-Runtime wird immer mit dem SDK installiert.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="5d6f2-108">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="5d6f2-108">Install with an installer</span></span>

<span data-ttu-id="5d6f2-109">Windows verfügt über eigenständige Installer, die zur Installation des .NET Core 3.1 SDK verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="5d6f2-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="5d6f2-110">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="5d6f2-111">x86-CPUs (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="5d6f2-112">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="5d6f2-112">Install with an installer</span></span>

<span data-ttu-id="5d6f2-113">macOS verfügt über eigenständige Installer, die zur Installation des .NET Core 3.1 SDK verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="5d6f2-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="5d6f2-114">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="5d6f2-115">Installieren mit dem Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="5d6f2-115">Install with a package manager</span></span>

<span data-ttu-id="5d6f2-116">Sie können das .NET Core SDK mit vielen der allgemeinen Linux-Paket-Manager installieren.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-116">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="5d6f2-117">Weitere Informationen finden Sie unter [Linux-Paket-Manager: Installieren von .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="5d6f2-117">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="5d6f2-118">Die Installation mit einem Paket-Manager wird nur in der x64-Architektur unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-118">Installing with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="5d6f2-119">Wenn Sie das .NET Core SDK mit einer anderen Architektur installieren (z. B. mit ARM), befolgen Sie die Anweisungen unter [Herunterladen und manuelles Installieren](#download-and-manually-install) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-119">If you're installing the .NET Core SDK with a different architecture, such as ARM, follow the [Download and manually install](#download-and-manually-install) instructions below.</span></span> <span data-ttu-id="5d6f2-120">Weitere Informationen zu den unterstützten Architekturen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="5d6f2-120">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="5d6f2-121">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="5d6f2-121">Download and manually install</span></span>

<span data-ttu-id="5d6f2-122">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um das SDK zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-122">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="5d6f2-123">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-123">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="5d6f2-124">Mit den oben aufgeführten `export`-Befehlen werden nur die .NET Core-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-124">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="5d6f2-125">Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-125">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="5d6f2-126">Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-126">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="5d6f2-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d6f2-127">For example:</span></span>
>
> - <span data-ttu-id="5d6f2-128">**Bash-Shell**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="5d6f2-128">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="5d6f2-129">**Korn-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="5d6f2-129">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="5d6f2-130">**Z-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="5d6f2-130">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="5d6f2-131">Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-131">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="5d6f2-132">Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-132">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="5d6f2-133">Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-133">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="5d6f2-134">Installieren mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5d6f2-134">Install with Visual Studio</span></span>

<span data-ttu-id="5d6f2-135">Für den Fall, dass Sie Visual Studio zum Entwickeln von .NET Core-Apps verwenden, finden Sie in der folgenden Tabelle basierend auf der .NET Core SDK-Zielversion die mindestens erforderliche Version von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-135">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="5d6f2-136">.NET Core SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5d6f2-136">.NET Core SDK version</span></span> | <span data-ttu-id="5d6f2-137">Visual Studio-Version</span><span class="sxs-lookup"><span data-stu-id="5d6f2-137">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="5d6f2-138">3.1</span><span class="sxs-lookup"><span data-stu-id="5d6f2-138">3.1</span></span>                   | <span data-ttu-id="5d6f2-139">Visual Studio 2019 Version 16.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="5d6f2-139">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="5d6f2-140">3.0</span><span class="sxs-lookup"><span data-stu-id="5d6f2-140">3.0</span></span>                   | <span data-ttu-id="5d6f2-141">Visual Studio 2019 Version 16.3 oder höher</span><span class="sxs-lookup"><span data-stu-id="5d6f2-141">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="5d6f2-142">2.2</span><span class="sxs-lookup"><span data-stu-id="5d6f2-142">2.2</span></span>                   | <span data-ttu-id="5d6f2-143">Visual Studio 2017 Version 15.9 oder höher</span><span class="sxs-lookup"><span data-stu-id="5d6f2-143">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="5d6f2-144">2.1</span><span class="sxs-lookup"><span data-stu-id="5d6f2-144">2.1</span></span>                   | <span data-ttu-id="5d6f2-145">Visual Studio 2017 Version 15.7 oder höher</span><span class="sxs-lookup"><span data-stu-id="5d6f2-145">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="5d6f2-146">Wenn Sie Visual Studio bereits installiert haben, können Sie Ihre Version mit den folgenden Schritten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-146">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="5d6f2-147">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-147">Open Visual Studio.</span></span>
01. <span data-ttu-id="5d6f2-148">Klicken Sie auf **Hilfe** > **Info**.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-148">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="5d6f2-149">Informieren Sie sich über die Versionsnummer im Dialogfeld **Info**.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-149">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="5d6f2-150">Visual Studio kann das neueste .NET Core SDK und die Runtime installieren.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-150">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="5d6f2-151">[Visual Studio herunterladen](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="5d6f2-151">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="5d6f2-152">Workload auswählen</span><span class="sxs-lookup"><span data-stu-id="5d6f2-152">Select a workload</span></span>

<span data-ttu-id="5d6f2-153">Wählen Sie in Abhängigkeit vom Typ der von Ihnen erstellten Anwendung beim Installieren oder Ändern von Visual Studio mindestens eine der folgenden Workloads aus:</span><span class="sxs-lookup"><span data-stu-id="5d6f2-153">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="5d6f2-154">Die Workload **Plattformübergreifende .NET Core-Entwicklung** im Abschnitt **Weitere Toolsets**</span><span class="sxs-lookup"><span data-stu-id="5d6f2-154">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="5d6f2-155">Die Workload **ASP.NET und Webentwicklung** im Abschnitt **Web und Cloud**</span><span class="sxs-lookup"><span data-stu-id="5d6f2-155">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="5d6f2-156">**Azure-Entwicklungsworkload** im Abschnitt **Web und Cloud**</span><span class="sxs-lookup"><span data-stu-id="5d6f2-156">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="5d6f2-157">**.NET-Desktopentwicklungsworkload** im Abschnitt **Desktop und mobil**</span><span class="sxs-lookup"><span data-stu-id="5d6f2-157">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="5d6f2-158">[![Windows Visual Studio 2019 mit .NET Core-Workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-158">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="5d6f2-159">Installieren mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="5d6f2-159">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="5d6f2-160">Visual Studio für Mac installiert das .NET Core SDK, wenn die **.NET Core-Workload** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-160">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="5d6f2-161">Informationen zu den ersten Schritten mit der .NET Core-Entwicklung unter macOS finden Sie unter [Installieren von Visual Studio 2019 für Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="5d6f2-161">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="5d6f2-162">Für die neueste Version .NET Core 3.1 müssen Sie die Vorschauversion von Visual Studio für Mac 8.4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-162">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="5d6f2-163">[![macOS-Feature für Visual Studio 2019 für Mac mit .NET Core-Workload](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-163">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="5d6f2-164">Installieren zusammen mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5d6f2-164">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="5d6f2-165">Visual Studio Code ist ein leistungsstarker und einfacher Quellcode-Editor, der auf Ihrem Desktop ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-165">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="5d6f2-166">Visual Studio Code ist für Windows, macOS und Linux verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-166">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="5d6f2-167">Zwar verfügt Visual Studio Code im Gegensatz zu Visual Studio über keine automatisierten .NET Core-Installer, allerdings ist das Hinzufügen der Unterstützung von .NET Core einfach.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-167">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="5d6f2-168">[Laden Sie Visual Studio Code herunter, und installieren Sie das Tool.](https://code.visualstudio.com/Download)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-168">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="5d6f2-169">[Laden Sie das .NET Core SDK herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-169">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="5d6f2-170">[Installieren Sie die C#-Erweiterung aus dem Visual Studio Code Marketplace.](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-170">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="5d6f2-171">Installieren mit PowerShell-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="5d6f2-171">Install with PowerShell automation</span></span>

<span data-ttu-id="5d6f2-172">Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen des SDK von Benutzern ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-172">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="5d6f2-173">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-173">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="5d6f2-174">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-174">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="5d6f2-175">Führen Sie das Skript mit der folgenden Option aus, um die aktuelle Version von .NET Core zu installieren:</span><span class="sxs-lookup"><span data-stu-id="5d6f2-175">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="5d6f2-176">Installieren mit Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="5d6f2-176">Install with bash automation</span></span>

<span data-ttu-id="5d6f2-177">Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen des SDK von Benutzern ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-177">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="5d6f2-178">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-178">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="5d6f2-179">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-179">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="5d6f2-180">Führen Sie das Skript mit der folgenden Option aus, um die aktuelle Version von .NET Core zu installieren:</span><span class="sxs-lookup"><span data-stu-id="5d6f2-180">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="5d6f2-181">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="5d6f2-181">All .NET Core downloads</span></span>

<span data-ttu-id="5d6f2-182">Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:</span><span class="sxs-lookup"><span data-stu-id="5d6f2-182">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="5d6f2-183">Downloads von .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5d6f2-183">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="5d6f2-184">Downloads von .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5d6f2-184">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="5d6f2-185">Downloads von .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="5d6f2-185">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="5d6f2-186">Downloads von .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5d6f2-186">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="5d6f2-187">Docker</span><span class="sxs-lookup"><span data-stu-id="5d6f2-187">Docker</span></span>

<span data-ttu-id="5d6f2-188">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-188">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="5d6f2-189">Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-189">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="5d6f2-190">.NET Core kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-190">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="5d6f2-191">Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-191">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="5d6f2-192">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-192">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="5d6f2-193">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-193">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="5d6f2-194">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5d6f2-194">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="5d6f2-195">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="5d6f2-195">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5d6f2-196">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5d6f2-196">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="5d6f2-197">[Tutorial: Hallo Welt-Tutorial](../tutorials/with-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-197">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="5d6f2-198">[Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-198">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="5d6f2-199">[Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-199">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="5d6f2-200">[Tutorial: Erste Schritte unter macOS](../tutorials/using-on-mac-vs.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-200">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="5d6f2-201">[Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="5d6f2-202">[Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="5d6f2-203">[Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-203">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="5d6f2-204">[Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="5d6f2-204">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
