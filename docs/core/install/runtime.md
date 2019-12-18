---
title: Installieren von .NET Core-Runtime unter Windows, Linux und macOS (.NET Core)
description: Erfahren Sie. wie Sie .NET Core unter Windows, Linux und macOS installieren. Entdecken Sie die erforderlichen Abhängigkeiten, die für die Ausführung von .NET Core-Apps benötigt werden.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998888"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="c4e5b-104">Installieren der .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="c4e5b-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="c4e5b-105">In diesem Artikel erfahren Sie, wie Sie die .NET Core-Runtime herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="c4e5b-106">Die .NET Core-Runtime wird zur Ausführung der mit .NET Core erstellten Apps verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="c4e5b-107">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="c4e5b-107">Install with an installer</span></span>

<span data-ttu-id="c4e5b-108">Windows verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="c4e5b-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="c4e5b-109">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="c4e5b-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="c4e5b-110">x86-CPUs (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="c4e5b-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="c4e5b-111">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="c4e5b-111">Install with an installer</span></span>

<span data-ttu-id="c4e5b-112">macOS verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="c4e5b-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="c4e5b-113">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="c4e5b-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="c4e5b-114">Installieren mit dem Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="c4e5b-114">Install with a package manager</span></span>

<span data-ttu-id="c4e5b-115">Sie können die .NET Core-Runtime mit vielen der allgemeinen Linux-Paket-Manager installieren.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="c4e5b-116">Weitere Informationen finden Sie unter [Linux-Paket-Manager: Installieren von .NET Core](linux-package-manager-rhel7.md).</span><span class="sxs-lookup"><span data-stu-id="c4e5b-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="c4e5b-117">Installieren mit PowerShell-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="c4e5b-117">Install with PowerShell automation</span></span>

<span data-ttu-id="c4e5b-118">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-118">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="c4e5b-119">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-119">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c4e5b-120">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-120">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="c4e5b-121">Sie können eine bestimmte Version durch Angeben der `Channel`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-121">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="c4e5b-122">Schließen Sie die `Runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-122">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="c4e5b-123">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-123">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="c4e5b-124">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-124">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="c4e5b-125">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-125">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="c4e5b-126">Installieren mit der Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="c4e5b-126">Install with bash automation</span></span>

<span data-ttu-id="c4e5b-127">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-127">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="c4e5b-128">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-128">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c4e5b-129">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-129">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="c4e5b-130">Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-130">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="c4e5b-131">Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-131">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="c4e5b-132">Andernfalls installiert das Skript das [SDK](sdk.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-132">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="c4e5b-133">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-133">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="c4e5b-134">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-134">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="c4e5b-135">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="c4e5b-135">All .NET Core downloads</span></span>

<span data-ttu-id="c4e5b-136">Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:</span><span class="sxs-lookup"><span data-stu-id="c4e5b-136">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="c4e5b-137">Downloads von .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c4e5b-137">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="c4e5b-138">Downloads von .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c4e5b-138">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="c4e5b-139">Downloads von .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c4e5b-139">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="c4e5b-140">Downloads von .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c4e5b-140">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="c4e5b-141">Docker</span><span class="sxs-lookup"><span data-stu-id="c4e5b-141">Docker</span></span>

<span data-ttu-id="c4e5b-142">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-142">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="c4e5b-143">Container auf demselben Computer teilen nur den Kernel und verwenden die in Ihrer Anwendung angegebenen Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-143">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="c4e5b-144">.NET Core kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-144">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="c4e5b-145">Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-145">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="c4e5b-146">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-146">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="c4e5b-147">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-147">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="c4e5b-148">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c4e5b-148">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="c4e5b-149">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung zu .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="c4e5b-149">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4e5b-150">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c4e5b-150">Next steps</span></span>

- <span data-ttu-id="c4e5b-151">[Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md)</span><span class="sxs-lookup"><span data-stu-id="c4e5b-151">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
