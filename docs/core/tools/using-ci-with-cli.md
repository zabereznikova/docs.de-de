---
title: "Verwenden des .NET Core SDK und der zugehörigen Tools in Continuous Integration (CI)"
description: "Hier erhalten Sie Informationen zur Verwendung des .NET Core SDK und der zugehörigen Tools auf dem Buildserver."
keywords: .NET, .NET Core, continuous integration, ci, build, automation, Travis CI, AppVeyor, Visual Studio Team Services, vsts
author: guardrex
ms.author: mairaw
ms.date: 05/18/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0d6e1e34-277c-4aaf-9880-3ebf81023857
ms.openlocfilehash: 596bc689e423082dcae0c79801e9f796b398391e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a><span data-ttu-id="eee73-104">Verwenden des .NET Core SDK und der zugehörigen Tools in Continuous Integration (CI)</span><span class="sxs-lookup"><span data-stu-id="eee73-104">Using .NET Core SDK and tools in Continuous Integration (CI)</span></span>

## <a name="overview"></a><span data-ttu-id="eee73-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="eee73-105">Overview</span></span>

<span data-ttu-id="eee73-106">In diesem Dokument wird die Verwendung des .NET Core SDK und der zugehörigen Tools auf einem Buildserver beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eee73-106">This document outlines using the .NET Core SDK and its tools on a build server.</span></span> <span data-ttu-id="eee73-107">Das .NET Core-Toolset arbeitet sowohl interaktiv – der Entwickler gibt Befehle an der Eingabeaufforderung ein – als auch automatisch, wenn ein Continuous Integration-Server (CI) ein Buildskript ausführt.</span><span class="sxs-lookup"><span data-stu-id="eee73-107">The .NET Core toolset works both interactively, where a developer types commands at a command prompt, and automatically, where a Continuous Integration (CI) server runs a build script.</span></span> <span data-ttu-id="eee73-108">Die Befehle, Optionen, Eingaben und Ausgaben sind dieselben, Sie stellen lediglich eine Methode zum Download der Tools und ein System zur Erstellung Ihrer App bereit.</span><span class="sxs-lookup"><span data-stu-id="eee73-108">The commands, options, inputs, and outputs are the same, and the only things you supply are a way to acquire the tooling and a system to build your app.</span></span> <span data-ttu-id="eee73-109">Dieses Dokument konzentriert sich auf Szenarien für den Tooldownload für CI mit Empfehlungen zum Entwerfen und Strukturieren Ihrer Buildskripts.</span><span class="sxs-lookup"><span data-stu-id="eee73-109">This document focuses on scenarios of tool acquisition for CI with recommendations on how to design and structure your build scripts.</span></span>

## <a name="installation-options-for-ci-build-servers"></a><span data-ttu-id="eee73-110">Installationsoptionen für CI-Buildserver</span><span class="sxs-lookup"><span data-stu-id="eee73-110">Installation options for CI build servers</span></span>

### <a name="using-the-native-installers"></a><span data-ttu-id="eee73-111">Verwenden der nativen Installationsprogramme</span><span class="sxs-lookup"><span data-stu-id="eee73-111">Using the native installers</span></span>

<span data-ttu-id="eee73-112">Native Installationsprogramme stehen für macOS, Linux und Windows zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eee73-112">Native installers are available for macOS, Linux, and Windows.</span></span> <span data-ttu-id="eee73-113">Für die Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Buildserver.</span><span class="sxs-lookup"><span data-stu-id="eee73-113">The installers require admin (sudo) access to the build server.</span></span> <span data-ttu-id="eee73-114">Der Vorteil der Verwendung eines nativen Installationsprogramms liegt darin, dass alle nativen Abhängigkeiten installiert werden, die zum Ausführen der Tools benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="eee73-114">The advantage of using a native installer is that it installs all of the native dependencies required for the tooling to run.</span></span> <span data-ttu-id="eee73-115">Native Installationsprogramme ermöglichen außerdem eine systemweite Installation des SDK.</span><span class="sxs-lookup"><span data-stu-id="eee73-115">Native installers also provide a system-wide installation of the SDK.</span></span>

