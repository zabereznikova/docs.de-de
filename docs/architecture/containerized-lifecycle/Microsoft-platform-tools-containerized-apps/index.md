---
title: Einführung in die Microsoft-Plattform und -Tools für Container-Apps
description: Lernen Sie die Microsoft-Lösungen für die Unterstützung des Lebenszyklus von Docker-Anwendungen kennen.
ms.date: 02/15/2019
ms.openlocfilehash: 84f4136c6b6c284dd5ecb3fc174ac825857a567e
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158501"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Einführung in die Microsoft-Plattform und -Tools für Container-Apps

*Vision: Erstellen eines anpassungsfähigen Lebenszyklus für Containeranwendungen auf Unternehmensniveau, der sich über Ihr gesamtes Management für Entwicklung, IT-Betrieb und Produktion erstreckt.*

Abbildung 3-1 zeigt die Hauptpfeiler im Lebenszyklus von Docker-Apps, die nach der Art der von mehreren Teams geleisteten Arbeit klassifiziert sind (App-Entwicklung, DevOps-Infrastrukturprozesse und IT-Verwaltung und -Betrieb). Normalerweise sind im Unternehmen die Profile der „Rollen“, die für jeden Bereich zuständig sind, unterschiedlich. Genau wie ihre Fähigkeiten.

:::image type="complex" source="./media/index/microsoft-tools-contanerized-docker-app.png" alt-text="Diagramm, das die Microsoft-Tools zeigt, die zum Verwalten von Docker-Apps erforderlich sind.":::
Microsoft-Tools. Für die Entwicklungs-/Entwurfsworkload: Docker-Engine für Windows, Visual Studio, Visual Studio Code, .NET Core und Azure Kubernetes Service Für die Build-/Test-/Auslieferungsworkoad: Azure DevOps, Team Foundation Server, Docker CLI, Azure Kubernetes Service. Für die Ausführungs-/Überwachungs-/Verwaltungsworkload: Azure Monitor, Azure-Portal, Azure Kubernetes Services, Service Fabric und andere Orchestratoren
:::image-end:::

**Abbildung 3-1.** Hauptpfeiler im Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und -Tools

Ein containerisierter Docker-Lebenszyklusworkflow kann anfangs auf der Basis von „standardmäßiger Produktauswahl“ vorgegeben werden, was es Entwicklern leichter macht, schneller einzusteigen. Es ist aber von grundlegender Bedeutung, dass es im Hintergrund ein offenes Framework geben muss, damit ein flexibler Workflow entsteht, der sich an die unterschiedlichen Kontexte jeder Organisation oder jedes Unternehmens anpassen kann. Die Workflowinfrastruktur (Komponenten und Produkte) muss flexibel genug sein, um die Umgebung abzudecken, die jedes Unternehmen in der Zukunft haben wird, und sie muss sogar in der Lage sein, Entwicklungs- oder DevOps-Produkte gegen andere auszutauschen. Diese Flexibilität, Offenheit und eine breite Auswahl an Technologien in der Plattform und Infrastruktur sind genau die Prioritäten von Microsoft für Docker-Containeranwendungen, wie in den folgenden Kapiteln erläutert wird.

Tabelle 3-1 zeigt, dass die Absicht von Microsoft DevOps für Docker-Containeranwendungen darin besteht, einen offenen DevOps-Workflow bereitzustellen, sodass Sie auswählen können, welche Produkte für jede Phase (Microsoft oder Drittanbieter) verwendet werden sollen, während ein vereinfachter Workflow zur Verfügung steht, der bereits verbundene „standardmäßige Produkte“ bereitstellt. So können Sie schnell mit Ihrem DevOps-Workflow für Docker-Apps auf Unternehmensebene beginnen.

**Tabelle 3-1.** Offener DevOps-Workflow für jede Technologie

| Host | Microsoft-Technologien | Drittanbieter, in Azure integrierbar |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Plattform für Docker-Apps   | • Microsoft Visual Studio und Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Kubernetes Service (AKS)<br /> • Azure Service Fabric<br /> • Azure Container Registry<br /> | • Beliebiger Code-Editor (z.B. Sublime)<br /> • Beliebige Sprache (Node.js, Java, Go usw.)<br /> • Beliebiger Orchestrator und Scheduler<br /> • Beliebige Docker-Registrierung<br /> |
| DevOps für Docker-Apps     | • Azure DevOps Services<br /> • Microsoft Team Foundation Server<br /> • Azure Kubernetes Service (AKS)<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion usw.<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI usw.<br /> • Lokales Docker-Datencenter, Docker Swarm, Mesos DC/OS, Kubernetes usw.<br /> |
| Verwaltung und Überwachung  | • Azure Monitor | • Marathon, Chronos usw.<br />|

Die Microsoft-Plattform und die Tools für containerisierte Docker-Anwendungen, wie in Tabelle 3-1 definiert, bestehen aus den folgenden Komponenten:

