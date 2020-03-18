---
title: Installieren von .NET Core-Runtime unter Windows, Linux und macOS (.NET Core)
description: Erfahren Sie. wie Sie .NET Core unter Windows, Linux und macOS installieren. Entdecken Sie die erforderlichen Abhängigkeiten, die für die Ausführung von .NET Core-Apps benötigt werden.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca55b8fab4aa9ca9f7e308cce57181e2c7e89f4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397962"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="c83ce-104">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="c83ce-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="c83ce-105">In diesem Artikel erfahren Sie, wie Sie die .NET Core-Runtime herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="c83ce-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="c83ce-106">Die .NET Core-Runtime wird zur Ausführung der mit .NET Core erstellten Apps verwendet.</span><span class="sxs-lookup"><span data-stu-id="c83ce-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="c83ce-107">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="c83ce-107">Install with an installer</span></span>

<span data-ttu-id="c83ce-108">Windows verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="c83ce-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="c83ce-109">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="c83ce-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="c83ce-110">x86-CPUs (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="c83ce-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="c83ce-111">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="c83ce-111">Install with an installer</span></span>

<span data-ttu-id="c83ce-112">macOS verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="c83ce-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="c83ce-113">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="c83ce-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="c83ce-114">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="c83ce-114">Download and manually install</span></span>

<span data-ttu-id="c83ce-115">Alternativ zu den macOS-Installationsprogrammen für .NET Core können Sie die Runtime herunterladen und manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="c83ce-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="c83ce-116">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu installieren und die Verwendung von .NET Core-CLI-Befehle im Terminal zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="c83ce-117">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="c83ce-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="c83ce-118">Bei diesen Befehlen wird dabei ausgegangen, dass die Runtime in die `~/Downloads/dotnet-runtime.pkg`-Datei heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="c83ce-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="c83ce-119">Installieren mit dem Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="c83ce-119">Install with a package manager</span></span>

<span data-ttu-id="c83ce-120">Sie können die .NET Core-Runtime mit vielen der allgemeinen Linux-Paket-Manager installieren.</span><span class="sxs-lookup"><span data-stu-id="c83ce-120">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="c83ce-121">Weitere Informationen finden Sie unter [Linux-Paket-Manager: Installieren von .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="c83ce-121">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="c83ce-122">Die Installation mit einem Paket-Manager wird nur in der x64-Architektur unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c83ce-122">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="c83ce-123">Wenn Sie die .NET Core-Runtime mit einer anderen Architektur installieren (z. B. mit ARM), befolgen Sie die Anweisungen im Abschnitt [Herunterladen und manuelles Installieren](#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="c83ce-123">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="c83ce-124">Weitere Informationen zu den unterstützten Architekturen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="c83ce-124">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="c83ce-125">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="c83ce-125">Download and manually install</span></span>

<span data-ttu-id="c83ce-126">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-126">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="c83ce-127">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="c83ce-127">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="c83ce-128">Mit den oben aufgeführten `export`-Befehlen werden nur die .NET Core-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c83ce-128">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="c83ce-129">Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-129">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="c83ce-130">Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-130">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="c83ce-131">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c83ce-131">For example:</span></span>
>
> - <span data-ttu-id="c83ce-132">**Bash-Shell**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="c83ce-132">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="c83ce-133">**Korn-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="c83ce-133">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="c83ce-134">**Z-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="c83ce-134">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="c83ce-135">Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c83ce-135">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="c83ce-136">Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.</span><span class="sxs-lookup"><span data-stu-id="c83ce-136">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="c83ce-137">Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="c83ce-137">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="c83ce-138">Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c83ce-138">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="c83ce-139">Installieren mit PowerShell-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="c83ce-139">Install with PowerShell automation</span></span>

<span data-ttu-id="c83ce-140">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="c83ce-140">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="c83ce-141">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-141">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c83ce-142">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="c83ce-142">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="c83ce-143">Sie können eine bestimmte Version durch Angeben der `Channel`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-143">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="c83ce-144">Schließen Sie die `Runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c83ce-144">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="c83ce-145">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="c83ce-145">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="c83ce-146">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="c83ce-146">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="c83ce-147">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="c83ce-147">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="c83ce-148">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="c83ce-148">Download and manually install</span></span>

<span data-ttu-id="c83ce-149">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="c83ce-150">Erstellen Sie dann ein Installationsverzeichnis wie z. B. `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="c83ce-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="c83ce-151">Extrahieren Sie schließlich die heruntergeladene ZIP-Datei in dieses Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c83ce-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="c83ce-152">Standardmäßig verwenden .NET Core-CLI-Befehle und -Apps nicht auf diese Weise installiertes .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c83ce-152">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="c83ce-153">Sie müssen dessen Verwendung explizit auswählen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-153">You have to explicitly choose to use it.</span></span> <span data-ttu-id="c83ce-154">Ändern Sie hierzu die Umgebungsvariablen, mit denen eine Anwendung gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="c83ce-154">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="c83ce-155">Bei diesem Ansatz können Sie mehrere Versionen in separaten Speicherorten installieren und dann explizit auswählen, welcher Installationsspeicherort von einer Anwendung verwendet werden soll, indem die Anwendung mit Umgebungsvariablen ausgeführt wird, die auf diesen Speicherort zeigen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-155">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="c83ce-156">Selbst wenn diese Umgebungsvariablen festgelegt sind, berücksichtigt .NET Core bei der Auswahl des besten Frameworks für die Ausführung der Anwendung nach wie vor den standardmäßigen globalen Installationsspeicherort.</span><span class="sxs-lookup"><span data-stu-id="c83ce-156">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="c83ce-157">Der Standardwert ist normalerweise `C:\Program Files\dotnet`, den die Installationsprogramme verwenden.</span><span class="sxs-lookup"><span data-stu-id="c83ce-157">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="c83ce-158">Sie können die Runtime anweisen, nur den benutzerdefinierten Installationsspeicherort zu verwenden, indem Sie diese Umgebungsvariable festlegen:</span><span class="sxs-lookup"><span data-stu-id="c83ce-158">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="c83ce-159">Installieren mit Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="c83ce-159">Install with bash automation</span></span>

<span data-ttu-id="c83ce-160">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="c83ce-160">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="c83ce-161">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-161">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c83ce-162">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="c83ce-162">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="c83ce-163">Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-163">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="c83ce-164">Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c83ce-164">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="c83ce-165">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="c83ce-165">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="c83ce-166">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="c83ce-166">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="c83ce-167">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="c83ce-167">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="c83ce-168">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="c83ce-168">All .NET Core downloads</span></span>

<span data-ttu-id="c83ce-169">Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:</span><span class="sxs-lookup"><span data-stu-id="c83ce-169">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="c83ce-170">Downloads von .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c83ce-170">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="c83ce-171">Downloads von .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c83ce-171">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="c83ce-172">Docker</span><span class="sxs-lookup"><span data-stu-id="c83ce-172">Docker</span></span>

<span data-ttu-id="c83ce-173">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="c83ce-173">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="c83ce-174">Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="c83ce-174">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="c83ce-175">.NET Core kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c83ce-175">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="c83ce-176">Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c83ce-176">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="c83ce-177">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c83ce-177">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="c83ce-178">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="c83ce-178">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="c83ce-179">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c83ce-179">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="c83ce-180">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="c83ce-180">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c83ce-181">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c83ce-181">Next steps</span></span>

- <span data-ttu-id="c83ce-182">[Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md)</span><span class="sxs-lookup"><span data-stu-id="c83ce-182">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
