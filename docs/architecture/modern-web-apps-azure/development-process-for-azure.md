---
title: Entwicklungsprozess für Azure
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Entwicklungsprozess für Azure
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 7a641c1b6665af6e9e78ef182174b360041d74aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77450041"
---
# <a name="development-process-for-azure"></a>Entwicklungsprozess für Azure

> _„Mit der Cloud können Einzelpersonen und kleine Unternehmen im Handumdrehen Dienste für ihr Unternehmen einrichten.“_  
> _– Roy Stephan_

## <a name="vision"></a>Ziel

> *Entwickeln von ausgereiften ASP.NET Core-Anwendungen mit Visual Studio oder der DotNet-CLI und Visual Studio Code oder einem anderen Editor Ihrer Wahl.*

## <a name="development-environment-for-aspnet-core-apps"></a>Entwicklungsumgebung für ASP.NET Core-Apps

### <a name="development-tools-choices-ide-or-editor"></a>Auswahlmöglichkeiten für das Entwicklungstool: IDE oder Editor

Egal, ob Sie eine vollständige und leistungsstarke integrierte Entwicklungsumgebung (IDE) oder einen einfachen und flexiblen Editor bevorzugen: Microsoft bietet Ihnen Tools, die Sie zum Entwickeln von ASP.NET Core-Anwendungen verwenden können.

**Visual Studio 2019.** Visual Studio 2019 ist die beste IDE für die Entwicklung von Anwendungen für ASP.NET Core. Die IDE bietet eine Reihe von Features, die die Produktivität von Entwicklern steigern. Sie können sie zur Entwicklung der Anwendung verwenden und dann ihre Leistung und andere Merkmale analysieren. Mit dem integrierten Debugger können Sie die Codeausführung anhalten und den Code während der Ausführung schrittweise durchlaufen. Mit dem integrierten Test Runner können Sie Ihre Tests und deren Ergebnisse organisieren und während des Programmierens auch Live Unit Testing ausführen. Mithilfe von Live Share können Sie in Echtzeit mit anderen Entwicklern zusammenarbeiten und Ihre Codesitzung reibungslos über das Netzwerk freigeben. Sobald Sie soweit sind, enthält Visual Studio alles, was Sie zum Veröffentlichen Ihrer Anwendung in Azure oder an anderer Stelle benötigen.

