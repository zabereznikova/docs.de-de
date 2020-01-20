---
title: Continuous Integration (CI) mit dem .NET Core SDK und Tools
description: Erfahren Sie, wie Sie das .NET Core SDK und die zugehörigen Tools auf dem Buildserver mit Continuous Integration verwenden.
author: mairaw
ms.date: 05/18/2017
ms.openlocfilehash: 65d062fce2f364932ebf8091bd9c6cdef561b633
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714121"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a>Verwenden des .NET Core SDK und der zugehörigen Tools in Continuous Integration (CI)

In diesem Dokument wird die Verwendung des .NET Core SDK und der zugehörigen Tools auf einem Buildserver beschrieben. Das .NET Core-Toolset arbeitet sowohl interaktiv – der Entwickler gibt Befehle an der Eingabeaufforderung ein – als auch automatisch, wenn ein Continuous Integration-Server (CI) ein Buildskript ausführt. Die Befehle, Optionen, Eingaben und Ausgaben sind dieselben, Sie stellen lediglich eine Methode zum Download der Tools und ein System zur Erstellung Ihrer App bereit. Dieses Dokument konzentriert sich auf Szenarien für den Tooldownload für CI mit Empfehlungen zum Entwerfen und Strukturieren Ihrer Buildskripts.

## <a name="installation-options-for-ci-build-servers"></a>Installationsoptionen für CI-Buildserver

### <a name="using-the-native-installers"></a>Verwenden der nativen Installationsprogramme

Native Installationsprogramme stehen für macOS, Linux und Windows zur Verfügung. Für die Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Buildserver. Der Vorteil der Verwendung eines nativen Installationsprogramms liegt darin, dass alle nativen Abhängigkeiten installiert werden, die zum Ausführen der Tools benötigt werden. Native Installationsprogramme ermöglichen außerdem eine systemweite Installation des SDK.

macOS-Benutzer sollten die PKG-Installationsprogramme verwenden. Unter Linux können Sie entweder einen feedbasierten Paket-Manager, z.B. apt-get für Ubuntu oder yum für CentOS, oder die Pakete selbst (also DEB oder RPM) verwenden. Verwenden Sie unter Windows den MSI-Installer.

Die neuesten stabilen Binärdateien finden Sie unter [.NET Downloads](https://dotnet.microsoft.com/download). Wenn Sie die neuesten (möglicherweise instabilen) Vorabtools verwenden möchten, nutzen Sie die Links im [dotnet/core-sdk-GitHub-Repository](https://github.com/dotnet/core-sdk#installers-and-binaries). Für Linux-Distributionen stehen `tar.gz`-Archive (auch bekannt als `tarballs`) zur Verfügung. Verwenden Sie die Installationsskripts in den Archiven, um .NET Core zu installieren.

### <a name="using-the-installer-script"></a>Verwenden des Installationsprogrammskripts

Das Installationsprogrammskript ermöglicht eine Installation ohne Administratorrechte auf dem Buildserver und bietet eine einfache Automatisierung zum Download der Tools. Das Skript kümmert sich um das Herunterladen der Tools und extrahiert diese zur Verwendung an einem Standardspeicherort bzw. dem von Ihnen angegebenen Speicherort. Sie können außerdem angeben, welche Version der Tools Sie verwenden möchten und ob das gesamte SDK oder nur die freigegebene Runtime installiert werden soll.

Das Installationsskript ist automatisiert, sodass es zu Beginn des Buildvorgangs ausgeführt wird, um die gewünschte Version des SDK abzurufen und zu installieren. Die *gewünschte Version* ist die Version des SDK, die zum Erstellen Ihrer Projekte benötigt wird. Das Skript ermöglicht es Ihnen, das SDK in einem lokalen Verzeichnis auf dem Server zu installieren, die Tools vom Installationsort auszuführen und nach der Builderstellung eine Bereinigung durchzuführen (Sie können die Bereinigung auch dem CI-Dienst überlassen). Dies ermöglicht eine Kapselung und Isolation Ihres gesamten Buildprozesses. Die Referenz zu den Installationsskripts finden Sie im Artikel [dotnet-install](dotnet-install-script.md).

> [!NOTE]
> **Azure DevOps Services**
>
> Bei Verwendung des Installationsskripts werden native Abhängigkeiten nicht automatisch installiert. Sie müssen die nativen Abhängigkeiten installieren, wenn das Betriebssystem diese nicht umfasst. Weitere Informationen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../install/dependencies.md?tabs=netcore30&pivots=os-linux).

