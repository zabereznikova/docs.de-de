---
title: "Voraussetzungen für .NET Core unter Linux"
description: "Unterstützte Versionen von Linux-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf Linux-Computern zu entwickeln, bereitzustellen und auszuführen."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS
author: jralexander
ms.author: johalex
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 7bbb8405f39a52d2798fd1dbc78f3116cb3bedbb
ms.openlocfilehash: 9864ffa31caa007cb649a9e6e8913863d9cb2c35
ms.contentlocale: de-de
ms.lasthandoff: 09/05/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="6fa06-104">Voraussetzungen für .NET Core unter Linux</span><span class="sxs-lookup"><span data-stu-id="6fa06-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="6fa06-105">Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Linux.</span><span class="sxs-lookup"><span data-stu-id="6fa06-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="6fa06-106">Die unterstützten Linux-Verteilungen und -Versionen und die daraus folgenden Abhängigkeiten gelten für die beiden Möglichkeiten zum Entwickeln von .NET Core-Apps unter Linux:</span><span class="sxs-lookup"><span data-stu-id="6fa06-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="6fa06-107">Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="6fa06-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="6fa06-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6fa06-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="6fa06-109">Unterstützte Linux-Versionen</span><span class="sxs-lookup"><span data-stu-id="6fa06-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6fa06-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6fa06-111">.NET Core 2.0 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="6fa06-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="6fa06-112">Es gibt einen einzelnen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Distributionen.</span><span class="sxs-lookup"><span data-stu-id="6fa06-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="6fa06-113">.NET Core 2.x wird unter den folgenden Linux x64-Distributionen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6fa06-113">NET Core 2.x is supported on the following Linux x64 distributions/versions:</span></span>

 * <span data-ttu-id="6fa06-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="6fa06-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="6fa06-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="6fa06-115">CentOS 7</span></span>
 * <span data-ttu-id="6fa06-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="6fa06-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="6fa06-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="6fa06-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="6fa06-118">Debian 8.7 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="6fa06-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="6fa06-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="6fa06-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="6fa06-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="6fa06-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="6fa06-121">openSUSE 42.2 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="6fa06-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="6fa06-122">SUSE Enterprise Linux (SLES) 12 SP2 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="6fa06-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="6fa06-123">Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="6fa06-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6fa06-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6fa06-125">.NET Core 1.x wird unter den folgenden Linux x64-Distributionen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6fa06-125">.NET Core 1.x is supported on the following Linux x64 distributions/versions:</span></span>

