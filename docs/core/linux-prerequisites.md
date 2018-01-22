---
title: "Voraussetzungen für .NET Core unter Linux"
description: "Unterstützte Versionen von Linux-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf Linux-Computern zu entwickeln, bereitzustellen und auszuführen."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS
author: jralexander
ms.author: johalex
ms.date: 12/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.workload: dotnetcore
ms.openlocfilehash: d3c5dde443f848831f7c0585633339c35213357b
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="7bc32-104">Voraussetzungen für .NET Core unter Linux</span><span class="sxs-lookup"><span data-stu-id="7bc32-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="7bc32-105">Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Linux.</span><span class="sxs-lookup"><span data-stu-id="7bc32-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="7bc32-106">Die unterstützten Linux-Verteilungen und -Versionen und die daraus folgenden Abhängigkeiten gelten für die beiden Möglichkeiten zum Entwickeln von .NET Core-Apps unter Linux:</span><span class="sxs-lookup"><span data-stu-id="7bc32-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="7bc32-107">Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="7bc32-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="7bc32-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7bc32-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="7bc32-109">Unterstützte Linux-Versionen</span><span class="sxs-lookup"><span data-stu-id="7bc32-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7bc32-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7bc32-111">.NET Core 2.0 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="7bc32-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="7bc32-112">Es gibt einen einzelnen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Distributionen.</span><span class="sxs-lookup"><span data-stu-id="7bc32-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="7bc32-113">.NET Core 2.x wird unter den folgenden Linux x64-Distributionen und -Versionen (`x86_64` oder `amd64`) unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7bc32-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="7bc32-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="7bc32-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="7bc32-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7bc32-115">CentOS 7</span></span>
 * <span data-ttu-id="7bc32-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="7bc32-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="7bc32-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="7bc32-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="7bc32-118">Debian 8.7 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="7bc32-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="7bc32-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="7bc32-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="7bc32-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="7bc32-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="7bc32-121">openSUSE 42.2 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="7bc32-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="7bc32-122">SUSE Enterprise Linux (SLES) 12 SP2 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="7bc32-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="7bc32-123">Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7bc32-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7bc32-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7bc32-125">.NET Core 1.x wird unter den folgenden Linux x64-Distributionen und -Versionen (`x86_64` oder `amd64`) unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7bc32-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="7bc32-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="7bc32-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="7bc32-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7bc32-127">CentOS 7</span></span>
