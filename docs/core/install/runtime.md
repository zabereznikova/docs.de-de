---
title: Installieren von .NET Core-Runtime unter Windows, Linux und macOS (.NET Core)
description: Erfahren Sie. wie Sie .NET Core unter Windows, Linux und macOS installieren. Entdecken Sie die erforderlichen Abhängigkeiten, die für die Ausführung von .NET Core-Apps benötigt werden.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d36909e06bd9a3de0940c4c1b2b9eacbf9cafe7f
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740596"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="126af-104">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="126af-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="126af-105">In diesem Artikel erfahren Sie, wie Sie die .NET Core-Runtime herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="126af-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="126af-106">Die .NET Core-Runtime wird zur Ausführung der mit .NET Core erstellten Apps verwendet.</span><span class="sxs-lookup"><span data-stu-id="126af-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="126af-107">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="126af-107">Install with an installer</span></span>

<span data-ttu-id="126af-108">Windows verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="126af-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="126af-109">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="126af-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="126af-110">x86-CPUs (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="126af-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="126af-111">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="126af-111">Install with an installer</span></span>

<span data-ttu-id="126af-112">macOS verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="126af-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="126af-113">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="126af-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="126af-114">Installieren mit dem Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="126af-114">Install with a package manager</span></span>

<span data-ttu-id="126af-115">Sie können die .NET Core-Runtime mit vielen der allgemeinen Linux-Paket-Manager installieren.</span><span class="sxs-lookup"><span data-stu-id="126af-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="126af-116">Weitere Informationen finden Sie unter [Linux-Paket-Manager: Installieren von .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="126af-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="126af-117">Die Installation mit einem Paket-Manager wird nur in der x64-Architektur unterstützt.</span><span class="sxs-lookup"><span data-stu-id="126af-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="126af-118">Wenn Sie die .NET Core-Runtime mit einer anderen Architektur installieren (z. B. mit ARM), befolgen Sie die Anweisungen im Abschnitt [Herunterladen und manuelles Installieren](#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="126af-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="126af-119">Weitere Informationen zu den unterstützten Architekturen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="126af-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="126af-120">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="126af-120">Download and manually install</span></span>

<span data-ttu-id="126af-121">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="126af-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="126af-122">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="126af-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="126af-123">Mit den oben aufgeführten `export`-Befehlen werden nur die .NET Core-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="126af-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="126af-124">Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="126af-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="126af-125">Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen.</span><span class="sxs-lookup"><span data-stu-id="126af-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="126af-126">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="126af-126">For example:</span></span>
>
> - <span data-ttu-id="126af-127">**Bash-Shell**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="126af-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="126af-128">**Korn-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="126af-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="126af-129">**Z-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="126af-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="126af-130">Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="126af-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="126af-131">Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.</span><span class="sxs-lookup"><span data-stu-id="126af-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="126af-132">Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="126af-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="126af-133">Installieren mit PowerShell-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="126af-133">Install with PowerShell automation</span></span>

<span data-ttu-id="126af-134">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="126af-134">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="126af-135">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="126af-135">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="126af-136">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="126af-136">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="126af-137">Sie können eine bestimmte Version durch Angeben der `Channel`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="126af-137">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="126af-138">Schließen Sie die `Runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="126af-138">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="126af-139">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="126af-139">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="126af-140">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="126af-140">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="126af-141">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="126af-141">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="126af-142">Installieren mit der Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="126af-142">Install with bash automation</span></span>

<span data-ttu-id="126af-143">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="126af-143">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="126af-144">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="126af-144">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="126af-145">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="126af-145">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="126af-146">Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="126af-146">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="126af-147">Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="126af-147">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="126af-148">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="126af-148">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="126af-149">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="126af-149">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="126af-150">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="126af-150">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="126af-151">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="126af-151">All .NET Core downloads</span></span>

<span data-ttu-id="126af-152">Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:</span><span class="sxs-lookup"><span data-stu-id="126af-152">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="126af-153">Downloads von .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="126af-153">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="126af-154">Downloads von .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="126af-154">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="126af-155">Downloads von .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="126af-155">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="126af-156">Downloads von .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="126af-156">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="126af-157">Docker</span><span class="sxs-lookup"><span data-stu-id="126af-157">Docker</span></span>

<span data-ttu-id="126af-158">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="126af-158">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="126af-159">Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="126af-159">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="126af-160">.NET Core kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="126af-160">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="126af-161">Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="126af-161">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="126af-162">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="126af-162">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="126af-163">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="126af-163">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="126af-164">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="126af-164">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="126af-165">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="126af-165">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="126af-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="126af-166">Next steps</span></span>

- <span data-ttu-id="126af-167">[Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md)</span><span class="sxs-lookup"><span data-stu-id="126af-167">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