* <span data-ttu-id="6fa06-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="6fa06-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="6fa06-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="6fa06-127">CentOS 7</span></span>
* <span data-ttu-id="6fa06-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="6fa06-128">Oracle Linux 7</span></span>
* <span data-ttu-id="6fa06-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="6fa06-129">Fedora 24</span></span>
* <span data-ttu-id="6fa06-130">Debian 8.2 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="6fa06-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="6fa06-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="6fa06-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="6fa06-132">Ubuntu 16.10 wird vom neuesten Patchrelease von .NET Core 1.1 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6fa06-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="6fa06-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="6fa06-133">Linux Mint 17</span></span>
* <span data-ttu-id="6fa06-134">openSUSE 42.1 oder höhere Versionen (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="6fa06-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="6fa06-135">Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="6fa06-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="6fa06-136">Abhängigkeiten der Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="6fa06-136">Linux distribution dependencies</span></span>

### <a name="ubuntu"></a><span data-ttu-id="6fa06-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6fa06-137">Ubuntu</span></span>

<span data-ttu-id="6fa06-138">Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6fa06-138">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="6fa06-139">libunwind8</span><span class="sxs-lookup"><span data-stu-id="6fa06-139">libunwind8</span></span>
* <span data-ttu-id="6fa06-140">libunwind8-dev</span><span class="sxs-lookup"><span data-stu-id="6fa06-140">libunwind8-dev</span></span>
* <span data-ttu-id="6fa06-141">gettext</span><span class="sxs-lookup"><span data-stu-id="6fa06-141">gettext</span></span>
* <span data-ttu-id="6fa06-142">libicu-dev</span><span class="sxs-lookup"><span data-stu-id="6fa06-142">libicu-dev</span></span>
* <span data-ttu-id="6fa06-143">liblttng-ust-dev</span><span class="sxs-lookup"><span data-stu-id="6fa06-143">liblttng-ust-dev</span></span>
* <span data-ttu-id="6fa06-144">libcurl4-openssl-dev</span><span class="sxs-lookup"><span data-stu-id="6fa06-144">libcurl4-openssl-dev</span></span>
* <span data-ttu-id="6fa06-145">libssl-dev</span><span class="sxs-lookup"><span data-stu-id="6fa06-145">libssl-dev</span></span>
* <span data-ttu-id="6fa06-146">uuid-dev</span><span class="sxs-lookup"><span data-stu-id="6fa06-146">uuid-dev</span></span>
* <span data-ttu-id="6fa06-147">unzip</span><span class="sxs-lookup"><span data-stu-id="6fa06-147">unzip</span></span>

### <a name="centos"></a><span data-ttu-id="6fa06-148">CentOS</span><span class="sxs-lookup"><span data-stu-id="6fa06-148">CentOS</span></span>

<span data-ttu-id="6fa06-149">Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6fa06-149">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="6fa06-150">deltarpm</span><span class="sxs-lookup"><span data-stu-id="6fa06-150">deltarpm</span></span>
* <span data-ttu-id="6fa06-151">epel-release</span><span class="sxs-lookup"><span data-stu-id="6fa06-151">epel-release</span></span>
* <span data-ttu-id="6fa06-152">unzip</span><span class="sxs-lookup"><span data-stu-id="6fa06-152">unzip</span></span>
* <span data-ttu-id="6fa06-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="6fa06-153">libunwind</span></span>
* <span data-ttu-id="6fa06-154">gettext</span><span class="sxs-lookup"><span data-stu-id="6fa06-154">gettext</span></span>
* <span data-ttu-id="6fa06-155">libcurl-devel</span><span class="sxs-lookup"><span data-stu-id="6fa06-155">libcurl-devel</span></span>
* <span data-ttu-id="6fa06-156">openssl-devel</span><span class="sxs-lookup"><span data-stu-id="6fa06-156">openssl-devel</span></span>
* <span data-ttu-id="6fa06-157">zlib</span><span class="sxs-lookup"><span data-stu-id="6fa06-157">zlib</span></span>
* <span data-ttu-id="6fa06-158">libicu-devel</span><span class="sxs-lookup"><span data-stu-id="6fa06-158">libicu-devel</span></span>

<span data-ttu-id="6fa06-159">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Self contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Eigenständige Linux-Anwendungen).</span><span class="sxs-lookup"><span data-stu-id="6fa06-159">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="6fa06-160">Installieren der erforderlichen Abhängigkeiten für .NET Core mit nativen Installationsprogrammen</span><span class="sxs-lookup"><span data-stu-id="6fa06-160">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="6fa06-161">Native Installationsprogramme für .NET Core sind für unterstützte Linux-Distributionen und -Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6fa06-161">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="6fa06-162">Für die nativen Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Server.</span><span class="sxs-lookup"><span data-stu-id="6fa06-162">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="6fa06-163">Das Verwenden eines nativen Installationsprogramms hat den Vorteil, dass alle nativen Abhängigkeiten von .NET Core installiert werden.</span><span class="sxs-lookup"><span data-stu-id="6fa06-163">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="6fa06-164">Native Installationsprogramme installieren das .NET Core SDK zudem systemweit.</span><span class="sxs-lookup"><span data-stu-id="6fa06-164">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="6fa06-165">Unter Linux gibt es zwei Auswahlmöglichkeiten für Installationspakete:</span><span class="sxs-lookup"><span data-stu-id="6fa06-165">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="6fa06-166">Das Verwenden eines feedbasierten Paket-Managers, zum Beispiel „apt-get“ für Ubuntu oder „yum“ für CentOS/RHEL.</span><span class="sxs-lookup"><span data-stu-id="6fa06-166">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="6fa06-167">Das eigenständige Verwenden der Pakete, DEB oder RPM.</span><span class="sxs-lookup"><span data-stu-id="6fa06-167">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="6fa06-168">Das Skripten von Installationen mit dem Installationsskript von .NET Core</span><span class="sxs-lookup"><span data-stu-id="6fa06-168">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="6fa06-169">Die `dotnet-install` Skripts werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6fa06-169">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="6fa06-170">Sie können die Skripts aus dem [CLI-GitHub-Repository](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="6fa06-170">You can download the scripts from the [CLI GitHub repo](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).</span></span>

<span data-ttu-id="6fa06-171">Das Bash-Skript für das Installationsprogramm wird in Automatisierungsszenarios und für Installationen ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fa06-171">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="6fa06-172">Dieses Skript liest auch PowerShell-Schalter, sodass diese mit dem Skript auf Linux/OS X-Systemen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6fa06-172">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fa06-173">Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="6fa06-173">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="6fa06-174">Installieren von .NET Core auf Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="6fa06-174">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="6fa06-175">Installieren von .NET Core auf RHEL 7:</span><span class="sxs-lookup"><span data-stu-id="6fa06-175">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="6fa06-176">Aktivieren Sie den Red Hat .NET-Kanal, der in Ihrem Abonnement für RHEL 7 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6fa06-176">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="6fa06-177">Verwenden Sie Folgendes für den Red Hat Enterprise 7-Server:</span><span class="sxs-lookup"><span data-stu-id="6fa06-177">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="6fa06-178">Verwenden Sie Folgendes für die Red Hat Enterprise 7-Arbeitsstation:</span><span class="sxs-lookup"><span data-stu-id="6fa06-178">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="6fa06-179">Verwenden Sie Folgendes für den Red Hat Enterprise 7-HPC-Berechnungsknoten:</span><span class="sxs-lookup"><span data-stu-id="6fa06-179">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="6fa06-180">Installieren Sie das SCL-Tool.</span><span class="sxs-lookup"><span data-stu-id="6fa06-180">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="6fa06-181">Installieren Sie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6fa06-181">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6fa06-182">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-182">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6fa06-183">Installieren des .NET Core 2.0 SDKs und der Runtime:</span><span class="sxs-lookup"><span data-stu-id="6fa06-183">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="6fa06-184">Aktivieren des .NET Core 2.0 SDKs und der Runtime für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="6fa06-184">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6fa06-185">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-185">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6fa06-186">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="6fa06-186">**.NET Core 1.1**</span></span>

<span data-ttu-id="6fa06-187">Installieren des .NET Core 1.1 SDKs und der Runtime:</span><span class="sxs-lookup"><span data-stu-id="6fa06-187">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="6fa06-188">Aktivieren der .NET Core 1.1 SDKs und der Runtime für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="6fa06-188">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="6fa06-189">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="6fa06-189">**.NET Core 1.0**</span></span>

<span data-ttu-id="6fa06-190">Installieren des .NET Core 1.0 SDKs und der Runtime:</span><span class="sxs-lookup"><span data-stu-id="6fa06-190">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="6fa06-191">Aktivieren des .NET Core 1.0 SDKs und der Runtime für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="6fa06-191">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="6fa06-192">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6fa06-192">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="6fa06-193">Weitere Informationen zur Registrierung des Kanalzugriffs von Red Hat .NET finden Sie im Abschnitt „Red Hat“ in [Kapitel 1 des Leitfadens für erste Schritte mit .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/).</span><span class="sxs-lookup"><span data-stu-id="6fa06-193">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="6fa06-194">Installieren von .NET Core für Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 und Linux Mint 17, Linux Mint 18 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="6fa06-194">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="6fa06-195">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="6fa06-195">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6fa06-196">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-196">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="6fa06-197">Registrieren Sie den Microsoft-Produktschlüssel als vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="6fa06-197">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="6fa06-198">Richten Sie die gewünschte Version des Hostpaketfeeds ein.</span><span class="sxs-lookup"><span data-stu-id="6fa06-198">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="6fa06-199">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="6fa06-199">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="6fa06-200">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="6fa06-200">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="6fa06-201">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="6fa06-201">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="6fa06-202">Installieren Sie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6fa06-202">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="6fa06-203">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6fa06-203">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6fa06-204">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-204">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="6fa06-205">Richten Sie die gewünschte Version des Hostpaketfeeds ein.</span><span class="sxs-lookup"><span data-stu-id="6fa06-205">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="6fa06-206">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="6fa06-206">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="6fa06-207">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="6fa06-207">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="6fa06-208">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="6fa06-208">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="6fa06-209">Installieren Sie .NET Core 1.x auf Ubuntu oder Linux Mint:</span><span class="sxs-lookup"><span data-stu-id="6fa06-209">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="6fa06-210">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6fa06-210">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="6fa06-211">Installieren von .NET Core für Debian 8 oder Debian 9 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="6fa06-211">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="6fa06-212">So installieren Sie .NET Core für Debian 8 oder Debian 9 (64 Bit):</span><span class="sxs-lookup"><span data-stu-id="6fa06-212">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="6fa06-213">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="6fa06-213">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="6fa06-214">Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6fa06-214">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6fa06-215">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-215">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="6fa06-216">Installieren Sie Systemkomponenten.</span><span class="sxs-lookup"><span data-stu-id="6fa06-216">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="6fa06-217">Registrieren Sie den vertrauenswürdigen Microsoft-Produktschlüssel.</span><span class="sxs-lookup"><span data-stu-id="6fa06-217">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="6fa06-218">Registrieren Sie den Microsoft-Produktfeed.</span><span class="sxs-lookup"><span data-stu-id="6fa06-218">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="6fa06-219">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="6fa06-219">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="6fa06-220">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="6fa06-220">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="6fa06-221">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="6fa06-221">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="6fa06-222">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-222">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6fa06-223">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-223">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="6fa06-224">Beschaffen Sie die erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="6fa06-224">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="6fa06-225">Laden Sie die .NET Core SDK Binärdateien (Tarball) herunter.</span><span class="sxs-lookup"><span data-stu-id="6fa06-225">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="6fa06-226">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="6fa06-226">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="6fa06-227">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-227">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="6fa06-228">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6fa06-228">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="6fa06-229">Installieren von .NET Core für Fedora 24, Fedora 25 oder Fedora 26 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="6fa06-229">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="6fa06-230">So installieren Sie .NET Core für Fedora 26, Fedora 25 (.NET Core 2.x) oder Fedora 24 (.NET Core 1.x):</span><span class="sxs-lookup"><span data-stu-id="6fa06-230">To Install .NET Core for Fedora 26, Fedora 25 (.NET Core 2.x) or Fedora 24 (.NET Core 1.x):</span></span>

1. <span data-ttu-id="6fa06-231">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="6fa06-231">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="6fa06-232">Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6fa06-232">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6fa06-233">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-233">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6fa06-234">**Fedora 26 oder Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="6fa06-234">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="6fa06-235">Registrieren Sie den Microsoft-Signaturschlüssel.</span><span class="sxs-lookup"><span data-stu-id="6fa06-235">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="6fa06-236">Fügen Sie den Dotnet-Produktfeed hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-236">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="6fa06-237">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="6fa06-237">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="6fa06-238">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-238">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6fa06-239">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-239">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6fa06-240">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="6fa06-240">**Fedora 24**</span></span>

2. <span data-ttu-id="6fa06-241">Beschaffen Sie die erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="6fa06-241">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="6fa06-242">Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.</span><span class="sxs-lookup"><span data-stu-id="6fa06-242">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="6fa06-243">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="6fa06-243">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="6fa06-244">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-244">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="6fa06-245">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6fa06-245">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="6fa06-246">Installieren von .NET Core für CentOS 7.1 (64 Bit) und Oracle Linux 7.1 (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="6fa06-246">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="6fa06-247">Installieren von .NET Core für CentOS 7.1 (64 Bit) und Oracle Linux 7.1 (64 Bit):</span><span class="sxs-lookup"><span data-stu-id="6fa06-247">To Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="6fa06-248">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="6fa06-248">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="6fa06-249">Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6fa06-249">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6fa06-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-250">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="6fa06-251">Registrieren Sie den Microsoft-Signaturschlüssel.</span><span class="sxs-lookup"><span data-stu-id="6fa06-251">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="6fa06-252">Fügen Sie den Microsoft-Produktfeed hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-252">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="6fa06-253">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="6fa06-253">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="6fa06-254">Fügen Sie dotnet Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-254">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6fa06-255">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-255">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="6fa06-256">Beschaffen Sie die erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="6fa06-256">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="6fa06-257">Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.</span><span class="sxs-lookup"><span data-stu-id="6fa06-257">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="6fa06-258">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="6fa06-258">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="6fa06-259">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-259">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="6fa06-260">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6fa06-260">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="6fa06-261">Installieren von .NET Core für SUSE Linux Enterprise Server (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="6fa06-261">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="6fa06-262">So installieren Sie .NET Core 2.x für SUSE Linux Enterprise Server (SLES) 12 SP2 (64 Bit):</span><span class="sxs-lookup"><span data-stu-id="6fa06-262">To Install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="6fa06-263">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="6fa06-263">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="6fa06-264">Fügen Sie den Dotnet-Produktfeed hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-264">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="6fa06-265">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="6fa06-265">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="6fa06-266">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-266">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="6fa06-267">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6fa06-267">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="6fa06-268">Installieren von .NET Core für openSUSE (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="6fa06-268">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="6fa06-269">So installieren Sie .NET Core 2.x für openSUSE oder .NET Core 1.x für openSUSE (64 Bit):</span><span class="sxs-lookup"><span data-stu-id="6fa06-269">To Install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="6fa06-270">Entfernen Sie alle **früheren Versionen** von .NET Core von Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="6fa06-270">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="6fa06-271">Für Linux-Systeminstallationen von „tar.gz“ ist ein benutzergesteuertes Verzeichnis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6fa06-271">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6fa06-272">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-272">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="6fa06-273">Registrieren Sie den Microsoft-Signaturschlüssel.</span><span class="sxs-lookup"><span data-stu-id="6fa06-273">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="6fa06-274">Fügen Sie den Dotnet-Produktfeed hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-274">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="6fa06-275">Installieren Sie das .NET Core-SDK.</span><span class="sxs-lookup"><span data-stu-id="6fa06-275">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="6fa06-276">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-276">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6fa06-277">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6fa06-277">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="6fa06-278">Beschaffen Sie die erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="6fa06-278">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="6fa06-279">Laden Sie die .NET Core-SDK-Binärdateien (Tarball) herunter.</span><span class="sxs-lookup"><span data-stu-id="6fa06-279">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="6fa06-280">Extrahieren Sie die .NET Core SDK Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="6fa06-280">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="6fa06-281">Fügen Sie dotnet zu Ihrem Pfad hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fa06-281">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="6fa06-282">Führen Sie den Befehl `dotnet --version` aus, um zu überprüfen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6fa06-282">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="6fa06-283">Weitere Informationen zu Problemen mit der Installation von .NET Core 2.x auf einer unterstützten Linux-Verteilung oder -Version finden Sie im Thema [2.0 Known issues (2.0 Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0) für Ihre installierte Verteilung oder Version.</span><span class="sxs-lookup"><span data-stu-id="6fa06-283">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="6fa06-284">Weitere Informationen zu Problemen mit der Installation von .NET Core 1.x auf einer unterstützten Linux-Verteilung oder -Version finden Sie in den Themen [1.0.0 Known issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) für Ihre installierte Verteilung oder Version.</span><span class="sxs-lookup"><span data-stu-id="6fa06-284">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>

