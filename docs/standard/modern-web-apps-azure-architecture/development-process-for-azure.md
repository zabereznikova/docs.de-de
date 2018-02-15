---
title: "Entwicklungsprozess für Azure"
description: "Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Entwicklungsprozess für Azure"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 576a717cbdcb8cf465e8cb7b4898df1df7447aa7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="development-process-for-azure"></a>Entwicklungsprozess für Azure

> _"Mit der Cloud Einzelpersonen kleine Unternehmen können ihre Finger ausrichten und sofort unternehmenstauglichen Dienste einrichten."_  
> _- Roy Stephan_

 ## <a name="vision"></a>Vision

> *Entwickeln Sie ausgereifte ASP .NET Core-Anwendungen die Möglichkeit, die Ihnen gefällt mithilfe des Visual Studio oder die CLI-Dotnet und Visual Studio Code Editor Ihrer Wahl.*

## <a name="development-environment-for-aspnet-core-apps"></a>Entwicklungsumgebung für apps mit ASP.NET Core

### <a name="development-tools-choices-ide-or-editor"></a>Optionen für Entwicklungstools: IDE oder -Editor

Ob Sie eine vollständige und leistungsfähige IDE oder eine einfache und agile-Editor bevorzugen, hat Microsoft Sie beim Entwickeln von ASP.NET Core Anwendungen behandelt.

**Visual Studio 2017.** Bei Verwendung von *Visual Studio 2017* können erstellen ASP.NET Core-Anwendungen, solange Sie haben die *.NET Core plattformübergreifende Entwicklung* arbeitsauslastung installiert. Abbildung 10 – 1 zeigt die erforderliche Arbeitslast im Setupdialogfeld 2017 von Visual Studio.

![](./media/image10-1.png)

**Abbildung 10 – 1.** Installieren die .NET Core-arbeitsauslastung in Visual Studio 2017.