## <a name="ci-setup-examples"></a>Beispiele für die CI-Einrichtung

In diesem Abschnitt wird die manuelle Einrichtung unter Verwendung eines PowerShell- oder Bash-Skripts erläutert, und es werden verschiedene SaaS-CI-Lösungen (Software-as-a-Service) beschrieben. Die behandelten SaaS-CI-Lösungen sind [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) und [ Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).

### <a name="manual-setup"></a>Manuelle Einrichtung

Jeder SaaS-Dienst umfasst eigene Methoden zum Erstellen und Konfigurieren eines Buildprozesses. Wenn Sie eine andere SaaS-Lösung als die hier aufgeführten verwenden oder eine über die integrierte Unterstützung hinausgehende Anpassung erforderlich ist, müssen Sie einige manuelle Konfigurationsschritte ausführen.

Im Allgemeinen müssen Sie bei einer manuellen Einrichtung eine Version der Tools (oder die neuesten nächtlichen Builds der Tools) herunterladen und Ihr Buildskript ausführen. Sie können ein PowerShell- oder ein Bash-Skript verwenden, um die .NET Core-Befehle zu orchestrieren, oder Sie verwenden eine Projektdatei, die den Buildprozess beschreibt. Diese Optionen werden im [Abschnitt zur Orchestrierung](#orchestrating-the-build) weiter ausgeführt.

Nachdem Sie ein Skript zur Ausführung eines manuellen Setups eines CI-Buildservers erstellt haben, verwenden Sie es auf Ihrem Entwicklungscomputer, um lokalen Code zu Testzwecken zu erstellen. Nachdem Sie sich davon überzeugt haben, dass das Skript lokal wie erwartet funktioniert, stellen Sie es auf Ihrem CI-Buildserver bereit. Ein relativ simples PowerShell-Skript zeigt, wie Sie das .NET Core SDK herunterladen und auf einem Windows-Buildserver installieren:

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

Sie stellen die Implementierung für Ihren Buildprozess am Ende des Skripts bereit. Das Skript ruft die Tools ab und führt dann Ihren Buildprozess aus. Für UNIX-Computer werden die im PowerShell-Skript beschriebenen Aktionen durch das folgende Bash-Skript in ähnlicher Weise ausgeführt:

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

### <a name="travis-ci"></a>Travis CI

[Travis CI](https://travis-ci.org/) kann so konfiguriert werden, dass das .NET Core SDK mit der Sprache `csharp` und dem Schlüssel `dotnet` installiert wird. Weitere Informationen zum [Erstellen eines C#-, F#- oder Visual Basic-Projekts](https://docs.travis-ci.com/user/languages/csharp/) finden Sie in der offiziellen Travis CI-Dokumentation. Beachten Sie beim Zugriff auf die Travis CI-Informationen, dass der von der Community verwaltet Sprachbezeichner `language: csharp` für alle .NET-Sprachen (einschließlich F# und Mono) funktioniert.

Travis CI führt sowohl macOS- als auch Linux-Aufträge in einer *Buildmatrix* aus, wobei Sie eine Kombination aus Runtime, Umgebung und Einschlüssen/Ausschlüssen zur Abdeckung der Buildkombinationen für Ihre App angeben. Weitere Informationen finden Sie im Artikel [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) (Anpassen des Builds) in der Travis CI-Dokumentation. Die MSBuild-basierten Tools enthalten die Runtimes LTS (1.0.x) und Current (1.1.x) im Paket. Deshalb verfügen Sie nach der Installation des SDK über alle benötigten Buildkomponenten.

### <a name="appveyor"></a>AppVeyor

[AppVeyor](https://www.appveyor.com/) installiert das .NET Core 1.0.1 SDK mit dem Buildworkerimage `Visual Studio 2017`. Weitere Buildimages mit anderen Versionen von .NET Core SDK sind verfügbar. Weitere Informationen finden Sie in dem Artikel mit dem [appveyor.yml-Beispiel](https://github.com/dotnet/docs/blob/master/appveyor.yml) und dem Artikel [Build Worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) in der AppVeyor-Dokumentation.

Die .NET Core SDK-Binärdateien werden mithilfe des Installationsskripts heruntergeladen, in einem Unterverzeichnis entpackt und anschließend der Umgebungsvariable `PATH` hinzugefügt. Fügen Sie eine Buildmatrix hinzu, um Integrationstests mit mehreren Versionen des .NET Core SDK auszuführen:

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="azure-devops-services"></a>Azure DevOps Services

Verwenden Sie einen dieser Ansätze, um Azure DevOps Services zum Erstellen von .NET Core-Projekten zu konfigurieren:

1. Führen Sie das Skript aus dem Schritt für die [manuelle Einrichtung](#manual-setup) unter Verwendung Ihrer Befehle aus.
1. Erstellen Sie einen Build aus verschiedenen integrierten Azure DevOps Services-Buildtasks, die zur Verwendung der .NET Core-Tools konfiguriert sind.

Beide Ansätze sind gültige Vorgehensweisen. Mithilfe eines Skripts zur manuellen Einrichtung kontrollieren Sie, welche Version der Tools abgerufen wird, weil Sie die Tools im Rahmen des Builds herunterladen. Der Build wird aus einem Skript ausgeführt, das Sie erstellen müssen. In diesem Artikel wird nur die manuelle Option behandelt. Weitere Informationen zum Erstellen eines Builds mit Azure DevOps Services-Buildaufgaben finden Sie in der [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index)-Dokumentation.

Um ein Skript für ein manuelles Setup in Azure DevOps Services zu verwenden, erstellen Sie eine neue Builddefinition und geben das Skript an, das für den Buildschritt ausgeführt werden soll. Dies wird mithilfe der Azure DevOps Services-Benutzeroberfläche erreicht:

1. Beginnen Sie, indem Sie eine neue Builddefinition erstellen. Wenn der Bildschirm angezeigt wird, auf dem Sie angeben können, welche Art von Build Sie erstellen möchten, wählen Sie die Option **Leer** aus.

   ![Auswahl einer leeren Builddefinition](./media/using-ci-with-cli/select-empty-build-definition.png)

1. Nachdem Sie das zu erstellende Repository konfiguriert haben, gelangen Sie zu den Builddefinitionen. Wählen Sie **Buildschritt hinzufügen** aus:

   ![Hinzufügen eines Buildschritts](./media/using-ci-with-cli/add-build-step.png)

1. Als Nächstes wird der **Taskkatalog** angezeigt. Der Katalog enthält Tasks, die Sie im Build verwenden. Da Sie über ein Skript verfügen, klicken Sie auf die Schaltfläche **Hinzufügen** für **PowerShell: PowerShell-Skript ausführen**.

   ![Hinzufügen eines Schritts für ein PowerShell-Skript](./media/using-ci-with-cli/add-powershell-script.png)

1. Konfigurieren Sie den Buildschritt. Fügen Sie das Skript aus dem Repository hinzu, das Sie erstellen:

   ![Angeben des auszuführenden PowerShell-Skripts](./media/using-ci-with-cli/powershell-script-path.png)

## <a name="orchestrating-the-build"></a>Orchestrieren des Builds

In diesem Dokument wird hauptsächlich beschrieben, wie Sie die .NET Core-Tools herunterladen und verschiedene CI-Dienst konfigurieren, ohne darauf einzugehen, wie Sie Ihren Code mit .NET Core orchestrieren oder *tatsächlich einen Build erstellen*. Die Auswahl bei der Strukturierung des Buildprozesses hängt von vielen Faktoren ab, die hier nicht allgemein abgedeckt werden können. Um weitere Informationen zur Orchestrierung Ihrer Builds mit jeder Technologie zu erhalten, erkunden Sie die Ressourcen und Beispiele in der Dokumentation von [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) und [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).

Bei der Strukturierung des Buildprozesses für .NET Core-Code unter Verwendung der .NET Core-Tools können zwei allgemeine Ansätze verfolgt werden: die direkte Verwendung von MSBuild oder die Verwendung von .NET Core-Befehlszeilenbefehlen. Sie sollten den verwendeten Ansatz danach auswählen, wie vertraut Sie mit dem jeweiligen Ansatz sind und welche Kompromisse Sie in Bezug auf die Komplexität eingehen möchten. Mit MSBuild können Sie Ihren Buildprozess in Form von Tasks und Zielen beschrieben, Sie müssen jedoch die MSBuild-Projektdateisyntax beherrschen. Die Verwendung von .NET Core-Befehlszeilentools ist möglicherweise einfacher, erfordert aber, dass Sie Orchestrierungslogik in einer Skriptsprache wie `bash` oder PowerShell schreiben.

## <a name="see-also"></a>Siehe auch

- [.NET-Downloads – Linux](https://dotnet.microsoft.com/download?initial-os=linux)
