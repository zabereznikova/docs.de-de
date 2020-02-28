---
title: Installieren von .NET Core-Runtime unter Windows, Linux und macOS (.NET Core)
description: Erfahren Sie. wie Sie .NET Core unter Windows, Linux und macOS installieren. Entdecken Sie die erforderlichen Abhängigkeiten, die für die Ausführung von .NET Core-Apps benötigt werden.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ba50eb222d9eab6bffbb8ebfdf0ecf47951ce719
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543520"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="32370-104">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="32370-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="32370-105">In diesem Artikel erfahren Sie, wie Sie die .NET Core-Runtime herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="32370-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="32370-106">Die .NET Core-Runtime wird zur Ausführung der mit .NET Core erstellten Apps verwendet.</span><span class="sxs-lookup"><span data-stu-id="32370-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="32370-107">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="32370-107">Install with an installer</span></span>

<span data-ttu-id="32370-108">Windows verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="32370-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="32370-109">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="32370-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="32370-110">x86-CPUs (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="32370-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="32370-111">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="32370-111">Install with an installer</span></span>

<span data-ttu-id="32370-112">macOS verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="32370-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="32370-113">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="32370-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="32370-114">Installieren mit dem Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="32370-114">Install with a package manager</span></span>

<span data-ttu-id="32370-115">Sie können die .NET Core-Runtime mit vielen der allgemeinen Linux-Paket-Manager installieren.</span><span class="sxs-lookup"><span data-stu-id="32370-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="32370-116">Weitere Informationen finden Sie unter [Linux-Paket-Manager: Installieren von .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="32370-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="32370-117">Die Installation mit einem Paket-Manager wird nur in der x64-Architektur unterstützt.</span><span class="sxs-lookup"><span data-stu-id="32370-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="32370-118">Wenn Sie die .NET Core-Runtime mit einer anderen Architektur installieren (z. B. mit ARM), befolgen Sie die Anweisungen im Abschnitt [Herunterladen und manuelles Installieren](#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="32370-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="32370-119">Weitere Informationen zu den unterstützten Architekturen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="32370-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="32370-120">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="32370-120">Download and manually install</span></span>

<span data-ttu-id="32370-121">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="32370-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="32370-122">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="32370-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="32370-123">Mit den oben aufgeführten `export`-Befehlen werden nur die .NET Core-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="32370-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="32370-124">Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="32370-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="32370-125">Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen.</span><span class="sxs-lookup"><span data-stu-id="32370-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="32370-126">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="32370-126">For example:</span></span>
>
> - <span data-ttu-id="32370-127">**Bash-Shell**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="32370-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="32370-128">**Korn-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="32370-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="32370-129">**Z-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="32370-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="32370-130">Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="32370-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="32370-131">Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.</span><span class="sxs-lookup"><span data-stu-id="32370-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="32370-132">Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="32370-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="32370-133">Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="32370-133">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="32370-134">Installieren mit PowerShell-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="32370-134">Install with PowerShell automation</span></span>

<span data-ttu-id="32370-135">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="32370-135">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="32370-136">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="32370-136">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="32370-137">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="32370-137">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="32370-138">Sie können eine bestimmte Version durch Angeben der `Channel`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="32370-138">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="32370-139">Schließen Sie die `Runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="32370-139">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="32370-140">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="32370-140">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="32370-141">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="32370-141">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="32370-142">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="32370-142">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="32370-143">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="32370-143">Download and manually install</span></span>

<span data-ttu-id="32370-144">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="32370-144">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="32370-145">Erstellen Sie dann ein Installationsverzeichnis wie z. B. `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="32370-145">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="32370-146">Extrahieren Sie schließlich die heruntergeladene ZIP-Datei in dieses Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="32370-146">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="32370-147">Standardmäßig verwenden .NET Core-CLI-Befehle und -Apps nicht auf diese Weise installiertes .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32370-147">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="32370-148">Sie müssen dessen Verwendung explizit auswählen.</span><span class="sxs-lookup"><span data-stu-id="32370-148">You have to explicitly choose to use it.</span></span> <span data-ttu-id="32370-149">Ändern Sie hierzu die Umgebungsvariablen, mit denen eine Anwendung gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="32370-149">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="32370-150">Bei diesem Ansatz können Sie mehrere Versionen in separaten Speicherorten installieren und dann explizit auswählen, welcher Installationsspeicherort von einer Anwendung verwendet werden soll, indem die Anwendung mit Umgebungsvariablen ausgeführt wird, die auf diesen Speicherort zeigen.</span><span class="sxs-lookup"><span data-stu-id="32370-150">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="32370-151">Selbst wenn diese Umgebungsvariablen festgelegt sind, berücksichtigt .NET Core bei der Auswahl des besten Frameworks für die Ausführung der Anwendung nach wie vor den standardmäßigen globalen Installationsspeicherort.</span><span class="sxs-lookup"><span data-stu-id="32370-151">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="32370-152">Der Standardwert ist normalerweise `C:\Program Files\dotnet`, den die Installationsprogramme verwenden.</span><span class="sxs-lookup"><span data-stu-id="32370-152">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="32370-153">Sie können die Runtime anweisen, nur den benutzerdefinierten Installationsspeicherort zu verwenden, indem Sie diese Umgebungsvariable festlegen:</span><span class="sxs-lookup"><span data-stu-id="32370-153">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="32370-154">Installieren mit Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="32370-154">Install with bash automation</span></span>

<span data-ttu-id="32370-155">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="32370-155">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="32370-156">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="32370-156">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="32370-157">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="32370-157">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="32370-158">Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="32370-158">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="32370-159">Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="32370-159">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="32370-160">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="32370-160">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="32370-161">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="32370-161">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="32370-162">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="32370-162">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="32370-163">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="32370-163">All .NET Core downloads</span></span>

<span data-ttu-id="32370-164">Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:</span><span class="sxs-lookup"><span data-stu-id="32370-164">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="32370-165">Downloads von .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="32370-165">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="32370-166">Downloads von .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="32370-166">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="32370-167">Downloads von .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="32370-167">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="32370-168">Downloads von .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="32370-168">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="32370-169">Docker</span><span class="sxs-lookup"><span data-stu-id="32370-169">Docker</span></span>

<span data-ttu-id="32370-170">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="32370-170">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="32370-171">Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="32370-171">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="32370-172">.NET Core kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="32370-172">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="32370-173">Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32370-173">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="32370-174">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="32370-174">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="32370-175">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="32370-175">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="32370-176">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="32370-176">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="32370-177">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="32370-177">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="32370-178">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="32370-178">Next steps</span></span>

- <span data-ttu-id="32370-179">[Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md)</span><span class="sxs-lookup"><span data-stu-id="32370-179">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
