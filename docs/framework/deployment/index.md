---
title: Bereitstellen von .NET Framework und Anwendungen
description: Erste Schritte beim Bereitstellen von .NET mit Ihrer Anwendung. .NET bietet Anwendungen ohne Auswirkungen, standardmäßig private Komponenten, kontrollierte Codefreigabe und vieles mehr.
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
ms.openlocfilehash: cce888c962c9ab83c13cce4040eb9ba50270972d
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803500"
---
# <a name="deploying-the-net-framework-and-applications"></a>Bereitstellen von .NET Framework und Anwendungen

Dieser Artikel hilft Ihnen dabei, mit der Bereitstellung des .NET Framework mit Ihrer Anwendung zu beginnen. Die meisten der Informationen sind für Entwickler, OEM- und Organisationsadministratoren vorgesehen. Benutzer, die .NET Framework auf ihren Computern installieren möchten, sollten die Informationen unter [Installieren von .NET Framework](../install/index.md) lesen.

## <a name="key-deployment-resources"></a>Wichtige Bereitstellungsressourcen

Verwenden Sie die folgenden Links zu anderen MSDN-Themen, um genaue Informationen zum Bereitstellen und Warten von .NET Framework zu erhalten.

**Setup und Bereitstellung**

- Allgemeine Informationen zum Installer und der Bereitstellung:

  - Installeroptionen:

    - [Webinstaller](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

    - [Offline-Installer](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

  - Installationsmodi:

    - [Automatische Installation](deployment-guide-for-developers.md#chaining_custom)

    - [Anzeigen einer Benutzeroberfläche](deployment-guide-for-developers.md#chaining_default)

  - [Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen](reducing-system-restarts.md)

  - [Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)

- Bereitstellen von .NET Framework mit einer Clientanwendung (für Entwickler):

  - [Verwenden von InstallShield](deployment-guide-for-developers.md#installshield-deployment) in einem Setup- und Bereitstellungsprojekt

  - [Verwenden einer Visual Studio-ClickOnce-Anwendung](deployment-guide-for-developers.md#clickonce-deployment)

  - [Erstellen eines WiX-Installationspakets](deployment-guide-for-developers.md#wix)

  - [Verwenden eines benutzerdefinierten Installers](deployment-guide-for-developers.md#chaining)

  - [Zusätzliche Informationen](deployment-guide-for-developers.md) für Entwickler

- Bereitstellen von .NET Framework (für OEMs und Administratoren):

  - [Windows Assessment and Deployment Kit (ADK)](https://go.microsoft.com/fwlink/p/?LinkId=254976)

  - [Administratorhandbuch](guide-for-administrators.md)

**Wartung**

- Allgemeine Informationen finden Sie im [.NET Framework-Blog](https://devblogs.microsoft.com/dotnet/).

- [Erkennen von Versionen](../migration-guide/how-to-determine-which-versions-are-installed.md)

- [Erkennen von Service Packs und Updates](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)

## <a name="features-that-simplify-deployment"></a>Funktionen, die die Bereitstellung vereinfachen

.NET Framework stellt zahlreiche Grundfunktionen bereit, die die Bereitstellung Ihrer Anwendungen vereinfachen:

- Anwendungen ohne unerwünschte Auswirkungen.

     Diese Funktion bietet Anwendungsisolierung und beseitigt DLL-Konflikte. Komponenten haben standardmäßig keinen Einfluss auf andere Anwendungen.

- Private Komponenten (durch standardmäßige Voreinstellung).

     Komponenten werden standardmäßig im Anwendungsverzeichnis bereitgestellt und sind nur innerhalb der dort enthaltenen Anwendung sichtbar.

- Kontrollierte, gemeinsame Verwendung von Code.

     Im Fall gemeinsamer Verwendung von Code müssen Sie Code explizit zur gemeinsamen Verwendung bereitstellen. Dies sollte kein Standardverhalten sein.

- Paralleles Versioning.

     Mehrere Versionen einer Komponente oder einer Anwendung können gleichzeitig vorhanden sein. Sie können wählen, welche Versionen Sie verwenden möchten. Durch die Common Language Runtime werden Versionsrichtlinien erzwungen.

- Bereitstellung und Replikation durch XCOPY.

     Selbstbeschreibende und unabhängige Komponenten und Anwendungen können ohne Registrierungseinträge oder Abhängigkeiten bereitgestellt werden.

- Dynamische Updates.

     Administratoren können Hosts wie z. B. ASP.NET verwenden, um DLLs von Programmen auch auf Remotecomputern zu aktualisieren.

- Integration in Windows Installer.

     Für die Bereitstellung Ihrer Anwendung stehen Funktionen wie Werbung, Veröffentlichung, Reparatur und Installation bei Bedarf zur Verfügung.

- Enterprise-Bereitstellung.

     Diese Funktion macht die einfache Verteilung von Software, einschließlich der Verwendung von Active Directory, möglich.

- Herunterladen und Zwischenspeichern.

     Durch inkrementelles Herunterladen werden Downloads klein gehalten. Komponenten können isoliert werden und somit nur für eine Anwendung verfügbar sein und mit minimalen Auswirkungen bereitgestellt werden.

- Teilweise vertrauenswürdiger Code.

     Die Identität basiert auf dem Code, nicht auf dem Benutzer. Zertifikatdialogfelder werden nicht angezeigt.

## <a name="packaging-and-distributing-net-framework-applications"></a>Verpacken und Verteilen von .NET Framework-Anwendungen

Einige Informationen über das Packen und Bereitstellen in .NET Framework erhalten Sie in anderen Abschnitten der Dokumentation. Diese Abschnitte enthalten Informationen zu den selbstbeschreibenden Einheiten mit dem Namen [Assemblys](../../standard/assembly/index.md), die keine Registrierungseinträge benötigen, zu [Assemblys mit starkem Namen](../../standard/assembly/strong-named.md), die die Eindeutigkeit der Namen gewährleisten und das Vortäuschen von Namen verhindern, sowie zu [Assemblyversionen](../../standard/assembly/versioning.md), die viele der in Zusammenhang mit DLL-Konflikten auftretenden Probleme behandeln. In den folgenden Abschnitten finden Sie Informationen zum Verpacken und Verteilen von .NET Framework-Anwendungen.

### <a name="packaging"></a>Verpacken

In .NET Framework werden die folgenden Optionen für das Verpacken von Anwendungen bereitgestellt:

- Als einzelne Assembly oder als Auflistung von Assemblys.

     Bei dieser Option verwenden Sie einfach die DLL- oder EXE-Dateien so, wie sie erstellt wurden.

- Als CAB-Dateien.

     Mit dieser Option komprimieren Sie Dateien in CAB-Dateien, damit die Verteilung oder der Download weniger zeitaufwendig ist.

- Als Windows Installer-Paket oder in anderen Installer-Formaten.

     Mit dieser Option erstellen Sie MSI-Dateien zur Verwendung mit dem Windows Installer. Bei Verwendung eines anderen Installers verpacken Sie die Anwendung.

### <a name="distribution"></a>Verteilung

In .NET Framework werden die folgenden Optionen für das Verteilen von Anwendungen bereitgestellt:

- Verwenden von XCOPY oder FTP.

     Da Common Language Runtime-Anwendungen selbstbeschreibend sind und keine Registrierungseinträge erfordern, können Sie XCOPY oder FTP verwenden, um die Anwendung einfach in ein entsprechendes Verzeichnis zu kopieren. Die Anwendung kann dann von diesem Verzeichnis aus ausgeführt werden.

- Herunterladen von Code.

     Wenn Sie die Anwendung über das Internet oder ein Firmenintranet vertreiben, laden Sie den Code einfach auf einen Computer herunter und führen die Anwendung dort aus.

- Verwenden eines Installationsprogramms wie z. B. Windows Installer 2.0.

     Windows Installer 2.0 kann Assemblys von .NET Framework im globalen Assemblycache und in privaten Verzeichnissen installieren, reparieren oder daraus entfernen.

### <a name="installation-location"></a>Installationsspeicherort

Informationen zur Bereitstellung der Anwendungsassemblys für die Laufzeit finden Sie unter [So sucht Common Language Runtime nach Assemblys](how-the-runtime-locates-assemblies.md).

Sicherheitsüberlegungen können bei der Bereitstellung einer Anwendung ebenfalls eine Rolle spielen. Sicherheitsberechtigungen werden verwaltetem Code in Abhängigkeit von der Position gewährt. Das Bereitstellen von Anwendungen oder Komponenten an Speicherorten mit geringer Vertrauenswürdigkeit, z. B. im Internet, schränkt die Möglichkeiten hinsichtlich einer Anwendung oder Komponente ein. Weitere Informationen zu Bereitstellungs- und Sicherheitsüberlegungen finden Sie unter [Grundlagen der Codezugriffssicherheit](../misc/code-access-security-basics.md).

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[So sucht Common Language Runtime nach Assemblys](how-the-runtime-locates-assemblies.md)|Beschreibt, wie die Common Language Runtime ermittelt, welche Assembly zur Erfüllung einer Bindungsanforderung verwendet wird.|
|[Bewährte Methoden für das Laden von Assemblys](best-practices-for-assembly-loading.md)|In diesem Artikel werden Möglichkeiten zur Vermeidung von Problemen mit der Typidentität erläutert, die zu <xref:System.InvalidCastException>, <xref:System.MissingMethodException> und anderen Fehlern führen können.|
|[Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen](reducing-system-restarts.md)|Beschreibt den Neustart-Manager, der Neustarts nach Möglichkeit verhindert, und erläutert, wie Anwendungen, mit denen .NET Framework installiert wird, den Neustart-Manager nutzen können.|
|[Bereitstellungshandbuch für Administratoren](guide-for-administrators.md)|Hierin wird erläutert, wie ein Systemadministrator mit Microsoft Endpoint Configuration Manager .NET Framework und dessen Systemabhängigkeiten in einem Netzwerk bereitstellen kann.|
|[Bereitstellungshandbuch für Entwickler](deployment-guide-for-developers.md)|Es wird erklärt, wie Entwickler .NET Framework auf den Computern der Benutzer mit ihren Anwendungen installieren können.|
|[Bereitstellen von Anwendungen, Diensten und Komponenten](/visualstudio/deployment/deploying-applications-services-and-components)|Erläutert Bereitstellungsoptionen in Visual Studio, einschließlich Anweisungen zum Veröffentlichen einer Anwendung mit ClickOnce- und Windows Installer-Technologie.|
|[Veröffentlichen von ClickOnce-Anwendungen](/visualstudio/deployment/publishing-clickonce-applications)|Beschreibt, wie eine Windows Forms-Anwendung verpackt und mit ClickOnce auf Clientcomputern in einem Netzwerk bereitgestellt wird.|
|[Verpacken und Bereitstellen von Ressourcen](../resources/packaging-and-deploying-resources-in-desktop-apps.md)|Beschreibt das sternenförmige Modell von .NET Framework zum Verpacken und Bereitstellen von Ressourcen und enthält Informationen zu Namenskonventionen für Ressourcen, Fallbackprozessen und Verpackungsalternativen.|
|[Bereitstellen einer Interop-Anwendung](../interop/deploying-an-interop-application.md)|Erläutert, wie Interop-Anwendungen verteilt und installiert werden, die üblicherweise eine .NET Framework-Clientassembly enthalten. Außerdem wird beschrieben, wie Interopassemblys, die unterschiedliche COM-Typbibliotheken darstellen, sowie registrierte COM-Komponenten verteilt und installiert werden.|
|[How to: Abrufen des Status vom Installationsprogramm für .NET Framework 4.5](how-to-get-progress-from-the-dotnet-installer.md)|Beschreibt, wie der .NET Framework-Setupvorgang automatisch gestartet und nachverfolgt und dabei eine eigene Ansicht des Setupstatus angezeigt werden kann.|

## <a name="see-also"></a>Siehe auch

- [Entwicklungshandbuch](../development-guide.md)