[Herunterladen von Visual Studio 2019](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

**Visual Studio Code und DotNet-CLI** (Plattformübergreifende Tools für Mac, Linux und Windows). Wenn Sie einen einfachen und plattformübergreifenden Editor bevorzugen, der jede beliebige Entwicklungssprache unterstützt, können Sie Microsoft Visual Studio Code und die DotNet-CLI verwenden. Diese Produkte bieten eine einfachen aber widerstandsfähigen Prozess, der den Entwicklungsworkflow optimiert. Darüber hinaus unterstützt Visual Studio Code Erweiterung für die C\#- und Webentwicklung durch Bereitstellung von IntelliSense und Verknüpfungen für Aufgaben im Editor.

[.NET Core SDK herunterladen](https://dotnet.microsoft.com/download)

[Visual Studio Code herunterladen](https://code.visualstudio.com/download)

## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Entwicklungsworkflow für in Azure gehostete ASP.NET Core-Apps

Der Lebenszyklus der Anwendungsentwicklung beginnt am Computer eines Entwicklers, auf dem dieser die Anwendung mithilfe seiner bevorzugten Sprache codiert und lokal testet. Entwickler können ihr bevorzugtes System für die Quellcodeverwaltung auswählen und die Continuous Integration (CI) und bzw. oder die Continuous Delivery (CD) mithilfe eines Buildservers oder integrierten Azure-Features konfigurieren.

Für den Einstieg in die Entwicklung einer ASP.NET Core-Anwendung mit CI bzw. CD können Sie Azure DevOps Services oder Team Foundation Server (TFS) Ihrer Organisation verwenden.

### <a name="initial-setup"></a>Erste Einrichtung

Zum Erstellen einer Releasepipeline muss der Code Ihrer Anwendung sich in der Quellcodeverwaltung befinden. Richten Sie ein lokales Repository ein, und verbinden Sie es mit einem Remoterepository in einem Teamprojekt. Befolgen Sie diese Anweisungen:

- [Teilen Sie Ihren Code mit Git und Visual Studio](https://docs.microsoft.com/azure/devops/git/share-your-code-in-git-vs) oder

- [Teilen Sie Ihren Code mit TFVC und Visual Studio](https://docs.microsoft.com/azure/devops/tfvc/share-your-code-in-tfvc-vs)

Erstellen Sie einen Azure App Service, in dem Sie Ihre Anwendung bereitstellen. Erstellen Sie eine Webanwendung, indem Sie zum Blatt „App Services“ im Azure-Portal navigieren. Klicken Sie auf „+Hinzufügen“, wählen Sie die Vorlage „Web App“ aus, klicken Sie auf „Erstellen“, und geben Sie einen Namen sowie die anderen erforderlichen Informationen an. Auf die Webanwendung kann über „{name}.azurewebsites.net“ zugegriffen werden.

![AzureWebApp](./media/image10-2.png)

**Abbildung 10-1** Erstellen einer neuen Azure App Service-Webanwendung im Azure-Portal.

Der CI-Buildprozess führt einen automatisierten Buildvorgang aus, wenn neuer Code an das Quellcodeverwaltungs-Repository des Projekts committet wird. Dadurch erhalten Sie sofortiges Feedback, dass der Code erstellt wird (und im Idealfall die automatisierten Tests besteht) und bereitgestellt werden kann. Dieser CI-Build erstellt ein Web Deploy-Paketartefakt und veröffentlicht dieses für die Nutzung durch Ihren CD-Prozess.

[Definieren des CI-Buildprozesses](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#ci)

Achten Sie darauf, dass die Continuous Integration aktiviert ist, damit das System den Buildvorgang der Warteschlange hinzufügt, wenn jemand in Ihrem Team neuen Code committet. Testen Sie den Build und stellen Sie sicher, dass er ein Web Deploy-Paket als eines seiner Artefakte erstellt.

Wenn ein Build erfolgreich ist, werden die Ergebnisse Ihres CI-Builds durch Ihren CD-Prozess für Ihre Azure-Webanwendung bereitgestellt. Erstellen und konfigurieren Sie ein *Release*, das Sie dann für Ihren Azure App Service bereitstellen, um dies zu konfigurieren.

[Definieren des CD-Releaseprozesses](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#cd)

Sobald Ihre CI- und CD-Pipeline konfiguriert ist, können Sie Ihre Webanwendung aktualisieren und dann an die Quellcodeverwaltung committen, um diese bereitzustellen.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Entwicklungsworkflow für in Azure gehostete ASP.NET Core-Apps

Sobald Sie ihr Azure-Konto und Ihre CI- und CD-Prozesse konfiguriert haben, ist die Entwicklungen von in Azure gehosteten ASP.NET Core-Apps einfach. In der folgenden Abbildung (10-2) sind die grundlegenden Schritte zum Erstellen einer ASP.NET Core-App dargestellt, die in Azure App Service als Web-App gehostet wird.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**Abbildung 10-2** Exemplarischer Workflow für das Erstellen von ASP.NET Core-Apps und das Hosten dieser in Azure

#### <a name="step-1-local-dev-environment-inner-loop"></a>Schritt 1. Lokale Entwicklungsumgebung – innere Schleife

Die Entwicklung Ihrer ASP.NET Core-Anwendung für die Bereitstellung in Azure unterscheidet sich nicht von anderer Anwendungsentwicklung. Verwenden Sie eine lokale Entwicklungsumgebung, mit der Sie vertraut sind, egal ob es sich dabei um Visual Studio 2017, die DotNet-CLI mit Visual Studio Code oder um Ihren bevorzugten Editor handelt. Sie können Code schreiben, ausführen und Ihre Änderungen debuggen, automatisierte Tests ausführen und lokale Commits zur Quellcodeverwaltung erstellen, bis Sie bereit dazu sind, Ihre Änderungen an Ihr freigegebenes Repository zur Quellcodeverwaltung zu übergeben.

#### <a name="step-2-application-code-repository"></a>Schritt 2 Repository für Anwendungscode

Wenn Sie bereit dazu sind, Ihren Code mit Ihrem Team zu teilen, sollten Sie Ihre Änderungen vom lokalen Quellrepository an das freigegebene Quellrepository des Teams übergeben. Wenn Sie an einem benutzerdefinierten Branch gearbeitet haben, erfordert dieser Schritt in der Regel das Zusammenführen Ihres Codes in einen freigegebenen Branch (möglicherweise über einen [Pull Request](https://docs.microsoft.com/azure/devops/git/pull-requests)).

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>Schritt 3. Buildserver: Continuous Integration – Erstellen, Testen, Packen

Ein neuer Buildvorgang wird auf dem Buildserver ausgelöst, wenn ein neuer Commit an das freigegebene Repository für Anwendungscode ausgeführt wird. Als Teil des CI-Prozesses sollte dieser Buildvorgang die Anwendung vollständig kompilieren und automatisierte Tests ausführen, um sicherzustellen, dass alles wie erwartet funktioniert. Das Endergebnis des CI-Prozesses sollte eine gepackte Version der Webanwendung sein, die bereit für die Bereitstellung ist.

#### <a name="step-4-build-server-continuous-delivery"></a>Schritt 4. Buildserver: Continuous Delivery

Wenn ein Buildvorgang erfolgreich war, übernimmt der CD-Prozess die erstellten Buildartefakte. Ein Web Deploy-Paket wird einbezogen. Der Buildserver stellt dieses Paket für Azure App Service bereit und ersetzt dabei alle vorhandenen Dienste durch die neu erstellten. In der Regel ist dieser Schritt auf eine Stagingumgebung ausgerichtet. Manche Anwendungen führen durch einen CD-Prozess jedoch direkt eine Bereitstellung für die Produktion durch.

#### <a name="step-5-azure-app-service-web-app"></a>Schritt 5: Azure App Service-Web-App

Sobald sie bereitgestellt ist, wird die ASP.NET Core-App im Kontext einer Azure App Service-Web-App ausgeführt. Diese Web-App kann überwacht und mithilfe des Azure-Portals weiter konfiguriert werden.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>Schritt 6. Überwachung und Diagnose in der Produktion

Während die Web-App ausgeführt wird, können Sie die Integrität der Anwendung überwachen und Daten für die Diagnose und das Benutzerverhalten sammeln. Application Insights ist in Visual Studio enthalten und bietet automatische Instrumentierung für ASP.NET-Apps. Application Insights bietet Ihnen Informationen zu Verwendung, Ausnahmen, Anforderungen, Leistung und Protokollen.

## <a name="references"></a>Verweise

**Build and Deploy Your ASP.NET Core App to Azure (Erstellen und Bereitstellen Ihrer ASP.NET Core-App in Azure)**  
<https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core>

>[!div class="step-by-step"]
>[Zurück](test-asp-net-core-mvc-apps.md)
>[Weiter](azure-hosting-recommendations-for-asp-net-web-apps.md)