[Visual Studio 2017 herunterladen](https://www.visualstudio.com/downloads/)

**Visual Studio-Code und Dotnet CLI** (Cross-Platform-Tools für Mac-, Linux- und Windows). Wenn Sie einen einfachen und plattformübergreifende-Editor unterstützt Entwicklungssprache bevorzugen, können Sie Microsoft Visual Studio-Code und die Dotnet CLI. Diese Produkte bieten eine einfache, aber robuste Erfahrung, die den Entwickler Workflow optimiert. Darüber hinaus unterstützt Visual Studio Code Erweiterungen für C\# und Webentwicklung, die Bereitstellung von Intellisense und Verknüpfung-Aufgaben innerhalb des Editors.

[Die .NET Core SDK herunterladen](https://www.microsoft.com/net/download/core)

[Herunterladen der Visual Studio-Code](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Entwicklungsworkflow für Azure gehosteten ASP.NET Core-apps

Lebenszyklus der Anwendungsentwicklung beginnt bei jeder Entwickler-Computer, codieren die app ihre bevorzugte Programmiersprache und lokal testen. Entwickler können ihre bevorzugte Quellcodeverwaltungssystem und fortlaufende Integration (CI) und/oder Continuous Delivery/Bereitstellung (CD) mit einem Build-Server konfigurieren können oder basierend auf den integrierten Azure-Funktionen.

Zum Einstieg in eine ASP.NET Core-Anwendung, die mit der CI-CD zu entwickeln, können Sie die Visual Studio Team Services oder Ihrer Organisation verwenden Team Foundation Server (TFS) besitzen.

### <a name="initial-setup"></a>Anfangssetup

Um einer releasepipeline für Ihre app zu erstellen, müssen Sie den Anwendungscode in der quellcodeverwaltung haben. Richten Sie ein lokales Repository, und verbinden Sie ihn in einem Remoterepository in einem Teamprojekt. Gehen Sie wie folgt vor:

-   [Freigeben von Code mit Git als auch Visual Studio](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) oder

-   [Freigeben von Code in TFVC und Visual Studio](https://www.visualstudio.com/docs/tfvc/share-your-code-in-tfvc-vs)

Erstellen Sie ein Azure App Service, in dem Sie Ihre Anwendung bereitstellen. Erstellen Sie eine Web-App, gehen Sie im Azure-Portal auf dem Blatt "App-Dienste". Klicken Sie auf "+" hinzufügen, wählen Sie die Web-App-Vorlage, klicken Sie auf erstellen, und geben Sie einen Namen und andere Details. Die Web-app von {Name} zugegriffen werden. azurewebsites.net.

![AzureWebApp](./media/image10-2.png)

**Abbildung 10 – 2.** Erstellen eine neue Azure App Service Web-App im Azure-Portal an.

CI-Build-Prozess führt einen automatischen Buildvorgang aus, wenn Sie neuer Code an das Projekt Quellcodeverwaltungs-Repository übergeben wird. Dadurch erhalten Sie unmittelbar Feedback, in dem der Code erstellt (und automatisierte Tests im Idealfall übergibt) und potenziell bereitgestellt werden kann. Dieser CI-Build erzeugt eine Web Artefakt Paket bereitstellen und veröffentlichen Sie es für die Nutzung vom CD-Prozess.

[Definieren des Buildprozesses CI](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#ci)

Achten Sie darauf, dass Sie die fortlaufende Integration zu aktivieren, damit das System einen Build in die Warteschlange wird immer eine Person in Ihrem Team führt einen Commit für neuen Code. Testen Sie den Build, und stellen Sie sicher, dass sie eine Web erzeugt Paket als eines seiner Elemente bereitstellen.

Wenn ein Build erfolgreich ist, stellt der CD-Prozess die Ergebnisse der CI-Build für Ihre Azure-Web-app bereit. Um dies zu konfigurieren, erstellen und konfigurieren Sie eine *Version*, die Bereitstellung in Ihren Azure App Service.

[Definieren Sie den versionsprozess CD](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#cd)

Sobald die CI-CD-Pipeline konfiguriert ist, können Sie einfach Updates auf Ihre Web-app und übernehmen sie zur quellcodeverwaltung, die sie bereitgestellt haben.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Workflow für die Entwicklung von Azure gehosteten ASP.NET Core-Anwendungen

Nachdem Sie Ihre Azure-Konto und den CI-CD-Prozess konfiguriert haben, ist die Entwicklung von Azure gehosteten ASP.NET Core-Anwendungen einfach. Im folgenden sind die grundlegenden Schritte, die Sie normalerweise, beim Erstellen einer ASP.NET Core-app in Azure App Service als eine Web-App gehostet wird ausführen, wie in Abbildung 10 – 3 veranschaulicht.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**Abbildung 10 – 3.** Schrittweise Workflow zum Erstellen von ASP.NET Core-apps und das Hosten dieser in Azure

#### <a name="step-1-local-dev-environment-inner-loop"></a>Schritt 1. Lokale Dev Umgebung innere Schleife

Entwickeln Ihrer Anwendung ASP.NET Core zur Bereitstellung in Azure unterscheidet sich nicht von andernfalls Entwickeln Ihrer Anwendung. Verwenden Sie die lokalen Entwicklungs-Umgebung aus, der Sie mit, vertraut sind, ob das Visual Studio-2017 oder Dotnet-CLI und Visual Studio-Code oder Ihrem bevorzugten Text-Editor ist. Sie können Code schreiben, ausführen und Debuggen die Änderungen, Ausführen von automatisierten Tests und lokalen Commits zur quellcodeverwaltung stellen, bis Sie die Änderungen per Push auf Ihre freigegebenen Quellcodeverwaltungs-Repository übertragen möchten.

#### <a name="step-2-application-code-repository"></a>Schritt 2 Anwendung Code Repository

Wenn Sie zur Freigabe des Codes mit Ihrem Team bereit sind, sollten Sie Ihre Änderungen aus Ihrem lokalen Quellrepository zu freigegebenen Quellrepository Ihres Teams per Push übertragen. Wenn Sie in einer benutzerdefinierten Verzweigung gearbeitet haben, in der Regel dieser Schritt umfasst das Zusammenführen von Code in eine freigegebene Verzweigung (z. B. mithilfe von einer [Pull-Anforderung](https://www.visualstudio.com/docs/git/pull-requests)).

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>Schritt 3 Build-Server: Fortlaufende Integration. Build, Test-Paket

Ein neuer Build wird auf dem Buildserver ausgelöst, wenn ein neuer Commit an die freigegebene Anwendung Code Repository vorgenommen wird. Als Teil der CI-Prozess sollte dieser Build vollständig kompilieren Sie die Anwendung und Ausführen von automatisierten Tests, um sicherzustellen, dass alles wie erwartet funktioniert. Das Endergebnis der CI-Prozess sollte eine gepackte Version der Web-app, für die Bereitstellung bereit.

#### <a name="step-4-build-server-continuous-delivery"></a>Schritt 4. Build-Server: Continuous Delivery

Einmal einen Build als erfolgreich, das CD-Prozess die Build-Elemente, die erzeugt übernehmen. Dazu gehören eine Web deploy-Paket. Der Build-Server stellt dieses Paket für Azure App Service, und Ersetzen Sie dabei alle vorhandenen Dienst mit der neu erstellten bereit. In der Regel wird dieser Schritt eine Stagingumgebung ausgerichtet ist, aber einige Anwendungen, die direkt für die Produktion durch einen CD-Prozess bereitstellen.

#### <a name="step-5-azure-app-service-web-app"></a>Schritt 5. Azure App Service. Web-App.

Nach der Bereitstellung wird die ASP.NET Core-Anwendung im Kontext einer Azure App Service-Web-App ausgeführt. Diese Web-App können überwacht werden und weiter konfiguriert mithilfe des Azure-Portals.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>Schritt 6. Produktion Überwachung und Diagnose

Während der Web-App ausgeführt wird, können Sie die Integrität der Anwendung überwachen und Sammeln von Diagnose- und Verhalten von Benutzerdaten. Application Insights in Visual Studio enthalten ist, und bietet automatische Instrumentation für ASP.NET-Apps. Sie können Sie Informationen zur Nutzung, Ausnahmen, Anforderungen, Leistung und Protokolle bereitstellen.

## <a name="references"></a>Verweise

**Erstellen und Bereitstellen der ASP.NET Core-App in Azure**  
<https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure>


>[!div class="step-by-step"]
[Vorherigen] (Test-asp-net-core-mvc-apps.md) [weiter] (Azure-hosting-recommendations-for-asp-net-web-apps.md)