* <span data-ttu-id="7bc32-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="7bc32-128">Oracle Linux 7</span></span>
* <span data-ttu-id="7bc32-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="7bc32-129">Fedora 24</span></span>
* <span data-ttu-id="7bc32-130">Debian 8.2 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="7bc32-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="7bc32-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="7bc32-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="7bc32-132">Ubuntu 16.10 wird vom neuesten Patchrelease von .NET Core 1.1 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7bc32-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="7bc32-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="7bc32-133">Linux Mint 17</span></span>
* <span data-ttu-id="7bc32-134">openSUSE 42.1 oder höhere Versionen (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="7bc32-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="7bc32-135">Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7bc32-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="7bc32-136">Abhängigkeiten der Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="7bc32-136">Linux distribution dependencies</span></span>

<span data-ttu-id="7bc32-137">Bei folgenden Paketen handelt es sich um Beispiele.</span><span class="sxs-lookup"><span data-stu-id="7bc32-137">The following are intended to be examples.</span></span> <span data-ttu-id="7bc32-138">Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7bc32-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="7bc32-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7bc32-139">Ubuntu</span></span>

<span data-ttu-id="7bc32-140">Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7bc32-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="7bc32-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="7bc32-141">libunwind8</span></span>
* <span data-ttu-id="7bc32-142">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="7bc32-142">liblttng-ust0</span></span>
* <span data-ttu-id="7bc32-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="7bc32-143">libcurl3</span></span>
* <span data-ttu-id="7bc32-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="7bc32-144">libssl1.0.0</span></span>
* <span data-ttu-id="7bc32-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="7bc32-145">libuuid1</span></span>
* <span data-ttu-id="7bc32-146">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="7bc32-146">libkrb5-3</span></span>
* <span data-ttu-id="7bc32-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="7bc32-147">zlib1g</span></span>
* <span data-ttu-id="7bc32-148">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="7bc32-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="7bc32-149">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="7bc32-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="7bc32-150">libicu57 (für 17.X)</span><span class="sxs-lookup"><span data-stu-id="7bc32-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="7bc32-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="7bc32-151">CentOS</span></span>

<span data-ttu-id="7bc32-152">Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7bc32-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="7bc32-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="7bc32-153">libunwind</span></span>
* <span data-ttu-id="7bc32-154">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="7bc32-154">lttng-ust</span></span>
* <span data-ttu-id="7bc32-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="7bc32-155">libcurl</span></span>
* <span data-ttu-id="7bc32-156">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="7bc32-156">openssl-libs</span></span>
* <span data-ttu-id="7bc32-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="7bc32-157">libuuid</span></span>
* <span data-ttu-id="7bc32-158">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="7bc32-158">krb5-libs</span></span>
* <span data-ttu-id="7bc32-159">libicu</span><span class="sxs-lookup"><span data-stu-id="7bc32-159">libicu</span></span>
* <span data-ttu-id="7bc32-160">zlib</span><span class="sxs-lookup"><span data-stu-id="7bc32-160">zlib</span></span>

<span data-ttu-id="7bc32-161">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Self contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Eigenständige Linux-Anwendungen).</span><span class="sxs-lookup"><span data-stu-id="7bc32-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="7bc32-162">Installieren der erforderlichen Abhängigkeiten für .NET Core mit nativen Installationsprogrammen</span><span class="sxs-lookup"><span data-stu-id="7bc32-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="7bc32-163">Native Installationsprogramme für .NET Core sind für unterstützte Linux-Distributionen und -Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7bc32-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="7bc32-164">Für die nativen Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Server.</span><span class="sxs-lookup"><span data-stu-id="7bc32-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="7bc32-165">Das Verwenden eines nativen Installationsprogramms hat den Vorteil, dass alle nativen Abhängigkeiten von .NET Core installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7bc32-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="7bc32-166">Native Installationsprogramme installieren das .NET Core SDK zudem systemweit.</span><span class="sxs-lookup"><span data-stu-id="7bc32-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="7bc32-167">Unter Linux gibt es zwei Auswahlmöglichkeiten für Installationspakete:</span><span class="sxs-lookup"><span data-stu-id="7bc32-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="7bc32-168">Das Verwenden eines feedbasierten Paket-Managers, zum Beispiel „apt-get“ für Ubuntu oder „yum“ für CentOS/RHEL.</span><span class="sxs-lookup"><span data-stu-id="7bc32-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="7bc32-169">Das eigenständige Verwenden der Pakete, DEB oder RPM.</span><span class="sxs-lookup"><span data-stu-id="7bc32-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="7bc32-170">Das Skripten von Installationen mit dem Installationsskript von .NET Core</span><span class="sxs-lookup"><span data-stu-id="7bc32-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="7bc32-171">Die `dotnet-install` Skripts werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7bc32-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="7bc32-172">Sie können das Skript unter https://dot.net/v1/dotnet-install.sh herunterladen.</span><span class="sxs-lookup"><span data-stu-id="7bc32-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="7bc32-173">Das Bash-Skript für das Installationsprogramm wird in Automatisierungsszenarios und für Installationen ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="7bc32-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="7bc32-174">Dieses Skript liest auch PowerShell-Schalter, sodass diese mit dem Skript auf Linux/OS X-Systemen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7bc32-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bc32-175">Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="7bc32-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7bc32-176">Installieren von .NET Core auf Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="7bc32-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="7bc32-177">Installieren von .NET Core auf RHEL 7:</span><span class="sxs-lookup"><span data-stu-id="7bc32-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="7bc32-178">Aktivieren Sie den Red Hat .NET-Kanal, der in Ihrem Abonnement für RHEL 7 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7bc32-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="7bc32-179">Verwenden Sie Folgendes für den Red Hat Enterprise 7-Server:</span><span class="sxs-lookup"><span data-stu-id="7bc32-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="7bc32-180">Verwenden Sie Folgendes für die Red Hat Enterprise 7-Arbeitsstation:</span><span class="sxs-lookup"><span data-stu-id="7bc32-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="7bc32-181">Verwenden Sie Folgendes für den Red Hat Enterprise 7-HPC-Berechnungsknoten:</span><span class="sxs-lookup"><span data-stu-id="7bc32-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="7bc32-182">Installieren Sie das SCL-Tool.</span><span class="sxs-lookup"><span data-stu-id="7bc32-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="7bc32-183">Installieren Sie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7bc32-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7bc32-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7bc32-185">Installieren des .NET Core 2.0 SDKs und der Runtime:</span><span class="sxs-lookup"><span data-stu-id="7bc32-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="7bc32-186">Aktivieren des .NET Core 2.0 SDKs und der Runtime für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="7bc32-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7bc32-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7bc32-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="7bc32-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="7bc32-189">Installieren des .NET Core 1.1 SDKs und der Runtime:</span><span class="sxs-lookup"><span data-stu-id="7bc32-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="7bc32-190">Aktivieren der .NET Core 1.1 SDKs und der Runtime für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="7bc32-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="7bc32-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="7bc32-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="7bc32-192">Installieren des .NET Core 1.0 SDKs und der Runtime:</span><span class="sxs-lookup"><span data-stu-id="7bc32-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="7bc32-193">Aktivieren des .NET Core 1.0 SDKs und der Runtime für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="7bc32-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="7bc32-194">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="7bc32-195">Weitere Informationen zur Registrierung des Kanalzugriffs von Red Hat .NET finden Sie im Abschnitt „Red Hat“ in [Kapitel 1 des Leitfadens für erste Schritte mit .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/).</span><span class="sxs-lookup"><span data-stu-id="7bc32-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="7bc32-196">Installieren von .NET Core für Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 und Linux Mint 17, Linux Mint 18 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="7bc32-197">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="7bc32-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7bc32-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="7bc32-199">Registrieren Sie den Microsoft-Produktschlüssel als vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="7bc32-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="7bc32-200">Richten Sie die gewünschte Version des Hostpaketfeeds ein.</span><span class="sxs-lookup"><span data-stu-id="7bc32-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="7bc32-201">**Ubuntu 17.10**</span><span class="sxs-lookup"><span data-stu-id="7bc32-201">**Ubuntu 17.10**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-artful-prod artful main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```
   <span data-ttu-id="7bc32-202">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="7bc32-202">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="7bc32-203">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="7bc32-203">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="7bc32-204">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="7bc32-204">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="7bc32-205">Installieren Sie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7bc32-205">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.1.3
   ```

4. <span data-ttu-id="7bc32-206">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-206">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7bc32-207">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-207">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="7bc32-208">Richten Sie die gewünschte Version des Hostpaketfeeds ein.</span><span class="sxs-lookup"><span data-stu-id="7bc32-208">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="7bc32-209">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="7bc32-209">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="7bc32-210">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="7bc32-210">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="7bc32-211">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="7bc32-211">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="7bc32-212">Installieren Sie .NET Core 1.x auf Ubuntu oder Linux Mint:</span><span class="sxs-lookup"><span data-stu-id="7bc32-212">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="7bc32-213">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-213">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="7bc32-214">Installieren von .NET Core für Debian 8 oder Debian 9 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-214">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="7bc32-215">So installieren Sie .NET Core für Debian 8 oder Debian 9 (64 Bit):</span><span class="sxs-lookup"><span data-stu-id="7bc32-215">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="7bc32-216">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="7bc32-216">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="7bc32-217">Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bc32-217">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7bc32-218">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-218">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="7bc32-219">Installieren Sie Systemkomponenten.</span><span class="sxs-lookup"><span data-stu-id="7bc32-219">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="7bc32-220">Registrieren Sie den vertrauenswürdigen Microsoft-Produktschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7bc32-220">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="7bc32-221">Registrieren Sie den Microsoft-Produktfeed.</span><span class="sxs-lookup"><span data-stu-id="7bc32-221">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="7bc32-222">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="7bc32-222">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="7bc32-223">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="7bc32-223">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="7bc32-224">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="7bc32-224">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="7bc32-225">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-225">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="7bc32-226">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-226">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7bc32-227">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-227">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="7bc32-228">Beschaffen Sie die erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="7bc32-228">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="7bc32-229">Laden Sie die .NET Core SDK Binärdateien (Tarball) herunter.</span><span class="sxs-lookup"><span data-stu-id="7bc32-229">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="7bc32-230">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="7bc32-230">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="7bc32-231">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-231">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="7bc32-232">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-232">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="7bc32-233">Installieren von .NET Core für Fedora 24, Fedora 25 oder Fedora 26 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-233">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="7bc32-234">So installieren Sie .NET Core 2.x unter Fedora 26 oder Fedora 25, oder .NET Core 1.x unter Fedora 24</span><span class="sxs-lookup"><span data-stu-id="7bc32-234">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="7bc32-235">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="7bc32-235">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="7bc32-236">Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bc32-236">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7bc32-237">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-237">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7bc32-238">**Fedora 26 oder Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="7bc32-238">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="7bc32-239">Registrieren Sie den Microsoft-Signaturschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7bc32-239">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="7bc32-240">Fügen Sie den Dotnet-Produktfeed hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-240">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="7bc32-241">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="7bc32-241">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="7bc32-242">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-242">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7bc32-243">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-243">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7bc32-244">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="7bc32-244">**Fedora 24**</span></span>

2. <span data-ttu-id="7bc32-245">Beschaffen Sie die erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="7bc32-245">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="7bc32-246">Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.</span><span class="sxs-lookup"><span data-stu-id="7bc32-246">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="7bc32-247">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="7bc32-247">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="7bc32-248">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-248">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="7bc32-249">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-249">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="7bc32-250">Installieren von .NET Core für CentOS 7.1 (64 Bit) und Oracle Linux 7.1 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-250">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="7bc32-251">So installieren Sie .NET Core für CentOS 7.1 (64 Bit) und Oracle Linux 7.1 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-251">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="7bc32-252">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="7bc32-252">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="7bc32-253">Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bc32-253">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7bc32-254">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-254">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="7bc32-255">Registrieren Sie den Microsoft-Signaturschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7bc32-255">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="7bc32-256">Fügen Sie den Microsoft-Produktfeed hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-256">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="7bc32-257">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="7bc32-257">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="7bc32-258">Fügen Sie dotnet Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-258">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7bc32-259">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-259">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="7bc32-260">Beschaffen Sie die erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="7bc32-260">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="7bc32-261">Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.</span><span class="sxs-lookup"><span data-stu-id="7bc32-261">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="7bc32-262">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="7bc32-262">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="7bc32-263">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-263">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="7bc32-264">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-264">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="7bc32-265">Installieren von .NET Core für SUSE Linux Enterprise Server (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-265">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="7bc32-266">So installieren Sie .NET Core 2.x für SUSE Linux Enterprise Server (SLES) 12 SP2 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-266">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="7bc32-267">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="7bc32-267">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="7bc32-268">Fügen Sie den Dotnet-Produktfeed hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-268">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="7bc32-269">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="7bc32-269">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="7bc32-270">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-270">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="7bc32-271">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-271">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="7bc32-272">Installieren von .NET Core für openSUSE (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-272">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="7bc32-273">So installieren Sie .NET Core 2.x für openSUSE oder .NET Core 1.x für openSUSE (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="7bc32-273">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="7bc32-274">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="7bc32-274">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="7bc32-275">Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bc32-275">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7bc32-276">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-276">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="7bc32-277">Registrieren Sie den Microsoft-Signaturschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7bc32-277">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="7bc32-278">Fügen Sie den Dotnet-Produktfeed hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-278">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="7bc32-279">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="7bc32-279">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="7bc32-280">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-280">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7bc32-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7bc32-281">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="7bc32-282">Beschaffen Sie die erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="7bc32-282">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="7bc32-283">Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.</span><span class="sxs-lookup"><span data-stu-id="7bc32-283">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="7bc32-284">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="7bc32-284">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="7bc32-285">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc32-285">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="7bc32-286">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7bc32-286">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="7bc32-287">Weitere Informationen zu Problemen mit der Installation von .NET Core 2.x auf einer unterstützten Linux-Verteilung oder -Version finden Sie im Thema [2.0 Known issues (2.0 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0) für Ihre installierte Verteilung oder Version.</span><span class="sxs-lookup"><span data-stu-id="7bc32-287">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="7bc32-288">Weitere Informationen zu Problemen mit der Installation von .NET Core 1.x auf einer unterstützten Linux-Verteilung oder -Version finden Sie in den Themen [1.0.0 Known issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) für Ihre installierte Verteilung oder Version.</span><span class="sxs-lookup"><span data-stu-id="7bc32-288">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