<span data-ttu-id="eee73-116">macOS-Benutzer sollten die PKG-Installationsprogramme verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee73-116">macOS users should use the PKG installers.</span></span> <span data-ttu-id="eee73-117">Unter Linux können Sie entweder einen feedbasierten Paket-Manager, z.B. apt-get für Ubuntu oder yum für CentOS, oder die Pakete selbst (also DEB oder RPM) verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee73-117">On Linux, there's a choice of using a feed-based package manager, such as apt-get for Ubuntu or yum for CentOS, or using the packages themselves, DEB or RPM.</span></span> <span data-ttu-id="eee73-118">Verwenden Sie unter Windows den MSI-Installer.</span><span class="sxs-lookup"><span data-stu-id="eee73-118">On Windows, use the MSI installer.</span></span>

<span data-ttu-id="eee73-119">Die neuesten stabilen Binärdateien finden Sie unter [Erste Schritte mit .NET Core](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="eee73-119">The latest stable binaries are found at [Get Started with .NET Core](https://aka.ms/dotnetcoregs).</span></span> <span data-ttu-id="eee73-120">Wenn Sie die neuesten (möglicherweise instabilen) Vorabtools verwenden möchten, nutzen Sie die Links im [dotnet/cli-GitHub-Repository](https://github.com/dotnet/cli#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="eee73-120">If you wish to use the latest (and potentially unstable) pre-release tooling, use the links provided at the [dotnet/cli GitHub repository](https://github.com/dotnet/cli#installers-and-binaries).</span></span> <span data-ttu-id="eee73-121">Für Linux-Distributionen stehen `tar.gz`-Archive (auch bekannt als `tarballs`) zur Verfügung. Verwenden Sie die Installationsskripts in den Archiven, um .NET Core zu installieren.</span><span class="sxs-lookup"><span data-stu-id="eee73-121">For Linux distributions, `tar.gz` archives (also known as `tarballs`) are available; use the installation scripts within the archives to install .NET Core.</span></span>

### <a name="using-the-installer-script"></a><span data-ttu-id="eee73-122">Verwenden des Installationsprogrammskripts</span><span class="sxs-lookup"><span data-stu-id="eee73-122">Using the installer script</span></span>

<span data-ttu-id="eee73-123">Das Installationsprogrammskript ermöglicht eine Installation ohne Administratorrechte auf dem Buildserver und bietet eine einfache Automatisierung zum Download der Tools.</span><span class="sxs-lookup"><span data-stu-id="eee73-123">Using the installer script allows for non-administrative installation on your build server and easy automation for obtaining the tooling.</span></span> <span data-ttu-id="eee73-124">Das Skript kümmert sich um das Herunterladen der Tools und extrahiert diese zur Verwendung an einem Standardspeicherort bzw. dem von Ihnen angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="eee73-124">The script takes care of downloading the tooling and extracting it into a default or specified location for use.</span></span> <span data-ttu-id="eee73-125">Sie können außerdem angeben, welche Version der Tools Sie verwenden möchten und ob das gesamte SDK oder nur die freigegebene Runtime installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="eee73-125">You can also specify a version of the tooling that you wish to install and whether you want to install the entire SDK or only the shared runtime.</span></span>

<span data-ttu-id="eee73-126">Das Installationsskript ist automatisiert, sodass es zu Beginn des Buildvorgangs ausgeführt wird, um die gewünschte Version des SDK abzurufen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="eee73-126">The installer script is automated to run at the start of the build to fetch and install the desired version of the SDK.</span></span> <span data-ttu-id="eee73-127">Die *gewünschte Version* ist die Version des SDK, die zum Erstellen Ihrer Projekte benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="eee73-127">The *desired version* is whatever version of the SDK your projects require to build.</span></span> <span data-ttu-id="eee73-128">Das Skript ermöglicht es Ihnen, das SDK in einem lokalen Verzeichnis auf dem Server zu installieren, die Tools vom Installationsort auszuführen und nach der Builderstellung eine Bereinigung durchzuführen (Sie können die Bereinigung auch dem CI-Dienst überlassen).</span><span class="sxs-lookup"><span data-stu-id="eee73-128">The script allows you to install the SDK in a local directory on the server, run the tools from the installed location, and then clean up (or let the CI service clean up) after the build.</span></span> <span data-ttu-id="eee73-129">Dies ermöglicht eine Kapselung und Isolation Ihres gesamten Buildprozesses.</span><span class="sxs-lookup"><span data-stu-id="eee73-129">This provides encapsulation and isolation to your entire build process.</span></span> <span data-ttu-id="eee73-130">Die Referenz zu den Installationsskripts finden Sie im Thema [dotnet-install](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="eee73-130">The installation script reference is found in the [dotnet-install](dotnet-install-script.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="eee73-131">Bei Verwendung des Installationsskripts werden native Abhängigkeiten nicht automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="eee73-131">When using the installer script, native dependencies aren't installed automatically.</span></span> <span data-ttu-id="eee73-132">Sie müssen die nativen Abhängigkeiten installieren, wenn das Betriebssystem diese nicht umfasst.</span><span class="sxs-lookup"><span data-stu-id="eee73-132">You must install the native dependencies if the operating system doesn't have them.</span></span> <span data-ttu-id="eee73-133">Die Liste der Voraussetzungen finden Sie im Thema [.NET Core native prerequisites](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) (Systemvoraussetzungen für .NET Core).</span><span class="sxs-lookup"><span data-stu-id="eee73-133">See the list of prerequisites in the [.NET Core native prerequisites](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) topic.</span></span>

## <a name="ci-setup-examples"></a><span data-ttu-id="eee73-134">Beispiele für die CI-Einrichtung</span><span class="sxs-lookup"><span data-stu-id="eee73-134">CI setup examples</span></span>

<span data-ttu-id="eee73-135">In diesem Abschnitt wird die manuelle Einrichtung unter Verwendung eines PowerShell- oder Bash-Skripts erläutert, und es werden verschiedene SaaS-CI-Lösungen (Software-as-a-Service) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eee73-135">This section describes a manual setup using a PowerShell or bash script, along with a description of several software as a service (SaaS) CI solutions.</span></span> <span data-ttu-id="eee73-136">Die behandelten SaaS-CI-Lösungen sind [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) und [Visual Studio Team Services Build](https://www.visualstudio.com/docs/build/overview).</span><span class="sxs-lookup"><span data-stu-id="eee73-136">The SaaS CI solutions covered are [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Visual Studio Team Services Build](https://www.visualstudio.com/docs/build/overview).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="eee73-137">Manuelle Einrichtung</span><span class="sxs-lookup"><span data-stu-id="eee73-137">Manual setup</span></span>

<span data-ttu-id="eee73-138">Jeder SaaS-Dienst umfasst eigene Methoden zum Erstellen und Konfigurieren eines Buildprozesses.</span><span class="sxs-lookup"><span data-stu-id="eee73-138">Each SaaS service has its own methods for creating and configuring a build process.</span></span> <span data-ttu-id="eee73-139">Wenn Sie eine andere SaaS-Lösung als die hier aufgeführten verwenden oder eine über die integrierte Unterstützung hinausgehende Anpassung erforderlich ist, müssen Sie einige manuelle Konfigurationsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="eee73-139">If you use different SaaS solution than those listed or require customization beyond the pre-packaged support, you must perform at least some manual configuration.</span></span>

<span data-ttu-id="eee73-140">Im Allgemeinen müssen Sie bei einer manuellen Einrichtung eine Version der Tools (oder die neuesten nächtlichen Builds der Tools) herunterladen und Ihr Buildskript ausführen.</span><span class="sxs-lookup"><span data-stu-id="eee73-140">In general, a manual setup requires you to acquire a version of the tools (or the latest nightly builds of the tools) and run your build script.</span></span> <span data-ttu-id="eee73-141">Sie können ein PowerShell- oder ein Bash-Skript verwenden, um die .NET Core-Befehle zu orchestrieren, oder Sie verwenden eine Projektdatei, die den Buildprozess beschreibt.</span><span class="sxs-lookup"><span data-stu-id="eee73-141">You can use a PowerShell or bash script to orchestrate the .NET Core commands or use a project file that outlines the build process.</span></span> <span data-ttu-id="eee73-142">Diese Optionen werden im [Abschnitt zur Orchestrierung](#orchestrating-the-build) weiter ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="eee73-142">The [orchestration section](#orchestrating-the-build) provides more detail on these options.</span></span>

<span data-ttu-id="eee73-143">Nachdem Sie ein Skript zur Ausführung eines manuellen Setups eines CI-Buildservers erstellt haben, verwenden Sie es auf Ihrem Entwicklungscomputer, um lokalen Code zu Testzwecken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eee73-143">After you create a script that performs a manual CI build server setup, use it on your dev machine to build your code locally for testing purposes.</span></span> <span data-ttu-id="eee73-144">Nachdem Sie sich davon überzeugt haben, dass das Skript lokal wie erwartet funktioniert, stellen Sie es auf Ihrem CI-Buildserver bereit.</span><span class="sxs-lookup"><span data-stu-id="eee73-144">Once you confirm that the script is running well locally, deploy it to your CI build server.</span></span> <span data-ttu-id="eee73-145">Ein relativ simples PowerShell-Skript zeigt, wie Sie das .NET Core SDK herunterladen und auf einem Windows-Buildserver installieren:</span><span class="sxs-lookup"><span data-stu-id="eee73-145">A relatively simple PowerShell script demonstrates how to obtain the .NET Core SDK and install it on a Windows build server:</span></span>

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the 
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the 
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it 
#   does, it's removed. This is not strictly required, but it's a 
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the 
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the 
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the 
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

<span data-ttu-id="eee73-146">Sie stellen die Implementierung für Ihren Buildprozess am Ende des Skripts bereit.</span><span class="sxs-lookup"><span data-stu-id="eee73-146">You provide the implementation for your build process at the end of the script.</span></span> <span data-ttu-id="eee73-147">Das Skript ruft die Tools ab und führt dann Ihren Buildprozess aus.</span><span class="sxs-lookup"><span data-stu-id="eee73-147">The script acquires the tools and then executes your build process.</span></span> <span data-ttu-id="eee73-148">Für UNIX-Computer werden die im PowerShell-Skript beschriebenen Aktionen durch das folgende Bash-Skript in ähnlicher Weise ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="eee73-148">For UNIX machines, the following bash script performs the actions described in the PowerShell script in a similar manner:</span></span>

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a><span data-ttu-id="eee73-149">Travis CI</span><span class="sxs-lookup"><span data-stu-id="eee73-149">Travis CI</span></span>

<span data-ttu-id="eee73-150">[Travis CI](https://travis-ci.org/) kann so konfiguriert werden, dass das .NET Core SDK mit der Sprache `csharp` und dem Schlüssel `dotnet` installiert wird.</span><span class="sxs-lookup"><span data-stu-id="eee73-150">You can configure [Travis CI](https://travis-ci.org/) to install the .NET Core SDK using the `csharp` language and the `dotnet` key.</span></span> <span data-ttu-id="eee73-151">Weitere Informationen zum [Erstellen eines C#-, F#- oder Visual Basic-Projekts](https://docs.travis-ci.com/user/languages/csharp/) finden Sie in der offiziellen Travis CI-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="eee73-151">See the official Travis CI docs on [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) for more information.</span></span> <span data-ttu-id="eee73-152">Beachten Sie beim Zugriff auf die Travis CI-Informationen, dass der von der Community verwaltet Sprachbezeichner `language: csharp` für alle .NET-Sprachen (einschließlich F# und Mono) funktioniert.</span><span class="sxs-lookup"><span data-stu-id="eee73-152">Note as you access the Travis CI information that the community-maintained `language: csharp` language identifier works for all .NET languages, including F#, and Mono.</span></span>

<span data-ttu-id="eee73-153">Travis CI führt sowohl macOS- (OS X 10.11, OS X 10.12) als auch Linux-Aufträge (Ubuntu 14.04) in einer *Buildmatrix* aus, wobei Sie eine Kombination aus Runtime, Umgebung und Einschlüssen/Ausschlüssen zur Abdeckung der Buildkombinationen für Ihre App angeben.</span><span class="sxs-lookup"><span data-stu-id="eee73-153">Travis CI runs both macOS (OS X 10.11, OS X 10.12) and Linux (Ubuntu 14.04) jobs in a *build matrix*, where you specify a combination of runtime, environment, and exclusions/inclusions to cover your build combinations for your app.</span></span> <span data-ttu-id="eee73-154">Weitere Informationen finden Sie in der Datei [.travis.yml-Beispiel](https://github.com/dotnet/docs/blob/master/.travis.yml) und unter [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) (Anpassen des Builds) in der Travis CI-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="eee73-154">See the [.travis.yml example](https://github.com/dotnet/docs/blob/master/.travis.yml) file and [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) in the Travis CI docs for more information.</span></span> <span data-ttu-id="eee73-155">Die MSBuild-basierten Tools enthalten die Runtimes LTS (1.0.x) und Current (1.1.x) im Paket. Deshalb verfügen Sie nach der Installation des SDK über alle benötigten Buildkomponenten.</span><span class="sxs-lookup"><span data-stu-id="eee73-155">The MSBuild-based tools include the LTS (1.0.x) and Current (1.1.x) runtimes in the package; so by installing the SDK, you receive everything you need to build.</span></span>

### <a name="appveyor"></a><span data-ttu-id="eee73-156">AppVeyor</span><span class="sxs-lookup"><span data-stu-id="eee73-156">AppVeyor</span></span>

<span data-ttu-id="eee73-157">[AppVeyor](https://www.appveyor.com/) installiert das .NET Core 1.0.1 SDK mit dem Buildworkerimage `Visual Studio 2017`.</span><span class="sxs-lookup"><span data-stu-id="eee73-157">[AppVeyor](https://www.appveyor.com/) installs the .NET Core 1.0.1 SDK with the `Visual Studio 2017` build worker image.</span></span> <span data-ttu-id="eee73-158">Es stehen darüber hinaus weitere Buildimages mit anderen Versionen des .NET Core SDK zur Verfügung. Weitere Informationen hierzu finden Sie im [appveyor.yml-Beispiel](https://github.com/dotnet/docs/blob/master/appveyor.yml) und im Thema [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) (Buildworkerimages) in der AppVeyer-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="eee73-158">Other build images with different versions of the .NET Core SDK are available; see the [appveyor.yml example](https://github.com/dotnet/docs/blob/master/appveyor.yml) and the [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) topic in the AppVeyor docs for more information.</span></span>

<span data-ttu-id="eee73-159">Die .NET Core SDK-Binärdateien werden mithilfe des Installationsskripts heruntergeladen, in einem Unterverzeichnis entpackt und anschließend der Umgebungsvariable `PATH` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eee73-159">The .NET Core SDK binaries are downloaded and unzipped in a subdirectory using the install script, and then they're added to the `PATH` environment variable.</span></span> <span data-ttu-id="eee73-160">Fügen Sie eine Buildmatrix hinzu, um Integrationstests mit mehreren Versionen des .NET Core SDK auszuführen:</span><span class="sxs-lookup"><span data-stu-id="eee73-160">Add a build matrix to run integration tests with multiple versions of the .NET Core SDK:</span></span>

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="visual-studio-team-services-vsts"></a><span data-ttu-id="eee73-161">Visual Studio Team Services (VSTS)</span><span class="sxs-lookup"><span data-stu-id="eee73-161">Visual Studio Team Services (VSTS)</span></span>

<span data-ttu-id="eee73-162">Verwenden Sie einen dieser Ansätze, um Visual Studio Team Services (VSTS) zum Erstellen von .NET Core-Projekten zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="eee73-162">Configure Visual Studio Team Services (VSTS) to build .NET Core projects using one of these approaches:</span></span>

1. <span data-ttu-id="eee73-163">Führen Sie das Skript aus dem Schritt für die [manuelle Einrichtung](#manual-setup) unter Verwendung Ihrer Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="eee73-163">Run the script from the [manual setup step](#manual-setup) using your commands.</span></span>
1. <span data-ttu-id="eee73-164">Erstellen Sie einen Build aus verschiedenen integrierten VSTS-Buildtasks, die zur Verwendung der .NET Core-Tools konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="eee73-164">Create a build composed of several VSTS built-in build tasks that are configured to use .NET Core tools.</span></span>

<span data-ttu-id="eee73-165">Beide Ansätze sind gültige Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="eee73-165">Both solutions are valid.</span></span> <span data-ttu-id="eee73-166">Mithilfe eines Skripts zur manuellen Einrichtung kontrollieren Sie, welche Version der Tools abgerufen wird, weil Sie die Tools im Rahmen des Builds herunterladen.</span><span class="sxs-lookup"><span data-stu-id="eee73-166">Using a manual setup script, you control the version of the tools that you receive, since you download them as part of the build.</span></span> <span data-ttu-id="eee73-167">Der Build wird aus einem Skript ausgeführt, das Sie erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="eee73-167">The build is run from a script that you must create.</span></span> <span data-ttu-id="eee73-168">In diesem Thema wird nur die manuelle Option behandelt.</span><span class="sxs-lookup"><span data-stu-id="eee73-168">This topic only covers the manual option.</span></span> <span data-ttu-id="eee73-169">Weitere Informationen zum Erstellen eines Builds mit VSTS-Buildtasks finden Sie im VSTS-Thema [Continuous integration and deployment](https://www.visualstudio.com/docs/build/overview) (Continuous Integration und Continuous Deployment).</span><span class="sxs-lookup"><span data-stu-id="eee73-169">For more information on composing a build with VSTS build tasks, visit the VSTS [Continuous integration and deployment](https://www.visualstudio.com/docs/build/overview) topic.</span></span>

<span data-ttu-id="eee73-170">Um ein Skript für ein manuelles Setup in VSTS zu verwenden, erstellen Sie eine neue Builddefinition und geben das Skript an, das für den Buildschritt ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eee73-170">To use a manual setup script in VSTS, create a new build definition and specify the script to run for the build step.</span></span> <span data-ttu-id="eee73-171">Dies wird mithilfe der VSTS-Benutzeroberfläche erreicht:</span><span class="sxs-lookup"><span data-stu-id="eee73-171">This is accomplished using the VSTS user interface:</span></span>

1. <span data-ttu-id="eee73-172">Beginnen Sie, indem Sie eine neue Builddefinition erstellen.</span><span class="sxs-lookup"><span data-stu-id="eee73-172">Start by creating a new build definition.</span></span> <span data-ttu-id="eee73-173">Wenn der Bildschirm angezeigt wird, auf dem Sie angeben können, welche Art von Build Sie erstellen möchten, wählen Sie die Option **Leer** aus.</span><span class="sxs-lookup"><span data-stu-id="eee73-173">Once you reach the screen that provides you an option to define what kind of a build you wish to create, select the **Empty** option.</span></span>

   ![Auswahl einer leeren Builddefinition](./media/using-ci-with-cli/screen1.png)

1. <span data-ttu-id="eee73-175">Nachdem Sie das zu erstellende Repository konfiguriert haben, gelangen Sie zu den Builddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="eee73-175">After configuring the repository to build, you're directed to the build definitions.</span></span> <span data-ttu-id="eee73-176">Wählen Sie **Buildschritt hinzufügen** aus:</span><span class="sxs-lookup"><span data-stu-id="eee73-176">Select **Add build step**:</span></span>

   ![Hinzufügen eines Buildschritts](./media/using-ci-with-cli/screen2.png)

1. <span data-ttu-id="eee73-178">Als Nächstes wird der **Taskkatalog** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eee73-178">You're presented with the **Task catalog**.</span></span> <span data-ttu-id="eee73-179">Der Katalog enthält Tasks, die Sie im Build verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee73-179">The catalog contains tasks that you use in the build.</span></span> <span data-ttu-id="eee73-180">Da Sie über ein Skript verfügen, klicken Sie auf die Schaltfläche **Hinzufügen** für **PowerShell: PowerShell-Skript ausführen**.</span><span class="sxs-lookup"><span data-stu-id="eee73-180">Since you have a script, select the **Add** button for **PowerShell: Run a PowerShell script**.</span></span>

   ![Hinzufügen eines Schritts für ein PowerShell-Skript](./media/using-ci-with-cli/screen3.png)

1. <span data-ttu-id="eee73-182">Konfigurieren Sie den Buildschritt.</span><span class="sxs-lookup"><span data-stu-id="eee73-182">Configure the build step.</span></span> <span data-ttu-id="eee73-183">Fügen Sie das Skript aus dem Repository hinzu, das Sie erstellen:</span><span class="sxs-lookup"><span data-stu-id="eee73-183">Add the script from the repository that you're building:</span></span>

   ![Angeben des auszuführenden PowerShell-Skripts](./media/using-ci-with-cli/screen4.png)

## <a name="orchestrating-the-build"></a><span data-ttu-id="eee73-185">Orchestrieren des Builds</span><span class="sxs-lookup"><span data-stu-id="eee73-185">Orchestrating the build</span></span>

<span data-ttu-id="eee73-186">In diesem Dokument wird hauptsächlich beschrieben, wie Sie die .NET Core-Tools herunterladen und verschiedene CI-Dienst konfigurieren, ohne darauf einzugehen, wie Sie Ihren Code mit .NET Core orchestrieren oder *tatsächlich einen Build erstellen*.</span><span class="sxs-lookup"><span data-stu-id="eee73-186">Most of this document describes how to acquire the .NET Core tools and configure various CI services without providing information on how to orchestrate, or *actually build*, your code with .NET Core.</span></span> <span data-ttu-id="eee73-187">Die Auswahl bei der Strukturierung des Buildprozesses hängt von vielen Faktoren ab, die hier nicht allgemein abgedeckt werden können.</span><span class="sxs-lookup"><span data-stu-id="eee73-187">The choices on how to structure the build process depend on many factors that cannot be covered in a general way here.</span></span> <span data-ttu-id="eee73-188">Erkunden Sie die Ressourcen und Beispiele in der Dokumentation von [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) und [VSTS](https://www.visualstudio.com/docs/build/overview), um weitere Informationen zur Orchestrierung Ihrer Builds mit jeder Technologie zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eee73-188">Explore the resources and samples provided in the documentation sets of [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [VSTS](https://www.visualstudio.com/docs/build/overview) for more information on orchestrating your builds with each technology.</span></span>

<span data-ttu-id="eee73-189">Bei der Strukturierung des Buildprozesses für .NET Core-Code unter Verwendung der .NET Core-Tools können zwei allgemeine Ansätze verfolgt werden: die direkte Verwendung von MSBuild oder die Verwendung von .NET Core-Befehlszeilenbefehlen.</span><span class="sxs-lookup"><span data-stu-id="eee73-189">Two general approaches that you take in structuring the build process for .NET Core code using the .NET Core tools are using MSBuild directly or using the .NET Core command-line commands.</span></span> <span data-ttu-id="eee73-190">Sie sollten den verwendeten Ansatz danach auswählen, wie vertraut Sie mit dem jeweiligen Ansatz sind und welche Kompromisse Sie in Bezug auf die Komplexität eingehen möchten.</span><span class="sxs-lookup"><span data-stu-id="eee73-190">Which approach you should take is determined by your comfort level with the approaches and trade-offs in complexity.</span></span> <span data-ttu-id="eee73-191">Mit MSBuild können Sie Ihren Buildprozess in Form von Tasks und Zielen beschrieben, Sie müssen jedoch die MSBuild-Projektdateisyntax beherrschen.</span><span class="sxs-lookup"><span data-stu-id="eee73-191">MSBuild provides you the ability to express your build process as tasks and targets, but it comes with the added complexity of learning MSBuild project file syntax.</span></span> <span data-ttu-id="eee73-192">Die Verwendung von .NET Core-Befehlszeilentools ist möglicherweise einfacher, erfordert aber, dass Sie Orchestrierungslogik in einer Skriptsprache wie `bash` oder PowerShell schreiben.</span><span class="sxs-lookup"><span data-stu-id="eee73-192">Using the .NET Core command-line tools is perhaps simpler, but it requires you to write orchestration logic in a scripting language like `bash` or PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="eee73-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eee73-193">See also</span></span>

[<span data-ttu-id="eee73-194">Schritte zum Download von Ubuntu</span><span class="sxs-lookup"><span data-stu-id="eee73-194">Ubuntu acquisition steps</span></span>](https://www.microsoft.com/net/core#linuxubuntu)   