- **Plattform für die Entwicklung von Docker Apps**: Die Entwicklung eines Diensts oder einer Sammlung von Diensten, aus denen sich eine „App“ zusammensetzt. Die Entwicklungsplattform stellt alle Aufgaben bereit, die Entwickler benötigen, bevor sie ihren Code in ein gemeinsames Coderepository mithilfe von Push verschieben. Die Entwicklung von Diensten, die als Container bereitgestellt werden, ähnelt der Entwicklung derselben Anwendungen oder Dienste ohne Docker. Sie verwenden weiterhin Ihre bevorzugte Sprache (.NET, Node.js, Go usw.) und Ihren bevorzugten Editor bzw. Ihre bevorzugte IDE wie Visual Studio oder Visual Studio Code. Anstatt Docker jedoch als Bereitstellungsziel zu betrachten, entwickeln Sie Ihre Dienste in der Docker-Umgebung. Die Erstellung, das Ausführen und Testen sowie das Debuggen Ihres Codes erfolgt lokal in Containern, und Sie stellen die Zielumgebung zur Entwicklungszeit zur Verfügung. Indem sie die Zielumgebung lokal bereitstellen, richten Docker-Container eine Umgebung ein, die Sie erheblich dabei unterstützen wird, Ihren DevOps-Lebenszyklus zu optimieren. Visual Studio und Visual Studio Code verfügen über Erweiterungen für die Integration von Docker-Containern in Ihren Entwicklungsprozess.

- **DevOps für Docker-Apps**: Entwickler, die Docker-Anwendungen erstellen, können [Azure DevOps Services](https://azure.microsoft.com/services/devops/) oder andere Drittanbieterprodukte wie Jenkins verwenden, um eine umfassende automatisierte ALM-Verwaltung (Application Lifecycle Management) einzurichten.

  Mit Azure DevOps Services können Entwickler containerzentrierte DevOps für einen schnellen, iterativen Prozess erstellen, der die Quellcodeverwaltung von jedem beliebigen Ort aus (Azure DevOps Services-Git, GitHub, beliebiges Git-Remoterepository oder Subversion), Continuous Integration (CI), interne Komponententests, containerübergreifende/Dienstintegrationstests, Continuous Delivery (CD) und Release-Management (RM) ermöglicht. Entwickler können auch ihre Docker-Anwendungsreleases in Azure Kubernetes Service (AKS) automatisieren: von der Entwicklung bis hin zu Staging- und Produktionsumgebungen.

- **Verwaltung und Überwachung** Die IT kann Produktionsanwendungen und -dienste in verschiedener Weise überwachen und mehrere Perspektiven auf einer konsolidierten Benutzeroberfläche integrieren.

  - **Azure-Portal** Wenn Sie Open Source-Orchestratoren verwenden, helfen Ihnen Azure Kubernetes Service (AKS), Service Fabric und andere Orchestratoren beim Einrichten und Verwalten ihrer Docker-Umgebungen. Wenn Sie Azure Service Fabric verwenden, ermöglicht Ihnen das Tool Service Fabric Explorer die Visualisierung und Konfiguration Ihres Clusters.

  - **Docker-Tools** : Sie können Ihre Containeranwendungen mit vertrauten Tools verwalten. Es besteht keine Notwendigkeit, Ihre vorhandenen Docker-Verwaltungsverfahren zu ändern, um Containerworkloads in die Cloud zu verschieben. Nutzen Sie die Ihnen bereits vertrauten Anwendungsverwaltungstools, und verbinden Sie sich über die API-Standardendpunkte mit dem Orchestrator Ihrer Wahl. Sie können auch andere Tools von Drittanbietern verwenden, um Ihre Docker-Anwendungen zu verwalten, z. B. Docker Datacenter oder sogar CLI-Tools von Docker.

    Selbst wenn Sie mit Linux-Befehlen vertraut sind, können Sie Ihre Containeranwendungen mithilfe von Microsoft Windows und PowerShell mit einer Eingabeaufforderung des Linux-Subsystems und den Produktclients (Docker, Kubernetes…) verwenden, die in dieser Linux-Subsystemfunktionalität ausgeführt werden. Sie erfahren mehr über die Verwendung dieser Tools unter dem Linux-Subsystem mithilfe Ihres bevorzugten Microsoft Windows-Betriebssystems im weiteren Verlauf dieses Handbuchs.

  - **Open Source-Tools** : Da AKS die API-Standardendpunkte für die Orchestrierungs-Engine bereitstellt, sind die gängigsten Tools mit AKS kompatibel und in den meisten Fällen sofort einsatzbereit (einschließlich Visualisierung, Überwachung, Befehlzeilentools und sogar zukünftige Tools, sobald diese verfügbar sind).

  - **Azure Monitor** Die Azure-Lösung, um jeden Winkel Ihrer Produktionsumgebung zu überwachen. Sie können Docker-Produktionsanwendungen überwachen, indem Sie einfach deren SDK in Ihren Diensten einrichten, damit Sie vom System generierte Protokolldaten von den Anwendungen abrufen können.

Damit stellt Microsoft eine vollständige Grundlage für einen End-to-End-Lebenszyklus von Docker-Containeranwendungen breit. Es handelt sich jedoch um *eine Sammlung von Produkten und Technologien, die es Ihnen ermöglichen, optional vorhandene Tools und Prozesse auszuwählen und zu integrieren*. Die Flexibilität durch einen umfassenden Ansatz und die Stärke der tiefgreifenden Funktionen versetzen Microsoft in eine starke Position für die Entwicklung von Docker-Containeranwendungen.

>[!div class="step-by-step"]
>[Zurück](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[Weiter](../design-develop-containerized-apps/index.md)
