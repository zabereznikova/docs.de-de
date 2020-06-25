---
title: 'Installieren des .NET Core SDK unter Windows, Linux und macOS: .NET Core'
description: Hier erfahren Sie, wie Sie .NET Core unter Windows, Linux und macOS installieren. Informieren Sie sich über die erforderlichen Abhängigkeiten, die für die Entwicklung von .NET Core-Apps benötigt werden.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 9b170765740600641f96056adc08ff0b69a03338
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768313"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="77824-104">Installieren des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="77824-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="77824-105">In diesem Artikel wird erläutert, wie Sie das .NET Core SDK installieren.</span><span class="sxs-lookup"><span data-stu-id="77824-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="77824-106">Das .NET Core SDK wird zum Erstellen von .NET Core-Apps und -Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="77824-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="77824-107">Die .NET Core-Runtime wird immer mit dem SDK installiert.</span><span class="sxs-lookup"><span data-stu-id="77824-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="77824-108">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="77824-108">Install with an installer</span></span>

<span data-ttu-id="77824-109">Windows verfügt über eigenständige Installer, die zur Installation des .NET Core 3.1 SDK verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="77824-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="77824-110">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="77824-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="77824-111">x86-CPUs (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="77824-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="77824-112">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="77824-112">Install with an installer</span></span>

<span data-ttu-id="77824-113">macOS verfügt über eigenständige Installer, die zur Installation des .NET Core 3.1 SDK verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="77824-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="77824-114">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="77824-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="77824-115">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="77824-115">Download and manually install</span></span>

<span data-ttu-id="77824-116">Alternativ zu den macOS-Installationsprogrammen für .NET Core können Sie das SDK herunterladen und manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="77824-116">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK.</span></span>

<span data-ttu-id="77824-117">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um das SDK zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="77824-117">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="77824-118">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="77824-118">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="77824-119">Bei diesen Befehlen wird dabei ausgegangen, dass die Runtime in die `~/Downloads/dotnet-sdk.pkg`-Datei heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="77824-119">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-sdk.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="77824-120">Installation unter Linux</span><span class="sxs-lookup"><span data-stu-id="77824-120">Install on Linux</span></span>

<span data-ttu-id="77824-121">Dieser Artikel wird bald entfernt.</span><span class="sxs-lookup"><span data-stu-id="77824-121">This article will be removed soon.</span></span> <span data-ttu-id="77824-122">Er wird derzeit durch [Installieren von .NET Core unter Linux](linux.md) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="77824-122">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="77824-123">Installieren mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="77824-123">Install with Visual Studio</span></span>

<span data-ttu-id="77824-124">Für den Fall, dass Sie Visual Studio zum Entwickeln von .NET Core-Apps verwenden, finden Sie in der folgenden Tabelle basierend auf der .NET Core SDK-Zielversion die mindestens erforderliche Version von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="77824-124">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="77824-125">.NET Core SDK-Version</span><span class="sxs-lookup"><span data-stu-id="77824-125">.NET Core SDK version</span></span> | <span data-ttu-id="77824-126">Visual Studio-Version</span><span class="sxs-lookup"><span data-stu-id="77824-126">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="77824-127">3.1</span><span class="sxs-lookup"><span data-stu-id="77824-127">3.1</span></span>                   | <span data-ttu-id="77824-128">Visual Studio 2019 Version 16.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="77824-128">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="77824-129">3.0</span><span class="sxs-lookup"><span data-stu-id="77824-129">3.0</span></span>                   | <span data-ttu-id="77824-130">Visual Studio 2019 Version 16.3 oder höher</span><span class="sxs-lookup"><span data-stu-id="77824-130">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="77824-131">2.2</span><span class="sxs-lookup"><span data-stu-id="77824-131">2.2</span></span>                   | <span data-ttu-id="77824-132">Visual Studio 2017 Version 15.9 oder höher</span><span class="sxs-lookup"><span data-stu-id="77824-132">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="77824-133">2.1</span><span class="sxs-lookup"><span data-stu-id="77824-133">2.1</span></span>                   | <span data-ttu-id="77824-134">Visual Studio 2017 Version 15.7 oder höher</span><span class="sxs-lookup"><span data-stu-id="77824-134">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="77824-135">Wenn Sie Visual Studio bereits installiert haben, können Sie Ihre Version mit den folgenden Schritten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="77824-135">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="77824-136">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="77824-136">Open Visual Studio.</span></span>
01. <span data-ttu-id="77824-137">Klicken Sie auf **Hilfe** > **Info**.</span><span class="sxs-lookup"><span data-stu-id="77824-137">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="77824-138">Informieren Sie sich über die Versionsnummer im Dialogfeld **Info**.</span><span class="sxs-lookup"><span data-stu-id="77824-138">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="77824-139">Visual Studio kann das neueste .NET Core SDK und die Runtime installieren.</span><span class="sxs-lookup"><span data-stu-id="77824-139">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="77824-140">[Visual Studio herunterladen](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="77824-140">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="77824-141">Workload auswählen</span><span class="sxs-lookup"><span data-stu-id="77824-141">Select a workload</span></span>

<span data-ttu-id="77824-142">Wählen Sie in Abhängigkeit vom Typ der von Ihnen erstellten Anwendung beim Installieren oder Ändern von Visual Studio mindestens eine der folgenden Workloads aus:</span><span class="sxs-lookup"><span data-stu-id="77824-142">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="77824-143">Die Workload **Plattformübergreifende .NET Core-Entwicklung** im Abschnitt **Weitere Toolsets**</span><span class="sxs-lookup"><span data-stu-id="77824-143">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="77824-144">Die Workload **ASP.NET und Webentwicklung** im Abschnitt **Web und Cloud**</span><span class="sxs-lookup"><span data-stu-id="77824-144">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="77824-145">**Azure-Entwicklungsworkload** im Abschnitt **Web und Cloud**</span><span class="sxs-lookup"><span data-stu-id="77824-145">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="77824-146">**.NET-Desktopentwicklungsworkload** im Abschnitt **Desktop und mobil**</span><span class="sxs-lookup"><span data-stu-id="77824-146">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="77824-147">[![Windows Visual Studio 2019 mit .NET Core-Workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77824-147">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="77824-148">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="77824-148">Download and manually install</span></span>

<span data-ttu-id="77824-149">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="77824-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="77824-150">Erstellen Sie dann ein Installationsverzeichnis wie z. B. `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="77824-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="77824-151">Extrahieren Sie schließlich die heruntergeladene ZIP-Datei in dieses Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="77824-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="77824-152">Standardmäßig nutzen die Befehle und Anwendungen der .NET Core CLI auf diese Weise installiertes .NET Core nicht. Sie müssen sich explizit dafür entscheiden, es zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="77824-152">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="77824-153">Ändern Sie hierzu die Umgebungsvariablen, mit denen eine Anwendung gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="77824-153">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="77824-154">Bei diesem Ansatz können Sie mehrere Versionen in separaten Speicherorten installieren und dann explizit auswählen, welcher Installationsspeicherort von einer Anwendung verwendet werden soll, indem die Anwendung mit Umgebungsvariablen ausgeführt wird, die auf diesen Speicherort zeigen.</span><span class="sxs-lookup"><span data-stu-id="77824-154">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="77824-155">Selbst wenn diese Umgebungsvariablen festgelegt sind, berücksichtigt .NET Core bei der Auswahl des besten Frameworks für die Ausführung der Anwendung nach wie vor den standardmäßigen globalen Installationsspeicherort.</span><span class="sxs-lookup"><span data-stu-id="77824-155">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="77824-156">Der Standardwert ist normalerweise `C:\Program Files\dotnet`, den die Installationsprogramme verwenden.</span><span class="sxs-lookup"><span data-stu-id="77824-156">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="77824-157">Sie können die Runtime anweisen, nur den benutzerdefinierten Installationsspeicherort zu verwenden, indem Sie diese Umgebungsvariable festlegen:</span><span class="sxs-lookup"><span data-stu-id="77824-157">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="77824-158">Installieren mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="77824-158">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="77824-159">Visual Studio für Mac installiert das .NET Core SDK, wenn die **.NET Core-Workload** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="77824-159">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="77824-160">Informationen zu den ersten Schritten mit der .NET Core-Entwicklung unter macOS finden Sie unter [Installieren von Visual Studio 2019 für Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="77824-160">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="77824-161">Für die neueste Version .NET Core 3.1 müssen Sie die Vorschauversion von Visual Studio für Mac 8.4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="77824-161">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="77824-162">[![macOS-Feature für Visual Studio 2019 für Mac mit .NET Core-Workload](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77824-162">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-windows,os-macos"

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="77824-163">Installieren zusammen mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="77824-163">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="77824-164">Visual Studio Code ist ein leistungsstarker und einfacher Quellcode-Editor, der auf Ihrem Desktop ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="77824-164">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="77824-165">Visual Studio Code ist für Windows, macOS und Linux verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77824-165">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="77824-166">Zwar verfügt Visual Studio Code im Gegensatz zu Visual Studio über keine automatisierten .NET Core-Installer, allerdings ist das Hinzufügen der Unterstützung von .NET Core einfach.</span><span class="sxs-lookup"><span data-stu-id="77824-166">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="77824-167">[Laden Sie Visual Studio Code herunter, und installieren Sie das Tool.](https://code.visualstudio.com/Download)</span><span class="sxs-lookup"><span data-stu-id="77824-167">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="77824-168">[Laden Sie das .NET Core SDK herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core)</span><span class="sxs-lookup"><span data-stu-id="77824-168">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="77824-169">[Installieren Sie die C#-Erweiterung aus dem Visual Studio Code Marketplace.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span><span class="sxs-lookup"><span data-stu-id="77824-169">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="77824-170">Installieren mit PowerShell-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="77824-170">Install with PowerShell automation</span></span>

<span data-ttu-id="77824-171">Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen des SDK von Benutzern ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="77824-171">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="77824-172">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="77824-172">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="77824-173">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="77824-173">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="77824-174">Führen Sie das Skript mit der folgenden Option aus, um die aktuelle Version von .NET Core zu installieren:</span><span class="sxs-lookup"><span data-stu-id="77824-174">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="77824-175">Installieren mit Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="77824-175">Install with bash automation</span></span>

<span data-ttu-id="77824-176">Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen des SDK von Benutzern ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="77824-176">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="77824-177">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="77824-177">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="77824-178">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="77824-178">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="77824-179">Führen Sie das Skript mit der folgenden Option aus, um die aktuelle Version von .NET Core zu installieren:</span><span class="sxs-lookup"><span data-stu-id="77824-179">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="77824-180">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="77824-180">All .NET Core downloads</span></span>

<span data-ttu-id="77824-181">Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:</span><span class="sxs-lookup"><span data-stu-id="77824-181">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="77824-182">Downloads von .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="77824-182">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="77824-183">Downloads von .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="77824-183">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="77824-184">Downloads von .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="77824-184">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="77824-185">Downloads von .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="77824-185">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="77824-186">Docker</span><span class="sxs-lookup"><span data-stu-id="77824-186">Docker</span></span>

<span data-ttu-id="77824-187">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="77824-187">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="77824-188">Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="77824-188">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="77824-189">.NET Core kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="77824-189">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="77824-190">Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77824-190">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="77824-191">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="77824-191">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="77824-192">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="77824-192">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="77824-193">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="77824-193">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="77824-194">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="77824-194">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="77824-195">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="77824-195">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="77824-196">[Tutorial: Hallo Welt-Tutorial](../tutorials/with-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="77824-196">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="77824-197">[Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="77824-197">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="77824-198">[Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="77824-198">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="77824-199">[Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md)</span><span class="sxs-lookup"><span data-stu-id="77824-199">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="77824-200">[Tutorial: Erste Schritte unter macOS](../tutorials/using-on-mac-vs.md)</span><span class="sxs-lookup"><span data-stu-id="77824-200">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="77824-201">[Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="77824-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="77824-202">[Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="77824-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="77824-203">[Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="77824-203">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="77824-204">[Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="77824-204">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
