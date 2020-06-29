---
title: Installieren von .NET Core-Runtime unter Windows, Linux und macOS (.NET Core)
description: Erfahren Sie. wie Sie .NET Core unter Windows, Linux und macOS installieren. Entdecken Sie die erforderlichen Abhängigkeiten, die für die Ausführung von .NET Core-Apps benötigt werden.
author: adegeo
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 6a0390ff1db900815628e4c7eb69e7a6c5f148a8
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324591"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="0ad06-104">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="0ad06-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="0ad06-105">In diesem Artikel erfahren Sie, wie Sie die .NET Core-Runtime herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="0ad06-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="0ad06-106">Die .NET Core-Runtime wird zur Ausführung der mit .NET Core erstellten Apps verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ad06-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="0ad06-107">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="0ad06-107">Install with an installer</span></span>

<span data-ttu-id="0ad06-108">Windows verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="0ad06-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="0ad06-109">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="0ad06-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="0ad06-110">x86-CPUs (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="0ad06-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="0ad06-111">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="0ad06-111">Install with an installer</span></span>

<span data-ttu-id="0ad06-112">macOS verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="0ad06-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="0ad06-113">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="0ad06-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="0ad06-114">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="0ad06-114">Download and manually install</span></span>

<span data-ttu-id="0ad06-115">Alternativ zu den macOS-Installationsprogrammen für .NET Core können Sie die Runtime herunterladen und manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="0ad06-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="0ad06-116">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu installieren und die Verwendung von .NET Core-CLI-Befehle im Terminal zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="0ad06-117">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="0ad06-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="0ad06-118">Bei diesen Befehlen wird dabei ausgegangen, dass die Runtime in die `~/Downloads/dotnet-runtime.pkg`-Datei heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0ad06-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="0ad06-119">Installation unter Linux</span><span class="sxs-lookup"><span data-stu-id="0ad06-119">Install on Linux</span></span>

<span data-ttu-id="0ad06-120">Dieser Artikel wird bald entfernt.</span><span class="sxs-lookup"><span data-stu-id="0ad06-120">This article will be removed soon.</span></span> <span data-ttu-id="0ad06-121">Er wird derzeit durch [Installieren von .NET Core unter Linux](linux.md) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="0ad06-121">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="0ad06-122">Installieren mit PowerShell-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="0ad06-122">Install with PowerShell automation</span></span>

<span data-ttu-id="0ad06-123">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ad06-123">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="0ad06-124">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-124">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="0ad06-125">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="0ad06-125">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="0ad06-126">Sie können eine bestimmte Version durch Angeben der `Channel`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-126">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="0ad06-127">Schließen Sie die `Runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0ad06-127">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="0ad06-128">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="0ad06-128">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="0ad06-129">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="0ad06-129">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="0ad06-130">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="0ad06-130">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="0ad06-131">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="0ad06-131">Download and manually install</span></span>

<span data-ttu-id="0ad06-132">[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-132">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="0ad06-133">Erstellen Sie dann ein Installationsverzeichnis wie z. B. `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="0ad06-133">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="0ad06-134">Extrahieren Sie schließlich die heruntergeladene ZIP-Datei in dieses Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0ad06-134">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="0ad06-135">Standardmäßig nutzen die Befehle und Anwendungen der .NET Core CLI auf diese Weise installiertes .NET Core nicht. Sie müssen sich explizit dafür entscheiden, es zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-135">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="0ad06-136">Ändern Sie hierzu die Umgebungsvariablen, mit denen eine Anwendung gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="0ad06-136">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="0ad06-137">Bei diesem Ansatz können Sie mehrere Versionen in separaten Speicherorten installieren und dann explizit auswählen, welcher Installationsspeicherort von einer Anwendung verwendet werden soll, indem die Anwendung mit Umgebungsvariablen ausgeführt wird, die auf diesen Speicherort zeigen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-137">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="0ad06-138">Selbst wenn diese Umgebungsvariablen festgelegt sind, berücksichtigt .NET Core bei der Auswahl des besten Frameworks für die Ausführung der Anwendung nach wie vor den standardmäßigen globalen Installationsspeicherort.</span><span class="sxs-lookup"><span data-stu-id="0ad06-138">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="0ad06-139">Der Standardwert ist normalerweise `C:\Program Files\dotnet`, den die Installationsprogramme verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ad06-139">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="0ad06-140">Sie können die Runtime anweisen, nur den benutzerdefinierten Installationsspeicherort zu verwenden, indem Sie diese Umgebungsvariable festlegen:</span><span class="sxs-lookup"><span data-stu-id="0ad06-140">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="0ad06-141">Installieren mit Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="0ad06-141">Install with bash automation</span></span>

<span data-ttu-id="0ad06-142">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ad06-142">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="0ad06-143">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-143">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="0ad06-144">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="0ad06-144">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="0ad06-145">Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-145">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="0ad06-146">Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0ad06-146">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="0ad06-147">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="0ad06-147">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="0ad06-148">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="0ad06-148">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="0ad06-149">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="0ad06-149">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="0ad06-150">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="0ad06-150">All .NET Core downloads</span></span>

<span data-ttu-id="0ad06-151">Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:</span><span class="sxs-lookup"><span data-stu-id="0ad06-151">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="0ad06-152">Downloads von .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="0ad06-152">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="0ad06-153">Downloads von .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0ad06-153">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="0ad06-154">Docker</span><span class="sxs-lookup"><span data-stu-id="0ad06-154">Docker</span></span>

<span data-ttu-id="0ad06-155">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="0ad06-155">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="0ad06-156">Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="0ad06-156">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="0ad06-157">.NET Core kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0ad06-157">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="0ad06-158">Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0ad06-158">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="0ad06-159">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0ad06-159">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="0ad06-160">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="0ad06-160">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="0ad06-161">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0ad06-161">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="0ad06-162">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="0ad06-162">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ad06-163">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0ad06-163">Next steps</span></span>

- <span data-ttu-id="0ad06-164">[Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md)</span><span class="sxs-lookup"><span data-stu-id="0ad06-164">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
